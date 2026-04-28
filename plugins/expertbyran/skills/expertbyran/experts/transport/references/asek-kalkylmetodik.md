# ASEK-kalkylmetodik

## Vad är ASEK?

ASEK = Analysmetod och samhällsekonomiska kalkylvärden för transportsektorn.
Trafikverket ansvarar och publicerar ny version **1 april varje år**.
Nuvarande version: **ASEK 8.0** (publicerad 2 april 2024). Genomförde en
"omfattande översyn" med revideringar av både principer och kalkylvärden.

**Obs!** ASEK 8.0 (april 2024) ersatte ASEK 7.0 — en vanlig felkälla.

## Struktur och kalkylkomponenter

ASEK-rapporten täcker:

| Komponent | Beskrivning |
|-----------|-------------|
| **Tidsvärden** | Reskostnadskoefficienter per färdmedel och resändamål |
| **Olyckskoefficienter** | Värdet av ett statistiskt liv (VSL), skadegrad |
| **Klimatvärden** | Koldioxidvärde — hanteras via prissättning i driftskostnader, inte som explicit extern effekt. Separatrapport: "Hantering av klimat i basprognos 2024 och ASEK 8" (2025-06-04) |
| **Diskonteringsränta** | 3,5 % real (EU-harmoniserat för infrastruktur) |
| **Investeringskostnader** | Metodik för kalkylering och osäkerhetsintervall |

**Kalkylbilaga**: Numeriska värden (restidsvärden per trafikslag, VSL-belopp,
CO2-pris per ton) finns i Excel-bilagan (371 MB) — tillgänglig på
Trafikverkets branschportal men inte via webbtjänst.

## Nettonuvärdeskvot (NNK) — roll och begränsningar

NNK > 0 = samhällsekonomiskt lönsamt. Men NNK är inte enda beslutsgrunden.

**RiR:s empiriska fynd** om NP 2022–2033:
- NNK = -0,4 (nettonuvärde -145 mdr kr) för planen som helhet
- Exkluderat stambanetapper: NNK = 0,2 (svagt lönsam)
- Åtgärder *utanför* planförslaget hade i genomsnitt **högre** lönsamhet —
  medlen vallokeerades alltså inte till de mest lönsamma objekten

**Slutsats**: NNK styr inte faktisk prioritering på plannivå. Politiska
hänsynsmål (tillgänglighet, regional balans) vägs in och kan övervinna NNK.

**Implikation för granskning**: En enskild kalkyl med positiv NNK är
nödvändigt men inte tillräckligt för att hävda att objektet borde ha
prioriterats. Frågan är om NNK var jämförbar med alternativa objekt och om
beslutsprocessen faktiskt använde NNK som prioriteringsgrund.

## Granskningspunkter: hur kontrollerar man rätt ASEK-version?

I en granskning av infrastrukturinvestering:

1. **Kontrollera ASEK-version vid beslutstidpunkten.** Kalkylvärden uppdateras
   årligen och kan ge väsentligt olika NNK-utfall. ASEK 8.0 (april 2024) innebar
   en "omfattande översyn" — en analys med ASEK 7.0-värden ger potentiellt
   andra NNK-utfall.

2. **Kontrollera diskonteringsperiod och basår.** En längre diskonteringsperiod
   gynnar projekt med stor nyttovolym (kollektivtrafik, godsjärnväg).

3. **Kontrollera om kalkylvärden är i löpande eller fasta priser.** Systematiska
   jämförelser (NP 2014 → NP 2018) görs i *fasta priser*.

4. **Kontrollera osäkerhetsintervall.** ASEK förutsätter att kalkyler redovisar
   känslighetsanalys — om intervallet är litet är det en varningssignal.

5. **Kontrollera om NNK redovisas objekt-för-objekt** vid planrevideringarna.
   Riksrevisionen har noterat att transparensen brister (RiR 2021:22).

## Primärkällor — ASEK

| Dokument | Typ | Nyckelinnehåll |
|----------|-----|----------------|
| ASEK 8.0-rapport (2024-04-02) | PDF, 2 MB | Principer, metodik, kalkylvärden |
| ASEK 8.0-kalkylbilaga (2024-04-02) | Excel, 371 MB | Numeriska kalkylvärden per trafikslag |
| "Vad är nytt i ASEK 8.0?" (PM 2024-03-04) | PM | Förändringar vs. ASEK 7.0 |
| "Hantering av klimat i basprognos 2024 och ASEK 8" (2025-06-04) | Separatrapport | Klimatvärdenas metodhantering |
| Diskonteringsverktyg (användarhandledning 2024) | Handledning | Praktisk tillämpning |
