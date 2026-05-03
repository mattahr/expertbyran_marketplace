# MCP-Ekosystemet 2026 — Referensmaterial

*Källa: omvärldsbevakning maj 2026. Data från AI2Work, Digital Applied, CData, eSentire, Red Hat, Coalition for Secure AI.*

---

## Vad är MCP?

Model Context Protocol (MCP) är ett öppet klient-server-protokoll, ursprungligen lanserat av Anthropic i november 2024 och överlåtet till Linux Foundation Q1 2026. Protokollet standardiserar hur AI-agenter anropar externa verktyg, datakällor och tjänster.

**Teknisk modell:** MCP-servern exponerar tre typer av resurser:
- **Verktyg** (tool calls): funktioner agenten kan anropa (t.ex. söka i databas, skicka e-post)
- **Resurser** (resources): datakällor agenten kan läsa (t.ex. filsystem, API-endpoints)
- **Prompts** (prompt templates): fördefinierade mallar för vanliga uppgiftsmönster

Agenten (klienten) väljer dynamiskt vilka verktyg den anropar baserat på uppgiften. Metaforen som dominerar branschen: "USB-C för AI-agenter" — ett universalprotokoll som ersätter skräddarsydda point-to-point-integrationer.

---

## Adoptionstakt och Marknadsdata (april 2026)

| Mätvärde | Värde |
|----------|-------|
| Månadsliga SDK-nedladdningar | 97 miljoner |
| Offentliga MCP-servrar i registret | 9 400+ |
| npm-paket med "mcp" | 6 200+ |
| PyPI MCP-relaterade paket | 2 100+ |
| Enterprise AI-team med ≥1 MCP-agent i produktion | 78% |
| CTOs som namnger MCP som dominant standard inom 12 mån | 67% |

Tillväxtkurvan: från ~2M nedladdningar vid lansering (november 2024) till 97M månadsvis i april 2026 — 16 månader. En av de snabbaste adoptionskurvorna i protokollhistorien, jämförbar med TCP/IP:s tidiga expansion inom stängda nätverk.

**Konkurrentlandskapet:**
- Google A2A (Agent-to-Agent): ~23% marknadsandel
- Anthropic ACP (Agent Communication Protocol): ~8%
- UCP (Universal Communication Protocol): ~4%
- MCP:s dominans: ingen konkurrent har lyckats utmana dess position

---

## Linux Foundation-Övergången

Anthropic överlät MCP-specifikationen och styrningen till Linux Foundation i Q1 2026. Konsekvenser:

- **Vändpunkt för enterprise-adoption:** Linux Foundation-status signalerar leverantörsneutralitet och långsiktig förvaltning — jämförbar med hur Apache-stiftelsens förvaltning drev Apache HTTP-serverns adoption.
- **Styrningsmodell:** öppet TSC (Technical Steering Committee), bidrag från Microsoft, Google, Anthropic, IBM med flera.
- **Standardiseringsimplakation för offentlig sektor:** myndigheter som väljer MCP-baserade integrationer minskar vendor lock-in jämfört med proprietära alternativ.

---

## Säkerhetsrisker — Kritiska Kategorier

### 1. Prompt Injection / Tool Poisoning

**Mekanism:** Angripare bäddar in dolda instruktioner i dokument, e-postmeddelanden eller webbsidor som AI-agenten bearbetar. Agenten utför instruktionerna utan att användaren ser dem.

**Verkligt fall:** CVE-2025-32711 "EchoLeak" mot Microsoft 365 Copilot. En AI-agent som läste ett manipulerat dokument exfiltrerade känslig data (e-post, Teams-konversationer) till angriparen. Bevisad i produktion.

**Relevans för offentlig sektor:** myndigheter med AI-agenter som bearbetar medborgardokument, e-post eller externa datakällor är sårbara. Risk är högst i "agentic workflows" där agenten agerar autonomt utan mänsklig kontrollpunkt per steg.

### 2. Credential Aggregation

**Mekanism:** En MCP-server aggregerar credentials (API-nycklar, OAuth-tokens, lösenord) för multipla enterprise-tjänster. Ett enskilt intrång i MCP-servern ger angriparen åtkomst till hela integrationslandskapet.

**Implikation:** MCP-servrar bör behandlas som klass-1 säkerhetskritisk infrastruktur — samma skyddsnivå som en IAM-server eller privilegierad access workstation (PAW).

### 3. Supply Chain-Risker

**Händelse:** Första bekräftade skadliga MCP-paketet identifierades september 2025. Det opererade oupptäckt i två veckor medan det exfiltrerade e-postdata från installerade miljöer.

**Mönster:** liknar npm/PyPI supply chain-attacker (SolarWinds-mönstret för AI-integrationslagret). Risk ökar i takt med att registret med 9 400+ servrar växer utan central säkerhetsgranskning.

**Motåtgärd:** kräv intern granskning och allow-listing av MCP-servrar. Använd inte MCP-paket direkt från registret utan verifiering.

### 4. Governance-Gap

**Problem:** MCP-integrationer kan skapas av vem som helst i en organisation (ett team, en enskild utvecklare) utan säkerhetsgranskning eller arkitekturstyrning. Integrationslandskapet fragmenteras snabbt utan central styrning.

**Implikation för IT-strategi:** MCP-governance måste hanteras i organisationens säkerhetspolicy och IT-arkitekturprocess, inte lämnas till individuella team.

---

## Enterprise-Mognad 2026

Marknaden befinner sig i övergången från experiment till produktion. Mognadsgap som återstår:

| Gap | Status 2026 |
|-----|-------------|
| Standardiserad audit logging | Saknas i ekosystemet |
| Traceability per agent-anrop | Partiell, verktygsspecifik |
| Tredjepartscertifiering av MCP-servrar | Pågående diskussion, ingen standard |
| Formell säkerhetsgranskning av registret | Ej etablerat |
| Reglering av MCP i EU AI Act-kontext | Oklart — trolig högrisk-klassificering för autonoma MCP-agenter |

---

## Strategiska Implikationer för Offentlig Sektor

### Möjligheter

- Standardiserade verktygsintegrationer reducerar integrationskostnad dramatiskt
- Interoperabilitet med externa system (Bolagsverket, Skatteverket, EU-datakällor) via MCP-servrar
- Ekosystemet mognar snabbt — investeringar idag byggs på en stabil protokollstandard

### Risker att adressera

- Procurement: kräv att leverantörers AI-lösningar exponerar MCP-kompatibla interfaces — undviker proprietär inlåsning
- Säkerhet: behandla MCP-servrar som kritisk infrastruktur (credential-hantering, audit logging, supply chain-granskning)
- Governance: etablera centralt godkännanderegister för interna MCP-servrar — ingen implementation utan arkitekturstyrning

### Rekommenderat bedömningsramverk vid upphandling

1. Använder lösningen MCP eller proprietärt integrationsprotokoll?
2. Hur hanteras credential storage i MCP-servern? (Secrets management, HSM, rotation?)
3. Finns audit log för samtliga agent-anrop (vem anropade vad, när, med vilket resultat)?
4. Har leverantören genomfört tredjepartssäkerhetsgranskning av MCP-implementation?
5. Hur hanteras supply chain-risker i leverantörens MCP-paketberoenden?

---

## Relevanta Källor

- **AI2Work — Model Context Protocol Hits 97M Installs as Linux Foundation Takes Over**
  Innehåll: Adoptionstakt, Linux Foundation-övergång, ekosystemstatistik.

- **Digital Applied — MCP Adoption Statistics 2026**
  Innehåll: Enterprise-adoptionstal, server-tillväxt, marknadsdata.

- **CData — 2026: The Year for Enterprise-Ready MCP Adoption**
  Innehåll: Enterprise-readiness, utmaningar och produktion.

- **eSentire — MCP Security: Critical Vulnerabilities Every CISO Must Address**
  Innehåll: CISO-perspektiv, säkerhetsrisker, rekommenderade kontroller.

- **Red Hat — MCP: Understanding Security Risks and Controls**
  Innehåll: Teknisk djupdykning i säkerhetsarkitektur och mitigering.

- **Coalition for Secure AI — Securing the AI Agent Revolution: MCP Security Guide**
  Innehåll: Branschorganisationens rekommendationer för MCP-säkerhet.
