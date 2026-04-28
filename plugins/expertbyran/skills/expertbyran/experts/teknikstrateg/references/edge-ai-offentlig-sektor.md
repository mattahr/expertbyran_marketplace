# Edge-AI i offentlig sektor — TRL-positionering och skalbarhetsgap

*Källa: fortbildning EXP-1102, april 2026. Data från Edge AI and Vision Alliance, Omdia, MDPI, Barbara.tech, EU AI Act.*

---

## Vad är edge-AI?

AI-modeller som körs lokalt på enheter nära datakällan — i IoT-enheter, kameror, fordon, sensorer — snarare än i centrala molnmiljöer. Fördelen är lägre latens, reducerad dataöverföring och möjlighet att operera utan kontinuerlig nätverksuppkoppling.

---

## TRL-positionering 2024–2025

Edge-AI befinner sig på **TRL 7–8** för mogna applikationer (bildanalys, objektigenkänning, taligenkänning) men sjunker till **TRL 5–6** för mer avancerade användningsfall:

| Användningsfall | TRL-intervall |
|-----------------|---------------|
| Bildanalys och objektigenkänning | 7–8 |
| Prediktivt underhåll (industriell IoT) | 7 |
| Federerad inlärning (distribuerad träning) | 5–6 |
| Privacy-preserving inference på heterogen hårdvara | 5–6 |
| Autonom beslutsfattning i kritisk infrastruktur | 4–5 |

**Konsekvens:** Teknisk grundprestanda är bevisad för kärnfunktioner. Kvarvarande problem är inte tekniska — de är implementerings- och ekosystemproblem.

---

## Skalbarhetsgapet — de fyra primära hindren

Marknadsdata bekräftar ett strukturellt skalbarhetsgap: drygt 50% av företag förväntas ha adopterat edge computing 2025, men färre än en tredjedel rapporterar fullt driftsatta lösningar. I industriella miljöer staller ~70% av Industry 4.0-projekt i pilotfas.

**Fyra drivande faktorer:**

1. **Orkestreringsutmaningar** — modellsdriftsättning i distribuerade, heterogena miljöer saknar mogna standarder. Versionshantering, rollback och A/B-testning av modeller på tusentals edge-enheter är olöst.

2. **Energieffektivitetskrav** — AI-inferens är energikrävande. Standardhårdvara möter inte kraven för batteridriven eller passivt kyld edge-hårdvara.

3. **EU AI Act-compliance** — edge-AI som fattar beslut om individer (t.ex. biometrisk identifiering, tillståndsbedömning) kan klassificeras som högrisk och kräva conformity assessment, loggsystem och mänsklig tillsyn.

4. **Brist på standardiserade edge-plattformar** — ingen dominant plattform för säker livscykelhantering av edge-AI-enheter. Fragmenterat ekosystem ökar integrations- och underhållskostnader.

---

## Halvledarberoende för edge-AI

Edge-AI-hårdvara är beroende av specialiserade processorer:
- **AI-processorer (NPU/TPU):** domineras av Qualcomm, Apple, MediaTek — TSMC-tillverkade
- **Neuromorphic chips:** Intel Loihi, IBM TrueNorth — relativt nisch
- **Industriell edge-AI-hårdvara:** NVIDIA Jetson, Google Coral — TSMC-baserade ekosystem

**EU:s Chips Act-effekt inom 5-årshorisont:** EU:s kapacitetsökning till 20% marknadsandel 2030 minskar men eliminerar inte TSMC-beroendet för edge-AI-hårdvara. Europeiska alternativ (STMicroelectronics, Infineon) täcker i huvudsak mognare noder och är inte direkt utbytbara mot cutting-edge NPU:er.

**Rekommendation:** Diversifiera hårdvaruleverantörsbasen och säkerställ kompatibilitet med europeiska alternativ parallellt med TSMC-baserade ekosystem.

---

## Fasindelad plan för offentlig sektors 5-årshorisont (2024–2029)

### Fas 1: Kompetensuppbyggnad och standardisering (2024–2026)

**Prioriteringar:**
- Inventera befintliga use cases och bedöm TRL-nivå
- Bygg intern kompetens i edge-AI-arkitektur och EU AI Act-compliance
- Välj en begränsad edge-plattform (standardisera tidigt — plattformsskifte är dyrt)
- Starta kontrollerade pilotprojekt med tydliga use cases:
  - Bildanalys för anläggningssäkerhet (TRL 7–8, relativt låg compliance-risk)
  - IoT-baserad tillståndsbedömning av infrastruktur (TRL 7)
- Etablera governance: modellregister, loggning, incident-rapporteringsrutiner

**Vad man undviker i fas 1:**
- Storskalig driftsättning utan standardiserad plattform
- Use cases som klassificeras som högrisk-AI utan compliance-plan

### Fas 2: Kontrollerad skalning (2026–2028)

**Förutsättningar för övergång:**
- Pilot har levererat mätbara resultat mot definierade KPI:er
- Compliance-ramverk etablerat och testat
- Plattformsstandardisering klar

**Prioriteringar:**
- Skala ut beprövade use cases till fler enheter/platser
- Integrera edge-AI med centrala system via standardiserade API:er
- Utvärdera halvledarberoenden och börja diversifiera mot europeiska alternativ

### Fas 3: Full driftsättning och ekosystemintegration (2028–2029)

- Skalat, standardiserat edge-AI som stödjande kapacitet i kärnverksamheten
- Aktiv deltagare i nationella och europeiska plattformsekosystem (Gaia-X, Edgeless Systems)
- Kontinuerlig TRL-uppföljning av ny edge-AI-teknik

---

## Nyckelinsikt för bedömningar

**Edge-AI 2024 är inte en teknologisk fråga — det är en implementerings- och ekosystemfråga.** Den offentliga myndighet som lyckas lösa TRL 7→9-övergången internt skapar ett hållbart försprång i digitalisering under resten av decenniet.

---

## Källor

- **Edge AI and Vision Alliance**: Teknisk referens för edge-AI-deployment och hårdvarustandarder.

- **Omdia — Technology Analysis: AI Edge Platforms**: Marknadsdata om adoption och skalbarhetshinder.

- **MDPI (peer-reviewed)**: Akademisk litteratur om federerad inlärning och privacy-preserving inference.

- **Barbara.tech**: Industriell edge-AI-deployment — praktiska implementeringserfarenheter.

- **EU AI Act (Förordning EU 2024/1689)**: Compliance-krav för edge-AI-system, särskilt högrisk-klassificering.
