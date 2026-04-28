# ML-baserad kausalinferens och meta-learner-familjen

Uppdaterad: 2026-04-28

---

## Grundläggande distinktion: ML löser dimensionalitet, inte confounding

ML-metoder och klassiska kausala metoder (IV, DiD, RDD) är **komplementära**, inte substitut (Athey & Imbens 2017, JEP). Rollfördelning:

- **IV / DiD / RDD** — löser *identifikation*: etablerar ett kausalt antagande
- **ML (DML, GRF)** — löser *dimensionalitet*: hanterar hundratals kovariater utan manuellt variabelval

En ML-metod utan kausalt identifieringsantagande ger inte kausala slutsatser. ML identifierar *vem* som påverkas (CATE), inte *varför*.

---

## Double/Debiased ML (DML)

**Syfte:** Skatta genomsnittlig behandlingseffekt (ATE eller LATE) när confounders är högt dimensionella.

**Grundproblem som DML löser:**

*Regulariseringsbias:* ML-metoder avväger bias mot varians. Regulariseringsbias i störvariabeln ĝ fortplantas multiplikativt till θ̂. Konvergenshastigheten sjunker (t.ex. N^{−1/4}) — inte den √N som krävs för asymptotisk normalitet.

*Overfittingbias:* Om samma data tränar ML-modellen OCH konstruerar score-funktionen ger overfitting ett systematiskt förträngningsbias med felaktig riktning.

**Lösning — två principer:**
1. **Neyman-ortogonalitet:** Score-funktionen är lokalt okänslig (till första ordning) för perturbationer i störvariabelparametern kring sanna värden. Gör att ML-estimation av nuisance-parametrar inte fortplantas till θ̂.
2. **Cross-fitting (k-fold):** Data delas i k-folds; ML tränas på komplementärfold, scores konstrueras på hållen-ut-fold. Undviker overfitting-bias.

**Estimering (partialing-out / Robinson-transformering):**
- Ỹᵢ = Yᵢ − Ê[Y|Xᵢ] (residual från ML-prediktion av Y på X)
- D̃ᵢ = Dᵢ − Ê[D|Xᵢ] (residual från ML-prediktion av D på X)
- θ̂ = (Σ D̃ᵢ²)^{−1} Σ D̃ᵢỸᵢ — OLS på residualerna

**Resultat:** √N-konsistens och asymptotisk normalitet → klassiska konfidensintervall gäller.

**Nyckelreferenser:** Chernozhukov m.fl. (2018, Econometrics Journal); Belloni m.fl. (2014, ReStud) för Post-double-selection LASSO.

**Kombinationer med klassiska metoder:**
- IV + LASSO (Belloni 2014): välj instrument och kontroller via LASSO, DML för first/second stage
- DR-DiD (Sant'Anna & Zhao 2020): doubly robust DiD med ML-prediktion av propensity och utfall

---

## Causal Forest / GRF (Generalized Random Forest)

**Syfte:** Skatta heterogena behandlingseffekter (CATE) — vem påverkas mest av en insats?

**Kärninnovation — ärliga skogar (honest forests):**
- **Subsampeldelning:** Varje träd delar data i *splitting-sample* (S) och *estimation-sample* (E).
- S används för att välja splitregler (maximera behandlingsheterogenitet).
- E används för att skatta CATE i bladet.
- Resultat: Inga överlappande observationer mellan splitting och estimation → asymptotiskt giltiga konfidensintervall via infinitesimal jackknife (Wager & Athey 2018, JASA).

**CATE-skattning och aggregering:**
- τ̂(x) = E[Y(1) − Y(0) | X = x] — lokal genomsnittlig behandlingseffekt vid kovariatkombination x
- Aggregering till subgrupps-ATE via AIPW-scores (doubly robust):
  Γᵢ = τ̂(Xᵢ) + (Dᵢ − ê(Xᵢ))·(Yᵢ − μ̂(Xᵢ,Dᵢ))/(ê(Xᵢ)(1−ê(Xᵢ)))

**Validering av heterogenitet:**
- `best_linear_projection()` (BLP): Testar om τ̂(x) korrelerar med faktiska effekter. Nollhypotes: ingen heterogenitet.
- `test_calibration()`: Kalibrerar genomsnittlig effekt och heterogenitetsprojektionen.
- Visualisering: Sorted group average treatment effects (GATES) — rankordna enheter efter τ̂(x), jämför top- och bottomkvintil.

**R-paket:** `grf` v2.6.1 (Tibshirani m.fl.)

**Nyckelreferenser:** Wager & Athey (2018, JASA); Athey, Tibshirani & Wager (2019, Annals of Statistics)

---

## Meta-learner-familjen

Meta-learners delar upp CATE-problemet i delsteg som var och en kan lösas med valfri ML-algoritm. Beslutsmatris:

| Learner | Lämpar sig för | Svaghet | Nyckelreferens |
|---|---|---|---|
| **S-learner** | — | Regulariseringsbias mot noll för D; undviks | — |
| **T-learner** | Balanserade behandlade/kontroll; binär behandling | Extrapolationsfel vid imbalans | Klassisk |
| **X-learner** | Imbalanserade grupper; propensity-viktad sammanslagning | Känslig för dålig propensity-skattning | Künzel m.fl. (2019, PNAS) |
| **R-learner** | ATE (via DML-PLR) eller CATE (via GRF); quasi-oracle | Beror på Robinson-transformation | Nie & Wager (2021, Biometrika) |
| **DR-learner** | Doubly robust; okänd propensity; AIPW-pseudo-utfall | Konsistens kräver att propensity eller utfall stämmer | Kennedy (2020, AoAS) |

**Samband mellan learners:**
- R-learner **unifierar** DML-PLR (globalt ATE) och GRF (lokalt CATE) — samma residuallogik, olika aggregeringsnivå.
- DR-learner är **identisk** med GRF:s interna AIPW-aggregering vid subgrupps-ATE.
- X-learner: Propensity-score ê(x) viktar samman CATE-skattningar från de två grupperna — robust mot imbalans men känslig om ê är dåligt skattad.

**Beslutsflöde:**
1. ATE räcker och N > 1 000 → DML-PLR
2. CATE-heterogenitet är revisionsfrågan → GRF
3. Imbalanserade grupper, CATE → X-learner
4. Propensity osäker, doubly robust önskas → DR-learner
5. S-learner → undvik alltid

---

## Vetenskapliga krav 4.3 vid ML-metoder

Utöver standardkraven (täljare/nämnare, tidsperiod, osäkerhetsmarginaler) krävs:

| Krav | Innehåll |
|---|---|
| **Verktygstransparens** | Paket och version, t.ex. R `grf` v2.6.1, Python `econml` v0.15 |
| **Hyperparametrar** | Antal träd, min. bladstorlek, honesty fraction (GRF) |
| **Cross-fitting** | Antal folds och hur uppdelning gjordes (DML) |
| **Kovariatlista** | Fullständig lista över variabler — inte bara de med hög importans |
| **Overfitting-kontroll** | Out-of-sample validering, korsvalidering; BLP/calibration test (GRF) |
| **Hedging** | CATE-skattningar för subgrupper: "indikerar" snarare än "visar" om inte pre-specifikation gjorts |
| **Kausalitetsvillkor explicit** | ML hanterar dimensionalitet — kausalt identifieringsantagande måste anges separat |

---

## Kommunikationsutmaningar mot icke-teknisk publik

1. **"Svart låda"-uppfattningen:** Visa variabelimportans och redovisa vilka variabler som driver resultatet.
2. **Ärliga konfidensintervall är bredare:** Kommunicera som styrka (konservativitet), inte svaghet.
3. **CATE gäller per subgrupp:** Tydliggör aggregeringsnivå och undvik att generalisera CATE-resultat till hela populationen.
4. **Reproducerbarhet:** Dokumentera slumpfröet (seed), antal träd/iterationer.

---

## Kombinationer: ML + klassisk kausal metod

| Kombination | Syfte |
|---|---|
| IV + LASSO (Belloni 2014) | Objektivt val av instrument och kontroller vid IV |
| DR-DiD (Sant'Anna & Zhao 2020) | Doubly robust DiD med ML-prediktion |
| GRF + BLP | Testa och kommunicera heterogenitet i RCT/DiD |
| DML + IV | Skalbar IV med högdimensionella kontroller |

---

## Källöversikt

| Referens | Bidrag |
|---|---|
| Athey & Imbens (2017, JEP) | ML och kausal ekonometri — sammanhängande ramverk |
| Belloni m.fl. (2014, ReStud) | Post-double-selection LASSO |
| Chernozhukov m.fl. (2018, Econometrics J) | DML — Neyman-ortogonalitet och cross-fitting |
| Wager & Athey (2018, JASA) | Ärliga skogar — asymptotiska KI |
| Athey, Tibshirani & Wager (2019, AoAS) | GRF — generaliseringsramverket |
| Künzel m.fl. (2019, PNAS) | X-learner |
| Sant'Anna & Zhao (2020, JoE) | DR-DiD |
| Kennedy (2020, AoAS) | DR-learner |
| Nie & Wager (2021, Biometrika) | R-learner |
