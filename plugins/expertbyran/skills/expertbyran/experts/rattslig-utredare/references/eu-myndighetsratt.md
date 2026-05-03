# EU-myndighetsrätt — EU:s digitala lagstiftning för statliga myndigheter

> Referensfil för rättslig utredare på Expertbyrån.
> Täcker: EU AI-förordningen, GDPR/FRIA-relation, Data Governance Act,
> Data Act (inkl. OSL-kollisionsanalys), NIS2/cybersäkerhetslagen,
> samt revisionsfrågebanker.

---

## 1. EU AI-förordningen (2024/1689) — deployer-skyldigheter för statliga myndigheter

### 1.1 Tillämpningsomfång och tidpunkt

AI-förordningens krav på deployers av högrisk-AI (bilaga III) gäller fr.o.m. **2 augusti 2026**.

**Myndigheter som deployers:** En statlig myndighet som tar i bruk ett högrisk-AI-system (bilaga III) är *deployer* och har egna skyldigheter gentemot AI-systemets slutanvändare och medborgare — oberoende av om systemet upphandlats externt.

**Bilaga III — högrisk-AI-typer (urval relevant för statliga myndigheter):**
- Punkt 1: Biometrisk identifiering och kategorisering
- Punkt 2: Kritisk infrastruktur (tillsynsmyndighet: PTS)
- Punkt 5: Sysselsättning och hantering av arbetstagare
- Punkt 6: Tillgång till och åtnjutande av väsentliga privata tjänster och offentliga tjänster (inkl. socialtjänst, socialförsäkring, sjukvård, utbildning)
- Punkt 8: Rättsväsende och demokratiska processer

### 1.2 Deployers sex konkreta skyldigheter (art. 26)

| Skyldighet | Innebörd |
|-----------|---------|
| 1. Bruksanvisning (art. 26.1) | Använda AI-systemet i enlighet med leverantörens bruksanvisning |
| 2. Kompetens/AI-kunnighet (art. 26.2) | Säkerställa att personal som arbetar med systemet har tillräcklig AI-kunnighet — *aktiv och kompetensbaserad* mänsklig tillsyn, inte bara formell möjlighet till överpröving |
| 3. Indata (art. 26.3) | Säkerställa att indata som matas in i systemet är relevanta och tillräckligt representativa |
| 4. Övervakning (art. 26.5) | Övervaka systemets drift och rapportera incidenter till leverantören |
| 5. Loggar (art. 26.6) | Behålla loggar under den period det är rimligt och nödvändigt |
| 6. FRIA (art. 27) | Genomföra konsekvensbedömning avseende grundläggande rättigheter (FRIA) — se avsnitt 1.3 |

**Kopplingen till FL 28 §:** AI-förordningens art. 26.2 kräver i kombination med FL 28 § (automatiserade beslut) *aktiv och kompetensbaserad* mänsklig kontroll — inte bara en teoretisk möjlighet till överpröving. En myndighet som delegerar beslutsfattande till ett AI-system utan att personal aktivt kan bedöma systemets output brister i sin FL 28 §-skyldighet.

### 1.3 FRIA — konsekvensbedömning avseende grundläggande rättigheter (art. 27)

**Vem är skyldig:** Offentligrättsliga organ som deployers av högrisk-AI i bilaga III — *undantag* för punkt 2 (kritisk infrastruktur, tillsyn av PTS).

**Sexdelad FRIA-bedömning:**
1. Identifiera de delar av befolkningen som kan påverkas negativt
2. Fastställa kategorier av grundläggande rättigheter som sannolikt kan komma att påverkas
3. Bedöma sannolikheten och svårighetsgraden av negativ påverkan
4. Identifiera och genomföra tekniska och organisatoriska åtgärder
5. Beakta möjligheten att sätta upp mekanismer för klagomål och prövning
6. Ange den myndighet som är ansvarig för FRIA-genomförandet

**Underrättelseskyldighet:** Deployer ska underrätta marknadskontrollmyndigheten (Konsumentverket för flertalet kategorier) efter genomförd FRIA. AI-byrån ska ta fram ett mallfrågeformulär.

**Leverantörens informationsskyldighet (art. 28):** Leverantören ska ge deployer skriftlig information om hur AI-systemet fungerar, vilket underlag FRIA kräver. Riksrevisionen och andra myndigheter bör kontraktuellt säkra att leverantören uppfyller art. 28 — se avsnitt 1.6.

### 1.4 Transparens och mänsklig kontroll (art. 13–14)

- **Art. 13 (transparens):** AI-system ska vara tillräckligt transparenta för att deployers ska kunna tolka utdata och använda dem på lämpligt sätt.
- **Art. 14 (mänsklig kontroll):** System för mänsklig tillsyn ska göra det möjligt att (a) förstå systemets kapaciteter och begränsningar, (b) identifiera situationer av malfunktion, (c) övervaka och ingripa, (d) avbryta eller koppla ur systemet.

### 1.5 RF 1:9 och FL som kompletterande bedömningsgrunder

- **RF 1:9 (objektivitetsprincipen):** AI-algoritmer får bara beakta rättsligt tillåtna faktorer. Proxy-diskriminering — när en korrelerad variabel (t.ex. postnummer) ersätter en otillåten faktor (t.ex. etnicitet) — är ett RF-brott.
- **FL 28 § (automatiserade beslut):** Gäller fullt ut för AI-baserade myndighetsbeslut.
- **FL 32 § (beslutsmotivering):** Gäller fullt ut — beslut baserade på AI-output måste motiveras för den enskilde.
- **RiR 2020:22 (Riksrevisionens granskning av automatiserat beslutsfattande):** Tre bedömningskriterier som fortfarande är relevanta: (a) likabehandling, (b) förutsebarhet, (c) dokumentation. Dessa kompletteras och skärps av art. 26/27 fr.o.m. 2 aug 2026.

### 1.6 LOU-kopplingen vid AI-upphandling

- Art. 26/27 är myndighetens egna skyldigheter — de regleras inte av LOU utan gäller direkt.
- LOU 17 kap. (kontraktsvillkor) + art. 28 styr vad myndigheten bör kräva av leverantören för att kunna uppfylla sina FRIA-skyldigheter.
- **Kommissionens MCC-AI (mars 2025):** Frivilliga standardklausuler (Model Contractual Clauses for AI, uppdaterade mars 2025, Public Buyers Community) — verktyg för att kontraktuellt säkra information från leverantören för FRIA-ändamål.
- **PTS** är tillsynsmyndighet för bilaga III punkt 2 (kritisk infrastruktur). **IMY** och sektorsspecifika myndigheter för övriga kategorier.

---

## 2. AI Act / GDPR — normkonfliktanalys

### 2.1 Grundprincipen

AI Act och GDPR är **parallella och ömsesidigt tillämpbara** instrument — de är *inte* i lex specialis-relation till varandra (EDPB Statement 3/2024; SOU 2025:101 s. 204–205).

**Konsekvens:** En myndighet som deployer av bilaga III högrisk-AI (fr.o.m. 2 aug 2026) behöver *båda*:
- DPIA (GDPR art. 35) om behandling av personuppgifter sker
- FRIA (AI Act art. 27) för grundläggande rättighetsperspektivet

### 2.2 FRIA/DPIA-relation (art. 27.4 AI Act)

Art. 27.4 AI Act (SOU 2025:101 s. 901): FRIA ska "komplettera" DPIA för överlappande krav. DPIA räcker *aldrig* ensam, eftersom:
- DPIA täcker personuppgiftsbehandlingens risker (GDPR art. 35)
- FRIA täcker ett bredare grundrättighetsperspektiv (alla rättigheter i EU-stadgan, inte bara dataskydd)

**Praktisk samordning:** Genomför DPIA → identifiera överlappningar med art. 27.1 → komplettera med FRIA:s bredare rättighetsperspektiv (art. 27.4 medger att DPIA-täckta krav inte upprepas).

### 2.3 IMY:s praxis

IMY:s konkreta vägledning om DPIA/FRIA-gränsen var inte publicerad per april 2026. Detta är en öppen kunskapslucka — kontrollera IMY:s webbplats (imv.se) inför granskning.

---

## 3. Revisionsfrågebank — AI-granskning i 5 nivåer

### Nivå 1: Rättslig grund

- Har myndigheten lagstöd för det AI-baserade beslutsfattandet?
- Uppfyller systemet FL 28 § (automatiserade beslut)?
- Är beslutsmotivering given enligt FL 32 §?

### Nivå 2: Objektivitet och likabehandling

- RF 1:9 (objektivitetsprincipen): beaktar algoritmen bara rättsligt tillåtna faktorer?
- Förekommer proxy-diskriminering (korrelerade men ej tillåtna faktorer)?

### Nivå 3: Mänsklig kontroll

- AI Act art. 26.2 + FL 28 §: är tillsynen *aktiv och kompetensbaserad* (inte bara formell)?
- RiR 2020:22:s tre kriterier: likabehandling, förutsebarhet, dokumentation.

### Nivå 4: EU AI-förordningens krav (fr.o.m. 2 aug 2026)

- Art. 26: sex deployer-skyldigheter uppfyllda?
- Art. 27: FRIA genomförd för högrisk-AI (bilaga III, undantag punkt 2)?
- Art. 28: leverantörens informationslämnande dokumenterat?

### Nivå 5: GDPR-parallellitet

- DPIA (GDPR art. 35) genomförd separat (ersätts inte av FRIA)?
- Art. 27.4 AI Act utnyttjad för att koordinera FRIA och DPIA?

---

## 4. EU Data Governance Act (DGA, 2022/868)

### 4.1 Tillämpningsomfång för statliga myndigheter

DGA reglerar hur offentliga organ hanterar data som de innehar och som är föremål för skydd (personuppgifter, affärshemligheter, statistisk sekretess, immaterialrätt). Gäller fr.o.m. 24 september 2023.

### 4.2 Nyckelbestämmelser

| Artikel | Innehåll |
|---------|---------|
| Art. 3 | Förbud mot exklusiva arrangemang — offentliga organ får inte ge enskild aktör exklusiv rätt till data |
| Art. 4 | Villkor för re-use av skyddade data (jämförbara, transparenta, icke-diskriminerande) |
| Art. 5 | Tekniska genomförandesätt för re-use (säkra databehandlingsmiljöer) |
| Art. 6–7 | Behörigt organ och informationspunkt — varje MS ska utse organ som hjälper offentliga organ att uppfylla re-use-skyldigheterna |
| Art. 10–12 | Neutrala datamedlare — anmälningsplikt; offentliga organ kan inte vara ackrediterade datamedlare |

**Svensk komplettering:** Lag 2024:500 (i kraft september 2024).
**Tillsynsmyndighet:** PTS är tillsynsmyndighet för dataförmedlingstjänster (art. 10–12).

---

## 5. EU Data Act (DA, 2023/2854) — inkl. OSL-kollisionsanalys

### 5.1 Tillämpning

Data Act tillämpas fr.o.m. 12 september 2025. Reglerar rätt till data från uppkopplade produkter och rätten för offentliga organ att kräva data vid exceptionellt behov.

### 5.2 Myndigheters rätt till data från uppkopplade produkter (art. 3–6)

Myndigheter som *använder* uppkopplade produkter (IoT-enheter, sensorer, fordon) i sin verksamhet har rätt till den data produkten genererar — i realtid och historisk data. Rättslig grund: art. 3–4.

### 5.3 Offentliga organs rätt att kräva data vid exceptionellt behov (art. 14–22)

**Tillämpningssituationer (art. 14):**
- Exceptionellt behov: nödläge som hotar hälsa, säkerhet eller miljö (art. 15.1 a)
- Uppgiftshinder: offentligt organ kan inte skaffa data på annat sätt (art. 15.1 b)

**Begärans form:** Skriftlig och specificerad. Datahållaren kan invända av proportionalitetsskäl (art. 16).

**Viktiga begränsningar:**
- Art. 16 utesluter brottsbekämpning, tull och skatt från art. 14-mekanismen.
- Art. 14 gäller *operativa myndigheter* med uppgiftsplikter — inte Riksrevisionen som granskare. **Kritisk iakttagelse: DA art. 14 ger INTE Riksrevisionen revisionsrätt mot privata bolag** — detta är ett metodologiskt misstag att undvika i granskningsdesign.
- Skärningspunkten DA art. 17 och FL:s proportionalitetskrav: DA-begäran ska vara proportionerlig, tolkas i enlighet med FL 5 § 3 st.

**Nationell komplettering:** SOU 2025:118 ("Ökad och rättvis tillgång till data") är central källa; implementeringsproposition saknas per april 2026. PTS är utsedd behörig myndighet (okt 2025).

### 5.4 DA art. 14 × OSL-sekretess — konstitutionell kollisionsanalys

**Principproblemet (TF 2:2):**
Begränsning av offentlighetsprincipen kräver stöd i OSL eller lag OSL hänvisar till — även när begränsningen har sitt ursprung i en EU-rättsakt.

Data Act art. 19:s konfidentialitetskrav kan *inte* i sig läggas till grund för att begränsa den grundlagsstadgade rätten till insyn:

> *"Dataförordningens krav på konfidentialitet kan därför inte läggas till grund för att begränsa den grundlagsstadgade rätten till insyn i offentlig verksamhet."*
> — SOU 2025:118 s. 257

**SOU 2025:118:s slutsats:**
1. Inga nya OSL-bestämmelser behövs för data som inhämtas med stöd av art. 14–15.
2. Befintlig OSL-sekretess är tillräcklig hos mottagande offentliga organ.
3. Tillämpliga bestämmelser: 30 kap. 23 § (affärshemligheter), 30 kap. 24 §, 15 kap. 1 a § (sekretesslofte), 10 kap. 2/27/28 §§ OSL (generalklausul).

**Normkonfliktresolution vid konkret fall:**
```
K1: Verklig konflikt? → JA om data är offentlig handling och art. 19 kräver sekretess
K2: TF > EU-förordning vid grundrättighetsinskränkning → kräver OSL-stöd
K3: Finns tillämplig OSL-bestämmelse? → Vanligen JA (se 30 kap. 23 §)
K4: Skaderekvisit uppfyllt? → Presumtion för offentlighet i de flesta bestämmelser
K5: Om OSL-stöd saknas → DA art. 19 kan inte ensamt begränsa TF-rätten
```

**Praktisk regel:** En myndighet som nekar utlämnande med enbart DA-hänvisning utan OSL-stöd bryter mot TF 2:2.

**Begreppsavgränsning — DA art. 14 vs GDPR art. 14:**
Dessa är helt olika instrument. DA art. 14 = offentliga organs rätt att kräva data. GDPR art. 14 = informationsskyldighet vid insamling från tredje man. Felaktig identifiering förekommer i SOU-material.

---

## 6. NIS2-direktivet (2022/2555) och cybersäkerhetslagen (prop. 2025/26:28)

### 6.1 Vilka statliga myndigheter som omfattas

Cybersäkerhetslagen (i kraft 15 januari 2026) gäller för:
1. Statliga myndigheter med befogenhet att fatta beslut om gränsöverskridande rörlighet (Migrationsverket, Polisen m.fl.), PLUS
2. Myndigheter som regeringen bestämmer (beredskapsmyndigheter).

**Riksrevisionen undantas** som myndighet under riksdagen — viktig mandatiakttagelse för granskningsfrågor om vilka aktörer som kan rekommenderas.

### 6.2 Tio säkerhetsåtgärdskategorier (NIS2 art. 21)

| # | Kategori |
|---|---------|
| 1 | Riskanalys och informationssäkerhetspolicy |
| 2 | Incidenthantering |
| 3 | Kontinuitet (backup, katastrofhantering, krishantering) |
| 4 | Leveranskedjesäkerhet |
| 5 | Nätverks- och informationssystemsäkerhet |
| 6 | Effektivitetsutvärdering av cybersäkerhetsåtgärder |
| 7 | Cyberhygien och cybersäkerhetsutbildning |
| 8 | Kryptografi och kryptering |
| 9 | Personalsäkerhet, åtkomstkontroll och tillgångsförvaltning |
| 10 | Autentisering och auktorisering |

### 6.3 Ledningsutbildningskrav

Ledningsorgan (styrelse/generaldirektör) ska genomgå utbildning om cybersäkerhetsrisker och riskhanteringsåtgärder (prop. 2025/26:28, § 6.5).

### 6.4 Trestegig incidentrapportering

| Steg | Tidsgräns | Innehåll |
|------|-----------|---------|
| Upplysning | 24 timmar | Tidig varning om misstänkt incident |
| Anmälan | 72 timmar | Incidentanmälan med preliminär bedömning |
| Slutrapport | 1 månad | Fullständig rapport med åtgärdsbeskrivning |

### 6.5 Sanktioner

Inkluderar: böter, förelägganden, förbud mot ledningsfunktion (kan träffa generaldirektörer och styrelseledamöter personligen).

### 6.6 Tre granskningsobjekt ur riksrevisionsperspektiv

NIS2/cybersäkerhetslagen ger upphov till tre distinkta granskningsobjekt — Riksrevisionen väljer nivå beroende på syfte:

| Granskningsobjekt | Beskrivning | Bedömningsgrund | Rekommendationsmottagare |
|-------------------|-------------|-----------------|--------------------------|
| **1. Verksamhetsutövare** | Uppfyller de berörda myndigheterna och organisationerna de tio säkerhetsåtgärdskategorierna (NIS2 art. 21)? Har de ledningsutbildning? Rapporterar de incidenter i tid? | Cybersäkerhetslagen + NIS2 art. 21 + förordningens krav på respektive sektor | Berörda myndigheter/verksamhetsutövare |
| **2. Tillsynsmyndigheter** | Utövar de sektoriella tillsynsmyndigheterna tillsyn i enlighet med sina befogenheter? Är tillsynen riskbaserad och proportionerlig? | Cybersäkerhetslagen + respektive sektorslag + tillsynsmyndighetens instruktion | Respektive tillsynsmyndighet och/eller regeringen |
| **3. Regeringsstyrning** | Har regeringen inrättat en sammanhängande och effektiv tillsynsstruktur? Koordineras de sektoriella tillsynsmyndigheterna? Är NIS2:s nationella strategi genomförd? | NIS2 art. 7 (nationell strategi), art. 8 (behöriga myndigheter), art. 14 (nationell ram) | Regeringen (Finansdepartementet/DIGG) |

**Riksrevisionen undantas** som myndighet under riksdagen — Riksrevisionen är inte verksamhetsutövare i NIS2:s mening och kan alltså granska utan att vara granskningsobjekt.

### 6.7 Sektoriella tillsynsmyndigheter under cybersäkerhetslagen

| Sektor | Tillsynsmyndighet | Anmärkning |
|--------|-------------------|------------|
| Elektronisk kommunikation / digital infrastruktur | PTS (Post- och telestyrelsen) | Primär NIS2-tillsynsmyndighet |
| Energi (el, gas, fjärrvärme) | Energimarknadsinspektionen (Ei) | |
| Transport (väg, järnväg, luftfart, sjöfart) | Transportstyrelsen | |
| Hälso- och sjukvård | IVO (Inspektionen för vård och omsorg) | |
| Bank och finansmarknadsinfrastruktur | Finansinspektionen (FI) | |
| Digitala tjänster (molntjänster, sökmotorer, plattformar) | PTS | Sektorsövergripande digitala tjänster |
| Dricksvatten | Livsmedelsverket + kommunal tillsyn | Delad tillsyn |
| Avloppsvatten | Naturvårdsverket + kommunal tillsyn | Delad tillsyn |
| Rymden | Rymdstyrelsen (SNSA) | |
| Offentlig förvaltning | MSB / DIGG (samordning) | Statliga myndigheter under regeringen |
| Post | PTS | |
| Produktion och distribution av livsmedel | Livsmedelsverket | |

**Övergripande koordinering:** NCSC (Nationellt cybersäkerhetscenter) — tvärfunktionellt organ med SÄPO, FRA, FMV, MSB. Uppgift: operativ koordinering av cyberhot och vägledning till tillsynsmyndigheter.

**Portalövergång 2026:** MCF (Myndigheten för cybersäkerhet och integritetsskydd, fd MSB:s del) övergår till FRA-led NCSC-struktur under 2026. Konsekvens för incidentrapporteringskedjan är ett aktivt osäkerhetsmoment vid granskningar under 2026.

### 6.8 Sanktionssystem

| Typ av åtgärd | Tillämpning |
|---------------|-------------|
| Böter (viktiga entiteter) | Upp till 10 MEUR eller 2 % av global omsättning (det högsta beloppet) |
| Böter (viktiga tjänster — lägre kategori) | Upp till 7 MEUR eller 1,4 % av global omsättning |
| Föreläggande | Kräva att specifika åtgärder vidtas; kan kombineras med löpande vite |
| Förbud att utöva ledningsfunktion | Personligt ansvar för GD/VD/styrelseledamöter — kan riktas individuellt |
| Offentliggörande | Tillsynsmyndigheten kan offentliggöra identitet på överträdare (NIS2 art. 32.4 g) |

**Mandatanalys:** Riksrevisionen kan granska *om* tillsynsmyndigheterna använder sina sanktionsbefogenheter — men kan inte rekommendera ett specifikt sanktionsbeslut. Rekommendationen riktas mot tillsynsmyndigheten om sanktionsbefogenheterna underutnyttjas strukturellt.

### 6.9 Parallell tillämpning med AI-förordningen

Myndigheter i känsliga sektorer (t.ex. energi, transport, hälsa) som också deployar bilaga III högrisk-AI-system kan stå under *dubbelt tryck*: cybersäkerhetslagens krav + AI-förordningens deployer-skyldigheter. Revisionsfrågebanken (avsnitt 3) och cybersäkerhetsanalys bör genomföras parallellt.

---

*Källor: EU AI-förordningen 2024/1689 (art. 13, 14, 26, 27, 28, bilaga III); SOU 2025:101 s. 204–205, 493, 523, 721–724, 855, 901; Prop. 2025/26:150; Ds 2025:7 s. 253; EDPB Statement 3/2024; EU MCC-AI (mars 2025, Public Buyers Community); EU Data Governance Act 2022/868; Lag 2024:500; EU Data Act 2023/2854; SOU 2025:118 s. 257, 273–274; TF 2:2; OSL 30:23, 30:24, 15:1a, 10:2/27/28; NIS2-direktivet 2022/2555; Prop. 2025/26:28; SOU 2024:18; SOU 2024:64; RiR 2020:22; RF 1:9; FL 28 §, 32 §.*
