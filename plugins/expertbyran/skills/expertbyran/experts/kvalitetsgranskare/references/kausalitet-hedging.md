# Kausalitetskrav och hedging — referens

## Designhierarki för kausalitetskrav

Vilken studiedesign krävs för att bära en viss typ av kausalitetspåstående?

| Påståendetyp | Minsta acceptable design |
|--------------|--------------------------|
| "X orsakar Y" / "X leder till Y" | RCT med adekvat power och låg risk of bias |
| "X har effekt på Y" | Stark kvasi-experimentell design (DiD, RDD, IV, SCM) med kontrollerade confounders |
| "X tyder starkt på effekt på Y" | Flera konvergenta väldesignade observationsstudier (kohort/case-control), låg confounding-risk |
| "X tyder på samband med Y" | Enstaka väldesignad observationsstudie med relevant justeringsstrategi |
| "X är förenligt med samband med Y" | Deskriptiv tvärsnittsdata eller process-tracing-fallstudie |
| "X väcker frågan om samband med Y" | Anekdotisk evidens, enstaka fall, expertbedömning |

## Vanliga kvasi-experimentella designer

- **DiD (Difference-in-Differences)** — jämför förändring i behandlad grupp med förändring i kontrollgrupp over tid. Kräver parallelltrend-antagandet.
- **RDD (Regression Discontinuity Design)** — utnyttjar en tröskel i en kontinuerlig variabel. Kräver att inga andra förändringar sker vid tröskeln.
- **IV (Instrumental Variables)** — instrument som påverkar behandling men inte utfall direkt. Kräver exklusions-restriktion och relevans.
- **SCM (Synthetic Control Method)** — konstruerar syntetisk kontrafaktisk enhet från vägd kombination av donatorer. Kräver god pre-period-matchning.
- **PSM (Propensity Score Matching)** — matchar behandlade och kontroller på sannolikheten att få behandling. Kräver att alla relevanta confounders är observerade (stark antagelse).

## Hedging-formuleringar — exempelbank

### Stark kausalitet (RCT-nivå)
- "Granskningen visar att X leder till Y."
- "Resultaten bekräftar ett kausalt samband mellan X och Y."

### Kvasi-experimentell design
- "Analysen tyder starkt på att X har haft effekt på Y."
- "De empiriska beläggen ger starkt stöd för att X påverkar Y."

### Väldesignad observationsstudie
- "Resultaten tyder på att X är associerat med Y."
- "Granskningen finner ett positivt samband mellan X och Y, vilket är förenligt med att X bidrar till Y."

### Deskriptiv data / fallstudie
- "Mönstret är förenligt med att X spelar en roll för Y."
- "Data utesluter inte att X påverkar Y, men tillåter inte att dra kausala slutsatser."

### Anekdotisk / expert-baserad
- "Det finns indikationer på att X kan ha samband med Y, men beläggen är otillräckliga för att dra slutsatser."
- "Enskilda fall väcker frågan om huruvida X bidrar till Y."

## Checklista för kausalitetsgranskning

1. Identifiera alla meningar med kausalt eller kvasi-kausalt språk.
2. Avgör vilket typ av påstående som görs (orsakar / leder till / tyder på / etc.).
3. Kontrollera att studiedesignen bär den kausalitetsnivå som påstås.
4. Om designen är för svag: föreslå hedgad omformulering från exempelbanken ovan.
5. Kontrollera att alternativa förklaringar (confounders, omvänd kausalitet, selektion) diskuteras.
