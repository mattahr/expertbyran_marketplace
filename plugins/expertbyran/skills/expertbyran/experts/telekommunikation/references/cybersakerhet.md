# Cybersäkerhet i Telekominfrastruktur

Senast uppdaterad: 2026-04-29

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

### NIS2 vs LEK 8 kap. (överlapp och resolution)

- **LEK 8:1–4 (ersatt):** Krävde "ändamålsenliga och proportionella tekniska och organisatoriska åtgärder" — fokus på *nätets driftsäkerhet* och incidentrapportering till PTS.
- **NIS2/Cybersäkerhetslagen:** Bredare scope — supply chain, kryptering, ledningsansvar, utbildning som explicita krav. Incidentrapportering skärps.
- **Resultat (Prop. HD0328):** LEK 8:1–4 upphävs och ersätts av cybersäkerhetslagen — en hänvisning kvarstår i LEK för tydlighet.

### Tillsynsstruktur under NIS2

- PTS kvarstår som tillsynsmyndighet för digital infrastruktur och digitala tjänster
- Antalet tillsynsmyndigheter utökas från 7 till 11 (fem länsstyrelser + Läkemedelsverket tillkommer)
- MSB kvarstår som nationell kontaktpunkt och CSIRT-enhet
- MSB + PTS fick sep 2025 uppdrag att förbereda föreskriftsarbetet

---

## 5G-säkerhet och Leverantörsbedömning

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

PTS är tillsynsmyndighet för telekomoperatörernas efterlevnad av leverantörsbedömning (5G-säkerhetslagen, cybersäkerhetslagen). CSA2 + CRA adderar ytterligare lager; koordinering med MSB, SÄPO, FM behövs. NCSC-utredning om effektiv organisering beredd i Regeringskansliet (svar inkom vår 2024).

---

## Nyckelkällor

- SOU 2024:18 — Nya regler om cybersäkerhet (NIS2 + CER) (DocRec-id: 13575, HCB318)
- Prop. HD0328 — Ett starkt skydd för nätverks- och informationssystem (DocRec-id: 24047)
- Prop. 2019/20:15 (H70315) — Skydd av Sveriges säkerhet vid radioanvändning
- SOU 2021:87 (H9B387) — Granskning av utländska direktinvesteringar (Huawei-beslutet)
- PTS-ER-2024:12 — Beslut fattade med stöd av LEK år 2023
- EC press corner ip_26_105 (jan 2026) — EU Cybersecurity Package
- Prop. 2024/25:1 Utg.omr. 22 (DocRec id 13979), sid. 108–109
