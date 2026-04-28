# Spektrum, 5G-status och 6G-forskning

## Sveriges spektrumtilldelning — översikt

| Frekvensband | Auktion/tilldelning | Tillståndshavare | Notering |
|---|---|---|---|
| 700 MHz | Dec 2018 | Telia, Net4Mobility | Täckningskrav 300 Mkr (Telia). Lågt band, god yttäckning; drev 5G-expansion 2023 |
| 3,5 GHz + 2,3 GHz | Jan 2021 | Telia, Hi3G (Tre), Net4Mobility, Teracom | Kärnband för storskalig 5G. Säkerhetsvillkor. Huawei-förbud |
| 900 MHz, 2,1 GHz, 2,6 GHz | Sept–okt 2023 | (auktionsvinnare) | Tillstånd fr.o.m. 1 jan 2026 (~25 år). Täckningskrav: 900 MHz (nya master i täckningsgap), 2,1/2,6 GHz (järnvägstäckning) |
| 1 800 MHz | Planerad 2025 | — | Ännu ej tilldelat (apr 2026) |
| 26 GHz (mmWave) | Ej tilldelat kommersiellt | — | Testtillstånd möjliga sedan 2017 (upp till 1 000 MHz). PTS leder EU-harmoniseringsarbetsgrupp |

**Nästa spektrumhändelse:** Kommersiell tilldelning av 26 GHz-bandet — hög kapacitet men begränsad räckvidd; relevant för densanätverk i städer, inte glesbygd.

## 5G-täckningsstatus Sverige (oktober 2023)

| Indikator | Okt 2022 | Okt 2023 |
|-----------|----------|----------|
| 5G-täckning hushåll | 57% | **90%** |
| 5G-yttäckning (geografisk) | ~11% | **29,7%** |
| 5G i glesbygd (hushåll) | 29% | **67,8%** |
| 1 Gbit/s tillgänglig | 97% | **98,6%** |

**Nyckelinsikter:**
- Gigabitmålet (98% av hushållen) uppnått i praktiken 2023/2024 — ett år före 2025-målet
- Mobilmålet 2023 (stabila mobila tjänster) *ej* uppnått: 95% av berörda ytor täcks; brister kvarstår längs järnvägar
- 5G-expansionen 2022→2023 drevs av 700 MHz-utbyggnad
- Källa: PTS-ER-2024:13; Prop. 2024/25:1 Utg.omr. 22 (DocRec 13979)

## Satellitkommunikation — regulatorisk behandling

**Regleringsstruktur:**
- *Upplänk* (terminal → satellit): kräver PTS-tillstånd enligt LEK 3 kap.
- *Nedlänk* (satellit → terminal): regleras av ITU:s radioreglemente — PTS har inget direkt mandat
- PTS-avgifter för satellitupplänk: 19 332 kr/år (< 10 GHz), 661 kr/år (14,0–14,5 GHz och 29,5–30 GHz)

**Starlink (LEO-satellit):**
- SpaceX LEO-system anmält till ITU via FCC (USA)
- PTS godkände Starlink för svenska terminaler (upplänk) i slutet av 2021
- Starlink: fullständig täckning över hela Sverige sedan 2024
- PTS identifierar satellit som "det enda realistiska alternativet" för att nå sista procenten av bredbandsmålet

**Regulatorisk asymmetri:**
- Sverige ger tillstånd för terminaldelen men saknar mandat över: satellitsegmentet, prissättning, öppet tillträde, tjänstenivåer (SLA)
- Satellit räknas inte som "gigabitnät" i GIA:s mening — inga skyldigheter om öppet tillträde, samordning
- Statligt subventionerade terminalinstallationer skapar kommersiell beroendeposition till ett icke-regulerat utländskt monopol

## 6G — Tidslinje och standardisering

**Tidslinje:**
- ~2026: Formell 6G-standardisering inleds (3GPP Rel-20+)
- ~2030: Kommersiell driftsättning av 6G förväntas

**Kandidatband för 6G (WRC-27-studier):**
- 7 125–8 400 MHz (övre 6 GHz-bandet) — pekat ut som nyckelband
- 14,8–15,35 GHz — under studie
- WRC-27 ska fatta beslut om pionjärband

**EU 6G-program — SNS JU (Smart Networks and Services Joint Undertaking):**
- Inrättat 2021; budget €1,8 miljarder 2021–2027 (€900M EU + €900M industri)
- Call 1–3: 80+ projekt finansierade
- Call 4 (maj 2025): €104M, öppen t.o.m. sept 2025
- Call 5 / Work Programme 2026: €116M till 20 projekt + €22M till 5 projekt
- Fokus: teknologisk suveränitet, säkerhet, samverkan med partner (USA, Japan, Sydkorea)
- Källa: smart-networks.europa.eu; digital-strategy.ec.europa.eu/en/policies/6g

**EU:s Digital Decade 2030-mål (6G-kontext):**
- Alla EU-hushåll täckta av gigabitnät
- Alla befolkade ytor täckta av 5G
- 10 000 klimatneutrala edge-noder
- 6G är fasen bortom Digital Decade; planering sker parallellt

**Säkerhetsaspekter specifikt för 6G:**
- EU planerar att tillämpa högrisk-leverantörs-logiken (5G-verktygslådan) på 6G
- EU Cybersecurity Package 2026 (CSA2) ger kommissionen befogenhet att utpeka högrisk-leverantörer — gäller alla generationer
- Tyskland har nationellt förbjudit kinesiska komponenter i framtida 6G-nät
- OpenRAN-arkitektur studeras som säkerhetsalternativ (minskar leverantörsberoende)

## Svensk 6G-satsning

**Regeringsuppdrag (U2024/00713, KN2024/00613):**
- Vinnova + Vetenskapsrådet stärker grundforskning, tillämpad forskning och innovation inom 6G
- Total budget: 390 Mkr; slutredovisas mars 2027
- Vinnova: 90 Mkr i utlysningar (nationell + internationell samverkan)
- Vetenskapsrådet: 60 Mkr 2025, 65 Mkr 2026

**Internationell samverkan:**
- EU (SNS JU), USA, Kanada, UK, Japan, Sydkorea, Singapore
- Ericsson är central aktör i svensk 6G-forskning och deltar i SNS JU

**Risk: relativ eftersläpning:**
- AI-kommissionen (SOU 2025): Sverige rankades plats 21 globalt i GSMA 5G-konnektivitetsindex 2024
- Norge, Finland, Danmark tillhör alla topp 7 globalt
- Sverige prioriterade låga frekvensband (yttäckning) på bekostnad av kapacitet i 3,5 GHz-bandet
- Risken är att denna eftersläpning förstärks om 6G-investeringarna inte följs upp

## 5G-verktygslådan och PTS löpande tillsynsarbete

- PTS fortsätter nationellt tillsynsarbete och EU-arbete kring 5G-säkerhetsrisker inklusive OpenRAN-arkitektur
- Sverige drivande i EU:s 5G-verktygslåda
- **Nationella telesamverkansgruppen:** stärkt lagstiftning from 1 maj 2024 — PTS kan besluta om deltagandekrav
- **Reservel Gotland:** pilot avslutat; erfarenheter om motståndskraft vid elavbrott kan tillämpas nationellt
- NCSC: PTS + MSB + FM + SÄPO fördjupar samverkan; utredning om effektiv NCSC-organisering beredd i Reg.kansliet
- Källa: Prop. 2024/25:1 Utg.omr. 22 (DocRec 13979, sid. 108–109)
