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

## RiR-specifik hedging-kalibrering

Tre återkommande brister i Riksrevisionens effektivitetsrevisioner, med
kalibrerade omformuleringar.

### Brist 1 — Registerdata + kausalt påstående utan jämförelsegrupp

**Ursprungsformulering (typexempel):**
> "Granskningen visar att bristen på uppföljning leder till att individer
> faller ur systemen."

**Problem:** registerdata utan kontrafaktisk jämförelsegrupp bär inte ett
"leder till"-påstående. Konfunderat med selektion (de som faller ur kan
skilja sig systematiskt från de som stannar kvar).

**Kalibrerad omformulering:**
> "Granskningen finner att individer som inte följs upp i högre utsträckning
> lämnar systemen. Sambandet är förenligt med att uppföljningsbrister bidrar
> till systemavgång, men alternativa förklaringar — inklusive att de som
> lämnar frivilligt undviker uppföljning — kan inte uteslutas med tillgängliga
> data."

---

### Brist 2 — Intervjudata → strukturell slutsats

**Ursprungsformulering (typexempel):**
> "Granskningen visar att Arbetsförmedlingens styrning är otydlig."

**Problem:** slutsatsen om *strukturell otydlighet* bygger på utsagor från
ett strategiskt urval tjänstemän. Intervjudata bär en beskrivande slutsats
om upplevd otydlighet — inte en strukturell slutsats om styrsystemet som
helhet.

**Kalibrerad omformulering:**
> "Intervjuade handläggare och chefer beskriver styrningen som otydlig i
> fråga om X och Y. Granskningen har inte kunnat verifiera dessa upplevelser
> mot strukturella data, men mönstret är konsistent och pekar på att
> otydligheten är systematisk snarare än individuell."

---

### Brist 3 — Underspecificerade effektivitetskriterier i slutsats

**Ursprungsformulering (typexempel):**
> "Granskningen visar att insatsen inte är effektiv."

**Problem:** "effektiv" är inte definierat i slutsatsen. Effektiv i förhållande
till vad? Vilket utfall, vilken tidhorisont, vilken målgrupp?

**Kalibrerad omformulering:**
> "Granskningen finner inte stöd för att insatsen uppnår sitt angivna mål
> [specificera mål] inom den granskade perioden [specificera period] för
> målgruppen [specificera]. Evidensen är otillräcklig för att bedöma
> insatsens effektivitet för delmålgruppen [X] eller på längre sikt."

---

## Kalibrering mot evidenshierarkins svagaste länk

En slutsats är aldrig starkare än det svagaste ledet i beviskedjan. Regel:

1. Identifiera alla evidenskällor som bär slutsatsen.
2. Klassificera varje källa i evidenshierarkin (primär / sekundär / tertiär).
3. Hedga slutsatsen mot den *svagaste* källan — inte den starkaste.
4. Om en sekundär källa (granskningsobjektets egna uppgifter) är kritisk
   för slutsatsen utan att trianguleras mot primärdata: höj hedging-nivån
   ett steg och flagga bristen explicit.

**Cirkulär argumentation:** om en slutsats motiveras med att "rapporten
visar att X" och "X visar att slutsatsen stämmer" — utan extern evidens —
är argumentet cirkulärt. Vanligast när intervjudata om upplevda brister
används för att belägga existensen av de brister som intervjuerna frågade om.
