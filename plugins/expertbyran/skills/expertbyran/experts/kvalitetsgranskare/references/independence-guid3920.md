# Independence assurance och QA per revisionsprocessfas

## INTOSAI-P 10 — de åtta pelarna för SAI-oberoende

INTOSAI-P 10 (Mexico Declaration on SAI Independence) specificerar åtta
oberoendepelare som utgör minimistandarden:

| Pelare | Krav |
|--------|------|
| 1 | Konstitutionell/lagstadgad förankring av SAI-oberoendet |
| 2 | Oberoende mandat med bred granskningsrätt |
| 3 | Obegränsad tillgång till information |
| 4 | Rätt och skyldighet att rapportera till parlament/allmänhet |
| 5 | Frihet att besluta om granskningsinnehåll och rapporttidpunkt |
| 6 | Finansiell och administrativ autonomi |
| 7 | Ledarutnämning och avsättning reglerad med rättssäkerhetsgarantier |
| 8 | Oberoende revision av SAI:s egna räkenskaper |

Vid independence assurance-bedömning: gå igenom pelarna systematiskt och
bedöm om det finns formella garantier *och* om de fungerar i praktiken.

---

## ISSAI 140 — Quality Management for SAIs (2024)

ISSAI 140 (gäller från 1 januari 2025) ställer krav på ett kvalitetslednings-
system (ISQM) på organisationsnivå, inte per uppdrag. Kärnkraven:

### Etiska krav-element

Fem etiska element som QMS-systemet måste säkerställa:

1. **Integritet** — handla med ärlighet och öppenhet
2. **Objektivitet** — opåverkad bedömning, inga partsintressen
3. **Professionell kompetens och omsorg** — hålla och upprätthålla kunskapsnivå
4. **Konfidentialitet** — skydda sekretessbelagd information
5. **Professionellt uppträdande** — följa relevant lag och undvika ageranden
   som misskrediterar professionen

### Systemnivå-QA vs. processintegrerad QA

| Nivå | Standard | Fokus |
|------|----------|-------|
| **Systemnivå** | ISSAI 140 | Organisationens övergripande QMS: policies, rutiner, kompetensförsörjning, etik, IT-infrastruktur |
| **Processintegrerad** | GUID 3920 | QA inbyggd i varje uppdragsfas: planering, genomförande, rapportering, uppföljning |

Dessa är **komplement, inte substitut**. En SAI kan ha ett fungerande
ISSAI 140-system men bristfällig processintegrerad QA — och vice versa.

---

## Hotkategorier för oberoende

ISSAI 140 och INTOSAI-P 10 identifierar fem primära hotkategorier mot
oberoende och objektivitet:

| Hot | Innebörd | Exempel |
|-----|----------|---------|
| **Egenintresse** | Personlig nytta påverkar bedömningen | Revisor äger aktier i granskningsobjektet |
| **Självgranskning** | Granskar sitt eget tidigare arbete | Revisor granskar ett system hen designade |
| **Advokating** | Agerar som förespråkare för part | Revisor lobbar för granskningsobjektets ståndpunkt |
| **Bekantskap** | Nära relation som skapar partiskhet | Lång samarbetstid ger övertro på objektets uppgifter |
| **Intimidation** | Påtryckning som påverkar bedömningen | Granskningsobjekt hotar med klagomål |

**Safeguards** — motåtgärder:
- Rotation av uppdragsansvariga
- Collegial review / second partner review
- Oberoende kvalitetsgranskning (EQCR) vid komplexa uppdrag
- Explicit dokumentation av oberoendebedömning per uppdrag

---

## INTOSAI GUID 3920 — QA per revisionsprocessfas

GUID 3920 (Supporting Guidance on the Audit Process) specificerar hur QA
ska vara integrerad i varje fas av revisionsprocessen.

### De fyra faserna och QA-kraven

**Fas 1 — Planering:**
- Revisionsfrågan är tydlig, avgränsad och testbar
- Metodval är motiverat och proportionerligt mot frågan
- Datainsamlingsplan matchar de kausalitetsanspråk som frågan implicerar
- Riskbedömning genomförd (evidensrisker, tillgångshinder)
- QA-check: intern granskning av projektplan *innan* fältarbete startar

**Fas 2 — Genomförande:**
- Data insamlas enligt plan; avvikelser dokumenteras
- Löpande evidensbedömning mot ISSAI 3000:s tre krav (sufficient, relevant, reliable)
- Triangulering genomförd och dokumenterad
- Mellanchef/senior reviewer godkänner att evidensbasen bär revisionsfrågan

**Fas 3 — Rapportering:**
- Slutsatser kalibrerade mot evidenshierarkin (hedging)
- Intern peer review (opponentuppdrag) genomförd *innan* extern remiss
- Rekommendationer proportionerliga mot bevisläget
- Metodbegränsningar redovisade explicit
- QA-check: kvalitetsgranskarens opponentroll legitimeras här — det är fas 3-QA

**Fas 4 — Uppföljning:**
- Rekommendationernas genomförande spåras
- Ny revisionscykel planeras om uppföljningen visar implementation-gap

### Opponentrollen som fas 3-QA

Riksrevisionens uppläggs- och rapportseminarier är processintegrerad QA
enligt GUID 3920:s fas 3-logik. Den externa opponenten fungerar som en
oberoende kvalitetsgranskning *innan* offentliggörande — vilket är GUID
3920:s rekommenderade safeguard för komplexa effektivitetsrevisioner.

**Vad detta innebär vid opponentuppdraget:**
- Min granskning är inte en fristående åsikt utan en formell fas 3-QA
- Invändningar ska vara handlingsbara och specifika — opponent-rollen är
  inte akademisk debatt utan en del av revisionsprocessens QA-system
- Jag dokumenterar mina invändningar på ett sätt som kan spåras i
  revisionsdokumentationen (GUID 3920 kräver audit trail för QA)
