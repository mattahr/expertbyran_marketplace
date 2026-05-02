# Bidragsanalys och bevisvärdering i effektivitetsrevision

## Problemet: kausalitet utan kontrafaktisk kontroll

Effektivitetsrevision riktar sig mot komplexa policy- och förvaltningsobjekt där randomiserade kontrollerade studier (RCT) sällan är möjliga. Logikmodellen — ett standardverktyg i designmatrisen — dokumenterar den förväntade kausala kedjan (insats → aktivitet → output → outcome), men *testar* inte kedjan.

När en granskare observerar att ett program genomförts och att ett önskat utfall inträffat, kvarstår frågan: bidrog programmet till utfallet, eller hände utfallet av andra skäl? Bidragsanalys ger ett strukturerat svar utan att kräva kontrafaktisk kontroll.

## Beviskaraktär i effektivitetsrevision (GUID 3920)

GUID 3920 (*The Performance Auditing Process*, INTOSAI 2019, ombenämning av ISSAI 3200) klargör att bevisning i effektivitetsrevision normalt är **persuasiv** (övertygande), inte **konklusiv** (bevisande).

- **Konklusiv bevisning:** logiskt nödvändig — slutsatsen följer med nödvändighet (t.ex. ett matematiskt bevis eller en kontradiktion).
- **Persuasiv bevisning:** pekar mot en slutsats utan att bevisa den logiskt nödvändigt. Det är det normala tillståndet vid komplexa granskningsobjekt — inte en svaghet.

**Implikationer för designmatrisen:**
- Indikatorer bör formuleras med hedging som matchar beviskaraktären. Om bevisningen för ett kriterium är persuasiv, formulera bedömningsgrunden med "borde normalt" eller "förväntas", inte "ska".
- Metodkapitlet bör specificera bevistyp per delfråga och hur triangulering hanterar den persuasiva karaktären.
- GUID 3920 kräver att revisorns professionella omdöme *dokumenteras* — inte bara vad bevisen visar, utan hur de tolkats.

## Bidragsanalys — Maynes metod (2001, 2012)

Bidragsanalys (contribution analysis) formulerades av John Mayne för Office of the Auditor General i Kanada — specifikt för revisions- och förvaltningsmiljöer, inte akademisk forskning. Det gör den direkt kompatibel med Riksrevisionens krav.

### Kärnan: bidragsanspråket

Istället för att isolera orsakssamband experimentellt byggs ett **bidragsanspråk** (contribution claim): insatsen bidrog med rimlig sannolikhet till det observerade resultatet, givet att:
1. En trovärdig **förändringsteori** (theory of change) kan formuleras
2. Bevisning stödjer att teorins kedja höll steg för steg
3. **Rivaliserande förklaringar** identifierats och i möjlig mån uteslutits

Det tredje steget är det centrala. Logikmodellen nämner ofta alternativa förklaringar som en reservation — bidragsanalysen kräver att de behandlas explicit som ett **metodologiskt krav**.

### De sex iterativa stegen (Mayne 2012)

1. **Definiera attribueringsproblemet** — vad vill vi påstå om insatsens bidrag?
2. **Formulera och dokumentera förändringsteori** — vilka mekanismer antas leda från insats till utfall?
3. **Samla bevisning** som bekräftar eller utmanar teorin länk för länk
4. **Bygga ett bidragsnarrativ** — sammanhängande resonemang om hur bevisningen stödjer teorin
5. **Söka ytterligare bevisning** för kvarstående luckor i narrativet
6. **Revidera narrativet** tills en trovärdig och rimlig redogörelse föreligger

Processen är iterativ: ny bevisning kan kräva att narrativet revideras och att nya bevisrundor genomförs.

### Samspelet med logikmodellen i designmatrisen

| Designmatriskolumn | Roll i bidragsanalysen |
|---|---|
| Revisionsfråga / delfråga | Definierar attribueringsproblemet (steg 1) |
| Bedömningsgrund / kriterium | Specificerar förväntad mekanism (steg 2) |
| Indikator | Mäter om mekanismen höll (steg 3) |
| Metodval | Bestämmer bevistyp och triangulering (steg 3–5) |

Rivaliserande förklaringar ska lyftas explicit i metodkapitlet, inte bara nämnas som en reservation i slutsatserna.

### Koppling till ISSAI 3000

ISSAI 3000 §136 kräver att revisorn tillämpar professionellt omdöme i sina slutledningar. Bidragsanalysens narrativ ger ett dokumenterat underlag för det omdömet: *varför* revisionsteamet bedömer att insatsen bidrog, och *hur* alternativa förklaringar hanterats.

GUID 3920:s fyra delar i en granskningsiakttagelse (kriterium, bevisning, orsak, effekt) korresponderar direkt mot bidragsanalysens logik — orsaks- och effektleden är de där kontrafaktiska antaganden och kausala anspråk görs, och där explicit hantering av rivaliserande förklaringar är mest kritisk.

### Gränser och formuleringsregel

Bidragsanalys ger ett **sannolikt bidrag**, inte ett bevisat orsakssamband.

**Rekommenderad formulering:** *"Insatsen bidrog sannolikt till utfallet, och vi har systematiskt bedömt alternativa förklaringar"* — aldrig *"insatsen orsakade utfallet"*.

Metoden fungerar bäst när:
- Teorin är relativt linjär och dokumenterbar
- Det finns tillgänglig bevisning för varje länk i kedjan
- De viktigaste rivaliserande förklaringarna är identifierbara

Den passar sämre för starkt komplexa systeminterventioner med många parallella mekanismer — där realist evaluation (CMO-konfiguration, se nedan) kan vara ett bättre alternativ.

## Realist evaluation — CMO-konfiguration (Pawson & Tilley 1997)

Realist evaluation är ett komplement när mekanismerna i sig är det primära granskningsobjektet. Kärnan är CMO-konfigurationen:

- **Context (C):** i vilka sammanhang fungerar insatsen?
- **Mechanism (M):** vad i insatsen utlöser förändring?
- **Outcome (O):** vad är utfallet av mekanismen i det sammanhanget?

CMO-konfigurationen gör mekanismerna explicita i designmatrisen. Istället för "fungerar programmet?" ställs frågan "vad fungerar, för vem, i vilka sammanhang?"

**Praktisk tillämpning:** CMO-konfiguration lämpar sig när det finns tydliga skillnader i utfall mellan grupper eller kontexter, och granskningsfrågan handlar om att förstå *varför* skillnaderna uppstår — snarare än om ett program *i genomsnitt* producerar ett önskat utfall.

## Triangulering och beviskonvergens

Oavsett om bidragsanalys eller CMO används kräver kausalitetspåståenden triangulering — att minst två datakällor konvergerar. Tre-källsmodellen:

1. **Dokument:** formella beslut, rapporter, styrdokument
2. **Intervjuer:** insiders och målgrupp, för att förstå mekanismer och kontext
3. **Register/data/observation:** kvantitativt underlag, ofta nödvändigt för att bedöma utfall

**Divergensprincipen:** när källa 1 och 2 konvergerar men källa 3 avviker, är avvikelsen metodologiskt viktigare än konvergenspunkterna — det är där djupare analys behövs.

## Primärkällor

- Mayne, J. (2001). *Addressing attribution through contribution analysis.* Canadian Journal of Program Evaluation.
- Mayne, J. (2012). *Contribution Analysis: Coming of Age?* Evaluation, 18(3), 270–280.
- Lemire, R. & Mayne, J. (2020). *Contribution Analysis in Practice.*
- INTRAC (2017). *Contribution Analysis.* Praxis Note.
- Pawson, R. & Tilley, N. (1997). *Realistic Evaluation.* SAGE.
- GUID 3920 (INTOSAI, 2019). *The Performance Auditing Process.* issai.org.
