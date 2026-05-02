# AI-genererade myndighetstexter — granskningsmodell

## Bakgrund och fokus

AI-genererade myndighetstexter uppvisar systematiska mönster som skiljer sig från traditionellt byråkratspråk. Nominalisering och passiv form är välkända problem, men AI lägger till tre nya riskdimensioner: hallucination (falsk precision i siffror och citat), generiska mallfraser som låter korrekta men är innehållslösa, samt kontextuell anonymitet — text som kunde stå i vilket dokument som helst. Språkrådets riktlinjer täcker de flesta traditionella problemen men behöver kompletteras med faktaverifiering och ett explicit kontextankringstest.

**Viktig distinktion:** Faktaverifiering ska alltid komma *innan* klarspråksgranskning — felaktig text kan aldrig bli ett bra dokument oavsett hur välskriven den är.

## Checklista AI-1 till AI-9

**AI-1: Faktaverifiering** *(AI-specifikt — täcks INTE av Språkrådets riktlinjer)*
Kontrollera alla siffror, datum, namn, laghänvisningar och citat mot primärkällan.

**Fyra typer av faktafel i AI-text — kräver olika verifieringsstrategier:**

| Feltyp | Karaktär | Verifieringsstrategi |
|---|---|---|
| **Konfabulation** | AI fyller statistiska luckor med plausibla men påhittade uppgifter. Icke-reproducerbar. | Kontrollera *alltid* mot primärkällan — uppgiften kan vara helt påhittad. |
| **Systematisk träningsfelaktighet** | Modellen är konsekvent fel p.g.a. fel i träningsdata. Reproducerbar. | Ifrågasätt uppgifter som verkar ovanliga men formuleras med säkerhet. |
| **Föråldrad information** | Korrekt vid träningskutoff men nu inaktuell (lagändring, ny statistik). | Kontrollera datum på refererad lagstiftning mot SFS och Riksdagens webbplats. |
| **Kontextuell missapplicering** | Korrekt information applicerad på fel situation. | Stäm av att lagregler och begrepp faktiskt avser det aktuella ärendet. |

**Varningssignal:** MIT-forskning (2025) visar att AI använder 34 % mer auktoritativt språk i konfabulerade svar än i korrekta. Hög säkerhet i formuleringen är *inte* ett tecken på korrekthet — snarare tvärtom.

*Termen "konfabulation" är mer korrekt än "hallucination": modellen "ser" inget som inte finns utan konstruerar plausibla påståenden ur statistiska mönster.*

---

**AI-2: Anonyma aktörer**
Identifiera alla passivkonstruktioner. Sätt in den faktiska aktören.
- "Det bedöms att" → "Riksrevisionen bedömer att"
- "Åtgärder har vidtagits" → "Myndigheten X har vidtagit åtgärder"

---

**AI-3: Nominalisering**
Sök efter substantiverade verb med ändelserna `-ning`, `-ande`, `-else`, `-tion`, `-itet`.
- "Genomförande av uppföljning av" → "följa upp"
- "Säkerställande av efterlevnad" → "säkerställa att reglerna följs"

---

**AI-4: AI-typiska mallfraser**
Identifiera och stryk fraser som fyller utrymme utan att tillföra innehåll:

| Stryk | Ersätt med |
|---|---|
| "Det bör noteras att" | — (gå direkt till påståendet) |
| "Det är viktigt att framhålla att" | — |
| "I detta sammanhang" | — |
| "Som nämnts ovan" | Repetera substantivet eller hänvisa specifikt |
| "Vidare kan konstateras att" | — |
| "Det är av stor vikt att" | — |
| "I syfte att" | "För att" |
| "Med anledning av ovanstående" | Specificera vad som avses |

---

**AI-5: Metatextrensning**
Stryk stycken som beskriver vad texten ska göra istället för att göra det.
- "Rapporten syftar till att belysa..." → börja med belysningen
- "I följande avsnitt redogörs för..." → börja med redogörelsen

---

**AI-6: Specificeringstest**
Fråga för varje mening: Kan den stå oförändrad i en rapport om ett helt annat ämne? Om ja — den är för generell.
- Specificera vem, vad, när, hur mycket
- Byt ut "verksamheten" mot myndighetens namn
- Byt ut "ökade nivåer" mot faktiska siffror

---

**AI-7: Terminologikonsistens**
Välj ett begrepp för varje entitet och håll fast vid det. AI varierar synonymer utan att markera betydelseskillnad:
- myndighet / aktör / organisation / instans — menar de samma sak?
- granskning / revision / kontroll / tillsyn — är det samma process?

---

**AI-8: Kontextuell förankring** *(AI-specifikt — täcks INTE explicit av Språkrådets riktlinjer)*
Kontrollera att texten är anpassad till det specifika uppdragets faktiska iakttagelser:
- Återspeglar texten det vi faktiskt såg i vår granskning?
- Är exemplen hämtade från de faktiska fallen, eller är de hypotetiska?
- Speglar rekommendationerna de specifika bristerna vi identifierat?

---

**AI-9: Generisk mottagare** *(AI-specifikt förstärkning)*
AI tenderar att använda tredjepersonstermer ("den sökande", "den enskilde") även i text riktad direkt till läsaren.

| Generisk form (stryk) | Direkt tilltal (använd) |
|---|---|
| "Den sökande ska lämna in..." | "Du ska lämna in..." |
| "Den enskilde har rätt att..." | "Du har rätt att..." |
| "Förmånstagaren informeras om..." | "Vi informerar dig om..." |

**Undantag — behåll tredjeperson i:**
- Lagtext och formella beslut (juridisk precision kräver tredjeperson)
- Text om en frånvarande part ("Arbetsgivaren ska meddela den anställde")
- Sammanfattningar av regler i utredningar och propositioner

## Täckningsanalys: Språkrådets riktlinjer vs AI-checklistan

| Checklista | Täcks av Språkrådet | Notering |
|---|---|---|
| AI-1 Faktaverifiering | Nej — nytt komplement | Utanför traditionell klarspråksgranskning |
| AI-2 Anonyma aktörer | Ja (aktiv form) | AI gör det mer systematiskt |
| AI-3 Nominalisering | Ja | AI producerar fler per mening |
| AI-4 Mallfraser | Delvis | AI-specifika fraser kräver egen lista |
| AI-5 Metatext | Delvis | AI-mönster är distinkt nog |
| AI-6 Specificeringstest | Ja (konkret framför abstrakt) | Behöver explicit test för AI |
| AI-7 Terminologikonsistens | Ja | AI gör fler synonymbyten. Nästan hälften av svenska myndigheter arbetar nu aktivt med terminologi (ISOF 2025, upp från ~15 % 2019) — men risken är ojämnt fördelad |
| AI-8 Kontextuell förankring | Nej — nytt komplement | Implicit i klarspråk men behövs explicit |
| AI-9 Generisk mottagare | Delvis (direkt tilltal) | AI gör det mer systematiskt |

## De tre kärnmönstren i AI-text

**Mönster 1 — Passivkonstruktioner utan agent (AI-2)**
Konkret mätvärde: en välskriven myndighetstext har max 20 % passiva konstruktioner. AI-text kan ligga på 40–60 %. Metod: identifiera alla passivkonstruktioner och ställ frågan "Vem gör detta?".

**Mönster 2 — Substantiveringskedjor (AI-3)**
Typstruktur: "genomförande av X-ificering av Y-hantering av Z". Tre substantiv i rad = röd flagga. EU-guiden rekommenderar 15–20 ord som riktlinje för meningslängd.

**Mönster 3 — Generisk mottagare (AI-9)**
Sök på "den sökande", "den enskilde", "förmånstagaren" och "mottagaren" — är dessa ersättningsbara med "du"?

## Hur Riksrevisionen bör tänka kring AI-stödd rapportskrivning

**Grundposition:** AI är ett verktyg för utkast, aldrig för slutprodukt. Den institutionella form som vuxit fram för detta är "expert-in-the-loop": AI genererar utkast, human expert verifierar och bearbetar (Språkbolaget 2025; SOU 2025:13). Det är inte en kompromiss — det är en metod.

**Fem konkreta principer:**
1. **Faktaverifiering är inte förhandlingsbar (AI-1):** Konfabulation sker utan varning.
2. **Iakttagelserna kan inte genereras (AI-8):** AI-utkast av metodkapitel och bakgrundstexter är rimliga. Rekommendationer och iakttagelsekapitel är inte det.
3. **Dokumentera AI-användningen:** Revision kräver transparens och spårbarhet.
4. **Klarspråksgranskning skärps, inte lättas:** AI-genererade avsnitt kräver granskning mot hela AI-1–AI-9-checklistan.
5. **Ansvarsprincipen hålls synlig:** Riksrevisionens rapporter är revisorns fagliga bedömning — AI tar inte ställning.

## Nationellt regelverk — luckor

**DIGG/IMY:s nationella riktlinjer för generativ AI** (jan 2025): 18 riktlinjer under åtta rubriker. Adresserar *inte* klarspråk, språklig kvalitet eller transparens om AI-genererat innehåll.

**Tydlig lucka:** Ingen nationell vägledning kopplar generativ AI till klarspråkskravet i språklagen ("vårdat, enkelt och begripligt").

**AI-förordningen (EU 2024/1689), artikel 50:** Myndigheters AI-genererade texter som mänskligt granskats är undantagna märkningsplikten — men transparensfrågan kvarstår ur förtroendesynpunkt.

**Kungliga bibliotekets språkmodellsuppdrag** (sep 2025, slutrapport juni 2026): Regeringen gav KB uppdraget att analysera och förbereda för bredare användning av svenska språkmodeller i offentlig sektor. Budget: 40 Mkr. KB samarbetar med Språkbanken (Göteborgs univ.). Fokus: infrastruktur och "svensk språklig suveränitet" — *inte* klarspråk eller textkvalitet. Luckan kvarstår: de svenska språkmodeller som myndigheterna framöver kan använda innehåller inga inbyggda klarspråkskrav.

**ISOF — klarspråk och terminologi** (enkät höst 2025, resultat mars 2026): Nästan hälften av svenska organisationer arbetar nu aktivt med terminologi som kvalitetsarbete — kraftig ökning jämfört med ~15 % i 2019 års enkät. Klarspråksarbetet pågår i drygt hälften av myndigheterna. Ingen specifik vägledning från Språkrådet om AI-genererade texter har identifierats 2024–2026.

**Internationellt referensexempel — USA (april 2026):** GovProTech US Org Solutions lanserade den första dedikerade AI-drivna plain language compliance-plattformen för amerikanska myndigheter. Granskar dokument mot Federal Plain Language Guidelines på sex dimensioner: målgruppspassning, logisk struktur, meningskomplexitet, jargontäthet, aktiv form och handlingsbarhet. Sverige har motsvarande rättslig grund i språklagen (2009:600) § 11 men saknar en liknande institutionell plattformsinfrastruktur.
