# NIS2-direktivet och Cybersäkerhetslagen (2025:1506)

*Baserat på: SOU 2024:18, SOU 2025:79, SOU 2025:115, Prop. 2025/26:28, Statskontoret 2025, Nationell strategi 2025–2029 (Skr 2024/25:121), RiR 2023:8, RiR 2024:6*

---

## Rättslig grund och tidslinje

| Händelse | Datum |
|----------|-------|
| NIS2-direktivet beslutades av EU | December 2022 |
| SOU 2024:18 — Nya regler om cybersäkerhet | Mars 2024 |
| NIS2 trädde i kraft provisoriskt i Sverige | Oktober 2024 |
| Proposition 2025/26:28 överlämnad | Oktober 2025 |
| Riksdagen antog cybersäkerhetslagen (2025:1506) | 10 december 2025 |
| Lagen trädde i kraft | 15 januari 2026 |
| Anmälningsportal öppnade (MKF:s portal) | 2 februari 2026 |
| Anmälningsdeadline | 16 februari 2026 |

---

## Tillämpningsområde

- **Sektorer:** Utökat från 7 (NIS1) till 18 sektorer
- Nya sektorer inkluderar: offentlig förvaltning, tillverkning, rymdsektorn, avloppshantering, livsmedel, kemikalier, post
- Gäller för **väsentliga** och **viktiga** entiteter — storlek och sektor avgör klassificering
- Inkluderar offentliga myndigheter, stora kommuner och regioner, privata verksamheter

---

## Kärnkrav (artikel 21 NIS2 — riskhanteringsåtgärder)

Organisationer måste implementera:
1. Policyer för riskanalys och informationssystemsäkerhet
2. Incidenthantering
3. Driftkontinuitet och katastrofåterställning
4. Leverantörskedjans säkerhet
5. Säkerhet vid förvärv, utveckling och underhåll av system
6. Policyer för bedömning av riskhanteringsåtgärders effektivitet
7. Grundläggande cyberhygien och utbildning
8. Kryptografi och kryptering
9. Personalsäkerhet, åtkomstkontroll och hantering av tillgångar
10. Multifaktorautentisering och säkra kommunikationskanaler

---

## Incidentrapportering (artikel 23 NIS2)

**Flerstegsstrategi:**
- **Inom 24 timmar:** Tidig varning om allvarlig incident misstänks
- **Inom 72 timmar:** Incidentanmälan med initial bedömning
- **Inom 1 månad:** Slutrapport med fullständig analys

**Mottagare i Sverige:**
- MSB (NIS2-incidenter, beredskapsförordningen) — tills FRA tar över
- FRA (föreslås, SOU 2025:79) ta över CSIRT-funktion och incidentrapportering
- PTS — incidentrapporter enligt lagen om elektronisk kommunikation (LEK) och eIDAS
- IMY — personuppgiftsincidenter (GDPR)
- SÄPO — säkerhetsskyddsincidenter
- Polisen — brottsanmälan

**Problem: Fragmenterat system.** Ingen gemensam kontaktpunkt för alla regelverk i Sverige (per 2026). Organisationer kan behöva rapportera till flera myndigheter för samma incident.

---

## Nyckelaktörer i det svenska systemet

| Aktör | Roll |
|-------|------|
| MSB | Nationell gemensam kontaktpunkt; leder samarbetsforum för tillsynsmyndigheter; CSIRT (tills vidare) |
| FRA | Föreslås ta över CSIRT, CERT-SE och incidentrapportering från MSB (SOU 2025:79); NCSC från nov 2024 |
| NCSC | Nationellt centrum för cybersäkerhet — placerat inom FRA sedan nov 2024 |
| PTS | Tillsyn elektronisk kommunikation |
| IMY | Personuppgiftsincidenter (GDPR) |
| SÄPO | Säkerhetsskyddstillsyn, säkerhetsskyddsincidenter |
| Länsstyrelsen Stockholm | Tillsyn tillverkningssektorer |
| 11 tillsynsmyndigheter totalt | Sektorsspecifik tillsyn under NIS2 |

---

## Tillsyn

**Tillsynsstruktur:**
- 11 myndigheter ska bedriva tillsyn (upp från 6 under NIS1)
- Sex av dem bedriver redan tillsyn från NIS1
- Fem nya tillsynsmyndigheter — saknar erfarenhet av cybersäkerhetstillsyn

**Tillsynsmyndigheternas befogenheter (artikel 32–33 NIS2):**
- Rättsliga bindande instruktioner
- Säkerhetsskanningar
- Revisioner (på plats eller på distans)
- Krav på information och bevis
- Sanktionsavgifter

**Sanktioner:**
- Väsentliga entiteter: max 10 MEUR eller 2 % av global omsättning
- Viktiga entiteter: max 7 MEUR eller 1,4 % av global omsättning
- Ansvar kan riktas mot ledningspersoner personligen

---

## Ledningens ansvar och utbildningsskyldighet

- Ledningspersoner ansvarar personligen för att organisationen lever upp till NIS2-kraven
- **Ny skyldighet:** Ledningspersoner ska genomgå utbildning i cybersäkerhet
- Diskussion under remiss (Hi3G/Tre): Om överträdelse av utbildningsskyldigheten ska ge sanktionsavgift (omtvistat, direktivet täcker detta ej explicit)

---

## Identifierade implementeringsutmaningar (Sverige, tidiga erfarenheter)

### 1. Tillsynskapacitetsbrist
- Statskontoret 2025: Tillsynsmyndigheterna saknar resurser och kompetens
- Länsstyrelsen Stockholm: Initialkostnad 5,4 MSEK, deltog ej i föreskriftsarbetet 2024–2025 pga resursbrist
- Flera nya myndigheter har aldrig arbetat med informationssäkerhetstillsyn

### 2. Föreskrifter inte klara vid ikraftträdandet
- Sektoriella föreskrifter ska tas fram gemensamt av MSB och respektive tillsynsmyndighet
- Flera tillsynsmyndigheter väntar med föreskriftsarbete tills resurser tilldelats
- Risk: Verksamhetsutövare vet inte exakt vad som krävs av dem

### 3. Oklart ansvarsfördelning under omorganisation
- SOU 2025:79 föreslår att FRA tar över från MSB: CSIRT, incidentrapportering, NCSC, föreskriftsrätt
- Nationell strategins handlingsplan innehåller notering: "ansvarsfördelning under översyn"
- Övergångsfas kan skapa luckor i tillsyn och stöd

### 4. Fragmenterad incidentrapportering
- Ingen gemensam kontaktpunkt för NIS2, GDPR, LEK, eIDAS, säkerhetsskyddslag
- SOU 2025:115 (cyberresiliensförordningen) uppmärksammar problemet men löser det ej
- Dubbelrapportering ger onödig administrativ börda

### 5. Kommuner och regioner — otillräcklig styrning
- MSB:s föreskrifter gäller statliga myndigheter; kommuner/regioner har bara rekommendationer
- Ingen nationell modell för riskbedömningar (kritik i RiR 2023:8)
- Vård- och omsorgssektorn i riskzon (RiR 2024:6)

---

## Nationell strategi för cybersäkerhet 2025–2029 (Skr 2024/25:121)

**Tre pelare:**
- A: Systematiskt och effektivt cybersäkerhetsarbete
- B: Utvecklad kunskap och kompetensutveckling
- C: Förmåga att förhindra och hantera cybersäkerhetsincidenter

**Dokumentet:**
- Beskriver nuläge för centrala aktörer och deras roller
- Innehåller handlingsplan som ska uppdateras löpande
- Anger att ansvarsfördelning "är under översyn" — reserverar sig för ändringar

---

## Granskningsbara frågor (riksrevisionsperspektiv)

Följande frågor är lämpliga för effektivitetsrevision kopplat till NIS2/cybersäkerhetslagen:

1. **Tillsynseffektivitet:** Har de 11 tillsynsmyndigheterna resurser, kompetens och föreskrifter för att bedriva meningsfull tillsyn?
2. **Incidentrapportering:** Rapporteras incidenter i rätt tid till rätt myndighet? Leder incidentrapporter till systemförbättringar?
3. **Kommuner och regioner:** Är den rättsliga styrningen tillräcklig för välfärdssektorn?
4. **Omorganisationen (MSB→FRA):** Medför flytten av CSIRT och incidentrapportering effektivitetsvinster eller risker?
5. **Riskhantering i praktiken:** Genomför statliga myndigheter systematiska riskanalyser som lever upp till kraven?
6. **Leveranskedjans säkerhet:** Hur hanterar offentliga aktörer säkerhetskrav på IT-leverantörer?

---

## Riksrevisionens befintliga granskningar (metoder och fynd)

| Rapport | År | Fynd | Metod |
|---------|-----|------|-------|
| RiR 2023:8 — Regeringens styrning av cybersäkerhet | 2023 | Strategin saknar riskbaserat tillvägagångssätt, tydliga prioriteringar, uppföljningsstruktur | Dokumentstudier + intervjuer (8 departement, MSB, FRA, SÄPO, Polisen) |
| RiR 2024:6 — Informationssäkerhet vård och omsorg | 2024 | Bristfällig tillsyn, kommuner saknar bindande regler, otillräckligt MSB-stöd vid incident | Intervjuer, enkät, fallstudie (cyberangrepp 2022) |
| RiR 2024:24 — Säkerhetspolisens verksamhet | 2024 | Tillsyn för inriktad på formalia, inte faktiska säkerhetsåtgärder | Enkät + dokumentgranskning |
| RiR 2026:3 — Infiltration i staten | 2026 | Säkerhetsarbete ej effektivt hos FMV, Kammarkollegiet, Kriminalvården | COSO-modell, enkät, dokumentgranskning |

**Riksrevisionens typiska metodverktygslåda för cybersäkerhetsgranskning:**
- Dokumentstudier: Strategier, regleringsbrev, uppdrag, årsredovisningar, internrevisionsrapporter
- Intervjuer: Nyckelpersoner hos granskade myndigheter och departement
- Enkäter: Bredare kartläggning av praxis hos flera myndigheter
- Fallstudier: Djupgående granskning av enskilt fall (t.ex. konkret cyberangrepp)
- Faktaprövning: Utkast faktagranskas av berörda aktörer

**Riksrevisionen genomför inte:** teknisk testning (penetrationstestning, sårbarhetsskanning) — det är tillsynsmyndigheternas uppgift.

---

## Centrala lagrum att kunna

| Regel | Innehåll |
|-------|---------|
| Cybersäkerhetslagen (2025:1506) | Huvudlag som implementerar NIS2 i Sverige |
| Artikel 21 NIS2 | Riskhanteringsåtgärder (tio krav) |
| Artikel 23 NIS2 | Incidentrapporteringsplikt och tidsfrister |
| Artikel 32–33 NIS2 | Tillsynsbefogenheter (väsentliga/viktiga entiteter) |
| Artikel 34 NIS2 | Sanktionsavgifter |
| SOU 2024:18 | Utredningsgrund, sektorsindelning, tillsynsstruktur |
| SOU 2025:79 | FRA tar över CSIRT och incidentrapportering från MSB |
| Prop. 2025/26:28 | Propositionstext med remissvar och motiveringar |
| MSBFS 2020:6 | MSB:s föreskrifter om informationssäkerhet (statliga myndigheter) |
| Förordning (2022:524) | Statliga myndigheters beredskap |
