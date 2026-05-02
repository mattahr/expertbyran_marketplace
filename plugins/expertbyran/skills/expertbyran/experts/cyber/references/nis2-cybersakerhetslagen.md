# NIS2-direktivet och Cybersäkerhetslagen (2025:1506)

*Baserat på: SOU 2024:18, SOU 2025:79, SOU 2025:115, Prop. 2025/26:28, Prop. 2025/26:214, Statskontoret 2025:8, Nationell strategi 2025–2029 (Skr 2024/25:121), RiR 2023:8, RiR 2024:6, ENISA Technical Implementation Guidance (jun 2025), MCF:s remissföreskrifter (apr 2026)*

**Namnbyte:** MSB (Myndigheten för samhällsskydd och beredskap) har bytt namn till **MCF (Myndigheten för civilt försvar)**. Webbplatsen msb.se omdirigerar nu till mcf.se. Alla hänvisningar till "MSB" i äldre dokument avser numera MCF.

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
| Anmälningsportal öppnade (MCF:s portal) | 2 februari 2026 |
| Anmälningsdeadline | 16 februari 2026 |
| ENISA Technical Implementation Guidance publicerad | 26 juni 2025 |
| MCFFS om säkerhetsåtgärder och utbildning — remiss | 15–29 april 2026 |
| MCFFS om säkerhetsrevisioner och skanning — remiss | 15 april – 13 maj 2026 |
| Auditdeadline NIS2-compliance (förlängd) | 30 juni 2026 |
| Uppgiftsskyldighetslag NCSC (Prop. 2025/26:214) träder i kraft | 15 juli 2026 |
| MCF:s CSIRT/CERT-SE och kontaktpunkt överförs till FRA/NCSC | 1 juli 2026 (planerat) |

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
| MCF (fd MSB) | Nationell gemensam kontaktpunkt; leder samarbetsforum för tillsynsmyndigheter; CSIRT/CERT-SE (tills 1 jul 2026); utfärdar MCFFS-föreskrifter |
| FRA | Tar över CSIRT, CERT-SE och incidentrapportering från MCF (fd MSB) per 1 jul 2026 (prop. 2025/26:214); NCSC från nov 2024 |
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
- Fem nya tillsynsmyndigheter — saknar erfarenhet av cybersäkerhetstillsyn (Statskontoret 2025:8)

**Sektorsspecifika förändringar (SOU 2024:18):**
- **PTS (Post- och telestyrelsen):** Utökat tillsynsansvar — elektronisk kommunikation, digitala tjänster, DNS/TLD-registreringstjänster. PTS definierar självständigt vilka aktörer som är tillsynsobjekt inom sin sektor.
- **Transportstyrelsen:** Kraftigt utökad portfölj — antalet tillsynsobjekt ökade från 130 till 750 (luftfart, järnväg, sjöfart, väg samlade under NIS2). Myndigheten befinner sig under kapacitetspress vid implementeringen.

**Föreskriftsstatus (maj 2026):**
- MCFFS 2026:1 (anmälan och identifiering) — i kraft sedan 2 feb 2026
- MCFFS om säkerhetsåtgärder och utbildning — remiss apr 2026, beslut väntat sommar 2026
- MCFFS om säkerhetsrevisioner och skanning — remiss apr–maj 2026, beslut väntat höst 2026
- MCFFS om incidentrapportering och informationsskyldighet — tidpunkt oklar
- Konsekvens: Verksamhetsutövare saknar bindande krav på säkerhetsåtgärder och revisioner tills föreskrifterna beslutats (SOU 2025:79)

**Tillsynsmyndigheternas befogenheter (artikel 32–33 NIS2):**
- Rättsliga bindande instruktioner
- Säkerhetsskanningar
- Revisioner (på plats eller på distans)
- Krav på information och bevis
- Sanktionsavgifter

**Sanktioner:**
- Väsentliga entiteter (enskilda): max 10 MEUR eller 2 % av global omsättning
- Viktiga entiteter (enskilda): max 7 MEUR eller 1,4 % av global omsättning
- Offentliga verksamhetsutövare: max 10 000 000 SEK (fast tak, inte omsättningsbaserat)
- Minimum för alla: 5 000 SEK
- **Ny sanktionsform: "Anmärkning"** — obligatorisk när ingen annan sanktion beslutas (prop. 2025/26:28 s. 346)
- Tillsynsmyndigheten kan även förelägga om offentliggörande av överträdelsen
- Ansvar kan riktas mot ledningspersoner personligen (förvaltningsdomstol)

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

### 2. Föreskrifter inte klara vid ikraftträdandet (status april 2026)

**Hittills antagen:**
- MCFFS 2026:1 — Anmälan och identifiering (i kraft 2 feb 2026)

**På remiss (april 2026):**
- MCFFS om **säkerhetsåtgärder och utbildning**: reglerar organisatoriska, tekniska, driftsrelaterade och fysiska säkerhetsåtgärder + obligatorisk ledningsutbildning. Remiss 15–29 apr 2026, beslut sommar 2026.
- MCFFS om **säkerhetsrevisioner och skanning**: reglerar tillsynsaktiviteter — villkor för säkerhetsrevisioner och säkerhetsskanning som tillsynsinstrument. Remiss 15 apr – 13 maj 2026, beslut höst 2026.

**Planeras:**
- MCFFS om incidentrapportering och informationsskyldighet: tidpunkt oklar.

Risk kvarstår: Verksamhetsutövare saknar tydliga krav tills föreskrifterna beslutats. Internationell referens: ENISA Technical Implementation Guidance (26 jun 2025) ger praktisk vägledning baserat på genomförandeförordning (EU) 2024/2690 — kan tillämpas i mellantiden.

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

## ENISA Technical Implementation Guidance (NIS2)

**Publicerad:** 26 juni 2025 | Källa: enisa.europa.eu/publications/nis2-technical-implementation-guidance

Baseras på genomförandeförordning (EU) 2024/2690. Ej rättsligt bindande men central referens för vad tillsynsmyndigheter och granskare förväntar sig.

**13 tematiska implementeringsområden:**
1. Governance & Policy (styrning och riktlinjer)
2. Risk Management (riskhantering)
3. Incident Handling & Reporting
4. Business Continuity & Crisis Management
5. Supply Chain Security
6. Secure Acquisition / Development / Maintenance
7. Effectiveness Measurement (mätning av effektivitet)
8. Cyber Hygiene & Training
9. Cryptography
10–13. (Ytterligare teknikspecifika områden)

**För granskare:** Vägledningen innehåller evidensexempel och mappingstabeller som kopplar lagkrav till konkreta implementeringsåtgärder. Kan användas som bedömningsram vid granskning av hur myndigheter lever upp till NIS2-krav.

**Auditdeadline:** Förlängd till 30 juni 2026 (från ursprungliga 31 december 2025).

---

## Implementeringsläget i offentlig sektor (2024)

**MCF:s Cybersäkerhetskollen (Infosäkkollen + It-säkkollen):**
- Frivilligt självskattningsverktyg — svarsfrekvens 86 % regioner, 53 % kommuner (2023)
- **2024: 8 av 120 myndigheter** når det MSB definierat som uppfyllande av MSBFS 2020:6
- 2023: Bara 4 av 120 myndigheter nådde målet — marginell förbättring
- Kommuner och regioner presterar sämre än statliga myndigheter
- Särskilt låga resultat: **ledningens styrning och kontroll** + **uppföljning och utvärdering**
- Källa: Budgetprop. 2025/26:1, uo6

**Incidentrapportering — mörkertal:**
- 319 it-incidenter rapporterades 2024 (minskning sedan 2023)
- Varav 170 från statliga myndigheter — nedåtgående trend sedan 2018
- CERT-SE hanterade 17 500 ärenden 2024 (+20 % vs 2023) — diskrepansen bekräftar stort mörkertal
- MCF bedömer sedan länge att mörkertalet är "stort"
- NIS2-kraven (obligatorisk rapportering med 24h/72h-frister) kan höja rapporteringsvolymerna men kräver bättre portal

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

1. **Myndigheternas NIS2-implementering:** Har myndigheter anmält sig till MCF:s portal? Har de tre grundkraven (anmälan, riskhantering, incidentrapportering) implementerats? Har ledningsorgan genomgått utbildning? — Bedömningsgrund: ENISA Technical Implementation Guidance + MCFFS 2026:1.
2. **Tillsynsarkitekturens funktionalitet:** Fungerar samordningen mellan MCF och de 11 sektortillsynsmyndigheterna? Har tillsynsmyndigheterna resurser, kompetens och färdiga föreskrifter för meningsfull tillsyn? — Referens: Statskontoret 2025:8.
3. **Säkerhetsrevisioner som tillsynsinstrument:** Hur tillämpas MCFFS om säkerhetsrevisioner och skanning (beslut höst 2026)? Är metoderna i linje med ENISA:s vägledning?
4. **Incidentrapportering och mörkertal:** Fyra konkreta granskningsobjekt (Källa: RiR 2023:8, SOU 2025:79):
   - a) Volym rapporterade incidenter (319 år 2024) kontra faktiska ärenden hos CERT-SE (17 500 år 2024) — kvantifierar mörkertalet och om NIS2-obligatoriet fått effekt.
   - b) MCF→FRA/NCSC-övergångens konsekvenser: risk för kapacitetsluckor i incidentrapporteringskedjan under övergången (planerad 1 jul 2026).
   - c) Portalkontinuitet: fungerar NIS2-portalen och CER-portalen utan avbrott under omorganisationen?
   - d) Systemförbättring: leder inkomna incidentrapporter faktiskt till uppföljningsåtgärder, eller arkiveras de utan åtgärd?
   Referens: Budgetprop. 2025/26:1 uo6, MCF:s årsrapport it-incidentrapportering 2024, RiR 2023:8, SOU 2025:79.
5. **NCSC-övergångens konsekvenser:** Verksamhetskontinuitet under flytten MCF→FRA/NCSC (pågår till 1 jul 2026). Hur hanteras informationsdelning med näringsliv? (Känt problem: RiR 2023:8 citeras i Prop. 2025/26:214.)
6. **Kommuner och regioner:** Är den rättsliga styrningen tillräcklig för välfärdssektorn? — Referens: RiR 2024:6.
7. **Riskhantering i praktiken:** Genomför statliga myndigheter systematiska riskanalyser som lever upp till kraven? (8 av 120 når kraven per 2024.)
8. **Leveranskedjans säkerhet:** Hur hanterar offentliga aktörer säkerhetskrav på IT-leverantörer?

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
| Prop. 2025/26:214 | Lagändringar för stärkt NCSC: uppgiftsskyldighet vid samverkan, sekretessregler; FRA tar över CSIRT/kontaktpunkt |
| MSBFS 2020:6 | MSB:s föreskrifter om informationssäkerhet (statliga myndigheter) |
| Förordning (2022:524) | Statliga myndigheters beredskap |
