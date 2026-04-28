# Kausalinferensmetoder — Beslutsmatris och metodbeskrivningar

Uppdaterad: 2026-04-29

---

## Beslutsmatris — Välj rätt metod

| Situation | Primär metod | Alternativ | Centralt antagande |
|---|---|---|---|
| Många behandlade, parallella trender | DiD (tvåvägs FE) | SDID | Parallella trender utan behandling |
| Staggerad adoption, binär behandling, heterogena effekter | CS-2021 (`did`), SA-2021 (`fixest::sunab()`) | Borusyak 2024 (`didimputation`) | Parallella trender per kohort |
| Staggerad adoption, icke-binär / kontinuerlig dos | dCdH (`did_multiplegt_dyn`) | Callaway 2024 (`contdid`) | Switchers-vs-stayers |
| Parallella trender osäkra — sensitivisering | HonestDiD (`HonestDiD`) | — | Begränsad avvikelse från PT |
| Enstaka behandlad enhet, lång tidsserie (T₀ ≥ 10) | SC | ASC | Konvexhull + pre-period fit |
| Enstaka enhet, imperfekt fit / extremvärde | ASC | SC | Lättare konvexhull-villkor |
| 5–20 behandlade, staggerad / DiD-hybrid | SDID | PP-SCM | Dubbelrobust: enhetsvikter × tidsvikter |
| Staggerad adoption, flera behandlingstidpunkter | PP-SCM | SDID | Separata SC per enhet × tidpunkt |
| Enstaka enhet, komplex temporal dynamik / lång ts | BSTS / CausalImpact | SC | Bayesiansk tillståndsrymdsmodell |
| Liten donorpool, oregelbunden/saknad data | MC-NNM | ASC | Latent faktormodell (low-rank matris) |
| Formella konfidensintervall med garantier | SC + Cattaneo-PI | SDID | Ändliga-stickprov prediktionsintervall |
| Klar tröskeleffekt, administrativ gräns | RDD | DiD | Lokal randomisering nära tröskel |
| Utbudschock / administrativ tilldelning | IV | DiD + IV | Instrument: relevant, exogent, exklusivt |

---

## Difference-in-Differences (DiD)

### Grundidé

Jämför förändringen i utfall för behandlad grupp med förändringen för kontrollgrupp, före och efter behandling. Identifikation kräver att parallella trender gäller: behandlad och kontrollgrupp hade samma trend i utfall, utan behandling.

**Formellt:**
- ATT = E[Y_{1,post} − Y_{1,pre}] − E[Y_{0,post} − Y_{0,pre}]
- Kräver: E[Y_{0,post} − Y_{0,pre} | D=1] = E[Y_{0,post} − Y_{0,pre} | D=0]

### Staggered adoption (Callaway & Sant'Anna, Goodman-Bacon)

Klassisk tvåvägs FE-DiD är inkonsistent när behandling sker vid olika tidpunkter och behandlingseffekten är heterogen. Moderna estimatorer (Callaway & Sant'Anna 2021, Goodman-Bacon 2021, Sun & Abraham 2021) aggregerar kohortspecifika ATT:er på ett välgrundat sätt.

**Viktiga resultat (Goodman-Bacon 2021, AER):**
- Tvåvägs FE-skattning är ett viktat genomsnitt av alla möjliga 2×2-DiD-jämförelser
- Tidigt behandlade enheter fungerar som "kontroll" för sent behandlade — vilket är problematiskt om effekterna är dynamiska

**Rekommendation:** Använd `did`-paketet (Callaway & Sant'Anna) i R vid staggered adoption med heterogena effekter.

### Robusthetskontroller

1. Placebotester: falskt behandlingsdatum i pre-perioden — ger falskt signifikant resultat?
2. Parallella trender: grafisk granskning + event study-specifikation
3. Alternativa kontrollgrupper
4. Kontrollerande för kovariater som kan variera parallellt med behandling

**Grundkällor:** Angrist & Pischke (2009) *Mostly Harmless Econometrics*; Callaway & Sant'Anna (2021, JoE); Goodman-Bacon (2021, JoE); Sun & Abraham (2021, JoE)

---

## Syntetisk kontrollmetod (SC)

### Grundidé och formalisering

SC konstruerar ett viktat genomsnitt av obehandlade donorenheter som approximerar den behandlade enhetens pre-behandlingsutveckling. Effektskattningen är skillnaden mellan faktiskt utfall och den "syntetiska" kontrafaktualen post-behandling.

**Formellt:**
- Behandlad enhet: *i = 1*, period *T* (behandling börjar period *T₀*)
- Donorpool: *j = 2, ..., J+1*
- Vikter *W* = *(w₂, ..., w_{J+1})*, *wⱼ ≥ 0*, Σ*wⱼ* = 1
- Välj *W** som minimerar ||*X₁ − X₀W*|| (pre-behandlingskovariater/utfall)
- Effektskattning: *α̂_{1t}* = *Y_{1t}* − Σ*wⱼ*·*Y_{jt}* för *t > T₀*

### Nyckelvillkor för giltighet

1. **Pre-period fit:** Viktat genomsnitt ska nära matcha behandlad enhets förhistoria (MSPE < 5 % av varians = god fit)
2. **Konvexhull-villkor:** Behandlad enhet ska ligga inom konvexhöljet av donorpoolen
3. **SUTVA:** Inga spillover-effekter mellan enheter
4. **Tillräcklig pre-period:** Minst 10–15 perioder; T₀ bör vara ≥ 2× post-period
5. **Stabil donatorbas:** Donatorernas utfall påverkas inte av behandlingen
6. **Donorpoolstorlek:** 10–40 enheter; för stor pool ger overfitting

### Inferens via placebotester

SC tillåter inte klassisk asymptotisk inferens (N = 1 behandlad enhet).
Standard: **placebotester (in-place)** — upprepa SC för varje donatorenhet och jämför deras post/pre-MSPE-kvoter med behandlad enhets.
P-värde = andelen donatorer med minst lika stor kvot.

**R-paket:** `Synth`, `tidysynth`

**Grundkällor:** Abadie & Gardeazabal (2003, AER); Abadie, Diamond & Hainmueller (2010, JASA; 2015, Am J Pol Sci); Abadie (2021, JEL 59(2):391–425)

---

## SC-varianter

### SDID — Syntetisk DiD (Arkhangelsky m.fl. 2021, AER)

Kombinerar SC-enhetsvikter med DiD-tidsvikter. Tidsvikterna tonar ned pre-perioder som är irrelevanta för att matcha pre-trendutvecklingen.

- **Dubbelrobust:** Konsistens kräver att *antingen* enhets- *eller* tidsviktningen fungerar
- **Asymptotisk inferens:** Formella standardfel (bootstrap eller permutationsbaserat)
- **Bättre än SC när:** 5–20 behandlingsenheter, nivåskillnader, formella KI önskas

**R-paket:** `synthdid`
**Källa:** Arkhangelsky, Athey, Hirshberg, Imbens & Wager (2021, AER)

---

### ASC — Augmenterat SC (Ben-Michael, Feller & Rothstein 2021, JASA)

Debiaserar SC-estimatorn med en ridge-regressions-baserad utfallsmodell. Korrektionen (*Δ̂*) kompenserar för imperfekt pre-period fit.

- *α̂_{ASC}* = *α̂_{SC}* + *Δ̂* (debias-korrektion från ridge-modell)
- Tillåter **begränsade negativa vikter** (konvexhull-villkoret lättas)
- **Bättre än SC när:** Behandlingsenheten är extremvärde, kort pre-period, liten donorpool

**R-paket:** `augsynth`
**Källa:** Ben-Michael, Feller & Rothstein (2021, JASA)

---

### MC-NNM — Matriskomplettering (Athey m.fl. 2021, JASA)

Formulerar counterfactual-imputering som ett matriskompletteringsproblem. Minimerar nuclear norm för att fylla i saknade potentiella utfall.

- Implicerar en interaktiv fixed effects-modell (latent faktormodell)
- Hanterar naturligt **staggered adoption** och oregelbunden missingness
- **Bättre än SC när:** Liten donorpool, staggered adoption, hög dimensionalitet
- **Begränsning:** Svår att kommunicera; kräver korsvalidering för regulariseringsparameter *λ*

**R-paket:** `MCPanel`
**Källa:** Athey, Bayati, Doudchenko, Imbens & Khosravi (2021, JASA)

---

### PP-SCM — Partiellt poolad SC vid staggered adoption (Ben-Michael, Feller & Rothstein 2022, JRSS-B)

**Publikation:** JRSS-B 84(2):351–381. DOI: 10.1111/rssb.12448
*(OBS: Ibland felciterad som "Review of Economic Studies" — korrekt tidskrift är JRSS-B)*

Standard-SC är designad för en enda behandlingsenhet och tidpunkt. PP-SCM hanterar staggered adoption: beräknar tidpunktsspecifika SC-vikter per (enhet × tidpunkt) och balanserar avvägningen mellan separata och poolade vikter.

- **Fullt separata SC:** En syntetisk kontroll per (enhet × tidpunkt) — ignorerar information om genomsnittlig effekt
- **Fullt poolade SC:** Gemensam kontroll för alla — antar homogena vikter
- **PP-SCM:** Delar styrka mellan tidpunkter men tillåter heterogenitet

**R-paket:** `augsynth` (kombinerar PP-SCM med ASC-debias)
**Relevans:** Reformer som implementeras stegvis i regioner/kommuner vid olika tidpunkter.
**Källa:** Ben-Michael, Feller & Rothstein (2022, JRSS-B)

---

### Prediktionsintervall för SC (Cattaneo, Feng & Titiunik 2021, JASA)

**Publikation:** JASA 116(536):1865–1880. DOI: 10.1080/01621459.2021.1979561

Konstruerar formella prediktionsintervall med ändliga-stickprov-garantier, baserade på två separata osäkerhetskällor:

1. **Viktkonstruktionsosäkerhet:** Feltolerans i SC-viktoptimeringen (pre-perioden)
2. **Stokastiskt residualfel:** Det oobserverade felledets variation post-behandling

**R-paket:** `scpi`
**Relevans:** När formella sannolikhetsgarantier behövs och p-värden från placebotester inte räcker.
**Källa:** Cattaneo, Feng & Titiunik (2021, JASA); uppföljning: Cattaneo m.fl. (2025, ReStatat)

---

## Regression Discontinuity Design (RDD)

### Grundidé

Identifierar kausal effekt nära en administrativ tröskel. Enheter precis under och precis över tröskeln antas vara likartade i allt utom behandlingstilldelning.

**Nyckelvillkor:**
- Klar, exogen tröskel — inte manipulerbar av enheter
- Ingen sortering ("manipulation test", McCrary 2008)
- Lokalt randomiseringsperspektiv: jämför bara enheter nära tröskeln

**Robusthetskontroller:**
1. McCrary density test (sorteringstest)
2. Placebo-utfall (förtröskelvariabler som inte borde brytas)
3. Bandwidthsensitivitet
4. Polynomordning: föredra lokal linjär regression (Fan & Gijbels rekommendation)

**R-paket:** `rdrobust`, `rddensity`

---

## Instrumentalvariabler (IV)

### Grundidé

Använder ett instrument *Z* som påverkar behandling *D* men inte utfall *Y* direkt. Identifierar lokal genomsnittlig behandlingseffekt (LATE) för "compliers" — de som ändrar behandling som svar på instrumentet.

**Tre villkor för giltigt instrument:**
1. **Relevanst:** Z korrelerar starkt med D (svagt instrument → bias)
2. **Exogent:** Z är okorrelerat med oobserverade confounders (u)
3. **Exklusivitetsbegränsning:** Z påverkar Y enbart via D

**Vanliga instrument i svensk offentlig sektor:**
- Administrativ tilldelning baserad på kvot eller kö
- Geografisk variation i tillgång till program
- Reformtidpunkter interagerade med förbehandlingsegenskaper

**Robusthetskontroller:**
- First stage F-statistik > 10 (Staiger & Stock tumregel); helst Kleibergen-Paap
- Placebo-instrument (falskt instrument bör ge nollresultat)
- Sensititivitetsanalys av exogenitetsantagandet (Conley m.fl. 2012)

---

## Svenska datakällor — Kvantitativa underlag

| Källa | Innehåll | Tillgänglighet |
|---|---|---|
| SCB (Statistiska centralbyrån) | Registerdata: sysselsättning, inkomst, utbildning, demografi | Mikrodata via forskarservice; aggregat via Statistikdatabasen |
| IFAU | Arbetsmarknads- och utbildningsutvärderingar | Rapporter fritt; mikrodata via ansökan |
| ISF (Inspektionen för socialförsäkringen) | Sjukförsäkring, föräldrapenning, a-kassa | Rapporter fritt; mikrodata via ansökan |
| Tillväxtanalys | Näringspolitik, regional utveckling | Rapporter fritt |
| Riksrevisionen | Granskningsrapporter med kvantitativa iakttagelser | Fritt via riksrevisionen.se |
| Socialstyrelsen | Hälso- och sjukvårdsdata, socialtjänst | Statistikdatabaser och rapporter |
| SKR (Sveriges kommuner och regioner) | Kommunal ekonomi, verksamhetsstatistik | Kolada, rapporter |

**Viktigt:** Definitionsändringar är vanliga i registrerade variabler. Kontrollera alltid om det skett metodändringar i SCB:s statistik (redovisas i tekniska noter) som bryter jämförbarheten över tid.

---

## dCdH — Icke-binär och kontinuerlig dos-DiD

### de Chaisemartin & D'Haultfoeuille-ramverket (AER 2020)

Klassisk DiD och CS-2021 förutsätter binär behandling. dCdH-ramverket hanterar **icke-binär dos** (t.ex. bidragsbelopp, inspektionsintensitet) och **staggerad adoption med heterogen dos**.

**Kärninnovatationen — switchers-vs-stayers:**

Identifikation baseras på jämförelse av enheter som *byter* dos (switchers) mot enheter som behåller sin dos (stayers). Under parallella trender för stayers ger detta ett lokalt ATT för switchers:

```
δ̂(ℓ) = genomsnittlig utfallsförändring för switchers vid event-time ℓ
        − genomsnittlig utfallsförändring för stayers
```

**R-paket:** `did_multiplegt_dyn` — event-study med dynamiska effekter, standard­fel via bootstrap.

**Callaway, Goodman-Bacon & Sant'Anna (2024) — kontinuerlig dosintensitet:**

Utvidgar CS-2021 till kontinuerlig dos via `contdid`-paketet. Estimerar hur ATT varierar med dosintensiteten (dos-responssamband). Kräver: strikta parallella trender, ingen anticipation, stöd för alla dosnivåer i kontrollgruppen.

**Beslutsregel dCdH vs. contdid:**
- Dos är ordinal eller kategorisk → `did_multiplegt_dyn`
- Dos är kontinuerlig och dos-responsfunktionen är av intresse → `contdid`

---

## HonestDiD — Sensitivisering av parallella trender-antagandet

**Rambachan & Roth (2023, ReStud)**

Klassisk DiD är sårbar om parallella trender är approximate snarare än exakta. HonestDiD konstruerar konfidensintervall som är robusta givet att avvikelsen från parallella trender är begränsad.

**Grundidé:**

Definiera M = max tillåten linjär avvikelse från parallella trender (i enheter av pre-trend-storleken). KI konstrueras för alla M-värden i ett plausibelt intervall. Resultaten är giltiga för alla avvikelser ≤ M.

**Två sensitivitetsparametrar:**
- **Mbar:** Tillåten linjär avvikelse — hur mycket kan trenden break utan att slutsatsen kollapsar?
- **Delta_SD (smooth deviations):** Tillåter icke-linjär, men smidig, avvikelse

**Tolkning:** Om KI förblir signifikant upp till "rimlig" M → slutsatsen är robust. Om KI kollapsar redan vid liten M → slutsatsen är känslig för pre-trend-antagandet.

**R-paket:** `HonestDiD` (Rambachan & Roth 2023); integrerat med `did`-paketets output.

**När använda:** Alltid som robusthetscheck vid DiD i revisionskontext där parallella trender inte kan testas direkt eller är ifrågasatta.

---

## BSTS / CausalImpact

### Brodersen m.fl. (2015, Annals of Applied Statistics)

**Syfte:** Skatta kausalt effekt av en intervention för en *enstaka behandlad enhet* med en lång tidsserie. Typfall: en region, ett program eller en policy som implementerades vid en känd tidpunkt.

**Modellen — Bayesiansk tillståndsrymdsmodell (BSTS):**

```
Yₜ = μₜ + βᵀXₜ + εₜ         (observations-ekvation)
μₜ₊₁ = μₜ + δₜ + ηₜ          (lokal nivå/trend)
```

- μₜ: lokal nivåkomponent (random walk)
- δₜ: lokal trend (om linjär trendkomponent aktiveras)
- Xₜ: kontrollserier — väljs via spike-and-slab-regression (Bayesiansk variabelurval)
- εₜ, ηₜ: Gaussiska störtermer

**Spike-and-slab-regression:** Bayesiansk prior sätter sannolikheten till noll för de flesta kovariater. Modellen väljer automatiskt relevanta kontrollserier bland donorerna — ingen manuell donor pool-process som i SC.

**Effektskattning:** Post-behandlingsperiodernas faktiska utfall jämförs med predikterat kontrafaktum från modellen. Kausalimpact = Σ(faktiskt − predikterat).

**Förperiodsregler med källbelägg:**
- Lokal nivåmodell: min **30 observationer** (Brodersen 2015, avsnitt 2–3)
- Linjär trend: min **50 observationer**
- Säsongskomponent: min **2,5 × säsongslängd** observationer
- 3×-regeln (CausalImpact-vignette, CRAN): förperiod ≥ 3 × post-period

**Effekttypens roll för minsta förperiod:**
- Spike / nivåskift → lokal nivåmodell → min max(30, 3×post)
- Trendbrott → linjär trend → min max(50, 3×post) — vid post=12 binder ≥50 obs, inte 3×-regeln

**Staggerad adoption med BSTS:**
- BSTS kräver g−1 ≥ 30 per enhet (g = behandlingstidpunkt)
- CS-2021 har inget absolut förperiodsminimum — parallella trender testbara med 2–3 förperiodsobs

**Metodval SDiD vs. BSTS:**

| Situation | Föredra |
|---|---|
| >3 kohorter, tidiga adoptörer, aggregerat ATT | SDiD / CS-2021 |
| Komplex temporal dynamik, enstaka enhet, lång ts (≥50 obs) | BSTS |
| Sequential SDiD (2024) vid PT-brott | Sequential SDiD |

**R-paket:** `CausalImpact` (Brodersen m.fl.; CRAN)

---

## Källöversikt — Kausalinferens

| Referens | Tidskrift | Bidrag |
|---|---|---|
| Abadie & Gardeazabal (2003) | AER | SC-grundmetod |
| Abadie, Diamond & Hainmueller (2010) | JASA | SC formalisering + Synth-paket |
| Abadie, Diamond & Hainmueller (2015) | Am J Pol Sci | SC-validering och replikation |
| Abadie (2021) | JEL 59(2):391–425 | Praktisk vägledning, datakrav |
| Angrist & Pischke (2009) | Princeton UP | DiD, IV, RDD — metodöversikt |
| Arkhangelsky m.fl. (2021) | AER | SDID — tidsvikter + asymptotisk inferens |
| Ben-Michael, Feller & Rothstein (2021) | JASA | ASC — debiaserat SC med ridge |
| Athey m.fl. (2021) | JASA | MC-NNM — matriskomplettering |
| Brodersen m.fl. (2015) | AoAS | BSTS / CausalImpact |
| Callaway & Sant'Anna (2021) | JoE | Staggered DiD — kohortspecifika ATT:er |
| Goodman-Bacon (2021) | JoE | Tvåvägs FE vid staggered — viktningsresultat |
| Sun & Abraham (2021) | JoE | Interaktions-DiD estimator |
| de Chaisemartin & D'Haultfoeuille (2020) | AER | dCdH — icke-binär dos, switchers-vs-stayers |
| Cattaneo, Feng & Titiunik (2021) | JASA 116(536):1865–1880 | SC prediktionsintervall |
| Ben-Michael, Feller & Rothstein (2022) | JRSS-B 84(2):351–381 | PP-SCM — staggered adoption |
| Rambachan & Roth (2023) | ReStud | HonestDiD — sensitivity för parallella trender |
| Borusyak, Jaravel & Spiess (2024) | ReStud | Imputation-estimator vid staggered adoption |
| Callaway, Goodman-Bacon & Sant'Anna (2024) | — | Kontinuerlig dos-DiD (`contdid`) |
| Cattaneo m.fl. (2025) | ReStatat | Utvidgad SC-osäkerhetskvantifiering |
