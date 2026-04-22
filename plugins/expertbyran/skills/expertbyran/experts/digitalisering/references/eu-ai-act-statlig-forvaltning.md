# EU AI Act och NIS2 — statlig förvaltning

*Senast uppdaterad: 2026-04-22*

---

## EU AI Act (Förordning 2024/1689) — struktur och tillämpning i staten

### Tillämpningsområde för myndigheter

Myndigheter är vanligen **operatörer/driftsansvariga (deployers)**, inte leverantörer — dvs. de köper eller beställer AI-system snarare än utvecklar dem. Operatörsskyldigheter regleras i Art. 26.

**Undantag:** AI-system för nationell säkerhet (militär, underrättelse) faller utanför AI Act.

### Art. 5 — Förbjudna AI-system (gäller från 2 februari 2025, inga undantag)

Alla förbud gäller omedelbart från 2 feb 2025 utan övergångstid.

| Artikel | Förbud | Undantag/kommentar |
|---------|--------|-------------------|
| 5.1(a) | Subliminal manipulation av beteende mot personens intressen | Inget |
| 5.1(b) | Utnyttjande av sårbarhet (ålder, funktionsnedsättning) | Inget |
| 5.1(c) | Social scoring av enskilda eller grupper (allmän bedömning av trovärdighet/beteende) | Relevant för FK/Arbetsförmedlingens riskprofiler — ingen EU-praxis ännu men möjlig gränsdragning |
| 5.1(d) | Prediktiv brottsriskbedömning *uteslutande* baserat på profilering/personlighetsdrag | Undantag: bedömning kopplad till *objektiva fakta* om konkret brottslig verksamhet |
| 5.1(e) | Skapande/utvidgning av ansiktsigenkänningsdatabaser via oriktad skrapning | Inget |
| 5.1(f) | Emotionsigenkänning på arbetsplatsen eller i utbildning | Undantag: medicinska/säkerhetsskäl |
| 5.1(g) | Biometrisk kategorisering för att härleda ras, politiska åsikter, fackmedlemskap, religion, sexualliv/läggning | Undantag: laglig märkning i brottsbekämpning |
| 5.1(h) | Realtids biometrisk fjärridentifiering (RTBID) på allmänt tillgängliga platser för brottsbekämpning | Tre snäva undantag: sökning efter saknade/offer; förhindra överhängande hot mot liv; lokalisering av gärningspersoner vid allvarliga brott |

**Art. 5.1(h) nationell implementering:** Kräver nationell tillståndslagstiftning. Prop. 2025/26:150 antagen för Polismyndigheten och SÄPO. Tillstånd av åklagare/domstol krävs; undantag för brådskande fall. Beslut med negativa rättsliga följder får inte fattas enbart på AI-utdata (Art. 5.3 direkt tillämplig).

### Bilaga III — Högrisk-AI-system (urval)

Högrisk-klassificering innebär krav per Art. 9–15 och Art. 26. Befintliga system: deadline 2 aug 2030 (men *varje betydande förändring* utlöser omedelbar complianceskyldighet).

| Kategori | Relevans i svensk stat |
|---|---|
| III.1 Biometri | Ansiktsigenkänning, fingeravtryck, retrospektiv biometri vid Polisen, NFC |
| III.2 Kritisk infrastruktur | Trafikledning, energinät |
| III.3 Utbildning | Urvalssystem, tentamensövervakning |
| III.5 Väsentliga tjänster | Försäkringskassans bidragsbeslut, kreditbedömning |
| III.6 Brottsbekämpning | Riskbedömning, Skatteverkets urvalssystem |
| III.7 Migration/gräns | Migrationsverkets ärendehandläggning, lögndetektorer, riskbedömning |
| III.8 Rättskipning | Domstolsstöd, bevisvärdering |

**Viktigt undantag III.1:** Biometrisk *verifiering/autentisering* (bekräfta att personen är den de utger sig för att vara) är INTE högrisk. Gäller BankID, e-legitimationsläsning, SITHS. Distinktionen:
- Biometrisk *identifiering* = söka i databas utan aktiv medverkan → högrisk
- Biometrisk *verifiering* = bekräfta identitet med aktiv medverkan → inte högrisk

### Art. 9–15 — Krav på högrisk-system

| Artikel | Krav | Praktisk kärna |
|---|---|---|
| Art. 9 | Riskhanteringssystem | Kontinuerlig, iterativ process under hela systemlivscykeln |
| Art. 10 | Data och datastyrning | Tränings-/testdata: relevant, representativ, fri från systematisk bias |
| Art. 11 | Teknisk dokumentation (Bilaga IV) | Upprättas *innan* driftssättning; hålls aktuell; 9 obligatoriska element |
| Art. 12 | Loggning och spårbarhet | Automatisk händelseloggning under hela driftsperioden |
| Art. 13 | Transparens | Operatören ska kunna tolka utdata; slutanvändare informeras |
| Art. 14 | Mänsklig översyn | Möjlighet att pausa, stoppa, åsidosätta beslut |
| Art. 15 | Tillförlitlighet och robusthet | Adekvat noggrannhet; motståndskraft mot fel och cyberhot |

**Bilaga IV — Teknisk dokumentation (9 obligatoriska element):**
1. Allmän beskrivning (syfte, version, API-format, maskinvarukrav)
2. Utvecklingsbeskrivning (algoritmlogik, arkitektur, tränings- och testdata, cybersäkerhet, Art. 14-bedömning)
3. Drift- och kontrolluppgifter (prestandabegränsningar, riskanalys, indatakvalitet)
4. Prestandamätvärden (noggrannhet, robusthet, icke-diskriminering)
5. Datablad för träningsdata
6. EU-förklaring om överensstämmelse
7. Mänsklig kontroll: åtgärder och gränssnitt
8. Cybersäkerhet och dataintegritet
9. Efterlevnadsplan efter utsläppande (Art. 72)

### Art. 26 — Operatörsskyldigheter (för driftsansvariga myndigheter)

- Säkerställa att systemet används i enlighet med leverantörens instruktioner.
- Utse ansvarig person (intern).
- Genomföra grundläggande rättighetskonsekvensanalys (Art. 27) *innan* driftssättning av III.5–8-system inom offentlig förvaltning.
- Bevaka och rapportera fel och allvarliga incidenter (Art. 73).
- Utöva mänsklig kontroll (Art. 14).

### Art. 27 — FRIA (Grundrättighetskonsekvensbedömning)

Obligatorisk för offentliga myndigheter som driftsätter högrisk-system i Bilaga III kategori 5–8.

De 6 obligatoriska momenten (a–f):
1. Processbeskrivning (besluts- och implementeringsprocessen)
2. Tidsperiod för systemets användning
3. Berörda grupper och individer
4. Konkreta risker för grundläggande rättigheter
5. Mänsklig kontroll: åtgärder och ansvarig
6. Klagomålsmekanismer och rättsmedel

**Viktigt:** SOU 2025:101 föreslår ingen sanktionsavgift för Art. 27-brott — svag incitamentsstruktur. DIGG:s vägledning (jan 2025) saknar FRIA-mall, notifieringsvägledning (Art. 27.3) och klassificeringshjälp (Bilaga III). Formulerat som möjlig granskningsfråga för Riksrevisionen.

### Art. 113 — Implementeringstidslinje

Källa: SOU 2025:101 Bilaga 2 (s. 729, 952, 954); Ds 2025:7 Bilaga (s. 307); Ds 2025:32 s. 22; SOU 2025:12 s. 91.

| Datum | Vad gäller |
|-------|-----------|
| 1 aug 2024 | AI Act trädde i kraft |
| 2 feb 2025 | Art. 5-förbud gäller (utan övergångstid) |
| 2 aug 2025 | GPAI-modellkrav (Art. 51–56); Art. 4 kompetenskrav |
| 2 aug 2026 | Högrisk-krav Art. 6.1 (Bilaga I-system); notifieringsorgan och marknadskontroll |
| 2 aug 2030 | Högrisk-krav Art. 6.2 (Bilaga III) för befintliga system (de som redan var i bruk) |

**Viktigt:** "Befintliga system" skyddas av övergångstiden till 2030 — men varje *betydande förändring* utlöser omedelbar complianceskyldighet.

**EU Digital Omnibus (2026):** Förslag att skjuta högrisk-deadline för befintliga privata system till 2 dec 2027. Offentliga myndigheter bör följa SOU 2025:101 och Prop. 2025/26:150 för att se om ändringen också träffar dem.

### Nationella genomföranden

| Dokument | Typ | År | Innehåll |
|----------|-----|----|---------|
| Prop. 2025/26:150 | Proposition | 2026 | AI Act — kompletterande lagstiftning (nationell); RTBID-tillstånd för Polisen |
| SOU 2025:101 | SOU | 2025 | Nationella AI Act-anpassningar: marknadskontrollmyndigheter per Bilaga III, tillsynsmodell, FRIA |
| Ds 2025:7 (HDB47) | Ds | 2025 | Polisens realtids ansiktsigenkänning — underlag till Prop. 2025/26:150 |
| Ds 2025:32 (HDB432) | Ds | 2025 | Retrospektiv biometri: Polis, SÄPO, Tullverk; Art. 26.10; ikraft 1 jan 2027 |
| Prop. 2024/25:37 | Proposition | 2024 | NFC-biometri mot Migrationsverkets register; biometri i brottsbekämpning |
| SOU 2024:80 | SOU | 2024 | Migrationsverket, EU biometriska informationssystem (Eurodac, SIS, VIS) |
| Ds 2024:11 | Ds | 2024 | Kamerabevakning och AI Act Bilaga III/Art. 5 i sin helhet |
| SOU 2025:46 | SOU | 2025 | Idrottsarrangemang; god genomgång av Art. 5 RTBID-förbud |

### Marknadskontrollmyndigheter

Källa: SOU 2025:101.

- **Bilaga III.1 (biometri), III.6, III.7, III.8:** Sammanhållet tillsynsansvar (s. 225).
- **Art. 5-förbud:** Tillsynsmyndigheter per kategori (s. 286–297).
- **Ds 2025:32 s. 58:** IMY utses till marknadskontrollmyndighet för Bilaga III.1 (biometri).
- **PTS (f.d.):** Notera att DIGG + PTS slås ihop till ny myndighet 1 jan 2027 (MKM-rollen förändras).

### Myndigheters AI Act-exponering — sammanfattning

| Myndighet | Primär exponering | Rättslig grund |
|-----------|------------------|----------------|
| Polismyndigheten | RTBID (Art. 5.1h + undantag), retrospektiv biometri (Art. 26.10), NFC-jämförelser (Bilaga III.1) | Prop. 2025/26:150; Ds 2025:32; Prop. 2024/25:37 |
| Säkerhetspolisen | Begränsat: nationell säkerhet faller utanför AI Act; viss brottsbekämpning inom ramen | Ds 2025:32 s. 39–40 |
| Tullverket | Retrospektiv biometri-AI i tullutredningar (Bilaga III.1) | Ds 2025:32 s. 38 |
| Migrationsverket | Biometriska register (söks av Polisen); fingeravtryck/foto-registrering; asylprövning (Bilaga III.7) | Prop. 2024/25:37; SOU 2024:80 |
| Försäkringskassan | Bidragsbeslut (Bilaga III.5); riskprofiler (möjlig Art. 5.1c-gränsdragning) | Se ISF 2026:1; Art. 26 och Art. 27 FRIA |
| Skatteverket | Urvalssystem (Bilaga III.6 brottsbekämpning) | RIR 2020:22; ISF 2026:1 |
| IMY | Marknadskontrollmyndighet Bilaga III.1; nationell dataskyddsmyndighet | Ds 2025:32 s. 58; SOU 2025:101 |
| Domstolsverket | Tillståndsprövning för RTBID och retrospektiv biometri | Ds 2025:32 s. 44; Prop. 2025/26:150 |

---

## AI-styrning i offentlig sektor 2025–2026

### Faktisk AI-användning i statliga myndigheter

Källa: RIR 2020:22, Statskontoret 2024, ESO 2025:2, SOU 2025:96.

- Mest AI i intern administration; riskfyllda satsningar mot enskilda fortfarande begränsade.
- Skatteverket: 20–45% effektiviseringspotential (ESO 2025:2).
- FK: ISF 2026:1 fastslår att FK saknar tillräckligt lagstöd för att använda AI i *komplexa bedömningsärenden*.
- Budgetprop. 2026 UO 22: 25 myndigheters AI-redovisningar visar att flertalet är i tidigt skede.

### Nationell AI-strategi och styrning

- **Sverige sjunker i Global AI Index:** plats 25 (2024) vs 17 (2023) — sämst på politisk styrning.
- **Sveriges AI-strategi (feb 2026):** mål i topp 10 globalt; AI-verkstad under SKV/FK (SOU 2025:12).
- **DIGG + PTS-sammanslagning 1 jan 2027:** ny myndighet tar över. MKM-rollen för AI Act förändras. Aktiv osäkerhet om ansvar under övergången.
- **DIGG + IMY riktlinjer generativ AI:** publicerade jan 2025 — rekommendationer men ingen bindande norm.

### GDPR × AI Act — skärningspunkter

- Art. 22 GDPR: rätt att inte bli föremål för *uteslutande* automatiserat beslut med rättsverkan. Relevant för FK och Arbetsförmedlingens riskmodeller.
- **SyRI-domen (ECLI:NL:RBDHA:2020:1878):** Nederländsk domstol stoppade holländsk myndighets riskprofileringssystem som kringgick Art. 22. Proportionalitetsbedömning central — systemet hittade noll fall men utredde tusentals. Referensdom för granskningsarbete.
- **IMY:s FK-VAB-beslut (nov 2025):** IMY beslutade att Försäkringskassans AI-urvalssystem för VAB-ärenden bröt mot GDPR. Art. 22-frågan för sjukpenningbeslut är fortfarande öppen — bekräftat av IMY:s ärendehantering.

---

## NIS2 och cybersäkerhetslagen

### Direktiv (EU) 2022/2555 — NIS2

Offentlig förvaltning är Bilaga I-entiteter (väsentliga). MSB är nationell kontaktpunkt och CSIRT.

**Art. 18 — 10 obligatoriska säkerhetsåtgärder:**
1. Riskanalys och informationssystemets säkerhetspolicyer
2. Incidenthantering
3. Driftskontinuitet (backup, katastrofåterställning, krishantering)
4. Säkerhet i leveranskedjan
5. Säkerhet i nätverks- och informationssystem (incl. sårbarhetsbedömning)
6. Procedurer för att bedöma effektiviteten av cybersäkerhetsåtgärder
7. Grundläggande cyberhygien och utbildning
8. Kryptografi och kryptering
9. Personalsäkerhet, åtkomstkontroll
10. Multifaktorautentisering och kontinuerlig autentisering

**Art. 20 — Ledningens ansvar:** Ledningsorgan ansvarar personligen; ska delta i utbildning. Sverige valde att INTE reglera godkännandefunktionen explicit.

**Art. 21 — Incidentrapportering:**
- 24 h: tidig varning till CSIRT/behörig myndighet
- 72 h: incidentanmälan med initial bedömning
- 1 månad: slutrapport

**Tillsynsmodell NIS2:** 11 sektormyndigheter + MSB (kontaktpunkt/CSIRT). Jämförelse med AI Act: bägge multi-myndighet. Överlapp i IMY (dataskydd) och MSB (cybersäkerhet) kräver samordning.

**DORA (EU 2022/2554):** Lex specialis för finanssektorn, gäller från jan 2025. FI tillsynar. Finansentiteter undantas från NIS2.

### Svenska genomföranden NIS2

| Dokument | Typ | År | Innehåll |
|----------|-----|----|---------|
| Prop. 2025/26:28 | Proposition | 2025 | Cybersäkerhetslagen — NIS2-implementering |
| SOU 2024:18 | SOU | 2024 | NIS2-utredning |
| SOU 2025:79 | SOU | 2025 | FRA/NCSC-omstrukturering |
| Statskontoret 2025:8 | Rapport | 2025 | Tillsynskostnader NIS2 |
