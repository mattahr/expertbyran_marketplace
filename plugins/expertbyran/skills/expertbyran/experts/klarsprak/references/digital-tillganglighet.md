# Digital tillgänglighet — referensmaterial

## Rättslig grund

**DOS-lagen (2018:1937)** — Lag om tillgänglighet till digital offentlig service genomför EU:s webbtillgänglighetsdirektiv. Offentliga aktörer ska uppfylla **WCAG 2.1 nivå AA** för webbplatser och digitalt publicerade dokument. DIGG (Myndigheten för digital förvaltning) utfärdar vägledning och utövar tillsyn.

Riksrevisionens rapporter i digitalt format — PDF på webb, HTML-version, interaktiva sammanfattningar — omfattas av DOS-lagen.

## Skrivregler för digital tillgänglighet (DT-1–DT-7)

**Regel DT-1: Semantisk rubrikhierarki**
Använd rubriknivåerna H1→H2→H3 efter logisk struktur, aldrig enbart för utseende. Hoppa inte över nivåer (H1 direkt till H3). Skärmläsare navigerar rapporten via rubriker — en trasig hierarki gör dokumentet oåtkomligt.
*WCAG 1.3.1 — Information och relationer*

**Regel DT-2: Meningsfulla alternativtexter**
Varje diagram, figur och tabell ska ha en alternativtext som förmedlar det faktiska budskapet (inte "diagram" eller "figur 3"). Komplexa diagram kräver dessutom en kompletterande textbeskrivning i brödtexten.
Formulering: "Antalet granskade myndigheter ökade från 12 till 47 under perioden 2018–2023" — inte "Stapeldiagram som visar ökning."
*WCAG 1.1.1 — Icke-textligt innehåll*

**Regel DT-3: Beskrivande länktext**
Länktext ska beskriva destinationen utan omgivande kontext. Skriv "Riksrevisionens rapport om statliga subventioner 2024 (PDF, 1,8 MB)" — inte "klicka här", "läs mer" eller "se bilaga". Filformat och storlek anges när det är relevant.
*WCAG 2.4.4 — Länkens syfte*

**Regel DT-4: Tillgängliga tabeller**
Datatabeller ska ha utpekade kolumn- och radrubriker som programmatiskt kopplas till cellerna. Undvik sammanslagna celler (colspan/rowspan) när det går — de bryter skärmläsarens navigering. Presentationstabeller (layout) ska markeras som dekorativa.
*WCAG 1.3.1*

**Regel DT-5: Färg som komplement, aldrig ensamt informationsbärare**
Använd aldrig färg som enda markör för information — t.ex. rött = problem, grönt = godkänt. Komplettera alltid med symbol, fetstil eller text. Textkontrast ska uppfylla AA-nivå: minst 4,5:1 mot bakgrunden (3:1 för stor text ≥18 pt).
*WCAG 1.4.1 — Användning av färg; 1.4.3 — Kontrast*

**Regel DT-6: Taggad och strukturerad PDF**
Rapporten ska exporteras som taggad PDF (Tagged PDF / PDF/UA). Läsordningen i PDF:en ska matcha den visuella ordningen. Dokumentspråket (svenska) ska vara deklarerat i dokumentegenskaperna. Bokmärken ska följa rubrikhierarkin.
*WCAG 1.3.2 — Meningsfull sekvens; DOS-lagen krav på tillgängliga dokument*

**Regel DT-7: Förklara förkortningar och akronymer vid första förekomst**
Skriv ut förkortningen första gången: "Myndigheten för digital förvaltning (DIGG)". Gäller i synnerhet lagbeteckningar, myndighetsakronymer och tekniska termer. I HTML-format kan `<abbr>`-elementet användas för maskinläsbar expansion.
*WCAG 3.1.4 — Förkortningar (god praxis på AA-nivå)*

## Tillämpning för granskningsrapporter

| Rapportdel | Tillgänglighetskrav |
|---|---|
| Sammanfattning | Fungera fristående; tydlig H1/H2-hierarki |
| Diagram och figurer | Alternativtext + förklaring i löptext |
| Tabeller med iakttagelser | Radrubriker = iakttagelse, kolumnrubriker = bedömningskriterier |
| Fotnoter | Ska ligga i läsordningen, inte enbart som visuell fotnot |
| Bilagor | Egna tillgänglighetsanpassade dokument, inte inskannade bilder |

## Europeiska tillgänglighetsakten (EAA) — Tillgänglighetslagen (2023:254)

**Rättslig grund:** Direktiv 2019/882, genomfört via Lagen (2023:254) om vissa produkters och tjänsters tillgänglighet och Förordningen (2023:676). Trädde i kraft **28 juni 2025**. Tillsynsmyndighet: Post- och telestyrelsen (PTS).

**Vem EAA täcker:** Privata tillverkare, importörer och tjänsteleverantörer — *inte* offentliga aktörer (de täcks av DOS-lagen). Kategorier: elektronisk kommunikation, e-handel, banktjänster, e-böcker, audiovisuella medietjänster, passagerartransport.

**Skillnad från DOS-lagen:**

| | DOS-lagen (2018:1937) | EAA/Tillgänglighetslagen (2023:254) |
|---|---|---|
| Tillsynsmyndighet | DIGG | PTS |
| Vem det gäller | Offentliga aktörer | Privata tillverkare/tjänsteleverantörer |
| Standard | WCAG 2.1 nivå AA | Funktionskrav (harmoniserade standarder) |
| Ikraftträdande | 2019 (stegvis) | 28 juni 2025 |

**Regel DT-8: EAA i upphandlad digital service**
När en myndighet upphandlar digitala tjänster som medborgare ska interagera med (e-handelslösning, bokningssystem, e-posttjänst, e-bok) ska förfrågningsunderlaget inkludera krav på EAA-överensstämmelse med hänvisning till Lagen (2023:254) och Förordningen (2023:676). Myndighetens egna dokument och webbplatser täcks av DOS-lagen — DT-1–DT-7 gäller oförändrat.
*Stöd i EAA art. 14; Tillgänglighetslagen 6 §; prop. 2022/23:42*
