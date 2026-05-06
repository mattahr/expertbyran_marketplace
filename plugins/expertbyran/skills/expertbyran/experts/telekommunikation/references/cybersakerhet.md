# Cybersäkerhet i Telekominfrastruktur

Senast uppdaterad: 2026-05-06

## NIS2 och Cybersäkerhetslagen — telekomspecifika krav

### Tillämplighetsområde för telekomoperatörer

Alla tillhandahållare av allmänt elektroniskt kommunikationsnät eller allmänt tillgänglig elektronisk kommunikationstjänst är *per automatik* antingen väsentliga eller viktiga entiteter beroende på storlek (SOU 2024:18, s. 107–108).

Telekomoperatörers hela nätinfrastruktur (elektroniska kommunikationsnät, sammankopplade enheter som automatiskt behandlar digitala uppgifter) faller under NIS2-systemets definition.

### Artikel 21-krav — minimiåtgärder

(Prop. HD0328, s. 87 — lagtext): "verksamhetsutövare ska vidta lämpliga och proportionella tekniska, driftsrelaterade och organisatoriska åtgärder för att hantera risker som hotar säkerheten i nätverks- och informationssystem."

Minimiåtgärder inkluderar:
- Riskanalys och riskhanteringspolicy
- Incidenthanteringsplan + incidentrapportering (tidig varning 24 h, mer detaljerat 72 h)
- Kontinuitetshantering (backup, katastrofåterställning)
- Supply chain security (krav att bedöma leverantörers säkerhetsnivå)
- Kryptering och åtkomstkontroll
- Utbildning och kompetens inom cybersäkerhet
- Multifaktorautentisering där tillämpligt
- *Ledningsansvar*: Styrelsen/ledningsorganet ska godkänna riskhanteringsåtgärder och kan hållas personligt ansvariga

### Sanktioner

- Väsentliga operatörer: upp till €10M eller 2% av global omsättning
- Viktiga operatörer: upp till €7M eller 1,4% av global omsättning

### Cybersäkerhetslagen — lagstatus (i kraft 15 januari 2026)

- **Riksdagen antog** Prop. 2025/26:28 den **10 december 2025** (rskr. 2025/26:113)
- **Utfärdad** 11 december 2025 som SFS 2025:1506 (cybersäkerhetslagen), 1508 (toppdomäner), 1510 (OSL), 1511 (LEK-ändring)
- **Ikraftträdande: 15 januari 2026** — lagen gäller nu
- NIS-lagen (2018:1174) upphävd
- Källa: Bet. 2025/26:FöU2 (Försvarsutskottet, DocRec 24209); Skr. 2025/26:75 (DocRec 24601)

### NIS2 vs LEK 8 kap. (löst)

- **LEK 8:1–4 upphävda** fr.o.m. 15 jan 2026; hänvisning kvarstår i LEK
- NIS-lagen (2018:1174) upphävd
- Cybersäkerhetslagen: bredare scope — supply chain, kryptering, ledningsansvar, utbildning som explicita krav

### Tillsynsstruktur under NIS2 (uppdaterad)

**PTS kvarstår som tillsynsmyndighet** för digital infrastruktur, digitala tjänster, rymden, post/bud och IKT-tjänsteförvaltning. Antalet tillsynsmyndigheter utökas från 7 till 11 (fem länsstyrelser + Läkemedelsverket tillkommer).

**PTS tillsynsbörda ökar dramatiskt:**
- Tillsynsobjekt: **40–50 (NIS1) → ~1 075 (NIS2 + LEK)** — en 20-faldig ökning
- Initialkostnad: **41,2 Mkr** (2025–2028)
- Finansieringsmodell: anslag (ej avgifter) → strukturell budgetrisk
- Källa: Statskontoret 2025:8 "Tillsynsmyndigheternas kostnader till följd av NIS2-direktivet" (DocRec 23710)

**⚠ STOR STRUKTURFÖRÄNDRING — FRA tar MSB:s CSIRT-roll:**
- SOU 2025:79 (DocRec 23926) föreslog flytt från MSB till FRA
- **Prop. 2025/26:214** "Lagändringar för ett stärkt nationellt cybersäkerhetscenter" (DocRec 24695, april 2026) genomför flytten:
  - FRA utses till **CSIRT-enhet, gemensam NIS2-kontaktpunkt och cyberkrishanteringsmyndighet** fr.o.m. 1 juli 2026
  - Uppgiftsskyldighetslagen (informationsdelning NCSC-samverkansmyndigheter) ikraft **15 juli 2026**
  - PTS kvarstår som samverkansmyndighet i NCSC (jämte FMV, FM, MCF, Polismyndigheten, SÄPO)
  - MSB behåller: säkra kommunikationstjänster, krisberedskap, civilt försvar
- NCSC organisatoriskt i FRA sedan november 2024
- **Konsekvens för incidentrapportering:** fr.o.m. 1 juli 2026 rapporterar telekomoperatörer signifikanta incidenter till FRA/NCSC — inte längre MSB

**Föreskriftsläge (maj 2026):**
- MSB + PTS fick sep 2025 uppdrag att förbereda föreskriftsarbetet
- PTSFS 2022:11 och PTSFS 2021:3 ersätts av nya föreskrifter under cybersäkerhetslagen
- Föreskrifterna ej publicerade per maj 2026 — bevaka

**Revisionsfråga — PTS kapacitet:**
Kan PTS hantera 20-faldig tillsynsexpansion med 41,2 Mkr initialbudget? Finansiering via anslag (ej avgifter) skapar strukturella risker vid oväntade kostnadsökningar. Statskontoret identifierar kompetensbrist som genomgående utmaning.

---

## 5G-säkerhet och Leverantörsbedömning

### PTS systematiska säkerhetsarbete — detaljerad tidslinje (uppdaterat 2026-05-06)

SOU 2025:115 (DocRec 24203) ger den hittills mest heltäckande bilden av PTS externa cybersäkerhetsarbete i 5G:

| Period | Aktivitet |
|---|---|
| Sedan 2019 | PTS representerar Sverige i EU:s NIS 5G Cybersecurity Workshop — **vice ordförande** i framtagandet av EU:s 5G Toolbox |
| Sedan 2020 | PTS inför cybersäkerhetskontroller direkt i **spektrumtillståndsvillkor** (frekvenstilldelning kopplad till säkerhetskrav) |
| 2021–2024 | PTS representerar Sverige i framtagandet av **EUCS 5G-certifieringsordningen** (EU Cybersecurity Scheme for 5G Networks) under EU:s cybersäkerhetsakt |
| Pågående | Genomfört **två regeringsuppdrag** om cybersäkerhetsriskanalyser i 5G-näten i Sverige |
| Sedan 2023 | Deltar i OECD Working Party on Digital Security; delegat i ENISA:s styrelse |
| 2024– | Marknadskontrollmyndighet för cybersäkerhetskrav i internetuppkopplad radioutrustning (delegerad CRA-förordning) |

**PTS som CRA-marknadskontrollmyndighet (föreslagen):** SOU 2025:115 föreslår PTS som marknadskontrollmyndighet för hela EU:s cyberresiliensförordning (CRA). Motiv: bred erfarenhet från NIS, eIDAS och LEK; etablerad marknadskontrollstruktur. Beslut väntas i proposition (ej antagen per maj 2026).

**Källa:** SOU 2025:115 (DocRec 24203, HDB3115), sid. 280, 287

### Tre säkerhetsmekanismer i det svenska systemet

**1. Leverantörsbedömning (5G-säkerhetslagen):**
Lag (2019:904) möjliggör att PTS — efter samråd med SÄPO och FM — kan ställa säkerhetsvillkor och utesluta högrisk-leverantörer. Bedömningsmallen: (a) nationell säkerhetsrisk, (b) utländsk rättslig ram, (c) beroendeförhållanden.

**2. Spektrumvillkor som säkerhetsinstrument (fr.o.m. 2020):**
PTS inför cybersäkerhetskontroller direkt i frekvenstillstånden. Operatörer åläggs följa ENISA-riktlinjer och 5G Toolbox-rekommendationer som villkor i licensen — ett unikt instrument som kopplar spektrumreglering (LEK 11 kap.) med cybersäkerhetskrav.

**3. EUCS 5G-certifieringsordning (under CSA, 2021–2024):**
EU-harmoniserad certifiering av 5G-nätkomponenter. Status per maj 2026: Under formellt antagande; ej antagen. Granskningsbar fråga: kopplas certifieringskraven till operatörernas upphandlingsprocesser?

### Huawei-beslutet — mallen för leverantörsbedömning

PTS beslut okt 2020 att förbjuda Huawei i 3,5 GHz- och 2,3 GHz-band:
- Baserat på SÄPO/FM-bedömning om kinesiskt cyberspionage
- Förvaltningsrätten + kammarrätten bekräftade att PTS hade fog för beslutet
- Mallen: nationell säkerhetsrisk, utländsk rättslig ram, beroendeförhållanden

**Källa:** SOU 2021:87, sid. 416–417 (DocRec-id: H9B387)

### PTSFS 2022:11 — Föreskrifter om säkerhet i nät och tjänster

Genomför 8 kap. LEK 2022 (numera ersatt av cybersäkerhetslagen). Krav:
- Långsiktigt systematiskt säkerhetsarbete
- Riskanalys
- Tekniska/organisatoriska åtgärder
- Kryptering och redundans
- Reservkraft

### Nationella telesamverkansgruppen

Stärkt lagstiftning fr.o.m. 1 maj 2024 — PTS kan besluta om deltagandekrav.

**Reservel Gotland:** Pilot avslutat; utomhustäckning i alla mobilnät kan upprätthållas vid långvariga elavbrott.

### 5G SA-gapet — bortglömd säkerhets- och kapacitetsdimension (2026-05-06)

Sverige driver 5G **NSA (Non-Standalone)** — kärnnäten kör 4G LTE-kärna med 5G-radio. 5G **SA (Standalone)** med ren 5G-kärna (5GC) krävs för:
- Dynamisk nätslicning — isolering och differentiering av nätresurser
- Ultra-low latency för kritiska industriapplikationer
- Edge computing och avancerad AI-integration
- Bättre säkerhetssegmentering mellan nätslices

AI-kommissionen (SOU 2025:12, DocRec 14167, sid. 60) identifierar SA-gapet som risk för svensk AI-konkurrenskraft. **Ingen myndighetsreglering styr i dag SA-uppgraderingstakten** — ett potentiellt myndighetsgap. PTS:s täckningskrav (900/2100/2600 MHz, fr.o.m. 2026) mäter täckning och kapacitet, men kräver inte SA.

**Investeringsparadox:** Mobiloperatörernas lönsamhet understiger kostnaden för kapital. Trots +30% investeringstillväxt 2024 (4,7 Mdr kr) hämmas stora SA-uppgraderingar av låg avkastning och fragmenterad marknad.

---

## EU Cybersecurity Package 2026

**Paketet presenterades:** 20 januari 2026.

**Lagstiftningsstatus (maj 2026):**
- **CSA2 + NIS2-revisionen:** Trialogförhandlingar (rådet–parlamentet–kommissionen) pågår; politisk överenskommelse väntas **tidigt 2027**.
- **CRA:** Rapporteringskrav fr.o.m. **11 september 2026**; övriga produktkrav fr.o.m. **11 december 2027**.

**Två delar:**
1. Reviderad Cybersecurity Act (CSA2)
2. Direktiv med riktade NIS2-förenklingar

### Högrisk-leverantörsregim (CSA2)

- Kommissionen ges befogenhet att utpeka tredjeland som cybersäkerhetshot
- Kan identifiera "key ICT assets" och ställa krav på begränsning/utfasning
- Operatörer av elektroniska kommunikationsnät ska inte förlita sig på högrisk-leverantörer för kritiska tillgångar
- **Böter vid brott:** upp till 7% av global omsättning
- Inget EU-övergripande Huawei-/ZTE-förbud (ännu), men mekanismen finns på plats
- Tyskland har nationellt förbjudit kinesiska komponenter i framtida 6G-nät
- EU-medel i nästa MFF 2028–2034 tillgängliga om inga högrisk-leverantörer används

### Cyber Resilience Act (CRA)

- Trädde i kraft 10 december 2024
- Krav gäller fr.o.m. 11 december 2027; rapporteringskrav fr.o.m. 11 september 2026
- Täcker hårdvara/mjukvara med digitala element — relevant för nätverksutrustning

### Relation till 5G-verktygslådan

- Högrisk-leverantörs-logiken i 5G-verktygslådan utökas nu bortom telekommunikation till bredare ICT-försörjningskedja
- PTS (LEK/cybersäkerhetslagen) + MSB + SÄPO + FM koordinerar; NCSC-samverkan fördjupas

### Sverige och PTS

PTS är tillsynsmyndighet för telekomoperatörernas efterlevnad av leverantörsbedömning (5G-säkerhetslagen, cybersäkerhetslagen). CSA2 + CRA adderar ytterligare lager; koordinering med FRA/NCSC, SÄPO, FM behövs. FRA är nu huvud-CSIRT fr.o.m. 1 juli 2026 (Prop. 2025/26:214).

---

## Nyckelkällor

- SOU 2024:18 — Nya regler om cybersäkerhet (NIS2 + CER) (DocRec-id: 13575, HCB318)
- **Prop. 2025/26:28 (HD0328)** — Cybersäkerhetslagen antagen (DocRec-id: 24047) ← i kraft 15 jan 2026
- **Bet. 2025/26:FöU2** — Försvarsutskottets behandling (DocRec-id: 24209, 44 s.)
- **Prop. 2025/26:214 (HD03214)** — Lagändringar för stärkt NCSC; FRA tar CSIRT-rollen (DocRec-id: 24695)
- **SOU 2025:79 (HDB379)** — Samlade förmågor för ökad cybersäkerhet; FRA/MSB-utredning (DocRec-id: 23926)
- **Statskontoret 2025:8** — NIS2-tillsynsmyndigheternas kostnader (DocRec-id: 23710, 90 s.)
- Prop. 2019/20:15 (H70315) — Skydd av Sveriges säkerhet vid radioanvändning
- SOU 2021:87 (H9B387) — Granskning av utländska direktinvesteringar (Huawei-beslutet)
- PTS-ER-2024:12 — Beslut fattade med stöd av LEK år 2023
- EC press corner ip_26_105 (jan 2026) — EU Cybersecurity Package
- **SOU 2025:115 (HDB3115)** — Kompletterande bestämmelser till EU:s cyberresiliensförordning, 646 s. (DocRec-id: 24203) ← PTS systematiska 5G-säkerhetsarbete och CRA-roll, sid. 280, 287
- **SOU 2025:12 (HDB312)** — AI-kommissionens Färdplan för Sverige, 165 s. (DocRec-id: 14167) ← 5G SA-gapet och investeringsparadox, sid. 60
