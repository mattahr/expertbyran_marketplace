# Processspårning (Process Tracing) — referensmaterial

_Within-case kausal inferensmetod. De fyra bevistesterna, Bayesiansk PT, Contribution Tracing som mekanismkedja, genomräknat exempel, praktisk beslutsguide._

---

## Vad processspårning är

Processspårning är en teoristyrd metod för att spåra kausala mekanismer **inom ett enskilt fall**. Till skillnad från fallstudier som beskriver vad som hände, svarar processspårning på *hur och varför* ett utfall uppstod — vilka mekanismer som länkade orsak till effekt.

Metoden rekonstruerar en sekvens av händelser och beslut och testar om de stämmer överens med förutsägelserna från en kausal hypotes (programteori/logikmodell). Det är detektivarbete med explicit epistemisk logik.

**Kräver:**
- En explicit programteori/logikmodell *innan* man söker bevis. Utan den vet man inte vilka spår som är relevanta.
- Tillgång till dokumentspår (mötesprotokoll, e-post, regleringsbrev, PM). Om kritiska beslut aldrig dokumenterades saknas råmaterial.
- Aktiv testning av konkurrerande hypoteser — metoden fungerar bäst när alternativa förklaringar tas på allvar.

---

## De fyra bevistesterna (Beach & Pedersen)

Bevisens styrka bedöms med fyra test. Underliggande logik är Bayesiansk: bevis uppdaterar sannolikheten för hypotesen.

| Test | Nödvändigt? | Tillräckligt? | Om beviset finns | Om beviset saknas |
|------|------------|---------------|-----------------|-------------------|
| **Straw-in-the-wind** | Nej | Nej | Marginell ökning | Marginell minskning |
| **Hoop test** | Ja | Nej | Måttlig bekräftelse | **Eliminerar hypotesen** |
| **Smoking gun** | Nej | Ja | **Stark bekräftelse** | Eliminerar ej |
| **Doubly definitive** | Ja | Ja | **Definitiv bekräftelse** | **Definitiv eliminering** |

**Praktisk regel:**
1. Identifiera vad som *måste* vara sant om hypotesen stämmer → hoop-test (frånvaro eliminerar)
2. Leta sedan efter rökt gevär — bevis som är närmast omöjliga om hypotesen är falsk → smoking gun (närvaro bekräftar)

---

## Bayesiansk formalisering (Befani & Stedman-Bryce 2017)

Qualitativ PT (Beach & Pedersen) tillämpar bevistesterna som verbala omdömen. Befani & Stedman-Bryce gör logiken explicit och sifferbaserad.

### Prior och posterior

**Prior P(M):** Initial tilltro till att mekanismen M verkar, *innan* beviset setts. **Starta alltid från 0,5** — maximal osäkerhet. Det hindrar att förväntade resultat läses in i analysen.

**Posterior P(M|E):** Uppdaterad tilltro efter att bevis E observerats. Beräknas med Bayes' sats:

```
P(M|E) = [Se × P(M)] / [Se × P(M) + FPR × (1 − P(M))]
```

**Se (Sensitivity/Känslighet):** P(E|M sann) — hur sannolikt är det att vi ser beviset OM mekanismen verkar?

**FPR (False Positive Rate/Typ I-felsandel):** P(E|M falsk) — hur sannolikt är det att vi ser beviset OM mekanismen *inte* verkar?

### Bevistesternas Bayesianska struktur

Bevistesternas styrka förklaras av parameterkombinationen Se och FPR:

| Test | Se | FPR | Bevis finns → | Bevis saknas → |
|------|-----|-----|---------------|----------------|
| **Straw-in-the-wind** | Medel | Medel | Marginell ökning | Marginell minskning |
| **Hoop test** | Hög | Hög | Måttlig ökning | Eliminerar (posterior → 0) |
| **Smoking gun** | Låg | Låg | Stark ökning (posterior → 1) | Måttlig minskning |
| **Doubly definitive** | Hög | Låg | Definitiv ökning | Definitiv eliminering |

**Tumregel:** Hög Se → frånvaro av bevis är informativt (hoop-logik). Låg FPR → närvaro av bevis är informativt (smoking gun-logik). Båda → doubly definitive.

---

## Contribution Tracing — mekanismkedja

Befani & Stedman-Bryce kombinerar Bayesiansk PT med contribution analysis (Mayne). Mekanismen testas inte som ett enda påstående utan som en kedja:

```
Insats → M1 → M2 → M3 → Utfall
```

Varje länk i kedjan:
1. Formuleras som ett empiriskt falsifierbart påstående
2. Tilldelas prior = 0,5
3. Testas med relevanta bevis vars Se och FPR skattas
4. Uppdateras till en posterior

**Den svagaste länkens posterior bestämmer det totala förtroendet för bidragsanspråket.**

---

## Praktisk beslutsguide — vilket test väljer jag?

**Steg 1:** Formulera mekanismledet M som ett empiriskt falsifierbart påstående.
("Kommunledningen prioriterade om resurser *på grund av* statsbidraget, inte av egna skäl.")

**Steg 2:** Identifiera vilket bevis E du kan samla (dokument, intervjuutsaga, statistik).

**Steg 3:** Ställ de två nyckelfrågorna:
- "Hur sannolikt är detta bevis *om M är sann*?" → Se
- "Hur sannolikt är detta bevis *om M är falsk*?" → FPR

**Steg 4:** Välj testtyp:

| Fråga | Svar | Välj testtyp |
|-------|------|-------------|
| Alla starka mekanismer borde producera detta bevis? | Ja | **Hoop** (Se hög) — frånvaro eliminerar |
| Bara denna mekanism kan producera detta bevis? | Ja | **Smoking gun** (FPR låg) — närvaro bekräftar |
| Båda ovan? | Ja | **Doubly definitive** — starkast möjliga |
| Inget av ovan, men ändå relevant? | Ja | **Straw-in-the-wind** — svag signal |

**Steg 5:** Räkna posterior. Om du inte vill räkna:
- Hoop-test missat → anspråket faller
- Smoking gun funnet → anspråket stärks kraftigt
- Doubly definitive funnet → anspråket etablerat
- Straw-in-the-wind → noteras men avgör inte

**Revisions-exempel:**

| Bevis | Testtyp | Motivering |
|-------|---------|------------|
| Regleringsbrev nämner styrmedlet | Straw-in-the-wind | Alla regleringsbrev nämner saker |
| Intern PM kopplar budgetbeslut till statsbidraget explicit | Smoking gun | Chefer skriver sällan så om det inte stämmer |
| Protokoll visar att budgetdiskussionen ägde rum | Hoop | Om mekanismen verkat *borde* diskussionen finnas |
| Tre oberoende källtyper kongruera kring beslutskedjan | Doubly definitive | Konvergens av hoop + smoking gun |

---

## Operationellt Bayes-exempel — genomräknat

**Mekanismhypotes M:** "Statsbidraget förändrade kommunledningens prioriteringsordning, vilket ledde till att lärartjänster rekryterades som annars inte hade prioriterats."

**Prior P(M) = 0,50**

---

**Bevis E1 — Budgetprotokoll (hoop-test)**

*Resonemang:* Om M är sann borde protokoll koppla bidraget till rekryteringsbeslutet (Se=0,85). Kommuner rekryterar även utan bidrag och skriver protokoll om det (FPR=0,70).

```
P(M|E1) = (0,85 × 0,50) / (0,85 × 0,50 + 0,70 × 0,50) = 0,425 / 0,775 ≈ 0,55
```

*Resultat:* Protokoll funnet, posterior = 0,55. Svag ökning — hoop-test passat.

---

**Bevis E2 — Intern PM med explicit koppling till statsbidraget (smoking gun)**

*Resonemang:* Chefen skriver sällan explicit om sin beslutslogik utan om det faktiskt stämmer (Se=0,30; FPR=0,03).

```
P(M|E2) = (0,30 × 0,55) / (0,30 × 0,55 + 0,03 × 0,45) = 0,165 / 0,1785 ≈ 0,92
```

*Resultat:* PM funnet, posterior = 0,92. Smoking gun-testet driver konfidensen kraftigt.

---

**Bevis E3 — Intervjuutsaga: "Vi rekryterade pga. bidraget" (straw-in-the-wind)**

*Resonemang:* Förenlig med M men aktören kan ha incitament att beskriva bidraget positivt (Se=0,70; FPR=0,50).

```
P(M|E3) = (0,70 × 0,92) / (0,70 × 0,92 + 0,50 × 0,08) = 0,644 / 0,684 ≈ 0,94
```

*Resultat:* Posterior = 0,94. Marginell ökning.

---

**Uppdateringskedja:**
```
Prior:       0,50  (ingen information)
Efter E1:    0,55  (hoop-test passat; svag ökning)
Efter E2:    0,92  (smoking gun funnet; stark ökning)
Efter E3:    0,94  (straw-in-the-wind; marginalökning)
```

**Slutsats:** Posterior = 0,94 ger starkt stöd. Drivande bevisenhet: E2 (smoking gun PM).

---

## Riksrevisionen 4.4-formulering

Ange explicit i metodavsnittet vilka bevistester som tillämpats och hur Se/FPR skattats. Möjliggör oberoende granskning av analytikerns bedömningsbeslut.

**Exempel:**
> "Beviset (PM 2022-11-14) bedömdes som ett smoking-gun-test (Se=0,30; FPR=0,05). Posterior uppdaterades från 0,5 till 0,76."

> "Tre bevisenheter testades mot mekanismhypotesen. Budgetprotokollet passerade hoop-testet (posterior: 0,55). En intern PM med explicit koppling till bidraget bedömdes som smoking-gun-bevis (posterior: 0,92). Intervjuutsagor från fyra av fem kommunledningsrepresentanter är kongruenta (posterior: 0,94). Sammantaget starkt stöd för att mekanismen verkade."

---

## Vanliga fallgropar

- **Prior ≠ 0,5:** Om man sätter prior utifrån förväntad slutsats upphör metoden att skydda mot bekräftelsebias.
- **Se och FPR utan argumentation:** Motivera dem som ankarpunkter i fsQCA — siffror utan argument ger falsk precision.
- **Evidenspaket behandlas som ett bevis:** Aggregera flera bevis systematiskt, inte godtyckligt.
- **Mekanismformulering för vag:** Om M inte är empiriskt falsifierbart kan inga bevis stärka eller eliminera det.

---

## Förhållande till andra metoder

- **Intervjumetodik** → leverar spåren (vittnesutsagor, redogörelser för beslut)
- **Dokumentanalys** → leverar spåren (mötesprotokoll, e-post, regleringsbrev)
- **Triangulering** → PT-analys kräver triangulering av spår mot hypoteser — det är metodens kärna
- **fsQCA** → cross-case; PT är within-case. Kombinationen är kraftfull: fsQCA identifierar konfigurationer, PT förklarar mekanismen i nyckelfall

---

## Källor

- Beach, D. & Pedersen, R.B. (2013) *Process-Tracing Methods: Foundations and Guidelines* — University of Michigan Press
- Beach, D. & Raimondo, E. (2025) *Process-Tracing Methods in Program Evaluation* — IEG Working Paper, World Bank
- Befani, B. & Stedman-Bryce, G. (2017) "Process Tracing and Bayesian Updating for Impact Evaluation" — *Evaluation* 23(1): 42–60
- Befani, B. (2020) "Letting Evidence Speak for Itself" — *New Directions for Evaluation*
- TASO (UK) *Process Tracing Briefing* — kortversion med bevistester
- Camacho Garland, Beach & Schmitt (2025) "Working with interviews in Process Tracing evaluation methods" — *Evaluation* journal
