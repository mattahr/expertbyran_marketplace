# OT/ICS-säkerhet — Granskningsmetodik

Kondenserad referens för granskning av operativ teknik (OT) och industriella styrsystem (ICS/SCADA) i samhällsviktig verksamhet. Täcker internationella ramverk, praktisk fasmodell, typiska fynd och Riksrevisionens specifika granskningspotential.

Senast uppdaterad: 2026-05-12 (EXP-2866)

---

## Varför OT-revision skiljer sig från IT-revision

OT-system i samhällskritisk infrastruktur kan inte granskas med traditionella IT-revisionsmetoder:

1. **Tillgänglighetskrav:** OT kör 24/7 — system kan inte tas offline för testning. Aktivt intrångstest kan slå ut ett kraftnät eller värmeverk.
2. **Protokollinkompatibilitet:** Standardsäkerhetsverktyg (portskanning, aktiv sårbarhetsskanning) kan korrumpera OT-protokoll som Modbus, DNP3 och IEC 61850.
3. **Kompetensglapp:** OT-säkerhetsspecialister är extremt sällsynta — bristen påverkar granskares möjlighet att rekrytera teknisk expertis.

**Konsekvens:** OT-granskning bygger huvudsakligen på **passiva metoder** — dokumentgranskning, intervjuer, arkitekturgenomgång och begränsad teknisk verifiering under kontrollerade former.

---

## Internationella referensramverk

### NIST SP 800-82 Rev. 3 (2023)

*Guide to Operational Technology (OT) Security*, publicerad september 2023. Det primära internationella ramverket för OT-säkerhetsbedömningar. Rev. 3 utvidgar scope från "ICS" till hela OT-begreppet.

**OT-overlay (Appendix D):** Kartlägger 20 kontrollfamiljer (från NIST SP 800-53) mot OT-kontext — anger om kontroller gäller utan modifiering, med OT-anpassning, eller inte alls.

De sex viktigaste kontrollfamiljerna för OT-granskning:

| Familj | OT-relevans | Typisk brist |
|--------|-------------|--------------|
| AC (Access Control) | Hög | Generiska inloggningar, delade lösenord |
| AU (Audit and Accountability) | Hög | Loggning saknas/täcker ej OT |
| CM (Configuration Management) | Hög | Ingen baselining av PLC-konfigurationer |
| IA (Identification and Authentication) | Hög | Standardlösenord på komponenter |
| IR (Incident Response) | Hög | OT-specifik IR-plan saknas |
| SC (System Communications Protection) | Hög | Flat network, ej segmenterat IT/OT |

**CISA CSET-verktyget:** CISA:s kostnadsfria *Cyber Security Evaluation Tool* implementerar NIST SP 800-82 som strukturerad enkät — kan användas direkt av granskare för baseliningbedömning.

Källa: https://csrc.nist.gov/pubs/sp/800/82/r3/final

### IEC 62443 — OT-säkerhetsstandarden

ISA/IEC 62443 är det primära tekniska ramverket för IACS-säkerhet (Industrial Automation and Control Systems). ENISA:s Technical Implementation Guidance för NIS2 (jun 2025) refererar explicit till IEC 62443 för OT-entiteter.

**Nyckelbegrepp:**
- **Zoner och kanaler:** Dela upp OT-miljön i zoner efter säkerhetsnivå, reglera flöden via kanaler
- **Säkerhetsnivåer (SL 1–4):** SL 1 = oavsiktlig kompromiss, SL 2 = aktörer med allmänna resurser, SL 3 = sofistikerade aktörer, SL 4 = nationalstater

**NIS2 Art. 21 ↔ IEC 62443-mappning:**
- Riskhantering → IEC 62443-3-2 (riskbedömning och systemdesign)
- Incident response → IEC 62443-2-1 (IACS Security Management System)
- Leverantörskedja → IEC 62443-2-4 (krav på systemintegratörer)

### GAO Cybersecurity Program Audit Guide (CPAG, GAO-23-104705)

GAO:s guide ger revisorer ett systematiskt tillvägagångssätt i tre nivåer:

1. **Programbedömning** — styrning, policy, roller, ansvar, riskhanteringsprocesser
2. **Systemsäkerhetsgranskning** — dokumentgranskning, konfigurationsgenomgång, kontrollverifiering
3. **Teknisk testning** — sårbarhetsskanning och penetrationstestning (med OT-anpassningar: passiva verktyg, underhållsfönster)

Källa: https://www.gao.gov/products/gao-23-104705

---

## Fasmodell för OT-granskning

### Fas 1: Informationsinsamling (passiv)

Begär följande dokument:
- Tillgångsinventering (asset inventory) för OT-komponenter
- Nätverksarkitekturdiagram inkl. IT/OT-gränssnitt
- Policydokumentation (informationssäkerhetspolicy, OT-riktlinjer)
- Riskbedömningsdokumentation (senaste OT-riskanalys)
- Patch- och underhållsloggar för OT-komponenter
- Incidentloggar (OT-relaterade)
- Leverantörs- och underhållsavtal med fjärråtkomstvillkor

### Fas 2: Arkitekturgenomgång

Nyckelfrågor:
- Är IT/OT-nätverken segmenterade med dokumenterade gränssnitt (DMZ, industriell brandvägg, unidirektionell gateway)?
- Är zoner och kanaler implementerade enligt IEC 62443-3-2?
- Hur hanteras fjärråtkomst för underhållsleverantörer (VPN, jump server, MFA)?
- Är luftgapen dokumenterade och tekniskt verifierade?

### Fas 3: Kontrollverifiering (stickprov, utan aktiv testning)

- Stämmer nätverksarkitekturdiagram med faktisk konfiguration? (logganalys, CMDB)
- Är patchhanteringsprocessen OT-anpassad? (leverantörsgodkännande, test i stagingmiljö)
- Är autentiseringsmekanismer implementerade? (granskning av användarkonton, behörighetsmatriser)
- Täcker SOC/SIEM OT-lager? (loggkälla-inventering)

### Fas 4: Intervjuer

**Ledning/CISO — nyckelfrämgor:**
- Har ledningsorganet godkänt OT-specifik riskhanteringspolicy? (NIS2 art. 20)
- Har ledningen genomgått OT-cybersäkerhetsutbildning?
- Är OT-säkerhet integrerat i ISMS?

**Driftpersonal:**
- Hur sker behörighetstilldelning för OT-system?
- Har OT-specifik incident response-plan övats? Senast när?
- Hur hanteras leverantörers fjärråtkomst?

**IT/OT-gränssnittspersonal:**
- Hur samordnas patch-cykler med OT-tillgänglighetswindows?
- Hur hanteras OT-incidenter som skiljer sig från IT-incidenter?

---

## Riksrevisionens metodmönster (anpassat för OT)

Riksrevisionens egna granskningar (RiR 2016:8, RiR 2023:8) visar tre analysperspektiv tillämpliga på OT:

1. **Organisatoriskt perspektiv:** Ledningens styrning, ansvarstrukturer, prioritering i styrelse/ledning
2. **Systemperspektiv:** Tillgångsinventering, tekniska kontroller, segmentering
3. **Riskhanteringsperspektiv:** Systematisk riskanalys, uppdatering, beslutsstöd

**Datainsamling:** Enkät (bredd) + intervjuer (djup, 3–6 org) + dokumentstudier + jämförelse med bedömningsgrunder (NIS2 art. 21, MCFFS om säkerhetsåtgärder, ENISA Technical Guidance).

---

## Typiska fynd i OT-säkerhetsgranskning

Baserat på internationell erfarenhet (ISA GCA, CISA, ENISA):

| Fynd | Frekvens | NIS2-koppling |
|------|---------|---------------|
| Standardlösenord på PLC/SCADA-komponenter | Mycket vanligt | Art. 21.2(i) |
| Flat network — ingen IT/OT-segmentering | Vanligt | Art. 21.2(h) |
| Föråldrad firmware (ej patchbar utan leverantörsstöd) | Mycket vanligt | Art. 21.2(e) |
| Avsaknad av OT-loggning/SIEM-täckning | Vanligt | Art. 21.2(b) |
| OT-specifik IR-plan saknas | Vanligt | Art. 21.2(c) |
| Obegränsad leverantörsfjärråtkomst utan MFA | Vanligt | Art. 21.2(j) |
| Tillgångsinventering saknas eller inaktuell | Mycket vanligt | Art. 21.2(a) |

---

## Riksrevisionens specifika granskningsfrågor för OT

**Om tillsynsmyndigheten (Energimyndigheten, Transportstyrelsen):**
- Har tillsynsmyndigheten OT-kompetens i sin organisation?
- Har myndigheten tagit fram OT-specifik tillsynsmetodik?
- Genomför myndigheten teknisk granskning av OT-system eller enbart dokumentgranskning?
- Är Transportstyrelses kapacitet tillräcklig? (Tillsynsobjekt ökade 130 → ~750 under NIS2)

**Om statliga OT-operatörer (Svenska kraftnät, Trafikverket/Infranord):**
- Är NIS2 art. 21-krav implementerade för OT-systemen?
- Är IEC 62443 (eller likvärdig standard) en del av säkerhetsarbetet?
- Finns OT-specifik incident response-plan, övad och dokumenterad?
- Hanteras OT-leverantörers fjärråtkomst med adekvata kontroller?

**Om NCSC:s stödfunktion (Nationell strategi 2025–2029, Mål 3):**
- Ger NCSC faktiskt OT-specifikt råd och stöd till sektorsansvariga myndigheter?
- Har NCSC kapacitet att ta emot och analysera OT-incidentrapporter?

**Om Energimyndighetens EU 2024/1366-implementering:**
- Har nationell riskbedömning av cybersäkerhet i stamnätet genomförts?
- Är tillsynsprocess etablerad för gränsöverskridande elflöden?

---

## Begränsningar för Riksrevisionen vid OT-granskning

1. **Teknisk kompetens:** OT-revision kräver specialistkompetens (IEC 62443, OT-protokoll). Riksrevisionen kan behöva upphandla extern expertis.
2. **Granskningsmandat:** Riksrevisionen kan inte kräva penetrationstestning — men kan granska *om* myndigheterna beställer och genomför sådana tester.
3. **Privata operatörer:** Energibolag, vattenbolag etc. är utanför direkt granskningsmandat. Tillsynsmyndigheterna och statliga operatörer är granskningsbara.
4. **Sekretess:** Detaljerade OT-arkitekturer kan vara säkerhetskänsliga — granskaren måste ha rätt behörighet.

---

## Identifierade granskningsobjekt och tidplan

| Granskningsobjekt | Granskningsbart från | Referens |
|-------------------|---------------------|---------|
| Energimyndighetens OT-tillsyn under NIS2 | Nu (2026) | Statskontoret 2025:8 |
| Svenska kraftnäts OT/SCADA-säkerhet | Nu (2026) | RiR 2023:15 (lucka) |
| Transportstyrelsens kapacitet för OT-tillsyn (~750 obj.) | Nu (2026) | Statskontoret 2025:8 |
| NCSC:s stöd till OT-operatörer (Nationell strategi Mål 3) | Nu (2026) | Prop. 2025/26:214 |
| MCF:s föreskrift om säkerhetsåtgärder — OT-täckning | 2027+ (efter beslut) | MCFFS (sommar 2026) |
| Energimyndighetens EU 2024/1366-genomförande | 2027+ | EU 2024/1366 |

---

## Källreferenser

- NIST SP 800-82 Rev. 3 (2023): https://csrc.nist.gov/pubs/sp/800/82/r3/final
- GAO CPAG (GAO-23-104705): https://www.gao.gov/products/gao-23-104705
- ENISA Technical Implementation Guidance on NIS2 (jun 2025): https://www.enisa.europa.eu/
- IEC 62443-serien: https://www.isa.org/standards-and-publications/isa-standards/isa-iec-62443-series-of-standards
- RiR 2016:8 — Informationssäkerhetsarbete på nio myndigheter
- RiR 2023:8 — Regeringens styrning av samhällets informations- och cybersäkerhet
- Statskontoret 2025:8 — Tillsynsmyndigheternas kostnader till följd av NIS2
- Skr. 2024/25:121 — Nationell strategi för cybersäkerhet 2025–2029 (Mål 3, OT-fokus)
- EU 2024/1366 — Sektorsspecifika cybersäkerhetskrav för gränsöverskridande elflöden
