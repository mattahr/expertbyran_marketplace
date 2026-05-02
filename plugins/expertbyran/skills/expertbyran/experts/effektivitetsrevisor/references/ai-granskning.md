# AI som granskningsobjekt i statsförvaltningen

Denna referensfil stöder granskning av statliga myndigheters användning av AI-system. Använd den när granskningsobjektet fattar eller bereder beslut med stöd av AI, eller när granskningen avser styrningen av AI-användning i en sektor.

---

## EU AI Act — fasad implementering

EU AI Act trädde i kraft 1 augusti 2024 med fasad implementering:
- **Feb 2025**: Förbud mot oacceptabel risk (manipulation, social scoring, realtids-biometri i offentliga miljöer)
- **Aug 2025**: Krav på AI-kompetens hos organisationer
- **Aug 2026**: Högrisk-AI-krav (Bilaga III) träder in fullt
- **Aug 2030**: Fullt genomförande av alla krav

### Högrisk-AI-kategorier (Bilaga III) — relevanta för statsförvaltningen

Dessa kategorier är primära granskningsobjekt i offentlig sektor:
- **Sociala förmåner och tjänster** — beslutsstöd vid bidragsbedömning (FK, socialtjänst, Migrationsverket)
- **Brottsbekämpning** — riskbedömning, brottsförutsägelse, ansiktsigenkänning
- **Migration och asyl** — automatiserad riskklassificering
- **Rättsskipning** — beslutsstöd i domstolar

### DPIA och FRIA-krav

Myndigheter som deployar högrisk-AI-system ska genomföra:
- **DPIA** (Data Protection Impact Assessment) — GDPR art. 35
- **FRIA** (Fundamental Rights Impact Assessment) — EU AI Act art. 27

**Granskningsfråga:** Har myndigheten genomfört DPIA/FRIA och är dokumentationen tillräcklig?

---

## GDPR — Informationsskyldighet vid AI-beslut

**Art. 13–14:** Myndigheter är skyldiga att informera den registrerade om att automatiserat beslutsfattande används, den bakomliggande logiken och tänkbara konsekvenser.

**Art. 22:** Rätt att inte vara föremål för enbart automatiserat beslutsfattande vid beslut med rättsverkan — mänsklig granskning måste finnas.

**Granskningsfråga:** Uppfyller myndigheten informationsskyldigheten transparent och i förväg (inte bara på begäran)?

---

## GAO AI Accountability Framework

GAO USA har formulerat ett ramverk med fyra principer som är direkt tillämpbart som bedömningsgrunder vid granskning av AI-system i svensk statsförvaltning (i avsaknad av en etablerad svensk/nordisk standard):

| Princip | Innehåll | Granskningsfrågor |
|---|---|---|
| **Governance** | Styrning, ansvar, etik, policyer | Finns en AI-policy? Vem ansvarar? Hur hanteras incidenter? |
| **Data** | Datakvalitet, bias, dokumentation | Är träningsdata representativ? Har bias-analys gjorts? |
| **Performance** | Noggrannhet, validering, felfrekvens | Hur valideras systemet? Vilka feltoleranser accepteras? |
| **Monitoring** | Löpande övervakning, uppdatering | Hur detekteras driftsavvikelser? Finns återkopplingsmekanismer? |

**Källa:** GAO (2021). *Artificial Intelligence: An Accountability Framework for Federal Agencies.* GAO-21-519SP.

---

## INTOSAI WGITA — AI-revision och vägledning

INTOSAI:s arbetsgrupp för IT-revision (WGITA) har AI-revision som prioriterat tema 2026–2028. Kommande vägledning (ej publicerad per 2025) väntas komplettera befintligt material:

- **GUID 5101** — Cybersäkerhetsgranskning (primärkälla för IT-säkerhetsaspekter)
- **WGITA 2023 Guidance** — Audit of AI (preliminär, cirkulerad till SAI-nätverket)

**INTOSAI Moscow Declaration (INCOSAI XXIII, 2025):** Formell uppmaning till SAI:er att använda AI och dataanalys, kombinerat med etikkrav.

---

## Etiska risker vid AI-system — tre primära

### 1. Svarta lådan (black box)
AI-systemets beslutsprocess är ogenomskinlig — det går inte att förklara varför ett specifikt beslut fattades. Relevant vid granskningsobjekt som FK, Migrationsverket, Kronofogden.

**Bedömningsgrund:** Kan myndigheten dokumentera och förklara varje enskilt AI-stött beslut på ett sätt som möjliggör rättslig prövning?

### 2. Algoritmisk bias
Systematisk snedvridning i träningsdata kan leda till att systemet diskriminerar skyddade grupper. Risken är störst vid historisk data som speglar tidigare orättvisor.

**Bedömningsgrund:** Har myndigheten genomfört bias-analys och kan den påvisa att systemet behandlar likartade fall lika?

### 3. Ansvarsgap
Oklart vem som bär ansvar när AI-systemet fattar felaktiga beslut — leverantören, it-avdelningen eller handläggaren?

**Bedömningsgrund:** Finns ett tydligt ansvarsramverk som täcker hela AI-systemets livscykel, inklusive när systemet är upphandlat från en extern leverantör?

---

## ISSAI 3000 §136 — Professionell skepticism är icke-delegerbar

> Revisorns professionella omdöme kan inte överlåtas till ett algoritmsystem. AI-verktyget kan flagga avvikelser och stödja urval, men det kritiska revisionella omdömet — om vad avvikelsen betyder och om den är väsentlig — är revisorns.

**Praktisk implikation:** Granskningsobjektet kan använda AI för att *bereda* beslut men inte för att *fatta* dem utan mänsklig verifiering vid individuella ärenden med rättsverkan.

---

## Continuous Auditing / Audit 4.0

Continuous auditing innebär realtids-elektroniskt stödsystem för automatisk normkontroll av en organisations transaktioner och processer. Teknisk arkitektur i fem lager:

1. Datapipelines (automatisk insamling)
2. ML-avvikelsedetektering (anomaly detection)
3. Varningssystem (alerts till revisor)
4. Dashboards (visualisering av mönster)
5. Mänsklig verifiering (revisorns omdöme)

**Status vid svenska SAI:er (2025):** Riksrevisionens effektivitetsrevision är inte AI-systematiserad per FiU-betänkande 2025. NAO (UK) och Helleniska revisionsrätten är bland de mer avancerade i EU-kontexten.

**Granskningsfråga:** Om ett granskningsobjekt påstår sig använda continuous auditing internt — stämmer de fem lagren, och finns mänsklig verifiering i steg 5?
