# Riskbedömning: ISO/IEC 27005:2022 vs NIST SP 800-30 Rev. 1

Kunskapsbas senast uppdaterad: 2026-04-28 (EXP-1096)

---

## Vad de är

**ISO/IEC 27005:2022** är den internationella standarden för riskhantering inom informationssäkerhet (ISO). Den är direkt länkad till ISO/IEC 27001 och utgör metodstödet för riskbedömning i ett ISMS (Information Security Management System).

**NIST SP 800-30 Rev. 1** (2012, fortfarande gällande) är en teknisk vägledning från NIST (USA). Den fokuserar på informationsrisk i IT-system och är del av NIST Risk Management Framework (RMF).

---

## Jämförelse: Kärnegenskaper

| Egenskap | ISO 27005:2022 | NIST SP 800-30 Rev. 1 |
|---|---|---|
| **Ursprung** | Internationell standard (ISO/IEC) | Amerikansk federal vägledning (NIST) |
| **Scope** | Hela organisationen: people, process, technology | Specifikt IT-system och dess gränser |
| **Tillgångsinventering** | Ja — central del | Nej — ingen formell tillgångsinventering |
| **Riskkalkylering** | Flexibel — flera metoder tillåtna | Prescriptiv — fastställd formel |
| **Certifieringskontext** | Obligatorisk för ISO 27001-certifiering | Ingen koppling till certifiering |
| **Abstraktionsnivå** | Strategisk/taktisk (ledningsfokus) | Operativ/teknisk (systemfokus) |
| **Kombinationsbarhet** | Kan kombineras med NIST-metoder | Kan kombineras med ISO 27005-kontext |

---

## Beslutsramverk: När väljer jag vad?

### Välj ISO 27005 när:

1. **Certifieringskontext** — organisationen siktar på ISO 27001-certifiering
2. **Organisatorisk bredd** — riskbedömningen ska täcka people, process och technology
3. **Strukturerat riskregister** — ni behöver ett levande riskregister kopplat till behandlingsplaner
4. **Internationellt erkännande** — EU/global kontext, revisorer utanför USA
5. **Ledningssystem** — del av ett bredare ISMS eller BCMS

**Typiska organisationer:** Europeiska företag, NIS2-skyldiga verksamheter, ISO 27001-certifierande organisationer

### Välj NIST SP 800-30 när:

1. **Systemspecifik bedömning** — ni bedömer risk för ett specifikt IT-system
2. **Myndighetskontext** — kopplar till NIST RMF och FedRAMP
3. **Teknisk djupdykning** — detaljerad hotanalys på infrastrukturnivå
4. **Prescriptiv vägledning** — bedömningsteamet behöver tydlig metodstyrning med färdiga taxonomier

**Typiska organisationer:** Svenska myndigheter med US-systemleverantörer, säkerhetsgranskning av enskilda IT-system

### Kombinationsansats (rekommenderat):

Forskning (Fikri & Putra, ScienceDirect 2019; IEEE 2024) visar att kombinationen ger bäst resultat:
- ISO 27005 för **övergripande organisatorisk riskbedömning och riskbehandlingsplan**
- NIST SP 800-30 för **systemspecifik hotanalys** som matar in till ISO 27005-riskregistret

---

## Metodprocess i korthet

### ISO 27005-processen (iterativ):

1. Etablera kontext (scope, kriterier)
2. Identifiera risker (tillgångar, hot, sårbarheter)
3. Analysera risker (sannolikhet × konsekvens)
4. Utvärdera risker (mot acceptansnivå)
5. Behandla risker (minska, acceptera, överföra, undvika)
6. Övervaka och granska

Kopplas till ISO 27001 Annex A för kontrollurval.

### NIST 800-30-processen (tre steg):

1. **Prepare** — Identifiera syfte, scope, antaganden, informationskällor
2. **Conduct** — Identifiera hot och sårbarhet → bedöm sannolikhet och konsekvens → beräkna risk
3. **Communicate/Maintain** — Rapportera resultat, upprätthåll riskbedömning

Riskformel: `Risk = Threat × Vulnerability × Impact`

---

## Koppling till svenska krav

**NIS2 / Cybersäkerhetslagen (2025:1506):** Artikel 21 kräver riskhanteringsåtgärder baserade på en "allriskmetod" (all-hazards approach). ISO 27005 är den naturliga metodologin eftersom den täcker hela organisationen.

**MSB:s vägledning för NIS2:** MSB rekommenderar ett riskbaserat arbetssätt i linje med ISO 27001/27005. Rapportering av riskhanteringsåtgärder sker till sektortillsynsmyndighet och samordnas av MSB.

---

## Källor

| Källa | Typ | Relevans |
|---|---|---|
| ISO/IEC 27005:2022 | Primärkälla (betald) | Den fullständiga standarden |
| NIST SP 800-30 Rev. 1 (2012) | Primärkälla (gratis) | nvlpubs.nist.gov |
| IEEE 2024: Risk Mitigation ISO 27005+NIST 800-30 | Forskning | ieeexplore.ieee.org/document/11384072/ |
| ScienceDirect 2019: Combination technique | Forskning | sciencedirect.com/science/article/pii/S1877050919319453 |
