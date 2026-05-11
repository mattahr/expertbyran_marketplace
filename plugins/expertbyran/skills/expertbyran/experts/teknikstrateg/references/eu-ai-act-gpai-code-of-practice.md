# EU AI Act — GPAI Code of Practice och tillsynsstruktur 2026

Referensmaterial för GPAI-spåret (general-purpose AI) inom EU AI Act: styrlogik, Code of Practice som efterlevnadsinstrument och den svenska tillsynsstrukturen. Kompletterar `references/eu-ai-act-strategisk-analys.md` med fokus på *governance och tillsyn*, inte den bredare högrisktidslinjen.

## Tidslinje att hålla isär

- **1 augusti 2024** — AI-förordningen (EU) 2024/1689 träder i kraft.
- **10 juli 2025** — AI Office publicerar slutversionen av GPAI Code of Practice. Frivilligt instrument för att visa efterlevnad av Article 53/55, framtaget i flerintressentprocess och endorserat av kommissionen och AI Board 2025-08-01.
- **2 augusti 2025** — GPAI-modellreglerna blir tillämpliga. Modeller som släpps efter datumet träffas direkt; modeller som redan fanns på marknaden får övergång till **2 augusti 2027**.
- **2 augusti 2026** — AI Act:s bredare tillsynsmaskineri ska vara operativt. Medlemsstaterna ska ha utsett behöriga marknadskontrollmyndigheter; högrisk- och styrningsbestämmelser börjar tillämpas brett. Sandlådekrav: en regulatorisk AI-sandlåda ska finnas på plats senast detta datum.

## GPAI som styrningsfråga — Article 53/55

- **Article 53** — generella skyldigheter för alla GPAI-leverantörer: teknisk dokumentation till AI Office och nedströmsleverantörer, publicerad sammanfattning av träningsdata, copyright compliance-policy.
- **Article 55** — skärpta skyldigheter för leverantörer av GPAI med *systemrisk*: standardiserade modellutvärderingar inkl. adversarial testing, riskbedömning och riskreducering på unionsnivå, incidentrapportering till AI Office utan onödigt dröjsmål, tillräcklig cybersäkerhet för modell och fysisk infrastruktur.
- **Systemrisktröskel: 10^25 FLOP träning** — modeller som tränats med beräkningsbudget över tröskeln *presumeras* utgöra systemrisk. Gruppen omfattar idag 5–15 leverantörer globalt.

## Code of Practice — struktur

Tre kapitel:

1. **Transparency** — gäller alla GPAI-leverantörer.
2. **Copyright** — gäller alla GPAI-leverantörer.
3. **Safety & Security** — gäller endast leverantörer av systemriskmodeller.

Det är AI Office:s anvisade operationaliseringsväg för Article 53/55-skyldigheter. Användning är frivillig men ger presumption om efterlevnad.

## Svensk tillsynsstruktur — SOU 2025:101

Utredningen *Anpassningar till AI-förordningen — Säker användning, effektiv kontroll och stöd för innovation* (SOU 2025:101, överlämnad 2025-10-06) föreslår en multi-myndighetsmodell:

- **PTS** — föreslås få huvudansvar för tillsyn enligt AI-förordningen samt rollen som samordnande myndighet och gemensam kontaktpunkt.
- **IMY** — ansvarar för förbjudna AI-system och behåller dataskyddstillsynen.
- **Finansinspektionen** — delar ansvar för högrisksystem enligt bilaga III.
- **Nio sektorsmyndigheter** — tillsyn över högrisksystem enligt bilaga I (sektorsspecifika).

Strukturen innebär överlappande gränssnitt: PTS, IMY, Finansinspektionen och nio sektorsmyndigheter måste etablera operativa rutiner före 2026-08-02 för att inte governance ska falla mellan stolarna.

## Granskningsperspektiv

GPAI-spåret blir granskningsbart när frågan flyttas från "är modellen smart?" till:

- Vem bär det faktiska ansvaret för att GPAI-relaterad dokumentation finns och är uppdaterad?
- Hur verifieras training data summary, copyright-policy och incidentrapportering i praktiken?
- Finns ett svenskt tillsynsupplägg som är begripligt för myndigheter som köper eller bygger på utländska GPAI-modeller?
- Är ansvarsfördelningen PTS / IMY / Finansinspektionen / sektorsmyndighet dokumenterad i myndighetens egna AI-styrdokument, eller endast som referens till SOU 2025:101?
- Hur hanteras *kedjestyrning* — kopplingen EU AI Office → svensk tillsynsmyndighet → deployer/myndighet?

## Källor

- Förordning (EU) 2024/1689 — AI-förordningen. <https://artificialintelligenceact.eu/>
- Article 53. <https://artificialintelligenceact.eu/article/53/>
- Article 55. <https://artificialintelligenceact.eu/article/55/>
- AI Office, *EU AI Act: General-Purpose AI Code of Practice — Final Version* (2025-07-10). <https://digital-strategy.ec.europa.eu/en/policies/contents-code-gpai> ; <https://code-of-practice.ai/>
- Latham & Watkins, *EU AI Act: GPAI Model Obligations in Force and Final GPAI Code of Practice in Place*. <https://www.lw.com/en/insights/eu-ai-act-gpai-model-obligations-in-force-and-final-gpai-code-of-practice-in-place>
- Covington Global Policy Watch, *AI Office Publishes Final Version of the Code of Practice for General-Purpose AI Models*. <https://www.globalpolicywatch.com/2025/07/ai-office-publishes-final-version-of-the-code-of-practice-for-general-purpose-ai-models/>
- SOU 2025:101. <https://regeringen.se/rattsliga-dokument/statens-offentliga-utredningar/2025/10/sou-2025101/> (PDF: <https://www.regeringen.se/contentassets/759c2d42b55843c587bfbc93540f4daa/anpassningar-till-ai-forordningen-sou-2025101.pdf>)
- IMY, sammanfattning av tillsynsförslagen. <https://www.imy.se/vanliga-fragor-och-svar/vilken-myndighet-kommer-overvaka-ai-forordningen-i-sverige/>
