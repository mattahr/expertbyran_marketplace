# Riksrevisionens krav 4.3 — Kvantitativa iakttagelser

Uppdaterad: 2026-04-22

---

## Grundkravet

Riksrevisionens vetenskapliga krav 4.3 stipulerar att kvantitativa iakttagelser i granskningsrapporten ska vara **entydigt formulerade, källbelagda och försedda med osäkerhetsangivelse**. Kravet syftar till att undvika:

- **Falsk precision:** En siffra med fler decimaler än datakvaliteten motiverar
- **Oidentifierade aggregat:** Siffror utan tydlig population, tidsperiod eller källa
- **Kausala överdrifter:** Korrelationsresultat som formuleras som om de vore kausala
- **Selektiv redovisning:** Att enbart rapportera de resultat som stödjer slutsatsen

---

## De fyra obligatoriska komponenterna

Varje kvantitativ iakttagelse ska innehålla:

### 1. Täljare och nämnare

Vad räknas, och ur vilket universum? En iakttagelse om "X procent av myndigheterna" kräver att det framgår hur många myndigheter som ingår i täljare respektive nämnare, och om andra myndigheter uteslutits och varför.

**Exempel på godkänd formulering:**
> "Av de 47 myndigheter som granskades 2022–2023 hade 31 (66 procent) en skriftlig internkontrollplan."

**Exempel på otillräcklig formulering:**
> "Majoriteten av myndigheterna saknade ändamålsenlig styrning."

### 2. Tidsperiod

Vilket år, kvartal eller period avser iakttagelsen? Jämförelser over tid kräver att perioder är konsekvent definierade och att metodändringar i källdata noteras.

**Kontrollpunkt:** Har SCB eller annan källa ändrat definition eller redovisningsmetod under perioden? Om ja — är siffrorna justerade för detta, eller ska en diskontinuitet noteras?

### 3. Källa

Vilken databas, rapport, eller register? Inkludera version, årgång eller hämtdatum om data kan uppdateras.

**Accepterade källformat:**
- SCB, Statistikdatabasen, tabell X, hämtad [datum]
- IFAU rapport 2023:N, tabell X, s. Y
- Myndighetens egna årsredovisning [år], s. X

### 4. Osäkerhetsmarginaler

Vilken osäkerhet finns i skattningen? Tre nivåer:

| Typ av osäkerhet | Hur den redovisas |
|---|---|
| **Stickprovsosäkerhet** | Konfidensintervall, standardfel |
| **Mätosäkerhet** | Förklara källdatats begränsningar (bortfall, mätfel) |
| **Modellspecifikationsosäkerhet** | Sensitivitetsanalys: varierar resultatet om design-val ändras? |

Om osäkerhet inte kan kvantifieras — ange detta explicit: "Ingen konfidensintervall kan beräknas för detta mått eftersom det avser en totalundersökning av [population]. Mätfelet bedöms som [litet/måttligt/stort] av följande skäl: …"

---

## Distinktionen korrelation–kausalitet

Riksrevisionens krav innebär att formuleringar inte får implicera kausalitet om den inte kan beläggas. Tre nivåer av påståendestyrka:

| Nivå | Formulering | Krav |
|---|---|---|
| **Deskriptiv** | "X samvarierar med Y" | Data visar samband — inga kausalvillkor |
| **Associativ** | "X är förknippat med Y" | Kontrollerade kovariater, men inga exogena variationer |
| **Kausal** | "X leder till Y" / "till följd av X" | Naturligt experiment, identifikationsstrategi, mekanismtest |

**Varningssignal:** Formuleringar som "beror på", "orsakas av", "leder till" kräver kausal identifikation — om den saknas, skriv om till associativ nivå.

---

## Falsk precision — praktisk guide

**Regel:** Antal redovisade decimaler ska motsvara datakvalitetens precision.

| Källdata | Lämplig precision |
|---|---|
| Registerdata (totalräkning) | 0–1 decimal |
| Surveydata, representativt urval | Avrunda till närmaste heltal eller 0,5 pp; redovisa KI |
| Administrativ statistik med stora bortfall | Avrunda grovt; notera bortfallsnivå |
| Ekonometrisk skattning | Punktskattning + KI; undvik fler sig. siffror än SE motiverar |

**Exempel:** Om ett konfidensintervall sträcker sig från 12 till 28 procent, är en punktskattning på "20,3 procent" falsk precision — skriv "ungefär 20 procent (95% KI: 12–28 procent)".

---

## Iakttagelsemall

Använd denna mall för att formulera kvantitativa iakttagelser:

```
Under [tidsperiod] var [mått/indikator] [värde] [enhet]
([källa], [tabell/sida/hämtdatum]).
[Osäkerhetsangivelse: konfidensintervall / metodbegränsning / bortfall.]
[Kausaltolkning om tillämplig: Detta samband kan / kan inte tolkas kausalt
eftersom [identifikationsstrategi / brist på densamma].]
```

**Konkret exempel:**
> Under 2020–2022 uppgick andelen ungdomar 18–24 år som varken arbetar eller studerar (NEET) till 8,4 procent (SCB, AKU, årsgenomsnitt, hämtat 2024-03-15). Skattningen baseras på ett urval om ca 29 500 individer per kvartal; konfidensintervallet är ±0,6 procentenheter. Skillnaden mot 2018–2019 (6,9 procent) kan inte kausalt hänföras till pandemin utan konfounding från strukturella arbetsmarknadsförändringar bör beaktas.

---

## Vanliga fel och hur de undviks

| Fel | Exempel | Korrigering |
|---|---|---|
| Nämnaren saknas | "Var fjärde tjänsteman…" | Ange N och population: "31 av 124 tjänstemän (25%) i urvalet…" |
| Perioden är oklar | "Under senare år" | Precisera: "2019–2023" |
| Kausalt språk utan identifikation | "Reformen ledde till lägre sjukfrånvaro" | "Sjukfrånvaron minskade [värde] åren efter reformen (samband, inte belagt kausalt)" |
| Decimaler utan stöd | "23,47 procent" | "23 procent" om surveydata |
| Källa saknas | "Enligt statistiken" | "[Källa], [tabell], [datum]" |
| Alternativa förklaringar ignoreras | Effektskattning utan att diskutera confounders | Lägg till ett stycke om alternativa förklaringar |
