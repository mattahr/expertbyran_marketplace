# Regelverkskarta: Telekommunikation & Digital Infrastruktur

Senast uppdaterad: 2026-04-29

## Primärt regelverk (Sverige)

| Lag/förordning | Kortnamn | Kärna | Relevant för |
|---|---|---|---|
| Lag (2022:482) om elektronisk kommunikation | LEK 2022 | Genomför EECC; PTS-tillsyn; säkerhetskrav ersatta av cybersäkerhetslagen; spektrumtilldelning 11 kap. | All telekomreglering |
| Lag (2018:1174) om informationssäkerhet för samhällsviktiga och digitala tjänster | NIS-lagen | Genomför NIS1; ersätts av cybersäkerhetslagen | Operatörer av samhällsviktiga tjänster (historik) |
| Cybersäkerhetslagen (Prop. HD0328, 2025) | Cybersäkerhetslagen | Genomför NIS2; ersätter LEK 8 kap. för telekomoperatörer; artikel 21-krav; ledningsansvar | Säkerhetskrav för telekomoperatörer fr.o.m. ikraftträdande |
| Lag (2019:904) om skydd av Sveriges säkerhet vid tillstånd att använda radiosändare | 5G-säkerhetslagen | Möjliggör säkerhetsvillkor i 5G-licenser; PTS samråder med SÄPO/FM | 5G-tillstånd, leverantörsbedömning |
| Lag (2016:534) om åtgärder för utbyggnad av bredbandsnät | Bredbandslagen | Öppet tillträde, samfordning, PTS tvistlösning — obsolet för delar som täcks av GIA fr.o.m. nov 2025 | Bredbandsutbyggnad (övergångsfas) |

## EU-regelverk

| Direktiv/förordning | Kortnamn | Kärna |
|---|---|---|
| Direktiv (EU) 2018/1972 | EECC | Europeisk kodex för elektronisk kommunikation; 20-åriga spektrumlicenser; genomfört via LEK 2022 |
| Direktiv (EU) 2022/2555 | NIS2-direktivet | Höjer cybersäkerhetskraven; genomförs i Sverige via cybersäkerhetslagen (Prop. HD0328) |
| Direktiv (EU) 2022/2557 | CER-direktivet | Kritiska entiteters motståndskraft; utreds parallellt med NIS2 |
| Förordning (EU) 2024/1309 | GIA / Gigabitinfrastrukturförordningen | Ersätter Utbyggnadsdirektivet (2014/61/EU); direkt tillämplig fr.o.m. 12 nov 2025 |

## Nyckelaktörer och deras roller

| Myndighet | Roll |
|---|---|
| PTS | Tillsynsmyndighet LEK, NIS (digital infrastruktur), GIA; tillståndsgivning spektrum; CSIRT-funktion |
| MSB | Nationell NIS-kontaktpunkt; CSIRT-enhet; NIS2-föreskrifter (MSBFS); samordning sektors-tillsynsmyndigheter |
| SÄPO | Bedömer nationella säkerhetsrisker vid 5G-tillståndsgivning (samråd med PTS) |
| FM (Försvarsmakten) | Militärt säkerhetsperspektiv i 5G-samråd |
| Länsstyrelserna | Handlägger regionala bredbandssubventioner; fem länsstyrelser blir tillsynsmyndigheter under NIS2 |
| Jordbruksverket | Förvaltar EU-medel för landsbygdsbredband |

## GIA — Gigabitinfrastrukturförordningen (EU 2024/1309)

**Status**: Tillämpas fr.o.m. 12 november 2025. Direkt tillämplig förordning. Ersätter Utbyggnadsdirektivet (2014/61/EU).

**Vad är nytt jämfört med Utbyggnadsdirektivet:**
- Skyldigheterna gäller inte bara nätoperatörer utan även *offentliga organ* och *facilitetsoperatörer*
- Strängare krav på informationstjänsten: central informationspunkt ska vara digital, tillstånd kan sökas via den
- Bindande tidsfrist: 4 månader för beslut om tillståndsansökan
- *Tyst godkännande* om tidsfrist överskrids — Sverige väljer skadeståndsrätt istället (Prop. HD0368)

**PTS nya uppgifter under GIA:**
- Ansvar för *central informationspunkt* (digital portal för infrastrukturinfo och tillståndsansökningar) — 50 Mkr engångskostnad, 15,6 Mkr/år drift
- *Tvistlösningsorgan* för tillträdes-, samordnings- och öppenhetstvister
- *Tillsynsmyndighet* för GIA-efterlevnad (14 Mkr/år); sanktionsinstrument: vitesförelägganden

**Genomförandestatus Sverige (april 2026):**
- Nov 2025: GIA direkt tillämplig; Bredbandslagen obsolet för överlappande delar
- Feb 2026: Art. 10 (fiberinfrastruktur i byggnader) tillämpas
- Mars 2026: Lag om avvikande från tyst godkännande (Prop. HD0368) i kraft
- Maj 2026: Kompletteringslag (SOU 2025:110) träder i kraft; Bredbandslagen upphävs

**Nyckelkällor:**
- SOU 2025:110 — Snabbare bredband i hela landet (DocRec-id: 24108)
- Prop. HD0368 — Avvikande från tyst godkännande (Justitiedepartementet 2025)
- Betänkande HD01TU11 (Trafikutskottet 2026)

## Satellitkommunikation — regulatorisk behandling

**Regleringsstruktur (LEK + ITU):**
- *Upplänk* (terminal → satellit): kräver PTS-tillstånd enligt LEK 3 kap.
- *Nedlänk* (satellit → terminal): regleras av ITU:s radioreglemente — inte av LEK. PTS har inget direkt mandat.
- PTS tillstånd 10 år med möjlig 5-årsförlängning.

**Starlink (LEO) i Sverige:**
- Anmält till ITU via FCC (USA). Frekvensband: Ka-band nedlänk 17,7–21,2 GHz; upplänk 27,5–29,5 GHz.
- PTS godkände Starlink för svenska terminaler (upplänk) sent 2021.
- Full täckning Sverige sedan 2024. PTS: "det enda realistiska alternativet" för de sista procenten av bredbandsmålet.

**Regulatorisk asymmetri:**
- SpaceX/Starlink koordineras med ITU via USA, inte Sverige.
- Sverige saknar mandat över: satellitsegmentet, prissättning, öppet tillträde, tjänstenivåer (SLA).
- Satellit räknas *inte* som "gigabitnät" i GIA — inga GIA-skyldigheter.
- Statligt subventionerade terminalinstallationer skapar beroendeposition till icke-reglerat utländskt monopol (SpaceX).

**Nyckelkällor:**
- SOU 2021:91 — En ny rymdlag (DocRec-id: 10729)
- SOU 2023 — Sveriges säkerhet i etern (DocRec-id: 11417, HBB363)
- PTS-ER-2022:18 — Satellit: en möjlighet till snabbt bredband 2025
