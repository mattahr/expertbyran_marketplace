# Instrumentvariabler (IV) och 2SLS — metodreferens

## Vad IV löser och när det används

Instrumentvariabler (IV) löser endogenitetsproblemet: behandlingsvariabeln D är korrelerad med oobserverade confounders U, och OLS ger inkonsistenta skattningar. IV kräver en variabel Z (instrumentet) som:
- påverkar D (relevans)
- inte påverkar Y annat än via D (exklusionsrestriktion)
- är oberoende av U (exogenitet)

2SLS (Two-Stage Least Squares) är standardestimatorn och identifierar LATE — lokal genomsnittlig behandlingseffekt för compliers.

---

## Identifieringsantaganden

**1. Relevans:** Cov(Z, D) ≠ 0. Testbart via first-stage F-statistik.

**2. Exklusionsrestriktion:** Z → Y enbart via D. Cov(Z, ε) = 0. Ej testbart med ett instrument — kräver substantiellt argumentationsblock i rapporten. Beskriv mekanismen och uteslut direkta kanaler explicit.

**3. Exogenitet/Oberoende:** Z ⊥ (Y⁰, Y¹, U). Kräver trovärdigt quasi-experiment: reformtidpunkt, lotteri, geografisk gräns, policytröskel.

**4. Monotonicitet:** Ingen defier-population. Instrumentet påverkar alla åt samma håll (eller inte alls). Nödvändigt för LATE-tolkning.

---

## 2SLS-mekanismen

**Steg 1:** `D = π₀ + π₁Z + Wγ + v` → predikterade värden D̂ fångar exogen variation i D.
**Steg 2:** `Y = β₀ + β₁D̂ + Wδ + ε` → β₁ är IV-skattningen.

**IV-kvoten:** β̂_IV = (Reducerad form) / (First stage) = ITT / First stage

Reducerad form = direkt effekt av Z på Y.
First stage = effekt av Z på D.

---

## LATE och complier-taxonomin

Med binärt Z och binär D:

| Typ | D|Z=0 | D|Z=1 | LATE-bidrag |
|---|---|---|---|
| Compliers | 0 | 1 | Ja (hela LATE) |
| Always-takers | 1 | 1 | Nej |
| Never-takers | 0 | 0 | Nej |
| Defiers | 1 | 0 | Utesluts (monotonicitet) |

**LATE = E[Y¹ − Y⁰ | Complier]**

LATE ≠ ATE. Om instrumentet påverkar en marginell/selektiv grupp kan LATE skilja sig kraftigt från genomsnittseffekten. Kommunicera alltid vad complier-gruppen är i rapporten.

Fuzzy RDD är ett specialfall av IV: LATE = ITT / First stage lokalt vid cutoff. Complier-taxonomi och diagnostik gäller identiskt.

---

## Weak Instruments — diagnostik

### Stock-Yogo (2005)
Tumregel: First-stage F > 10 → begränsar relativ IV-bias till < 10 % av OLS-bias.
Gäller under homoskedasticitet/i.i.d. — för klustrad eller heteroskedastisk data används effektivt F.

### Montiel Olea & Pflueger (2013) — effektivt F
Heteroskedasticitet- och kluster-robust F-statistik. Rapportera alltid detta istället för Cragg-Donald när data är klustrad. R: `ivDiag`-paketet.

### Lee, McCrary, Moreira & Porter (2022) *AER* — tF-proceduren
Standard t = 1,96 är för liberalt vid svaga instrument.
tF-kritiska värden justeras som funktion av first-stage F:

| First-stage F | Åtgärd |
|---|---|
| > 100 | Standard t = 1,96 OK |
| 20–100 | Rapportera tF-justerade CI |
| < 20 | Rapportera AR-konfidensintervall; starka hedges om slutsatser |

### Anderson-Rubin (AR)-test
CI robusta mot weak instruments — konservativa men giltiga oavsett instrumentstyrka. Bör alltid rapporteras när F < 20.

### Sargan-Hansen J-test (K > 1 instrument)
Testar om alla instrument är exogena. Förkastning → minst ett instrument bryter exklusionsrestriktionen. Begränsad kraft — tolkas med försiktighet och kompletteras med substantiellt argument.

### Diagnospaket
`ivDiag` (R, Xu m.fl.): effektivt F, AR-CI, tF-justerade CI i ett anrop.
https://yiqingxu.org/packages/ivDiag/

---

## Bartik/Shift-Share IV (SSIV)

**Konstruktion:** B_i = Σ_k s_{ik} × g_k
- s_{ik} = lokal area i:s andel av industri k i basåret
- g_k = nationell tillväxttakt i industri k

### Goldsmith-Pinkham, Sorkin & Swift (2020) — andelsbaserat perspektiv
Bartik numeriskt ekvivalent med viktad summa av K separata IV-estimat (ett per industri) med Rotemberg-vikter ω_k.

Praktiska implikationer:
1. **Rotemberg-vikter avslöjar känslighet:** Vilka industrier driver estimatet? Är det ekonomiskt rimligt? Rapportera alltid de fem tyngst vägda industrierna.
2. **Identifikationsantagande:** *Andelarna* s_{ik} ska vara exogena. Balanstest: regrera s_{ik} mot lokala karaktäristika i basåret (pre-treatment covariates). Förklaringskraft → andelarna är endogena.
3. **Heterogena effekter:** Bartik ger Rotemberg-viktat genomsnitt — tolka med hänsyn till vilka industrier som väger tyngst.

R: `ssaggregate`-paketet.

### Borusyak, Hull & Jaravel (2022) — chockbaserat perspektiv
Alternativ: *chockerna* g_k är quasi-slumpmässiga (t.ex. globala branschchocker), andelar s_{ik} behöver inte vara exogena.

Praktiska konsekvenser:
- Balanstest på **chocknivå** (är g_k balanserade mot lokala observable?)
- Standardfel klustras på **chocknivå** (K industrier, inte N areas)
- F-statistik beräknas på chocknivå

**Beslutsregel:**
- Andelarna mer trovärdigt exogena → GPS (2020)
- Chockerna mer trovärdigt quasi-slumpmässiga → BHJ (2022)
- Rapportera Rotemberg-vikter oavsett ramverk

---

## Beslutsmatris IV vs. DiD vs. RDD

| Situation | Föredra |
|---|---|
| Trovärdigt instrument, stark first stage (F > 40) | IV/2SLS |
| Instrument finns, F svag (< 20) | AR-CI; sök starkare instrument |
| Lokal effekt vid policytröskel | RDD (fuzzy = IV lokalt) |
| Staggerad behandling, parallella trender | DiD CS-2021/SA-2021 |
| Lokal industrichock + nationell branschtrend | Bartik/SSIV |

---

## Rapporteringsnorm för IV i granskningsrapporter

1. **Redovisa alltid:** first-stage F (effektivt F), first-stage koefficient, reducerad form, IV-estimat med CI.
2. **Argumentera explicit** för exklusionsrestriktionen — uteslut direkta kanaler.
3. **Kommunicera LATE-tolkning:** "Effekten gäller för [complier-grupp], d.v.s. de enheter vars [behandling] påverkades av [instrumentet]."
4. **Vid F < 100:** rapportera tF-justerade CI eller AR-CI som primärt konfidensintervall.
5. **Vid SSIV:** redovisa Rotemberg-vikter och de tyngst vägda industrierna/chockerna.

---

## Svenska tillämpningar

- **Utbildningsavkastning:** geografisk tillgång till gymnasium/college; IFAU-reformdesigns (gymnasiereform 1994, högskolereform 1977).
- **Arbetsmarknad:** Bartik med kommunal industrimix (SCB) och nationell konjunkturutveckling. Chockbaserat: globala importchocker (China shock-design, AD m.fl.).
- **Hälsa:** geografisk variation i sjukhuskapacitet, remissbenägenhet (Patientregistret/LiSA).
- **Transfereringar och socialförsäkring:** reform-IV med ikraftträdandedatum (FK, Af) — LATE för de vars status ändrades av reformens timing.

---

## Nyckelreferenser

- Angrist, J. & Pischke, J.-S. (2009), *Mostly Harmless Econometrics*. Princeton UP.
- Imbens, G. & Angrist, J. (1994), "Identification and Estimation of Local Average Treatment Effects", *Econometrica* 62(2): 467–475.
- Stock, J. & Yogo, M. (2005), "Testing for Weak Instruments in Linear IV Regression", i *Identification and Inference for Econometric Models*, Cambridge UP.
- Montiel Olea, J.L. & Pflueger, C. (2013), "A Robust Test for Weak Instruments", *JBES* 31(3): 358–369.
- Lee, D.S., McCrary, J., Moreira, M.J. & Porter, J. (2022), "Valid t-Ratio Inference for IV", *AER* 112(10): 3260–3290. https://www.aeaweb.org/articles?id=10.1257/aer.20211063
- Goldsmith-Pinkham, P., Sorkin, I. & Swift, H. (2020), "Bartik Instruments: What, When, Why, and How", *AER* 110(8): 2586–2624. https://www.nber.org/papers/w24408
- Borusyak, K., Hull, P. & Jaravel, X. (2022), "Quasi-Experimental Shift-Share Research Designs", *ReStud* 89(1): 181–213. https://www.nber.org/papers/w24997
- Borusyak, K., Hull, P. & Jaravel, X. (2025), "A Practical Guide to Shift-Share Instruments", *JEP* 39(1): 181–204.
