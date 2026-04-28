# DEA och kommunal benchmarking

Uppdaterad: 2026-04-29

---

## Vad DEA är — och vad det inte är

**Data Envelopment Analysis (DEA)** är en icke-parametrisk linjärprogrammeringsmetod för att mäta relativ effektivitet hos beslutsfattande enheter (Decision Making Units, DMU). DMU kan vara kommuner, skolor, myndigheter, sjukhus eller andra verksamheter.

**Viktigt:** DEA är deskriptivt-komparativt, inte kausalt. DEA visar *kan* bli effektivare (i förhållande till effektivitetsfronten), inte *varför* de är ineffektiva. Komplettera med DiD/RDD för kausala anspråk om varför effektivitetsskillnaderna uppstår.

---

## Grundmodeller

### CCR-modellen (Charnes, Cooper, Rhodes 1978) — konstant skalavkastning (CRS)

**LP-formuleringen (inputorientering):**

```
min θ
s.t.  Σⱼ λⱼ xᵢⱼ ≤ θ xᵢ₀    (inputbegränsning)
      Σⱼ λⱼ yᵣⱼ ≥ yᵣ₀        (outputbegränsning)
      λⱼ ≥ 0
```

- θ ∈ [0,1]: effektivitetspoäng för DMU₀. θ = 1 → på fronten; θ < 1 → ineffektiv
- λⱼ: vikter för referens-DMU:er på fronten
- Antar konstant skalavkastning (CRS) — optimal skala förutsätts

### BCC-modellen (Banker, Charnes, Cooper 1984) — variabel skalavkastning (VRS)

Lägger till begränsningen Σⱼ λⱼ = 1 för att tillåta variabel skalavkastning. Ger *ren teknisk effektivitet* skild från *skaleffektivitet*.

**Skaleffektivitet = CRS-poäng / VRS-poäng**

- Skaleffektivitet < 1 → DMU opererar på icke-optimal skala
- Tillåter ökande (IRS) och minskande skalavkastning (DRS)

### Input- vs. outputorientering

| Orientering | Fråga | Typisk användning |
|---|---|---|
| **Inputorientering** | Hur mycket kan inputs minskas givet nuvarande outputs? | Kostnadseffektivitet, resursanvändning |
| **Outputorientering** | Hur mycket kan outputs ökas givet nuvarande inputs? | Servicekapacitet, volymutveckling |

### Malmquist-produktivitetsindex (paneldata)

Mäter produktivitetsutveckling över tid som produkt av:
- **Effektivitetsförändring (catch-up):** Rör sig DMU mot fronten?
- **Teknologiförändring (frontier shift):** Rör sig fronten själv uppåt?

Malmquist > 1 = produktivitetsförbättring; < 1 = försämring.

---

## Tillämpning mot kommundata

**Typiska inputs (nettokostnader och personal):**
- Nettokostnad per verksamhet (kr/invånare)
- Personaltäthet (årsarbetare per 100 brukare)

**Typiska outputs (volymmått och kvalitetsindikatorer):**
- Antal utförda insatser, andel med beviljade insatser, brukarnas betyg
- Elever per lärare, meritvärde, andel behöriga till gymnasiet

**Datakällor:** Kolada (SKR), Socialstyrelsens öppna jämförelser, SCB kommunalekonomisk redovisning.

**Viktigt vid kommundata:**
- Kontrollera för strukturella skillnader (andel äldre, befolkningstäthet, socioekonomisk sammansättning) — dessa påverkar behovet, inte effektiviteten
- Kommuner med extremvärden kan dominera fronten och skeva resultaten — identifiera med super-effektivitet-DEA
- Definitionsändringar i Kolada-variabler kan bryta jämförbarheten

---

## Steg 2-analys — Simar-Wilson bootstrap

Steg 2-analysen syftar till att förklara *varför* effektivitetsskillnader uppstår (externa faktorer: strukturvariabler, socioekonomiska faktorer). Regressionen sker på effektivitetspoängerna som beroende variabel.

**Naiv Tobit är inkonsistent** som Steg 2-estimator (Simar & Wilson 2007, JoE). Skälet: DEA-poänger är seriellt korrelerade med varandra (de konstrueras relativt varandra), vilket bryter Tobit-modellens antaganden. Tobit kräver att residualerna är oberoende — DEA bryter detta.

**Korrekt metod: Simar & Wilson (2007) Algorithm 2 (bootstrappad trunkerad regression)**

1. Skatta DEA-poänger θ̂
2. Regressera θ̂ på externa faktorer Z med *trunkerad regression* (ej Tobit — trunkering vid 1 är korrekt när CRS/VRS fronten skalar poängerna till ≤ 1)
3. Bootstrap (B = 2 000 iterationer): resampla residualer, konstruera pseudo-θ, reskatta DEA + trunkerad regression
4. Beräkna bootstrap-KI och bias-korrigerade punktestimat

**R-paket:** `rDEA` (implementerar Simar-Wilson Alg. 1 och 2), `Benchmarking` (grundläggande DEA)

---

## Krav i granskningsrapporten

Fullständig dokumentation som krävs enligt vetenskapliga krav och kommunicerbarhetsstandarder:

| Krav | Innehåll |
|---|---|
| **Fullständig variabelförteckning** | Alla inputs och outputs explicit listade med källa och definition |
| **Motivering av variabelval** | Varför dessa inputs/outputs? Vad mäter de? |
| **Sensitivitetsanalys** | Kör om med alternativa variabelkombinationer — förändras rankningen signifikant? |
| **Orientering och modell motiveras** | CRS eller VRS? Input- eller outputorientering? Motivera |
| **Outlier-detektion** | Identifiera och dokumentera super-effektiva DMU:er; kör om utan dem |
| **Konvext hölje dokumenteras** | Hur ser fronten ut? Hur många referenspunkter? |
| **Steg 2 korrekt** | Simar-Wilson bootstrap, inte Tobit — ange paket och iterationsantal |
| **Kausalitetsgräns tydlig** | "DEA indikerar att kommunerna *kan* förbättra effektiviteten — inte att de *bör* eller *varför* de inte gör det" |

---

## Vanliga fallgropar

- **Tobit i Steg 2:** Inkonsistenta estimat. Använd Simar-Wilson bootstrap-trunkerad regression.
- **För många variabler relativt DMU-antal:** DEA degenererar (alla DMU:er hamnar på fronten). Tumregel: antal DMU:er ≥ max(m×s, 3(m+s)) där m = inputs, s = outputs.
- **Outlier-problemet:** En DMU med extremt högt output/input-förhållande sätter fronten för alla andra — kan vara datfel eller genuint annorlunda verksamhet.
- **Ignorera strukturella skillnader:** Kommuner med hög andel äldre ser ineffektiva ut i äldreomsorgs-DEA om man inte normaliserar för behov.
- **Kommunicera DEA som rankningsinstrument:** Effektivitetspoängen är relativ till den observerade fronten, inte till ett idealt maximum.

---

## Källöversikt

| Referens | Bidrag |
|---|---|
| Charnes, Cooper & Rhodes (1978, EJOR) | CCR-modellen — grundläggande CRS-DEA |
| Banker, Charnes & Cooper (1984, MS) | BCC-modellen — variabel skalavkastning |
| Simar & Wilson (1998, MS) | Bootstrap för DEA-KI |
| Simar & Wilson (2007, JoE) | Bootstrap Steg 2-regression — korrekt metod |
| Färe, Grosskopf & Lovell (1994) | Malmquist-index |
| Asmild m.fl. (2007, JPA) | Malmquist-dekompositjon — tillämpning offentlig sektor |
