# AI i svenska myndigheter — inventering 2026

Källa: ISF 2026:1 "Automatisering och AI i socialförsäkringen" (2026), RiR 2020:22 "Automatiserat beslutsfattande i statsförvaltningen" (2020), SOU 2025:33, Ds 2025:7.

## Nyckeliakttagelse

AI-användningen i svenska myndigheter är begränsad men snabbt ökande (2026). Ingen myndighet använder AI som beslutsfattare — AI används som beslutsstöd, i administrativa uppgifter, och för riskurval. Inför EU AI Acts deadline (aug 2026) är compliance-skulden stor hos flera myndigheter.

## Inventering per myndighet

### Försäkringskassan
- **SAMU** — NLP-verktyg som sorterar medicinska underlag för handläggare i aktivitetsersättning. Enda AI-verktyget med direkt koppling till förmånshandläggning.
- Transkribering, e-postsortering — i produktion
- **Dokumentationsbrist (RiR 2020:22):** Privatpersoner kan inte alltid spåra vad som skett i automatiserad handläggning. Brister mot EU AI Act Art. 13–14.

### Skatteverket
- **Skatti** — chattbot för folkbokföring och inkomstdeklaration
- Maskininlärning för kontroll av samordningsnummer (missbruksdetektering)
- E-postsortering, analysverktyg för stora datamängder

### Transportstyrelsen
- Regelbaserad automatisering av körkortstillstånd (sedan länge)
- Brist: inga slumpmässiga manuella kontroller av automatiserade beslut (RiR 2020:22)

### Migrationsverket
- Planerar AI/LLM för att detektera missbruk av uppehållstillståndsansökningar
- **Högrisk-AI** under EU AI Act Annex III punkt 6 — kräver konformitetsbedömning

### Polismyndigheten
- Utredning om AI för ansiktsigenkänning i realtid (Ds 2025:7)
- Tangerar biometrisk massövervakning — förbjudet i EU AI Act Art. 5 i realtidsscenarier

### Pensionsmyndigheten
- Inga AI-verktyg i produktion för förmånshantering (ISF 2026:1)
- Tidig experimentfas

## AI-verkstaden (gov. uppdrag jan 2026)

FK + Skatteverket bygger förvaltningsgemensam AI-infrastruktur på regeringsuppdrag (jan 2026). Tas i bruk juli 2026. Syftar till gemensamma AI-tjänster för offentlig sektor.

Regeringsuppdrag: https://www.regeringen.se/regeringsuppdrag/2026/01/uppdrag-till-forsakringskassan-och-skatteverket-att-etablera-en-ai-verkstad-for-den-offentliga-forvaltningen/

## Systemövergripande mönster

1. **AI = beslutsstöd, inte beslutsfattare** — myndigheterna bedömer diskrimineringsrisken som för hög för AI i beslutsmoment
2. **Teknisk skuld dominerar IT-agendan** — hämmar ny AI-adoption
3. **Riskurval i gråzon** — AI för att välja ut ärenden för manuell kontroll påverkar reellt vilka som granskas
4. **Compliance-skuld inför EU AI Act** — riskklassificering och teknisk dokumentation saknas hos flera myndigheter

## Granskningsfrågor

1. Har myndigheter med AI-verktyg (SAMU, samordningsnummermodellen) riskklassificerat dem under EU AI Act?
2. Leder riskurval till systematisk överrepresentation av specifika grupper?
3. Uppfylls dokumentationskravet (Art. 13–14) för befintliga system?
4. Vad är governance och riskhantering i AI-verkstaden?

## Läs när

Anropa denna fil när du: granskar en specifik svensk myndighets AI-system och behöver veta vad de faktiskt använder, ska bedöma om ett system är känt sedan tidigare, eller ska kontextualisera ett uppdrag i det nationella AI-landskapet.
