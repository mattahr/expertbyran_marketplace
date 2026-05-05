# Process tracing i effektivitetsrevision

Process tracing (PT), formulerad i sin moderna form av Beach & Pedersen (2013, 2019) och vidareutvecklad för utvärdering av Befani & Mayne (2014), Schmitt & Beach (2015) och Beach & Raimondo (World Bank IEG 2020), är en *case-based, theory-driven* metod för kausal slutledning *inom* enskilda fall. Till skillnad från contribution analysis (CA), som bygger ett *narrativt* bidragsanspråk, gör PT den probabilistiska logiken bakom slutledningen explicit: varje observation värderas mot hur sannolik den är givet hypotesen jämfört med rivaliserande hypoteser (Bayesiansk uppdatering).

## När PT är relevant i revision

Effektivitetsrevision arbetar nästan alltid med *generativ* kausalitet (mekanismbaserad), inte *kontrafaktisk* (RCT-baserad). De redan etablerade metoderna i fältet — triangulering enligt GUID 3920, contribution analysis, realistic evaluation — antar mekanismbaserad kausalitet men varierar i hur explicit logiken bakom enskilda evidensbedömningar är. PT är den metod som gör *evidensbedömningen* mest explicit.

Praktisk vinst: PT ger ett gemensamt språk när granskningsteamet diskuterar *varför* ett visst bevis är starkt eller svagt — något som annars ofta hanteras implicit i bedömningssamtalen.

PT är särskilt lämpligt vid:
- Granskningar av implementation och komplexa styrkedjor
- AI-/algoritmiska beslutssystem där input → modell → output → beslut måste specificeras stegvis
- Granskningar där triangulering behöver formaliseras
- Förstudier där kausalkedjan bakom en bedömningsgrund är oklar

## Tre varianter (Beach & Pedersen)

| Variant | Givet | Söks | Revisionell tillämpning |
|---------|-------|------|------------------------|
| Theory-testing PT | Mekanism + utfall | Verifiering av mekanismen i fallet | Test av programteori bakom bedömningsgrund |
| Theory-building PT | Orsak + utfall | Mekanism | Förstudier (steg 1.1–1.4) |
| Explaining-outcome PT | Endast utfall | Fullständig fallförklaring | "Varför uppnåddes inte målen?" |

## De fyra bevistesterna (Van Evera, Bennett, Collier)

Tester klassificeras längs två dimensioner: är observationen *nödvändig* för hypotesen och *unik* för den?

| Test | Nödvändig? | Unik? | Pass | Fall |
|------|------------|-------|------|------|
| Straw-in-the-wind | Nej | Nej | Svagt stöd; konvergerande straws ger affirmativ tyngd | Inget |
| Hoop test | Ja | Nej | Hypotesen lever vidare | Eliminerar hypotesen |
| Smoking gun | Nej | Ja | Stark konfirmation | Ingen elimination |
| Doubly decisive | Ja | Ja | Bekräftar och utesluter alla alternativ | Eliminerar |

**Tillämpning i designmatrisen:** klassificera *varje* indikator/bevis i evidenskolumnen efter testtyp. Det är ett konkret tillägg utöver GUID 3920:s persuasiv/konklusiv-distinktion: revisorn anger inte bara *vilken* bevisning som krävs utan *vilken inferentiell styrka* den ger. Ett hoop-test för en delfråga måste passeras för att bedömningsgrunden ska kunna anses uppfylld; ett smoking gun ger stark konfirmation även om det är ensamt.

## Process tracing vs. contribution analysis

| Dimension | Contribution analysis (Mayne) | Process tracing (Beach & Pedersen) |
|-----------|------------------------------|-----------------------------------|
| Slutledningslogik | Narrativ koherens | Bayesiansk uppdatering |
| Kausalitetsbegrepp | Generativt; "bidrog sannolikt till" | Generativt; mekanismbaserat |
| Specificitetskrav | Identifiera och bemöta rivaliserande förklaringar | Specificera mekanismen i kausala steg, testa varje |
| Bevisbehandling | Triangulering, narrativ koherens | Klassificering per evidens (straw/hoop/smoking gun) |
| Vanlig svaghet | Vag mekanismbeskrivning | Hög arbetsinsats per fall |

**Befani & Mayne (2014) och Schmitt & Beach (2015) argumenterar att de är komplement, inte substitut:** CA ger den övergripande strukturen och narrativet; PT ger den explicita logiken för enskilda evidenstest inom narrativet.

**Praktiskt mönster i designmatrisen:**
- Använd CA-strukturen som ramverk för delfrågan och förändringsteorin
- Använd PT-tester som klassificering av indikatorerna och bevisplanen
- Dokumentera mekanismen som kausala steg, inte bara start och slut

## Praktisk arbetsgång

1. **Specificera mekanismen som hypotes.** Bryt ned bedömningsgrunden i kausala länkar (X → M₁ → M₂ → Y), inte bara start och slut. Varje länk ska vara observerbar.
2. **Formulera observerbara implikationer per länk.** Vad *borde* vi se i dokument/data/intervjuer om länken faktiskt fungerar?
3. **Klassificera varje observation i förväg** som straw-in-the-wind, hoop, smoking gun eller doubly decisive — det styr designmatrisens metodval och datainsamlingens prioritering.
4. **Specificera rivaliserande mekanismer explicit.** Annars riskerar PT att bekräfta den enda hypotes man tänkt på. Detta är samma krav som CA ställer på alternativa förklaringar, men formuleras här som mekanismer, inte påståenden.
5. **Uppdatera bedömningen efter datainsamling.** Hoop-fall = mekanismen kan förkastas; konvergerande straws = inkrementell konfirmation; smoking gun = stark konfirmation; doubly decisive = avgörande.

## När PT *inte* lämpar sig

- **Statistiska populationsanspråk** — PT är inom-fall, inte mellan-fall
- **Renodlad compliance audit (ISSAI 4000)** — regelefterlevnad räcker; PT är overkill
- **Glesa primärdata** — PT kräver tät, granulär evidens per länk
- **Uppenbar mekanism** — formalismen blir då overhead utan tillkommande inferentiell styrka

## Kopplingar till annan revisionsmetodik

- **Triangulering (GUID 3920):** PT formaliserar varför viss konvergens är starkare än annan — straw-in-the-wind-konvergens från tre källor är fortfarande svagare än ett smoking gun från en källa.
- **Realistic evaluation (CMO):** mekanismen i CMO-konfigurationen är just det PT testar; CMO ger struktur, PT ger evidenstest.
- **Abduktiv slutledning / hedging:** PT:s testtypologi ger ett explicit språk för hedging i rapporten ("indicerar"/"ger starkt stöd för"/"bekräftar entydigt").
- **Bidragsanalys:** se separat referensfil; CA och PT integreras enligt Befani & Mayne 2014.

## Primärkällor

- Beach, D. & Pedersen, R. B. (2013/2019). *Process-Tracing Methods: Foundations and Guidelines* (2 uppl.). University of Michigan Press.
- Beach, D. & Raimondo, E. (2020). *Process-Tracing Methods in Program Evaluation.* World Bank IEG report.
- Befani, B. & Mayne, J. (2014). "Process Tracing and Contribution Analysis: A Combined Approach to Generative Causal Inference for Impact Evaluation." *IDS Bulletin* 45(6), 17–36.
- Schmitt, J. & Beach, D. (2015). "The contribution of process tracing to theory-based evaluations of complex aid instruments." *Evaluation* 21(4), 429–447.
- Wauters, B. & Beach, D. (2018). "Process tracing and congruence analysis to support theory-based impact evaluation." *Evaluation*.
- Collier, D. (2011). "Understanding Process Tracing." *PS: Political Science & Politics* 44(4), 823–830.
- Bennett, A. (2010). "Process Tracing and Causal Inference." I Brady & Collier (red.) *Rethinking Social Inquiry*.
