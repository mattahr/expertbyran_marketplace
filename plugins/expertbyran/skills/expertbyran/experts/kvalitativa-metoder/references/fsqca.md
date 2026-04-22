# Fuzzy-set QCA (fsQCA) — referensmaterial

_Set-teoretisk komparativ metod för nödvändiga och tillräckliga villkor vid medelstort N (10–50 fall). Kärnlogik, kalibrering, kommunexempel och fallgropar._

---

## Vad QCA är — och inte är

**Qualitative Comparative Analysis (QCA)** är en metod för att analysera nödvändiga och tillräckliga villkor för ett utfall, med hjälp av set-teoretisk logik. Den frågar: vilken kombination av villkor är *tillräcklig* för utfallet? Vilket villkor är *nödvändigt*?

**fsQCA (fuzzy-set QCA)** tillåter graderingar (0–1) istället för binära värden — varje fall kan vara delvis i en mängd.

**QCA är INTE ett statistiskt verktyg.** Det är logisk-jämförande. Varje fall ska förstås på djupet. Kalibreringsbeslut är substantiva, inte statistiska.

**Passar när:**
- N = 10–50 fall (medelstort)
- Man vill identifiera konfigurationer av villkor (inte isolerade effekter)
- Fallkännedom finns eller kan byggas upp
- Frågan är "vilken kombination av villkor är tillräcklig?" snarare än "hur mycket påverkar X Y?"

---

## Kalibrering — kärnlogiken

Kalibrering är processen att omvandla rådata (eller kvalitativa bedömningar) till mängdmedlemskapspoäng (0–1). Det är en **substantiv** process, inte statistisk. Ankarpunkterna väljs baserat på teorin och fallkunskap — **inte** utifrån datans distribution.

### De tre ankarpunkterna (direkt kalibrering)

| Ankarpunkt | Poäng | Innebörd |
|-----------|-------|----------|
| Fully in  | 0,95  | Klart en fullständig medlem av mängden — ingen rimlig bedömare ifrågasätter det |
| Crossover | 0,50  | Maximal tvetydighet — varken in eller ut; epistemisk osäkerhet |
| Fully out | 0,05  | Klart utanför mängden — ingen rimlig bedömare ifrågasätter det |

Värdena transformeras via logistisk S-kurva i `calibrate()`-funktionen (R-paketet `QCA` av Dusa).

### Hur man väljer ankarpunkterna — steg för steg

**1. Börja med crossover (0,5).**
Fråga: "Vad är den situation där jag genuint inte kan avgöra om en enhet tillhör mängden eller inte?" Det är 0,5 — inte medianen, inte statistisk gräns, utan substantiv tvetydighet för en välinformerad bedömare.

**2. Välj fully-in (0,95).**
Fråga: "Vilka enheter ska vara klara prototyper?" Fall som ingen rimligen ifrågasätter som fullständiga medlemmar.

**3. Välj fully-out (0,05).**
Fråga: "Vilka enheter ska vara klart utanför?" Fall som ingen rimligen ifrågasätter som icke-medlemmar.

**4. Motivera med externa referenspunkter.**
Ankarna ska ha stöd utanför datamaterialet: teori, expertkunskap, komparativa standarder, normdokument. Det skiljer kalibrering från godtycklig skalning.

**Ragin (2009):** Kalibrering är alltid en process av att "hänga" abstrakta set-begrepp på empiriska ankarpunkter med extern giltighet.

---

## 0,5-punktens substantiella logik — varför den inte är ett genomsnitt

**Vanligt misstag:** Sätta 0,5 vid medianen eller medelvärdet i data. Det är fel.

0,5 ska representera det epistemiska tillståndet "maximalt osäker" för en välinformerad bedömare. Om alla 18 kommuner råkar ha god intern kontroll, kan 0,5 ändå ligga på en absolut nivå som "tillräckligt god" — inte vid den faktiska datans mittvärde.

**Konsekvens:** Kalibreringen kan ge en distribution av poäng som är sned (många fall nära 0 eller 1) — det är metodologiskt korrekt om ankarpunkterna är substantivt motiverade.

---

## Kommunexempel: "Grad av intern kontroll"

Kalibrering av 18 kommuner på dimensionen "välutvecklad intern kontroll av socialtjänstens ekonomihantering":

**Fully out (0,05):**
Kommunen saknar dokumenterade rutiner för ekonomiuppföljning; revisionsanmärkningar om intern kontroll lämnades de senaste tre åren; ingen systematisk uppföljning av avvikelser.

**Crossover (0,5):**
Rutiner finns dokumenterade men efterlevs inkonsekvent; uppföljning sker men utan fastställd periodicity; enstaka revisionsanmärkningar.

*Motivering av crossover:* Det är just inkonsekvent efterlevnad som skapar tvetydighet — rutinerna finns men det är oklart om de utgör en reell kontroll. Substantivt argument, inte statistiskt.

**Fully in (0,95):**
Dokumenterade och regelbundet uppdaterade rutiner; systematisk uppföljning varje kvartal; inga signifikanta revisionsanmärkningar senaste tre åren; internkontrollplan antagen av nämnd.

---

## Tillämpning vid 15–30 kommunenheter

- 15–30 fall ger tillräcklig variation för meningsfull fsQCA-analys.
- Varje falls kalibreringsvärde ska kunna motiveras fallspecifikt — gå igenom vart och ett och kontrollera att poängen "känns rätt" mot fallkunskapen.
- Dokumentera kalibreringen transparent: visa vilka fall som ligger nära 0,5 och motivera varför de placeras där de gör.
- Kalibreringsdokumentation ska ingå som bilaga i granskningsrapporten eller som internt metodmemo.

---

## Analys av nödvändiga och tillräckliga villkor

**Nödvändigt villkor:** X är nödvändigt för Y om Y aldrig inträffar utan X. I fsQCA: mängden Y är en delmängd av mängden X. Täckning (coverage) och konsistens (consistency) > 0,9.

**Tillräckligt villkor:** X är tillräckligt för Y om Y alltid inträffar när X finns. I fsQCA: mängden X är en delmängd av mängden Y. Konsistens > 0,75 (vanlig tröskel, motiveras substantivt).

**INUS-logik (Mackie):** Mest typiska utfall är en kombination av ofullständiga men nödvändiga villkor som ingår i en otillräcklig men nödvändig konfiguration.

---

## Kombination med processspårning

fsQCA identifierar vilka konfigurationer av villkor som är associerade med utfallet. Processspårning i nyckelfall förklarar *mekanismen* — varför konfigurationen producerar utfallet.

**Typisk kombination:**
1. fsQCA pekar ut 2–3 tillräckliga konfigurationer.
2. Välj 1–2 nyckelfall per konfiguration för processspårning.
3. Processspårningen testar om den förväntade mekanismen faktiskt är aktiv.

---

## Fallgropar

- **Kalibrering på datadistribution:** Sätter 0,5 vid medianen. Fel. Kalibrering är substantiv.
- **För få fall per konfiguration:** Under 3 fall per konfiguration — slutsatser måste hedgas kraftigt.
- **Logisk minimering utan kausal teori:** QCA ger logiska slutsatser, inte kausala. Kausal tolkning kräver en underliggande mekanism.
- **Dold variation:** Om alla fall är homogena på en viktig dimension identifieras inte den variationen av QCA.
- **Felaktig tolkning av täckning:** Hög konsistens men låg täckning = konfigurationen stämmer men förklarar få fall. Rapportera båda.

---

## Källor

- Ragin, C.C. (2009) "Calibration versus Measurement" — University of California, Irvine (working paper)
- Rihoux, B. & Ragin, C.C. (eds.) (2009) *Configurational Comparative Methods* — Sage
- Dusa, A. (2019) *QCA with R: A Comprehensive Resource* — Springer (Bookdown-version tillgänglig)
- Schneider, C.Q. & Wagemann, C. (2012) *Set-Theoretic Methods for the Social Sciences* — Cambridge University Press
