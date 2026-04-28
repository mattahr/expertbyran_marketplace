# AI-säkerhet och hot mot kritisk infrastruktur

Kunskapsbas senast uppdaterad: 2026-04-28 (EXP-1096)

---

## Hotbilden: Hur AI förändrar cyberattacker

### AI som offensivt verktyg

AI har dramatiskt sänkt tröskeln för sofistikerade cyberattacker:

- **Adaptiv skadlig kod**: AI-driven malware kan kontinuerligt ändra sin filstruktur och obfuskera kod för att undvika signaturbaserad detektering, anpassa nyttolaster dynamiskt baserat på målets sårbarheter, och använda polymorf mutation.
- **AI-förstärkt social engineering**: AI-stödda nätfiskekampanjer utgjorde >80% av observerad social engineering-aktivitet globalt i början av 2025 (ENISA).
- **Deepfakes och syntetiska medier**: Används för identitetsstöld och BEC-attacker (Business Email Compromise).
- **Autonoma hotaktörer**: Verktyg som "Xanthorox AI" (identifierat av ENISA 2025) är utformade för att automatisera social engineering och skadlig kodutveckling.
- **IBM X-Force 2026**: AI-drivna attacker eskalerar; angripare identifierar sårbarheter snabbare än försvaret kan täppa till dem.

### Kritisk infrastruktur som måltavla

- 60% av intrång i kritisk infrastruktur sker via tredjepartsåtkomst (supply chain-vektorer).
- Operativ teknik (OT): SCADA-, PLC- och IoT-system har primärt designats för tillförlitlighet, inte säkerhet — ett strukturellt problem.
- OT-hot utgör 18,2% av alla identifierade hotkategorier i EU (ENISA 2025).
- Nordiska och baltiska regioner utsattes för omfattande DDoS-kampanjer hösten 2024, riktade mot energi, telekommunikation och statliga myndigheter.

### Hotaktörers konvergens

Gränserna suddas ut mellan hacktivister, cyberkriminella och statsunderstödda aktörer — delade verktyg, taktiker och infrastruktur blir allt vanligare (ENISA 2025).

---

## Adversarial AI — Angrepp mot AI-system

Adversariella angrepp riktar sig mot AI-modeller, inte bara infrastruktur som AI-verktyg attackerar:

### Angreppstyper (NIST AI 100-2e2025)

| Typ | Beskrivning |
|-----|-------------|
| **Evasion (undvikande)** | Manipulerade indata vid driftsättning leder modellen att fatta fel beslut |
| **Poisoning (förgiftning)** | Angripare kontrollerar träningsdata för att inplantera bakdörrar eller skeva modellen |
| **Model inversion** | Extrahera känslig information från modellens svar |
| **Backdoor attacks** | Dold trigger i tränad modell aktiverar skadligt beteende |

### Skyddsmekanismer

Forskning (ISACA, NIST, Springer 2025) pekar på att ingen enskild försvarsstrategi ger fullständigt skydd. Rekommenderat:

1. **Adversarial training** — träna modellen med adversariella exempel
2. **Input sanitization** — filtrera och validera indata
3. **Anomalitetsdetektering** — övervaka modellbeteende vid driftsättning
4. **Ensemble-metoder** — kombinera flera modeller för robusthet
5. **Kontinuerlig modellvalidering** — inte bara vid driftsättning
6. **Strikt styrning och incidentrespons** — governance-protokoll

Utmaning: Befintliga försvar är ofta skräddarsydda för specifika angreppsscenarier och generaliserar dåligt. Robusta modeller har hög beräkningskostnad.

---

## Regulatory Landscape: EU AI Act + NIS2 + CRA

### NIS2-direktivet / Cybersäkerhetslagen (2025:1506)

- Täcker leverantörer av samhällsviktiga och viktiga tjänster i EU.
- AI-system som ingår i samhällsviktiga tjänster är i scope via sin *funktion*, inte för att de är AI.
- Se `references/nis2-cybersakerhetslagen.md` för fullständig referens.

### EU AI Act

- Riskbaserat regelverk: AI-system kategoriseras efter risk (oacceptabel, hög, begränsad, minimal).
- "Hög risk"-system som driftsätts i kritisk infrastruktur (artikel 6, Annex III) utlöser automatiskt AI Act-krav.
- Allvarliga incidenter med hög-risk AI ska rapporteras till nationell marknadstillsynsmyndighet utan onödigt dröjsmål, max 15 dagar.
- Tidslinje: Gradvis tillämpning 2024–2026; hög-risk-regler fullt i kraft 2026.

### Samspelet och överlappningen

- En enda incident kan utlösa rapporteringskrav under *båda* regelverken → dubblerat compliance-arbete.
- Praktisk tumregel: Om ett AI-system är del av en samhällsviktig tjänst → NIS2 gäller. Om systemet klassas som hög-risk enligt AI Act → AI Act gäller ovanpå NIS2.
- Cyber Resilience Act (CRA) kompletterar med produktsäkerhetskrav på uppkopplade enheter.

---

## OWASP Top 10 för LLM-applikationer (2025)

Publicerat av OWASP Gen AI Security Project. Täcker de tio mest kritiska riskerna i LLM-baserade system.

| Rank | Kategori | Beskrivning |
|------|----------|-------------|
| LLM01 | **Prompt Injection** | Angripare manipulerar LLM-beteende via användarindata — direkt eller indirekt. Allvarligaste risken. |
| LLM02 | **Sensitive Information Disclosure** | LLM röjer känslig information i träningsdata, systempromptar eller via svar. |
| LLM03 | **Supply Chain** | Komprometterade grundmodeller, datasets, plugins eller leverantörsled. |
| LLM04 | **Data and Model Poisoning** | Angripare kontaminerar tränings-, finjusterings- eller embeddingdata. |
| LLM05 | **Improper Output Handling** | Osäker hantering av LLM-svar nedströms: XSS, SSRF, SQL-injektion via LLM-output. |
| LLM06 | **Excessive Agency** | LLM-agenter ges för breda befogenheter utan tillräcklig mänsklig kontroll. |
| LLM07 | **System Prompt Leakage** | Systempromptar med känslig info läcker via användarinteraktion. |
| LLM08 | **Vector and Embedding Weaknesses** | Svagheter i vektordatabaser och embedding-pipelines möjliggör dold datainjektion i RAG-system. |
| LLM09 | **Misinformation** | LLM genererar övertygande men felaktig information; högrisk i beslutsstöd för myndigheter. |
| LLM10 | **Unbounded Consumption** | Okontrollerat resursuttag via LLM-anrop — kostnad, DoS, kapacitetsläcka. |

**Primärkälla:** [OWASP Top 10 for LLM Applications 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

---

## NIST AI Risk Management Framework (AI RMF 1.0, 2023)

Frivilligt ramverk för riskhantering i AI-system, publicerat av NIST januari 2023 (AI 100-1). Icke-sektorspecifikt och rättighetsbevarande.

### De fyra funktionerna (GOVERN – MAP – MEASURE – MANAGE)

| Funktion | Syfte | Praktisk tillämpning |
|----------|-------|----------------------|
| **GOVERN** | Bygga AI-riskkultur och styrstruktur | Ledningsbeslut, policyer, ansvarsfördelning |
| **MAP** | Identifiera och kontextualisera AI-risker | Vad är systemet? Vilka påverkas? Var kan det gå fel? |
| **MEASURE** | Bedöma och kvantifiera AI-risker | Testa robusthet, bias, prestanda |
| **MANAGE** | Hantera identifierade risker | Kontrollåtgärder, incidentrespons, kontinuerlig övervakning |

NIST AI RMF kompletteras av NIST AI 100-2e2025 (Adversarial ML Taxonomy) för detaljerad terminologi.

**Primärkälla:** [NIST AI 100-1 (AI RMF 1.0)](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)

---

## ENISA Threat Landscape 2024 — Nyckelinsikter

**Period:** Juli 2023 – Juni 2024

### Sju primära hot (ETL 2024)

| Rank | Hot | Kommentar |
|------|-----|-----------|
| 1 | **Tillgänglighetsattacker (DDoS)** | Geopolitiskt motiverade kampanjer mot EU |
| 2 | **Ransomware** | Dubbel utpressning vanlig |
| 3 | **Datahot** (stöld/läckage) | Datatillgång driver kriminell ekonomi |
| 4 | **Skadlig kod (malware)** | AI-driven adaptiv malware ökar |
| 5 | **Social engineering** | AI-förstärkt phishing mot kritisk infrastruktur |
| 6 | **Informationsmanipulation** | Desinformation + deepfakes, eskalerande |
| 7 | **Supply chain-attacker** | Tredjepartsåtkomst som vektor |

**Primärkälla:** [ENISA Threat Landscape 2024](https://www.enisa.europa.eu/publications/enisa-threat-landscape-2024)

---

## Svensk kontext

- **NCSC-rapport 2025**: Attacker mot kritisk infrastruktur ökar; nästan en tredjedel av alla DDoS-attacker i Sverige riktade mot kritisk infrastruktur.
- **Hotbild 2025**: Ransomware +183%, identitetsbaserade attacker +32%, cyberrelaterade förluster >30 miljarder kr.
- **Nationell cybersäkerhetsstrategi 2025–2029**: Uppdaterad handlingsplan; FRA tar över delar av MSB:s cybersäkerhetsoperationer.
- AI-agenter (autonoma digitala aktörer) börjar integreras i affärskritiska system — ny attackyta.

---

## Riskscenario: AI-baserat beslutsstöd hos offentlig myndighet

**Kontext:** En svensk myndighet implementerar ett AI-system för automatiserat beslutsstöd.

### Kombinerat poisoning + prompt injection-angrepp

**Angreppsvektor 1 — Datapoisoning (LLM04 / NIST: Poisoning):** Insider eller komprometterad underleverantör kontaminerar träningsdata → modellen lär sig blinda fläckar selektivt.

**Angreppsvektor 2 — Prompt injection via fritextfält (LLM01):** Angripare bäddar in instruktioner i fritext → modellens beslut manipuleras direkt.

**Angreppsvektor 3 — Supply chain (LLM03):** Komprometterad modelluppdatering via extern API-leverantör.

### Skyddsåtgärder (kopplade till NIS2 artikel 21)

1. **Supply chain-säkerhet**: Vetting av modelleverantörer, hash-verifiering
2. **Åtkomstkontroll för träningsdata**: Minsta privilegium, 4-ögon-princip
3. **Adversarial robustness-testning**: Red team mot prompt injection och poisoning
4. **Anomalidetektering**: Övervaka modellens beslutsdistribution
5. **Input sanitering**: Sanera fritextfält; strukturerad output-validering

---

## Källor

| Källa | Typ | Relevans |
|-------|-----|----------|
| NIST AI 100-2e2025 | Primärkälla | Taxonomi och terminologi för adversarial ML |
| OWASP LLM Top 10 2025 | Primärkälla | Säkerhetsrisker i LLM-applikationer |
| NIST AI RMF 1.0 (AI 100-1) | Primärkälla | Ramverk för AI-riskhantering |
| ENISA Threat Landscape 2024 | Primärkälla | EU-hotbild inkl. AI-dimensioner |
| IBM X-Force Threat Index 2026 | Primärkälla | AI-eskalerande attacker |
| ISACA: Adversarial ML 2025 | Forskning | Skyddsmekanismer mot adversarial ML |
