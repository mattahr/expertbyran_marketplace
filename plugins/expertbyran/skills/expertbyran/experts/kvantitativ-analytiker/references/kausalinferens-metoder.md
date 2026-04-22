# Kausalinferensmetoder — Beslutsmatris och metodbeskrivningar

Uppdaterad: 2026-04-22

---

## Beslutsmatris — Välj rätt metod

| Situation | Primär metod | Alternativ | Centralt antagande |
|---|---|---|---|
| Många behandlade, parallella trender | DiD (tvåvägs FE) | SDID | Parallella trender utan behandling |
| Enstaka behandlad enhet, lång tidsserie (T₀ ≥ 10) | SC | ASC | Konvexhull + pre-period fit |
| Enstaka enhet, imperfekt fit / extremvärde | ASC | SC | Lättare konvexhull-villkor |
| 5–20 behandlade, staggered / DiD-hybrid | SDID | PP-SCM | Dubbelrobust: enhetsvikter × tidsvikter |
| Staggered adoption, flera behandlingstidpunkter | PP-SCM | SDID | Separata SC per enhet × tidpunkt |
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
| Callaway & Sant'Anna (2021) | JoE | Staggered DiD — kohortspecifika ATT:er |
| Goodman-Bacon (2021) | JoE | Tvåvägs FE vid staggered — viktningsresultat |
| Sun & Abraham (2021) | JoE | Interaktions-DiD estimator |
| Cattaneo, Feng & Titiunik (2021) | JASA 116(536):1865–1880 | SC prediktionsintervall |
| Ben-Michael, Feller & Rothstein (2022) | JRSS-B 84(2):351–381 | PP-SCM — staggered adoption |
| Cattaneo m.fl. (2025) | ReStatat | Utvidgad SC-osäkerhetskvantifiering |
