# Interoperabilitet — Europeisk och nationell styrning

Senast uppdaterad: 2026-04-29 (EXP-1112, baserat på EXP-1089)

---

## European Interoperability Framework (EIF v2) och EIRA

**EIF v2** (2017, COM(2017)134) — EU-kommissionens ramverk för interoperabilitet i offentlig förvaltning. 47 rekommendationer, 12 principer.

### Fyra interoperabilitetslager

| Lager | Vad det handlar om |
|-------|-------------------|
| **Rättslig** | Lagstiftningsharmonisering; undanröj lagliga hinder för datadelning |
| **Organisatorisk** | Processamordning; tydliga roller och ansvar |
| **Semantisk** | Gemensamma dataformat, metadata, kontrollerade ordlistor |
| **Teknisk** | Gränssnitt, protokoll, datautbytesformat |

### Semantisk interoperabilitet — hur den mäts

- Gemensamma vokabulärer och ontologier (ex. CPOV — Core Person Ontology)
- Registrering i EU:s semantiska katalog (SEMIC)
- EU-kommissionens **Interoperability Test Bed (ITB)** — validator-tjänster för att testa system mot EIRA
- **IMT (Interoperability Maturity Tools)** — självskattningsverktyg för offentliga förvaltningar att mäta sin interoperabilitetsmognad

### EIRA (European Interoperability Reference Architecture)

- EIRA 6.1.0 publicerad maj 2024
- Definierar "architecture building blocks" baserade på EIF
- Stöd för att visualisera och planera interoperabilitetslösningar
- EIRA Validator: validerar IT-system mot EIRA-specifikationerna

---

## Interoperable Europe Act (EU 2024/903)

Trädde i kraft 2024. Juridisk skyldighet (ej frivillig vägledning):

- **Interoperabilitetskonsekvensbedömning (IIA)** krävs för nya eller väsentligt förändrade gränsöverskridande digitala offentliga tjänster
- Inrättar **Interoperable Europe Board** med representanter från alla medlemsstater
- Stöder delning av interoperabilitetslösningar via Interoperable Europe Portal

---

## Prop. 2025/26:244 — Ny lag om interoperabilitet vid datadelning

**"Nya krav på interoperabilitet vid datadelning inom den offentliga förvaltningen"**

Obligatorisk interoperabilitet i offentlig sektor. Nytt lagrum skapar tvingande skyldigheter (till skillnad från tidigare frivilliga Ena-lösningar).

### Kärnförslag

- Offentlig förvaltning ska följa **nationella interoperabilitetslösningar** som DIGG tar fram och föreskriver om
- Täcker: statliga myndigheter, kommuner, regioner, kommunalförbund, kommunala bolag
- Exempel på tekniska krav: maskinläsbara format (JSON), gränssnitt (API)
- Undantag: om säkerhetsskäl gör det olämpligt
- DIGG ges **föreskriftsrätt** — men föreskriftsarbetet kräver ytterligare kartläggning

### Bakgrund och problem

- Historiskt: myndigheter har fritt valt egna datadelningsvillkor → fragmentering
- Ena (DIGG:s digital infrastruktur) underutnyttjad: RiR konstaterade att bara ~40 projekt nyttjat Ena-tjänster
- Större myndigheter bygger egna lösningar → extra gränssnittskostnader för mindre myndigheter
- DIGG har inte haft tvingande verktyg (bara kunnat locka med bra tjänster)

### Ekonomisk logik

Kostnader svårbedömda tills föreskrifterna är kända; men förväntad nätverkseffekt ger stora effektivitetsvinster långsiktigt (samhällsekonomiska vinster > initialkostnader).

### Granskningsperspektiv

Hur följer Riksrevisionen upp att myndigheterna verkligen implementerar nationella interoperabilitetslösningar när DIGG utfärdat föreskrifter? Nyckelrisker:
1. DIGG:s föreskriftsarbete tar tid — lagens tvingande kraft aktiveras inte förrän föreskrifter finns
2. Undantagsklausulen (säkerhetsskäl) kan tillämpas brett och urholka lagen
3. Kommuner och regioner har svagare incitament att ansluta sig än statliga myndigheter

---

## Nyckelkällor

| Dokument | Källa | År | Relevans |
|----------|-------|-----|---------|
| **Prop. 2025/26:244** "Nya krav på interoperabilitet vid datadelning" | Finansdepartementet | 2026 | Central: ny lag om obligatorisk interoperabilitet; DIGG:s föreskriftsrätt; täcker hela offentlig sektor | [HTML](https://data.riksdagen.se/dokument/HD03244.html) |
| **EU 2024/903** Interoperable Europe Act | EU-kommissionen / EP | 2024 | Rättslig skyldighet för IIA; Interoperable Europe Board | [EUR-Lex](https://eur-lex.europa.eu/eli/reg/2024/903/oj/eng) |
| **EIF v2** New European Interoperability Framework | EU-kommissionen (ISA²) | 2017 | 47 rekommendationer, 4 lager, 12 principer | [PDF](https://ec.europa.eu/isa2/sites/default/files/eif_brochure_final.pdf) |
| **EIRA 6.1.0** | EU-kommissionen | 2024 | Architecture building blocks; validator-tjänster | [Interoperable Europe Portal](https://interoperable-europe.ec.europa.eu/collection/european-interoperability-reference-architecture-eira) |
| **Skr. 2025/26:33** Riksrevisionens rapport om statliga strategiska digitaliseringsprojekt | Finansdepartementet | 2025 | Ena underutnyttjad, DIGG saknar verktyg, datakvalitetskrav saknas i 97 % av projekten | [HTML](https://data.riksdagen.se/dokument/HD0333.html) |
| **ARF v2.4/2.5** EUDI Wallet Architecture Reference Framework | EU-kommissionen | 2024–2025 | Teknisk interoperabilitetsmodell för EUDIW; attributcertifieringskedja; presentation protocols | [GitHub](https://github.com/eu-digital-identity-wallet/eudi-doc-architecture-and-reference-framework) |
