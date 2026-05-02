# Begriplighetsanalys — LIX och OVIX

## Primärkällor

- **Björnsson, C-H. (1968). *Läsbarhet*. Stockholm: Liber.** LIX-formelns ursprung. Formeln avser att vara enkel nog att beräknas manuellt utan specialverktyg.
- **Lundberg, I. & Reichenberg, M. (2013). *Läsbarhet — hur man skriver lättläst*. Lund: Studentlitteratur.** Kombinerar kvantitativa mått med kvalitativa — poängterar att LIX inte mäter begriplighet utan *ytkomplexitet*.
- **Holmberg, P. (Språkbanken, Göteborgs universitet).** OVIX-formelns tillämpning i svenska korpusar. Implementerad i Språkbankens Sparv-analysverktyg.

## LIX-formeln

**LIX = (O / M) + (L × 100 / O)**

| Symbol | Betyder |
|--------|---------|
| O | Totalt antal ord i texten |
| M | Antal meningar |
| L | Antal långa ord (fler än 6 bokstäver) |

**Tolkningsskala:**

| LIX-värde | Svårighetsgrad | Typisk text |
|-----------|---------------|-------------|
| Under 25 | Mycket lätt | Barnböcker |
| 25–35 | Lätt | Skönlitteratur, populärpress |
| 35–45 | Medel | Tidningstext |
| 45–55 | Svår | Officiella myndighetstexter |
| Över 55 | Mycket svår | Byråkratsvenska, juridiska dokument |

**Metodbegränsning (Lundberg & Reichenberg):** LIX mäter *ytkomplexitet* — meningslängd och ordens längd. Det mäter inte om innehållet är logiskt, konsekvent eller anpassat till läsaren. En text kan ha LIX 30 och ändå vara obegriplig p.g.a. bristande struktur eller okänt fackinnehåll.

## OVIX-formeln (ordvariationsindex)

**OVIX = log(N) / log(2 − log(V) / log(N))**

| Symbol | Betyder |
|--------|---------|
| N | Totalt antal ord (tokens) |
| V | Antal unika ordformer (types) |

**Tolkningsskala:**
- OVIX under 60–65: Lättläst text (begränsat ordförråd, hög upprepning)
- OVIX 65–75: Normal text
- OVIX 75+: Kräver stort ordförråd av läsaren

**Metodbegränsning:** OVIX är känsligt för textlängd — korta texter ger artificiellt höga värden. Meningsfull tolkning kräver minst 200 löpord.

## Praktisk analysmetod — steg för steg

1. **Mät LIX** — räkna ord, meningar, långa ord. LIX > 45 för myndighetsbeslut är vanligt men inte oundvikligt.
2. **Identifiera passivkonstruktioner** — sök på verb i passiv form (s-passiv: "meddelas", "genomföras", "konstaterats") och perifrastisk passiv ("ska… göras"). Fråga alltid: vem är aktören?
3. **Identifiera juridiska termer** — dela in i (a) fastlåsta termer som måste behållas men kan förklaras, och (b) interna myndighetstermer som kan ersättas med vardagsspråk.
4. **Skriv om** — en mening per besked, aktiv form, konkret aktör. Behåll lagstöd men separera det från beslutsformuleringen.
5. **Verifiera** — kontrollera att omskrivningen inte ändrar rättslig innebörd.

## Praktiskt mätexempel — Försäkringskassan sjukpenningbeslut

**Analysobjekt:** Representativ beslutstext, 180-dagarsprövning sjukpenning. LIX 51 (svår).

**Originaltexten:**
> Försäkringskassan har tagit del av det medicinska underlaget som inkommit avseende din sjukskrivning. Av det inkomna underlaget framgår det att du är diagnostiserad med utmattningssyndrom, vilket av läkaren bedömts som nedsättande för din arbetsförmåga med 50 procent. Med anledning av detta ska en prövning av din rätt till sjukpenning genomföras i enlighet med de regler som gäller för den s.k. 180-dagarsprövningen, i vilken det ska prövas om du kan utföra ett normalt förekommande arbete på arbetsmarknaden. Det har vid utredning konstaterats att det inte föreligger medicinska skäl som utgör hinder för att du kan beredas ett sådant arbete. Mot bakgrund av detta och med stöd av 27 kap. 46 § socialförsäkringsbalken (SFB) meddelas härmed beslut om avslag på ansökan om sjukpenning.

**LIX-beräkning:**

| Mätvariabel | Värde |
|------------|-------|
| Totalt antal ord (O) | 142 |
| Antal meningar (M) | 5 |
| Antal långa ord >6 bokstäver (L) | 32 |
| Ord per mening (O/M) | 28,4 |
| Andel långa ord i % (L×100/O) | 22,5 % |
| **LIX** | **50,9** |

**De tre tyngsta passivkonstruktionerna:**

| Passiv | Problem |
|--------|---------|
| "ska en prövning… *genomföras*" | Dubbel distansering — nominalisering + passiv. Vem prövar? |
| "Det har vid utredning *konstaterats* att" | Subjektslöst — ansvaret osynligt. |
| "*meddelas* härmed beslut om avslag" | Passiv + nominalisering. Myndigheten undviker "vi avslår". |

**De tre tyngsta juridiska termerna:**

| Term | Problem | Lösning |
|------|---------|---------|
| "180-dagarsprövningen" | FK:s interna term | Förklara: "Vi prövar nu om du kan arbeta i ett annat yrke (den s.k. 180-dagarsgränsen)" |
| "normalt förekommande arbete" | Juridisk term ur SFB | Förklara: "ett vanligt arbete som finns på arbetsmarknaden" |
| "27 kap. 46 § SFB" | Korrekt men placerad som appendix | Behåll — men separera beslutet från lagstödet |

**Omskriven version:**
> Vi har gått igenom din sjukskrivning och det läkarintyg som du skickat in. Läkaren bedömer att du är sjuk i utmattningssyndrom och att din arbetsförmåga är nedsatt med 50 procent.
>
> Du har nu varit sjukskriven i 180 dagar. Enligt lagen ska vi vid den här tidpunkten pröva om du kan arbeta i något annat yrke — inte bara det du hade tidigare. Vi bedömer att det finns arbeten du kan utföra trots din sjukdom.
>
> Därför avslår vi din ansökan om sjukpenning. Beslutet grundar sig på 27 kap. 46 § socialförsäkringsbalken (SFB).

**Notering:** Termen "socialförsäkringsbalken (SFB)" är fastlåst — juridisk beteckning som inte kan ersättas. Den kan förklaras i omgivande text men inte bytas ut.
