# AI-assisterad kvalitativ analys

## Metodologiska grunddistinktioner

**Deduktiv kodning** — ett förutbestämt kodschema appliceras på materialet. LLM-stöd är metodologiskt försvarbart när:
- Kodschemat är explicit och väldefinierat
- Inter-rater reliability mäts: κ > 0,6 mot mänsklig bedömning krävs
- Reliabilitetsberäkning dokumenteras och redovisas

**Induktiv/reflexiv tematisk analys** (Braun & Clarke-traditionen) — teman uppstår ur materialet i iterativ dialog med forskaren. LLM-stöd är metodologiskt kontroversiellt. Braun m.fl. (2025) avvisar explicit användning av generativ AI för reflexiv TA med argumentet att reflexivitet förutsätter forskarens situerade erfarenhet och tolkningsansvar.

**Grundad teori** — kombination med AI är möjlig för kodning av substantiva koder men kräver att teoretisk sampling och memoskrivning förblir forskardriven.

## Valideringsmetoder

- **κ-jämförelse:** beräkna Cohens κ mellan LLM-kodning och mänsklig kodning på ett representativt urval (≥10 % av materialet, ≥20 enheter). Redovisa κ-värde och tolkningsregler.
- **Multi-LLM-konsistens:** samma prompt till flera modeller; avvikelser flaggas för mänsklig bedömning.
- **Anomalidetektion:** låt LLM identifiera potentiellt avvikande fall — men låt människa avgöra om det är ett genuint undantag eller feltolkning.

## Etiska dimensioner

- **Miljöpåverkan:** LLM-inferens är energikrävande. Proportionalitetsprincipen: använd inte LLM-kodning om manuell kodning är genomförbar inom projektets resurser.
- **Anonymitet och datasäkerhet:** kvalitativa transkript innehåller ofta känsliga uppgifter. Kontrollera att data inte används för modellträning. Pseudonymisera före eventuell uppladdning till externa tjänster.
- **Upphovsrätt:** om materialet är tredje parts text (t.ex. myndighetsrapporter) — bedöm upphovsrättslig status före behandling via extern API.
- **Transparens i rapportering:** redovisa explicit om och hur AI-stöd använts i analysen. Dölj det inte i allmänna formuleringer om "digitala verktyg".

## Riksrevisionen 4.4-tillämpning

Vid granskning av en studie som påstår sig ha använt AI-assisterad kvalitativ analys — kontrollera:
1. Vilken typ av analys? (deduktiv/induktiv) Är LLM-valet metodologiskt motiverat för den typen?
2. Redovisas κ eller annan reliabilitetsmåttning?
3. Diskuteras begränsningar och etiska aspekter?
4. Är slutsatserna spårbara till materialet, eller bygger de på LLM-output som "svart låda"?

## Källor

- Braun, V., Clarke, V., Boulton, E., Davey, L. & McEvoy, C. (2025). Artificial intelligence and reflexive thematic analysis. *Qualitative Research in Psychology*.
- arxiv:2511.14528 — systematisk genomgång av LLM-stödd kvalitativ kodning.
- CSCW LATA 2025 — workshop om LLM-assisterad tematisk analys.
- JMIR (2025) — κ-validering av LLM mot mänsklig kodning i hälsokontexten.
