# Spektrumauktioner: Teori och Svensk Praxis

Senast uppdaterad: 2026-04-29

## Auktionsteori — grunden

### Milgrom & Weber (1982) — Linkage Principle

**Källa:** Paul Milgrom & Robert J. Weber, "A Theory of Auctions and Competitive Bidding", *Econometrica* vol. 50 (5), s. 1089–1122.

**Kärnbidrag:** *Linkage Principle* — öppna stigande auktioner (ascending-bid/English auction) ger systematiskt högre förväntade intäkter än slutna förstaprisauktioner vid privat-värde-osäkerhet. Budgivare kan lära sig av varandras bud och vinnartappfelet (winner's curse) minskar.

**Implikation för spektrum:** FCC:s val av SMRA-format 1994 motiverades direkt med Milgrom/Weber — informationsdelning i öppna auktioner ökar effektiviteten.

### SMRA — Simultaneous Multi-Round Auction

- **Ursprung:** Designad av Milgrom, Wilson m.fl. för FCC:s PCS-auktion 1994.
- **Princip:** Alla licenser auktioneras simultant i runda för runda tills ingen bjuder mer. Budgivare kan omfördela bud mellan licenser.
- **Svaghet — Aggregationsproblem (exposure problem):** Om en kombination av licenser är nödvändig för lönsamhet riskerar budgivaren att vinna ett subset till för hög kostnad.
- **PTS:** Använde SMRA i 3,5 GHz- och 2,3 GHz-auktionen (jan 2021).

### CCA — Combinatorial Clock Auction

- **Källa:** Cramton, Shoham & Steinberg (eds.), *Combinatorial Auctions* (MIT Press 2006); Cramton m.fl., *Handbook of Spectrum Auction Design* (Cambridge 2017).
- **Princip:** Tvåstegs-auktion. Steg 1 — klocka-fas (budgivare anger volym vid stigande pris per block); Steg 2 — supplementary round (slutna paketbud på valfria kombinationer). Vinnare bestäms via VCG-prissättning (Vickrey-Clarke-Groves).
- **Fördel:** Eliminerar aggregationsproblemet — budgivare kan lämna paketbud ("jag vill ha block A *och* block B, eller inget"). Vanligast globalt för stora 5G-auktioner.
- **Nackdel:** Mer komplicerat för budgivare; VCG-prissättning kan ge orealistiskt låga priser i små auktioner.

### EECC-restriktionen: inte enbart intäktsmaximering

Prop. 2021/22:136, s. 418: "Det är t.ex. inte tillåtet att utforma ett auktionsförfarande *enbart* som medel för att ge högsta möjliga intäkter till statsbudgeten." Syftet ska vara effektiv spektrumanvändning, konkurrens och innovation (LEK 11 kap.).

---

## PTS spektrumauktioner — historik

| Auktion | Band | År | Vinnare | Anmärkning |
|---|---|---|---|---|
| 700 MHz | 2 × 30 MHz + nedlänk | Dec 2018 | Telia, Net4Mobility | Täckningskrav: Telia 300 Mkr för utpekade glesbygdsområden |
| 3,5 GHz + 2,3 GHz | 5G-kärnband | Jan 2021 | Telia, Hi3G (Tre), Net4Mobility, Teracom | SMRA-format; Huawei utesluten via 5G-säkerhetslagen |
| 900 MHz, 2,1 GHz, 2,6 GHz | Förnyelseband | Sept–okt 2023 | (se PTS beslut) | Tillstånd fr.o.m. 1 jan 2026 (~25 år); täckningskrav: nya master längs vägar/järnvägar; kapacitetskrav järnväg |
| 26 GHz (mmWave) | Hög kapacitet | Ej genomförd (maj 2026) | — | Testtillstånd sedan 2017 (upp till 1 000 MHz). PTS efterfrågekonsultation (1,5/26/42 GHz) klar — svar inkomna juni 2025. Utomhustilldelning planerad 2026 (ev. 2025 i storstäder). PTS leder EU-harmoniseringsarbetsgrupp. |

**26 GHz — aktuell status (maj 2026):** PTS genomförde en efterfrågekonsultation för 1,5 GHz, 26 GHz och 42 GHz-banden (nytt band för första gången inkluderat) med svarsdeadline 9 juni 2025. Resultatet ska ligga till grund för fortsatt planeringsarbete. Kommersiell bred tilldelning ej genomförd. Hög kapacitet men kort räckvidd — relevant för tätortsdensanätverk, ej glesbygdstäckning.

---

## Granskningsfrågor: Hypotetisk granskning av svensk 5G-spektrumauktion

### Fråga 1 — Auktionsdesignens samhällsekonomiska ändamålsenlighet

Valde PTS en auktionsmodell (SMRA vs. CCA) som i tillräcklig utsträckning möjliggjorde aggregering av spektrumblock och minimerade aggregationsproblem — och motiverades designvalet av målen om effektiv spektrumanvändning och konkurrens snarare än av intäktsmaximering, vilket EECC (genomfört via LEK 11 kap.) förbjuder som *enda* syfte?

### Fråga 2 — Täckningskravens utformning och uppföljning

Utgjorde de täckningskrav som villkorades i 5G-licenser (t.ex. 300 Mkr-åtagandet i 700 MHz, täckning längs vägar i 900 MHz) ett effektivt styrmedel för att nå samhällsekonomisk nytta — särskilt glesbygdstäckning — och har PTS genomfört verifierbar uppföljning av om kraven faktiskt uppfyllts?

### Fråga 3 — Konkurrenseffekt och spektrumkoncentration

Medförde auktionsresultaten att konkurrensen på mobilmarknaden stärktes, eller var spektrumtaken och marknadsstrukturåtgärderna tillräckliga för att förhindra dominans — och hur stämmer utfallet med PTS förhandsbedömningar (HHI-analys, antal aktörer per band)?

---

## Nyckelkällor

- Milgrom & Weber (1982), *Econometrica* vol. 50(5) — auktionsteori, Linkage Principle
- Cramton m.fl., *Handbook of Spectrum Auction Design* (Cambridge 2017) — CCA-format
- SOU 2018:92 — En spektrumförvaltning för framtidens samhälle (DocRec-id: 9747)
- Prop. 2021/22:136 — Genomförande av EECC (LEK 2022); s. 418 om intäktsrestriktionen
- Betänkande 2023/24:TU16 (DocRec id 23282) — spektrumauktioner 2023
- PTS-ER-2024:12 — Beslut fattade med stöd av LEK år 2023
