# Expertbyråns expertkatalog

Detta är konsultchefens (`SKILL.md`) källa för vilka experter som finns på byrån. När en ny expert läggs till MÅSTE den listas här — annars är den osynlig för konsultchefen.

## Aktiva experter

| Mapp | Titel | Domän | Anropa när |
|---|---|---|---|
| `arbetsmarknad` | Arbetsmarknadsexperten | Svensk arbetsmarknad, sysselsättning, lönebildning, arbetsmarknadsreformer | LAS, a-kassa, Arbetsförmedlingen, aktiva åtgärder, partsmodellen, kompetensförsörjning, integration på arbetsmarknaden |
| `bistand` | Biståndsexperten | Internationellt bistånd, Sida, OECD-DAC, humanitärt bistånd | Biståndsinsatser, DAC-kriterierna, Sidas styrning, resultatmätning i bistånd, humanitär rätt |
| `cyber` | Cyberexperten | Cybersäkerhet, informationssäkerhet, säkerhetsskyddslagen | Säkerhetsskyddsanalys, NIS2, DORA, statliga IT-incidenter, NCSC, SÄPO-tillsyn, kritisk infrastruktur |
| `digitalisering` | Expert Digitalisering | Statlig digitalisering, IT-styrning, offentliga IT-projekt | Statliga IT-projekt, e-förvaltning, DIGG, Riksrevisionens IT-granskningar, digitaliseringsstrategi, AI i offentlig sektor |
| `effektivitetsrevisor` | Effektivitetsrevisorn | Revisionsmetodik, ISSAI-standarder, granskningsdesign | Formulera granskningsfråga, normkrav och iakttagelse–slutsats–kedja, metoddesign, ISSAI 300/3000, Riksrevisionens process |
| `forsvar` | Expert Försvar | Försvarspolitik, Försvarsmakten, totalförsvar, NATO | Försvarsmakten, FMV, NATO-anpassning, försvarsekonomin, totalförsvarets myndigheter, försvarsbeslut |
| `hallbarhet-esg` | Hållbarhets- och ESG-experten | ESG-rapportering, hållbarhetsreglering, CSRD | CSRD, GRI, TCFD, ISSB, EU Taxonomy, hållbarhetsredovisning, klimatrisk i finanssektorn |
| `halso-och-sjukvard` | Expert Hälso- och sjukvård | Hälso- och sjukvårdspolitik, regionstyrning, primärvård | Vårdgaranti, tillgänglighet, primärvårdsreformen, regionernas styrning, Socialstyrelsen, IVO, nära vård |
| `klarsprak` | Klarspråksexperten | Klarspråk, myndighetsskrivande, svenska brukstexter | Granska eller skriva om svenska texter till klarare språk, myndighetstext, byråkratiska konstruktioner, passiv form |
| `kvalitativa-metoder` | Experten på kvalitativa metoder | Kvalitativ forskningsmetodik, intervjustudier, fallstudier | Design av intervjustudier, tematisk analys, fallstudier, mixed methods, bedöma kvalitativ studies trovärdighet |
| `kvalitetsgranskare` | Kvalitetsgranskaren | Vetenskaplig granskning av revisionsrapporter, opponentmetodik | Granska iakttagelse–slutsats–rekommendationskedjor, vetenskapliga krav på granskningsrapporter, opponering |
| `kvantitativ-analytiker` | Den kvantitative analytikern | Statistik, kvantitativ metod, kausalidentifiering | Tolka statistiska resultat, regressionsanalyser, kausalitet vs korrelation, undersökningsdesign, visualisering |
| `miljo-och-klimat` | Miljö- och klimatexperten | EU klimatpolitik, svenska klimatramverket, energisystemet | ETS/CBAM/ESR/LULUCF, klimatlagen, netto-noll, Naturvårdsverkets/Energimyndighetens roll, elnät och elektrifiering |
| `offentliga-finanser` | Experten på offentliga finanser | Statsbudget, finanspolitik, skattesystem, kommunekonomi | Budgetpropositionen, överskottsmål, utgiftstak, skatteanalyser, finanspolitiskt ramverk, transfereringar, långsiktig hållbarhet |
| `rattslig-utredare` | Den rättslige utredaren | Förvaltningsrätt, EU-rätt, offentlig rätt, lagtolkning | Tolka lag och förordning, rättskedjans hierarki, förvaltningsrättsliga principer, EU-direktivimplementering, rättslig PM |
| `rattsvasendet` | Expert rättsväsende och civilt försvar | Rättsväsendets styrning, civilt försvar, brottsbekämpning | Polismyndigheten, Åklagarmyndigheten, civilt försvar, skydd av hotade personer, gängbrottslighet, rättskedjan vid höjd beredskap |
| `telekommunikation` | Expert Telekommunikation | Telekomreglering, bredband, digital infrastruktur, Post- och telestyrelsen | Bredbandsutbyggnad, täckning, PTS, frekvensförvaltning, telekommarknaden, 5G, digital infrastrukturpolitik |
| `transport` | Transportexperten | Transportinfrastruktur, järnväg, kollektivtrafik, trafiksäkerhet | Nationell transportplan, järnvägens punktlighet och underhållsskuld, Trafikverket, trafiksäkerhet, nollvisionen, hållbara transporter |
| `utbildning` | Utbildningsexperten | Skola, högskolepolitik, lärarförsörjning, likvärdighet | Skolresultat, PISA, likvärdighet, Skolverket, Skolinspektionen, lärarförsörjning, högskolans styrning, UKÄ |
| `valfard` | Välfärdsexperten | Socialförsäkring, socialtjänst, äldreomsorg, LSS | Försäkringskassan, sjukförsäkring, socialtjänst, äldreomsorgens kvalitet, LSS, barnpolitik, kommunernas välfärdsansvar |

Konsultchefen ska säga rakt ut till användaren när ingen expert matchar, snarare än att försöka improvisera utan expertroll.

## Icke-routningsbara mappar

Följande mappar finns under `experts/` men ska **aldrig** routas till. De är mallar och referenser för plugin-utveckling:

| Mapp | Syfte |
|---|---|
| `_TEMPLATE` | Skelettmall som kopieras när en ny expert skapas. |
| `_EXEMPEL` | Färdigskriven referens-EXPERT.md (klarspråksexpert) som visar hur en komplett expert ser ut. Används av `expert-utveckling`-skillen som konkret förebild. |

## Hur konsultchefen använder denna fil

1. Konsultchefen (`SKILL.md`) läser denna fil först varje gång den triggas.
2. Den matchar användarens behov mot raderna ovan.
3. För varje träff läser den `experts/<expertnamn>/EXPERT.md`.

## Lägga till en ny expert

INGEN annan än konsultchefen får lägga till en ny expert i katalogen!
Om du inte hittar din mapp - avbryt direkt och kontakta konsultchefen!

Se `[../../../CLAUDE.md](../../../CLAUDE.md)` på plugin-roten för fullständig checklista. Kortversion:

1. `cp -r experts/_TEMPLATE experts/<nytt-expertnamn>` (ASCII, kebab-case).
2. Fyll i `experts/<nytt-expertnamn>/EXPERT.md`.
3. Lägg eventuella tunga underlag i `experts/<nytt-expertnamn>/references/`.
4. **Lägg till en rad i tabellen ovan.** Detta steg glöms lättast.
5. Commit.
