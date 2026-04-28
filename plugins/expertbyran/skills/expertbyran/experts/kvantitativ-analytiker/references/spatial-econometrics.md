# Spatial econometrics för regionala skillnadsanalyser

Uppdaterad: 2026-04-29

---

## Grundläggande distinktion: spatial association ≠ kausalitet

Spatial econometrics beskriver geografiska mönster och testar för rumslig samkorrelation. **Spatial association är i grunden deskriptiv** — kausalitet kräver ytterligare identifieringsdesign (geografisk RD, SUTVA-robust DiD). Använd spatial analys för att:

- Diagnosticera om OLS-antaganden om oberoende residualer håller
- Identifiera lokala kluster för fördjupad granskning
- Testa om spillover-effekter existerar mellan angränsande enheter

---

## Rumslig viktmatris W

Viktmatrisen W definierar vem som är "granne" med vem — kärnan i alla spatiala metoder. Vanliga konstruktioner:

| Konstruktion | Beskrivning | När lämplig |
|---|---|---|
| **Queen contiguity** | Granne om delad kant eller hörn | Administrativa polygoner (kommuner, regioner) |
| **Rook contiguity** | Granne om delad kant (ej hörn) | Rutnätsdata |
| **k-NN (k närmaste grannar)** | k geografiskt närmaste centroids | Oregelbundna polygoner med stor storleksvariation |
| **Avståndströskel** | Granne om centroid-avstånd < d | Punktdata, servicetillgänglighet |

**Radnormalisering:** W normaliseras vanligen radvis (varje rad summerar till 1). Underlättar tolkning av spatial eftersläpning Wy som viktat genomsnitt av grannvärden.

**R-paket:** `spdep` (konstruera W), `sf` (spatiala polygoner och geometrier)

---

## Global Morans I — test för spatial autokorrelation

Testar om ett mönster är mer klustrat (Morans I > 0) eller mer spritt (Morans I < 0) än förväntat under rumslig slumpmässighet.

**Formel:**

```
I = (N / S₀) · (Σᵢ Σⱼ wᵢⱼ (xᵢ − x̄)(xⱼ − x̄)) / (Σᵢ (xᵢ − x̄)²)
```

- N = antal enheter; S₀ = summan av alla vikter
- Förväntat värde under H₀: E[I] = −1/(N−1)
- Inferens: permutationstest (monte carlo) föredras framför normalapproximation

**Tolkning:** Signifikant positiv I → liknande värden klustrar geografiskt (hög-hög eller låg-låg). Signifikant negativ I → spatiala schackbrädesmönster.

---

## LISA — lokal indikator för spatial association (Anselin 1995)

Delar upp global Morans I i lokala bidrag per enhet. Identifierar:

- **Hög-Hög (HH):** Enhet med högt värde, omgiven av högt värderade grannar — lokalt kluster
- **Låg-Låg (LL):** Enhet med lågt värde, omgiven av lågt värderade grannar — lokalt kluster
- **Hög-Låg (HL):** Spatial outlier — hög omgiven av låga
- **Låg-Hög (LH):** Spatial outlier — låg omgiven av höga

**Signifikansnivå:** Justeras för multipla tester (t.ex. 0,001 istället för 0,05). Visualiseras i LISA-karta.

**R-paket:** `spdep::localmoran()`, `spdep::lisa()`

---

## Spatial regressionsmodeller

### Spatial Lag Model (SAR — Spatial AutoRegressive)

**Modell:** y = ρWy + Xβ + ε

- ρ: spatial autoregressionsparameter
- Wy: viktat genomsnitt av grannvärdens utfall — *endogen spatial eftersläpning*
- **Tolkning:** Utfallet för en enhet påverkas direkt av grannars utfall — spatial spillover

**Skattning:** Inte OLS (Wy är endogen). Använd Maximum Likelihood (ML) eller GMM.

**Tillämpning i revision:** Kommuners socialtjänstutgifter påverkas av grannkommuners utgifter (benchmark-beteende, gemensamma arbetsmarknadsmönster).

### Spatial Error Model (SEM)

**Modell:** y = Xβ + u, u = λWu + ε

- λ: spatial autokorrelationsparameter i felleden
- **Tolkning:** Utfallet påverkas inte direkt av grannars utfall, men oobserverade faktorer är spatialt korrelerade — t.ex. lokala konjunkturer, geografiska strukturer
- OLS ger fortfarande konsistenta β-estimat men ineffektivt och standardfel är fel → spatial GLS eller ML

### Skillnad SAR vs. SEM

| | SAR | SEM |
|---|---|---|
| Spatial process | I utfallet (substantiell spillover) | I felen (spatial störning) |
| OLS-β | Inkonsistent | Konsistent men ineffektiv |
| Tolkning ρ | Spillover-effekt | Spatial struktur i ej mätta faktorer |

---

## LM-testsekvens för modellval (Anselin 1988)

Kör OLS → testa residualer → välj modell:

1. **LM-lag:** Testar om SAR är lämplig
2. **LM-error:** Testar om SEM är lämplig
3. **Robust LM-lag:** Testar SAR givet att SEM kan gälla (och vice versa)

**Beslutsregel:**
- Båda signifikanta → välj robust versionen som är mest signifikant
- Bara LM-lag signifikant → SAR
- Bara LM-error signifikant → SEM
- Ingen signifikant → OLS håller

**R-paket:** `spdep::lm.LMtests()`

---

## Tillämpningsexempel: kommunal socialtjänst

**Analysscenario:** Kartlägg om kommuners resursfördelning inom socialtjänsten är geografiskt klustrad och om det finns spillover-effekter.

1. Konstruera W (queen contiguity för kommunpolygoner, `spdep::poly2nb()` + `nb2listw()`)
2. Beräkna Morans I för nettokostnad per brukare — är fördelningen klustrad?
3. LISA-karta — vilka kommuner ingår i HH- och LL-kluster?
4. Kör OLS med strukturkontroller (andel äldre, inkomst, befolkningstäthet)
5. LM-test på OLS-residualer → välj SAR eller SEM
6. Tolka ρ (SAR): spatial spillover i utgiftsnivåer

**Kausalitetsgräns:** Spatial kluster och signifikant ρ visar att resursfördelningen är geografiskt strukturerad — inte varför. Komplettera med reformutvärdering (DiD) för orsaksanalys.

---

## Källöversikt

| Referens | Bidrag |
|---|---|
| Anselin (1988, Kluwer) | Grundläggande spatial econometrics — SAR/SEM/LM-tester |
| Anselin (1995, Geographical Analysis) | LISA — lokal Morans I |
| Anselin (2003, kap. i Florax & Nijkamp) | Spatial econometrics-survey |
| LeSage & Pace (2009, CRC) | Introduktion till spatial econometrics — modern lärobok |
| Bivand m.fl. (2013, Springer) | Applied Spatial Data Analysis with R — `spdep`/`spatialreg` |
