# Sensitivitetsanalys och MNAR i registerdata

Källa: VanderWeele & Ding (2017), Rosenbaum (2002/2010), White m.fl. (2011), Rubin (1976), svenska registerspecifika mönster.

---

## 1. Bortfallstaxonomi: MCAR, MAR, MNAR

| Typ | Definition | Konsekvens för analys |
|---|---|---|
| **MCAR** (Missing Completely at Random) | Bortfallet är oberoende av alla observerade och oobserverade variabler. | Komplett-fallsanalys är väntevärdesriktig (men ineffektiv). |
| **MAR** (Missing at Random) | Bortfallet betingas av observerade variabler, men inte av det oobserverade utfallsvärdet. | Multipel imputering (MICE) och ML-metoder är väntevärdesriktiga under MAR. |
| **MNAR** (Missing Not at Random) | Bortfallet beror på det oobserverade värdet självt — dvs. de med extrema utfall lämnar systemet. | Varken komplett-fallsanalys eller MICE ger konsistenta skattningar utan ytterligare antaganden. |

**Operationell tumregel:** behandla bortfall som potentiellt MNAR om det finns en mekanism som kopplar utfallet direkt till att data saknas (t.ex. "de som slutade delta i programmet" saknas i programmedeltaganderegistret; "de med dålig hälsa som dog" saknas i uppföljningsdata).

---

## 2. Svenska adminregister — typiska MNAR-mönster

### Programmedeltagande (IFAU/Arbetsförmedlingen)

* Deltagare som avbryter ett program försvinner ofta från programregistret. Avbrott korrelerar med negativa utfall (omedelbar sysselsättning eller försämrad hälsa), vilket innebär MNAR-bortfall i effektmåttet.
* **Konsekvens:** effektskattningar på kvarstannare överskattningsbias om utfallet är positivt korrelerat med att stanna.

### Hälsoregister (Patientregistret, Dödsorsaksregistret)

* Individer med låg vårdkonsumtion saknas i Patientregistret — inte för att de är friska, utan för att de inte söker vård. Bortfallet är kopplat till underliggande hälsa (MNAR).
* Dödsorsaksregistret har nära 100 % täckning för dödsfall, men specifik orsak kan saknas för äldre dödsfall — systematisk underskattning av t.ex. demens-dödsfall.

### Attrition i longitudinella paneler

* I LINDA/LISA försvinner individer ur urvalet vid emigration, dödsfall eller av administrativa skäl. Emigration är positivt korrelerat med arbetsmarknadsmisslyckanden (MNAR för inkomsttillväxt).
* Fusioner och namnändringar av arbetsgivare bryter anknytningslänkar i FAD; anknytningsuppehåll korrelerar med lågkonjunktur (tidsvarierande MNAR).

### Skatteregistret (inkomstdata)

* Svart inkomst, kapitalinkomster utomlands och informell ekonomi syns inte. Bortfallet är negativt korrelerat med observerad formell inkomst (MNAR för totalt välstånd).

---

## 3. E-värde (VanderWeele & Ding 2017)

### Definition

E-värdet är det **minsta** styrka på association (risk ratio) som en omätt confounding-variabel måste ha med *både* exponering och utfall för att fullt ut förklara bort en observerad effekt.

Formel för punktskattning (RR > 1):

```
E = RR + sqrt(RR × (RR − 1))
```

För det nedre konfidensgränsen: beräkna E för RR_lower istället för punktskattningen.

**Tolkning:** ett E-värde på 3 innebär att en okänd confoundervariabel måste vara 3 gånger starkare associerad med *både* exponering och utfall för att eliminera den observerade effekten. Ju större E-värde, desto mer robust är den kausala slutledningen.

### Rapportering i observationsstudier med kausalt anspråk

Krav 4.3-kompatibelt format:

> *"Den observerade oddskvoten var 2,4 (95 % KI: 1,8–3,2). E-värdet är 4,0; det nedre konfidensgränsens E-värde är 3,0. För att omätt confounding ska eliminera associationen måste den vara minst 4 gånger (eller 3,0 för undre KI) starkare kopplad till exponeringen och utfallet än vad observerade kovariater är."*

### Beräkningsverktyg

* **R-paket `EValue`:** `evalues.RR(est = 2.4, lo = 1.8, hi = 3.2)` (CRAN, Hunt m.fl.)
* **Webbkalkylator:** konfidentiell — citera istället paketet ovan.
* **Alternativa skalor:** för oddskvot (OR), hazard ratio (HR) eller standardiserad medelflykt (SMD) används separata formler i samma paket.

---

## 4. Rosenbaum-Γ-gränser (matchade studier)

### Definition

Γ (gamma) mäter hur stor ojämlikhet i oobserverade kvarstående confounders som behövs för att vända slutsatsen om behandlingseffekten i en matchad studie. Γ = 1 innebär att matchningen antas perfekt (ingen oobserverad confounding); Γ = 2 innebär att de matchade individernas chanser att få behandling kan skilja sig med en faktor 2 på grund av oobserverade skillnader.

**Tolkning:** en analys är robust om den håller för höga Γ-värden (t.ex. Γ ≥ 2 ger praktisk trovärdighet).

### R-paket

* **`rbounds`** (Keele): `psens(y = diffs, Gamma = 2, GammaInc = 0.1)` — kontinuerliga utfall, Wilcoxon signed-rank.
* **`sensitivitymv`** (Rosenbaum): för multipla utfall och mer generella matchningsdesigner.
* **`sensitivityfull`**: fulla implementationer av Rosenbaums M-estimatorer.

### Rapportering

> *"Matchad DiD med propensity score. Rosenbaum-Γ-analys: slutsatsen håller upp till Γ = 1,8; vid Γ > 1,8 kan oobserverade skillnader inte uteslutas. Referens: Rosenbaum (2010), `rbounds`-paket v2.1."*

---

## 5. Tipping-point-analys med pattern-mixture-modeller (MNAR i utfallet)

### Grundkoncept

Pattern-mixture-modellen separerar modellen för utfall Y på de som observeras (R=1) från de som saknas (R=0):

```
P(Y) = P(Y | R=1) × P(R=1) + P(Y | R=0) × P(R=0)
```

Under MAR: E[Y | R=0] = E[Y | R=1, X]. Under MNAR kan Y | R=0 avvika från den imputerade fördelningen med en shift-parameter δ.

### Shift-parametern δ och tipping-point

Tipping-point-analysen beräknar: **vilket värde på δ (hur mycket saknade värden måste avvika från imputerade)** räcker för att vända den statistiska slutsatsen (t.ex. göra behandlingseffekten icke-signifikant)?

**Implementering i MICE:**

```r
# Scenario: δ = 2 (saknade värden antas vara 2 enheter lägre än imputerade)
imp <- mice(data, method = "pmm", m = 20, seed = 123)
# Post-processing: minska imputerade värden för behandlingsgrupp med δ
imp_shifted <- imp
for (i in seq_len(imp$m)) {
  idx <- which(is.na(data$Y) & data$treat == 1)
  imp_shifted$imp$Y[[i]][idx, ] <- imp$imp$Y[[i]][idx, ] - delta
}
# Kör analys på varje imputation, poola med Rubin's rules
```

### Tipping-point-sökning

Variera δ från 0 till ett substantiellt värde och registrera vid vilket δ effektskattningens nedre konfidensintervall passerar noll. Det är tipping-point.

**Rapporteringsformat (krav 4.3):**

> *"Under MAR-antagandet (δ = 0) estimeras ATT = 1 200 kr/år (95 % KI: 400–2 000). Tipping-point uppnås vid δ = −1 800 kr — dvs. om de som saknar uppgifter om inkomst i genomsnitt tjänar 1 800 kr/år *mindre* än imputerat neutraliseras effekten. Med hänsyn till kände mekanismer för attrition (…) bedöms detta [trovärdig/osannolikt]."*

---

## 6. Praktiskt beslutssteg — integrerat med krav 4.3

Stegen nedan tillämpas på varje kvantitativ iakttagelse med kausalt anspråk:

**Steg 1 — Diagnostisera bortfallsmekanismen**
- Finns systematiska skillnader i observerade kovariater mellan de med och utan utfallsdata?
- Finns en substantiell mekanism som kopplar utfallet till bortfallet?
- Om ja på endera: behandla som potentiellt MNAR.

**Steg 2 — Välj sensitivitetsverktyg**

| Studietyp | Primärt verktyg | Sekundärt |
|---|---|---|
| Observationsstudie, kausalt anspråk | E-värde | MNAR tipping-point om bortfall |
| Matchad studie | Rosenbaum-Γ | E-värde som komplement |
| Registerdata med selektivt bortfall i utfall | Tipping-point (pattern-mixture) | E-värde |
| Alla ovanstående | — | HonestDiD om DiD-baserat |

**Steg 3 — Genomför och dokumentera**
- Beräkna valt mått.
- Formulera ett substantiellt riktmärke: "Γ = 2 motsvarar en okänd faktor lika stark som [känd kovariat X]."
- Rapportera enligt krav 4.3 med punkt-skattning, KI, sensitivitetsmåttets värde och tipping-point.

**Steg 4 — Bedöm trovärdighet och formulera hedgen**
- Är tipping-point/E-värde substantiellt sett troligt att uppnås? Motivera med substantiell kunskap om mekanismer.
- Formulera en epistemisk hedge i iakttagelsetexten: *"...förutsatt att oobserverade skillnader inte överstiger Γ = X"* eller *"...om inte saknade värden avviker med mer än δ = Y från imputerade."*

---

## 7. Gränser och fallgropar

* **E-värde är inte ett test av confounding** — det anger ett *tröskelvärde* för hur stark okänd confounding måste vara. Det utesluter inte MNAR-bortfall.
* **Rosenbaum-Γ gäller matchade studier** — direkt applicering på MatchedDiD kräver att matchningen genomförts korrekt (balance check).
* **MICE under MNAR är inte robust i sig** — MICE imputerar under MAR-antagandet. Tipping-point-analysen *kvantifierar* hur känsligt resultatet är för MNAR-avvikelse, men validerar inte att MAR gäller.
* **Pattern-mixture-modeller kräver substantiellt motiverade δ-värden** — slumpmässiga tester av godtyckliga δ är vilseledande; δ bör motiveras av substantiell teori om bortfallsmekanismen.
* **Falsk precision:** sensitivitetsanalysen kommuniceras med en precisionsgrad som matchar övriga iakttagelser — inga fler decimaler än vad datan motiverar.
