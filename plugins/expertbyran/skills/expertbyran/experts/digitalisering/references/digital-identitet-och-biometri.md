# Digital identitet och biometri i staten

*Senast uppdaterad: 2026-04-22*

---

## Grundläggande distinktioner

### Biometrisk identifiering vs. verifiering/autentisering

Distinktionen är avgörande för AI Act-klassificering:

| Begrepp | Definition | AI Act-status |
|---------|-----------|--------------|
| **Biometrisk fjärridentifiering** | Identifiera person *utan deras aktiva medverkan*, vanligtvis på distans, via jämförelse med referensdatabas (Art. 3.41) | Högrisk (Bilaga III.1) — eller förbjudet (Art. 5.1h för realtid) |
| **Biometrisk verifiering/autentisering** | Bekräfta att en specifik person *är den de utger sig för att vara* — med aktiv medverkan | **INTE högrisk** |
| **Realtid** | Insamling, jämförelse och identifiering sker utan betydande dröjsmål. Inkl. korta fördröjningar för att hindra kringgående (Art. 3.42) | Förbjudet för brottsbekämpning på allmän plats (Art. 5.1h) |
| **Efterhand** | Biometriska uppgifter samlades in *före* analysanvändningen. T.ex. sökning i befintligt kameramaterial (Art. 3.43) | Högrisk, tillståndsprocess Art. 26.10 |

**Praktisk konsekvens för myndighetskontakt:**
- BankID, SITHS-kort, e-legitimationsläsning = verifiering → inte högrisk under AI Act
- Ansiktsigenkänning i sökning utan personens medverkan = identifiering → högrisk eller förbjudet

---

## eIDAS 2.0 och EUDIW

### Regelverket

**eIDAS 2.0 (EU 2024/1183):** Förordning om europeisk digital identitet. Trädde i kraft maj 2024. Genomförandeakter publicerade dec 2024.

**EUDIW (European Digital Identity Wallet):** Europeisk digital identitetsplånbok — den centrala leveransen. Deadline: dec 2026.

### EUDIW-innehåll och funktion

Plånboken innehåller:
- **PID (Person Identification Data):** namn, personnummer/nationellt id, adress, födelsedata
- **Attributsintyg (QEAA):** körkort, utbildningsbevis, recept, yrkescertifieringar
- **Selektivt utlämnande:** användaren väljer vilka attribut som visas per tillfälle
- **Offline-stöd:** fungerar utan internetanslutning

### Ansvarsdelning i Sverige

| Aktör | Roll |
|-------|------|
| DIGG | Utfärdar EUDIW-plånboken; valideringsmekanism för attributsintyg |
| Polismyndigheten | Utfärdar bakomliggande e-legitimation på hög tillitsnivå (Sverige-id, planerat dec 2026) |
| PID-utfärdare | Ännu ej fastlagd (oklarhet i ekosystemet, aktiv osäkerhet apr 2026) |
| Privata aktörer | Kan certifieras att utfärda attributsintyg |
| Förlitande parter (FK, Pensionsmyndigheten, SKV) | Måste anpassa IT-system bort från personnummerbaserade e-tjänster |

**Lagstiftningsproposition:** Försenad (avsedd sep 2025 — ej levererad per apr 2026). Tillsynsstruktur för EUDIW-utfärdare ej fastlagd.

### Tillitsnivåer (eIDAS 2.0)

| Nivå | Beskrivning | Exempel |
|------|-------------|---------|
| Låg | Svag identitetsbindning | Enkelt lösenord |
| Väsentlig | Bekräftad identitet; tvåfaktors | BankID (de facto), Freja eID+ |
| Hög | Fysisk närvaro/biometri vid utfärdande | SITHS-kort, kommande Sverige-id |

Myndigheter ska kräva rätt tillitsnivå för respektive tjänst. EUDIW ger hög tillitsnivå. FK, Pensionsmyndigheten och SKV måste mappa sina tjänster mot tillitsnivåer och justera krav.

### Nyckelkällor eIDAS 2.0

| Dokument | Typ | År | Innehåll |
|----------|-----|----|---------|
| SOU 2024:45 | SOU | 2024 | DIGG föreslås tillhandahålla EUDIW + valideringsmekanism; privata aktörer kan certifieras |
| SOU 2025:108 kap. 11 | SOU | 2025 | Senaste nationella genomförandeöversyn; EUDIW-ekosystemet |
| EU 2024/1183 | Förordning | 2024 | eIDAS 2.0 — den fullständiga rättstexten |

---

## BankID och svensk e-legitimation

### BankID:s dominans och sårbarhet

BankID ägs och drivs av bankerna (Finansiell ID-teknik BID AB). Det är i praktiken den dominerande e-legitimationen för statliga e-tjänster — men det är *privat infrastruktur* utan statlig backup.

**Riksrevisionens granskning *Vem där*** belyser spänningen: statliga myndigheter förlitar sig på en privat aktör för grundläggande identitetsfunktion. Tillgänglighets-, säkerhets- och prisproblematik.

**Konsekvens av EUDIW:** Statlig e-legitimation (Sverige-id) via Polismyndigheten planeras till dec 2026. BankID:s dominerande roll kan minska, men privata aktörer kan också certifieras i EUDIW-ekosystemet.

### SITHS-kortet

Används inom offentlig sektor (vård, myndigheter) som tjänstelegitimation på hög tillitsnivå. Utfärdas av Inera. Certifikatbaserat.

---

## Identitetsfastställande vid statliga myndigheter

### Riksrevisionens granskning *Vem där* (2024)

Granskning av identitetsfastställande hos Skatteverket, Försäkringskassan och Polismyndigheten.

**Typiska problem som identifierades:**
- Otydliga rutiner för identitetskontroll vid distansärenden
- Variation mellan myndigheter för liknande tjänster
- Biometrisk kontroll används ojämnt och utan enhetliga regler
- Riskbedömning av identitetsbedrägerier saknar gemensam standard

**Rekommendationer:** Stärkt samordning (DIGG-rollen), enhetligare krav vid e-tjänster, tydligare reglering av biometri vid myndighetskontakt.

### Identitesbedrägerier och biometriska register

**SOU 2024:80** (*Vissa åtgärder för stärkt återvändandeverksamhet*):
- EU-gemensamma biometriska informationssystem: Eurodac, SIS, VIS, CIR (interoperabilitet)
- Migrationsverkets möjligheter att behandla biometri i utlänningsärenden
- Risker för identitetsbedrägerier vid uppehållstillstånd och medborgarskap
- Förslag om utökad fingeravtrycks-/fotoregistrering

**Prop. 2024/25:37** (*Biometri i brottsbekämpningen*):
- Polisens NFC (Nationellt forensiskt centrum) får använda automatiserad ansikts- och fingeravtrycksjämförelse mot *Migrationsverkets register*
- Syfte: identifiera okända misstänkta vid allvarlig brottslighet
- IMY och JO ansåg integritetsanalysen otillräcklig; regeringen gick vidare
- Läs: s. 133 (biometriska register, EU-interoperabilitet, Eurodac-koppling)

---

## Polisens biometriska AI

### Realtids ansiktsigenkänning (RTBID)

**Ds 2025:7** (HDB47, 330 s.) → **Prop. 2025/26:150** (*Polisens användning av AI för ansiktsigenkänning i realtid*, 342 s.)

Möjliggör för Polismyndigheten och SÄPO att använda AI-system för ansiktsigenkänning och annan biometrisk fjärridentifiering i *realtid* på allmän plats för brottsbekämpning, inom ramen för Art. 5.1(h)-undantagen.

- Tillstånd av åklagare/domstol krävs som utgångspunkt
- Undantag vid brådskande fall
- Beslut med negativa rättsliga följder får ej fattas enbart på AI-utdata (Art. 5.3 direkt tillämplig)
- Läs: Ds 2025:7 s. 110 (tillståndskrav, proportionalitet), s. 157 (skäl 32 och 30)

### Retrospektiv biometrisk identifiering

**Ds 2025:32** (HDB432, 96 s., ISBN 978-91-525-1435-1)

Tillståndsprocess för Polismyndigheten, SÄPO och Tullverket att använda biometri-AI för *efterhandsökning* (Art. 26.10 AI Act). Ikraftträdande planerat: 1 januari 2027.

- Tillstånd söks av åklagare
- Proportionalitetskrav
- Dokumentationskrav
- IMY: marknadskontrollmyndighet för Bilaga III.1

**Läs:** s. 24–40 (AI Acts systematik, Art. 26.10 i detalj, distinktionen realtid/efterhand), s. 35–43 (ny lags tillämpningsområde, Polisens och Tullverkets behov).

**Praktisk kontext:** Polisens NFC använder redan tekniken (t.ex. mordet i Almedalen 2022). Regleringen legaliserar befintlig praxis under AI Acts ramverk.

---

## Art. 26.10 AI Act — Retrospektiv biometrisk fjärridentifiering

Tillståndskrav för brottsbekämpande myndigheters *målinriktade* sökning av misstänkta/dömda med biometri-AI.

- Tillstånd söks av åklagare
- Krav: dokumentation, rapportering, omedelbar radering vid avslag
- **Förbjudet** att använda för generell övervakning (Art. 26.10 tredje stycket)

---

## GDPR och AI-baserad riskprofilering

### Art. 22 GDPR — automatiserade beslut

Rätt att inte bli föremål för *uteslutande* automatiserat beslut med rättslig eller liknande väsentlig verkan. Relevant för:
- FK:s bidragsbeslut och riskprofiler
- Arbetsförmedlingens matchningsalgoritmer
- Skatteverkets urvalssystem (brottsbekämpning: undantag)

### SyRI-domen (ECLI:NL:RBDHA:2020:1878)

**Rechtbank Den Haag, 5 februari 2020.** Systemet Systeem Risico Indicatie (SyRI) stoppades.

**Sakfråga:** Holländsk myndighet använde ett AI-system som kombinerade data från 17 register (inkomst, arbete, utbildning, bostadshistorik) för att generera en riskindikator för bidragsfusk — utan att medborgarna informerades om varför de flaggades.

**Domens kärna:**
- Kringgick Art. 22 GDPR genom att kalla outputen för en "indikator" snarare än ett beslut
- Proportionalitetsbedömning empirisk: systemet hade identifierat *noll* fall av faktisk brottslighet men undersökt tusentals medborgare
- Domstolen tillämpade Art. 8 ECHR (privatliv) och fann att intrånget inte var nödvändigt i ett demokratiskt samhälle

**Relevans för Sverige:** Referensdom för granskning av svenska myndigheters riskprofileringssystem. Proportionalitet är empirisk, inte hypotetisk — det räcker inte att systemet *kan* hitta fusk; det måste *faktiskt* göra det i proportion till intrånget.

**Källa:** Van Bekkum & Zuiderveen Borgesius (2021), ESCR-Net.

### IMY:s FK-VAB-beslut (november 2025)

IMY beslutade att Försäkringskassans AI-urvalssystem för tillfällig föräldrapenning (VAB) bröt mot GDPR.

**Viktigt klargörande:** Ärendet gällde *VAB*, inte sjukpenning. Art. 22-frågan för urvalssystem i sjukpenningbeslut är fortfarande öppen i Sverige. Mer ingripande AI-tillämpningar kan bli föremål för liknande granskning framöver.

**Källa:** IMY nyhetsartikel november 2025; ISF 2026:1.
