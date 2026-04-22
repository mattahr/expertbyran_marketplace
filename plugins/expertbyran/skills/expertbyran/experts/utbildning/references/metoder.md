# Metodreferens — utbildningsgranskning

Denna fil beskriver de kvantitativa metoder och datakällor som är centrala för effektivitetsgranskningar av det svenska skolväsendet. Innehållet är fristående — ingen annan fil behövs för att förstå det.

---

## Datakällor

### SCB/LISA (Longitudinell integrationsdatabas för sjukförsäkrings- och arbetsmarknadsstudier)

**Vad det är:** SCB:s länkade register med individdata om inkomst, utbildning, arbetsmarknadsstatus, familjeförhållanden m.m. Täcker hela befolkningen från och med 1990 (med viss variation per variabel).

**Styrkor:**
- Fullpopulationsdata — inget urvalsbortfall.
- Longitudinell struktur möjliggör panelanalys och uppföljning över lång tid.
- Kan länkas till Skolverkets register via personnummer.

**Begränsningar:**
- Utbildningsvariabler grovkorniga (SUN-koder = utbildningsnivå/-inriktning, inte specifik skola).
- Inkomstvariabler har tak för utbetalda ersättningar.
- Lag i uppdatering: senaste år ofta preliminärt.

### Skolverkets elevregister (SIRIS/SALSA-datamängder)

**Vad det är:** Individbaserade data om elever i grundskola och gymnasium: skolplacering, betyg, nationella provresultat, frånvaro, modersmål, bakgrundsvariabler.

**Styrkor:**
- Betygsinformation per kurs och ämne, per elev.
- Ger skolidentitet → möjliggör analys på skol- och klassrumsnivå.
- Inkluderar föräldrarnas utbildningsnivå och inkomstklass (hämtas delvis från LISA).

**Länkning LISA ↔ Skolverket:**
- Sker via personnummer.
- Möjliggör analys av t.ex. långsiktiga arbetsmarknadsutfall för elever i olika skoltyper.
- Kräver datadelningsavtal med SCB och Skolverket; Riksrevisionen har generell tillgång via sin ställning.

**Begränsningar:**
- Ej tillgängligt för alla år i alla variabler.
- Historiska data (pre-2000) saknar detalj om friskoleplacering.

---

## SALSA-modellen

**Vad det är:** Skolverkets modell för att beräkna förväntade meritvärden för en skola givet elevsammansättningen. Akronym: Skolors Arbete med Likvärdighet och SAMmansättning (inofficiell tolkning varierar).

**Syfte:** Jämföra skolors faktiska genomsnittliga meritvärde med det förväntade — en enkel form av "mervärde" (value added).

**Variabler i SALSA (bakgrundsfaktorer):**
- Föräldrarnas utbildningsnivå (genomsnitt per skola)
- Andel nyanlända elever (kort vistelsetid i Sverige)
- Andel pojkar/flickor
- Kommunens genomsnittliga utbildningsnivå (indirekt)

**Beräkning:** OLS-regression på kommunnivå/skolnivå. Skillnaden mellan faktiskt och förväntat meritvärde = "mervärde".

**Styrkor:**
- Enkelt att kommunicera till granskningsteam och politiker.
- Tar hänsyn till socioekonomisk sammansättning.

**Begränsningar och fallgropar:**
- Kontrollerar inte för selektion: elever som aktivt väljer en skola är inte slumpmässiga — motiverade elever (och deras föräldrar) söker sig till populära skolor.
- Aggregerad analys på skolnivå: ekologisk felslutning möjlig.
- Regression to the mean: skolor med extrema värden ett år tenderar att röra sig mot snittet nästa år — tolka inte som kausala förbättringar.
- Saknar information om klassrumsnivå, lärarkvalitet, undervisningstid.
- Föräldrarnas utbildningsnivå mäter inte familjens faktiska stöd i hemmet.

**Rekommendation för granskning:** SALSA ger en deskriptiv bild av mervärde men är inte ett kausalt mått. Komplettera med individbaserad analys om möjligt.

---

## Value Added Models (VAM)

**Vad det är:** En familj av statistiska modeller som beräknar en lärares eller skolas bidrag till elevernas kunskapsutveckling, givet kontroll för elevers förkunskaper och bakgrund.

**Grundstruktur:**
```
Prestation(t) = α·Prestation(t-1) + β·Bakgrundsfaktorer + γ·Skola/Lärare + ε
```

**Jämfört med SALSA:** VAM är individbaserat och kontrollerar för elevens eget tidigare resultat (t-1), vilket minskar sammansättningsbias.

**Styrkor:**
- Bättre kontroll för elevsammansättning jämfört med SALSA.
- Kan skilja på skol- och lärarbidrag om data finns på klassrumsnivå.

**Begränsningar:**
- Kräver longitudinella prestationsdata per elev (inte alltid tillgängligt i Sverige; nationella prov finns från åk 3, 6, 9).
- Selektion kvarstår: om elever väljer skola baserat på oobserverade faktorer som korrelerar med VAM-skattningen är skattningen skev.
- Hög varians i skattningarna från år till år för enskilda lärare/skolor — låg reliabilitet.
- Politiskt kontroversiellt att använda för ansvars­utkrävning (se USA:s erfarenheter).

**Rekommendation:** Använd VAM för deskriptiv analys och som komplement, inte som enda bevisunderlag i en granskning.

---

## Kvasiexperimentella designer

### OLS (Ordinary Least Squares)

Enklaste regressionsmetoden. Lämplig som deskriptivt underlag. Identifierar inte kausalitet utan starka antaganden (conditional independence, inget urvalsproblem).

**Vanliga tillämpningar i utbildningsforskning:**
- Beskriva samband mellan resurser och resultat.
- Kontrollera för bakgrundsfaktorer i tvärsnitt.

**Fallgrop:** selektionsbias — elever väljer skola, kommuner väljer policy. OLS-skattningen är i allmänhet inte kausal.

---

### Fixed Effects (FE) / Within-estimator

Kontrollerar för all tidsinvariant oobserverad heterogenitet på enhets­nivå (elev, skola, kommun).

**Formel:**
```
Y_it = α_i + β·X_it + ε_it
```
där `α_i` är enhets-fixed effect.

**Styrkor:**
- Eliminerar bias från tidsinvarianta confounders (t.ex. stabil kommunal kvalitet, elevens fasta förutsättningar).
- Identifierar effekter av *förändring* inom enheter.

**Begränsningar:**
- Identifierar inte effekter av tidsinvarianta variabler (t.ex. kön, etnicitet på individnivå).
- Kräver variation inom enhet över tid.
- Attrition (bortfall) kan skapa bias om bortfallet är systematiskt.

---

### Regression Discontinuity Design (RDD)

Utnyttjar att behandling tilldelas baserat på en kontinuerlig variabel (running variable) med en tröskel/cutoff.

**Typiska utbildningstillämpningar:**
- Behörighetsgränser (t.ex. betyg för tillträde till visst program).
- Åldersgräns för förskola eller bidrag.
- Urvalsgränser för resursprogram.

**Grundlogik:** Elever precis under och precis över cutoff antas vara jämförbara i allt utom behandlingen.

**Styrkor:**
- Nära-experimentell identifiering utan randomisering.
- Hög intern validitet nära cutoff.

**Begränsningar:**
- Begränsad extern validitet: effekten gäller bara för marginella enheter (Local Average Treatment Effect vid cutoff).
- Manipulation av running variable (t.ex. lärare som justerar betyg för att elever ska klara gräns) bryter identifikation — test: McCrary-test.
- Kräver tillräcklig datamängd nära cutoff.

---

### Difference-in-Differences (DiD)

Jämför förändringar i utfall före och efter en reform/intervention för en behandlingsgrupp mot en kontrollgrupp.

**Antagande:** parallel trends — behandlings- och kontrollgrupp hade följt samma trend utan behandlingen.

**Typiska utbildningstillämpningar:**
- Reformer som genomförs i vissa kommuner men inte andra.
- Lagändringar som gäller från ett specifikt år.
- Friskoleetablering i vissa kommuner.

**Fallgropar:**
- Parallella trender kan vara svåra att motivera — visualisera pre-treatment trender.
- Staggered DiD (reform i olika kommuner vid olika tidpunkter) kräver moderna estimatorer (Callaway & Sant'Anna, Sun & Abraham) för att undvika heterogena behandlingseffekt-bias.

---

### Instrumentalvariabel (IV)

Identifierar kausal effekt via ett instrument Z som påverkar behandling X men inte utfall Y direkt (exklusion).

**Typiska instrument i utbildningsforskning:**
- Geografisk variation i friskole­etablering (avstånd, kommunal policy) som instrument för friskole­val.
- Lotteri för överbelagda friskolekön.
- Politisk sammansättning i kommunfullmäktige som instrument för resurstilldelning.

**Styrkor:**
- Hanterar selektion om instrumentet är starkt och exogent.

**Begränsningar:**
- Svårt att hitta starka och valida instrument.
- Identifierar LATE (Local Average Treatment Effect) — effekten för compliers, inte hela populationen.
- Svag instrumental­variabel leder till stora standardfel och möjligen förstärkt bias.

---

## Praktiska råd för granskningsteam

1. **Börja med deskriptiv statistik.** Förklara variationen innan du förklarar den. Hur stor är spridningen? Hur har den förändrats?

2. **Sätt rätt etikett på metoden.** OLS är en beskrivande analys, inte ett kausalfynd. Skriv "samband" inte "effekt" om du inte har en identifieringsstrategi.

3. **Testa för manipulation.** Vid RDD: gör McCrary-test. Vid DiD: visa parallella trender grafiskt.

4. **Sensitetsanalys.** Hur robusta är resultaten mot alternativa specifikationer, bandwidths, kontrollvariabler?

5. **Aggregeringsnivå.** Kommunaggregat kan dölja stora variationer på skolnivå. Individdata är att föredra om tillgängliga.
