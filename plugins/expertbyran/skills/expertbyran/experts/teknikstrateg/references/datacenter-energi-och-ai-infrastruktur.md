# Datacenter, energi och AI-infrastruktur

Referensmaterial för bedömning av AI-infrastruktur som en sammanvävd energi-, etablerings- och säkerhetsfråga. Binder ihop suverän-AI-spåret med energipolitik och svensk etableringspolitik; ger konkreta KPI:er och granskningsfrågor.

## Kärnresonemang

AI-infrastruktur är fysiskt beroende av tre saker:

1. **Beräkningskapacitet** (GPU, accelerator, nätverk)
2. **El och nätkapacitet**
3. **Tillstånd, lokalisering och samhällsplanering**

Datacenter ska därför inte bedömas enbart som närings- eller digitaliseringspolitik — de är samtidigt energipolitik, industripolitik, säkerhetspolitik och revisionsbara styrningsobjekt.

## Globala prognoser — IEA *Energy and AI* (2025)

- Globala datacenter prognosticeras förbruka **~945 TWh år 2030** (från ~415 TWh 2024) — ungefär en dubblering.
- Andel av världselen rör sig från ~1,5 % mot ~3 %.
- AI är den viktigaste enskilda drivkraften.
- USA och Kina står för knappt 80 % av tillväxten.

Detta är ramen som svenska och europeiska beslut ska bedömas mot.

## EU-lagret — fysisk kapacitet bakom suverän AI

EU AI Continent Action Plan kopplar samman tre spår:

- **13 AI Factories i 17 medlemsstater**
- **9 nya AI-optimerade superdatorer 2025–2026** (EuroHPC-expansion)
- **CADA — Cloud and AI Development Act**: förenkla tillståndsgivning för ny datacenterkapacitet

Konsekvensen: om EU vill minska beroendet av amerikanska hyperscalers måste unionen bära kostnaden för egen fysisk AI-kapacitet — och hantera att compute-ambitioner kan öka snabbare än elnät, tillstånd och lokal acceptans.

## Sverige — styrkor och friktioner

Styrkor:

- Tillgång till **fossilfri el**
- **Gynnsamt klimat** för beräkningsintensiv infrastruktur
- Stark forskning i ML och AI-säkerhet

Friktioner:

- **Effektbrist i SE3/SE4**. ENTSO-E pekar ut SE4 som det elprisområde i Europa med minst installerad produktionskapacitet i förhållande till förväntad maxlast. Datacenter står idag för **~5 000–6 000 MW** i Svenska kraftnäts anslutningskö, varav **~80 % i SE3**, samtidigt som ~7 000 MW ny industriell elanvändning prognostiseras 2026–2030.
- **Datacenterelskatten har normaliserats**. Skattenedsättningen för datorhallar slopades 1 juli 2023 — energiskatten höjdes från 0,6 till 39,2 öre/kWh. Allmän energiskatt på el sänks till 41,1 öre/kWh från 2026. Etableringskalkylen har förändrats i annan riktning än de stöd RiR 2022:18 granskade.
- **Vatten- och lokal infrastrukturbelastning** i snabbväxande etableringskommuner.
- **Svag samordning** mellan närings- och energipolitiska mål i statens datacenterinsatser (RiR 2022:18).

## EED Article 12 — datacenter blir mätbart

Det reviderade energieffektiviseringsdirektivet (EED, 2023/1791) Article 12 + delegerad förordning (EU) 2024/1364 inför årlig rapporteringsskyldighet för datacenter i EU med installerad **IT-effekt ≥ 500 kW**.

Rapporterade KPI:er:

- **PUE** (Power Usage Effectiveness) — riktvärde för god praxis: PUE < 1,2.
- **WUE** (Water Usage Effectiveness)
- Andel **förnybar el**
- **ERF** (Energy Reuse Factor) — restvärmeåtervinning
- **Batterikapacitet**

Rapporteringscykel: första gången 15 september 2024, därefter senast 15 maj årligen, till EU-databas.

Restvärme, energieffektivitet och flexibilitet är därmed inte längre policyargument — de är mätbara, jämförbara och offentliga indikatorer.

## Effektkrav per anläggningstyp

- **Hyperscale**: 50–200 MW per anläggning är dagens normalstorlek; AI-fokuserade campus uppåt 300–1 000 MW planeras.
- **AI Factories (EU)**: typiskt 20–100 MW för dedikerade EuroHPC-instanser.
- **Edge-datacenter**: 0,5–5 MW.

Effektkravens skala styr nätanslutningskrav, vattenkylningens utformning och tillståndsprocessens längd.

## Granskningsfrågor (revisionsperspektiv)

- Har staten kopplat samman **AI-satsningar** med **energipolitiska förutsättningar**, eller behandlas de som separata spår?
- Fångar styrningen datacentrens möjliga bidrag till energisystemet — **restvärme**, **flexibilitet**, **energieffektivisering**?
- Är statliga och kommunala etableringsbeslut utformade så att **lokala kostnader** och **nationella nyttor** vägs mot varandra, särskilt i SE3/SE4?
- Finns trovärdigt underlag för att Sveriges konkurrensfördelar består när kapacitetskraven ökar och datacenterelskatten har normaliserats?
- Använder svenska tillsyns- och statistikmyndigheter de KPI:er som EED art. 12 nu kräver, eller riskerar Sverige att rapportera in mätetal som inte används i nationell granskning?

## Källor

- IEA, *Energy and AI* (april 2025). Executive summary: <https://www.iea.org/reports/energy-and-ai/executive-summary> ; <https://www.iea.org/reports/energy-and-ai/energy-demand-from-ai>
- IEA, *Data centre electricity use surged in 2025* (2025). <https://www.iea.org/news/data-centre-electricity-use-surged-in-2025-even-with-tightening-bottlenecks-driving-a-scramble-for-solutions>
- Direktiv (EU) 2023/1791 (EED, omarbetad), Article 12; delegerad förordning (EU) 2024/1364. <https://energy.ec.europa.eu/topics/energy-efficiency/energy-efficiency-targets-directive-and-rules/energy-efficiency-directive/energy-performance-data-centres_en>
- Kommissionen, *Commission adopts EU-wide scheme rating sustainability of data centres* (2024-03-15). <https://energy.ec.europa.eu/news/commission-adopts-eu-wide-scheme-rating-sustainability-data-centres-2024-03-15_en>
- EUDCA, sammanfattning av EED-art. 12. <https://www.eudca.org/energy-efficiency-directive>
- Svenska kraftnät, *Nätutvecklingsplan 2024–2033*. <https://www.svk.se/siteassets/om-oss/rapporter/2023/svk_natutveckling_2024-2033.pdf>
- Svenska kraftnät, *Så säkrar Svenska kraftnät elförsörjningen i södra Sverige*. <https://www.svk.se/utveckling-av-kraftsystemet/transmissionsnatet/sa-sakrar-svenska-kraftnat-elforsorjningen-i-sodra-sverige/>
- Skatteverket, *Slopad skattenedsättning för datorhallar* (2022). <https://skatteverket.se/foretag/skatterochavdrag/punktskatter/nyheterinompunktskatter/2022/nyheterinompunktskatter/slopadskattenedsattningfordatorhallar.5.1997e70d1848dabbac93896.html>
- Finansdepartementet, promemoria *Sänkt energiskatt på el* (Fi/2025/01060). <https://www.regeringen.se/rattsliga-dokument/departementsserien-och-promemorior/2025/05/sankt-energiskatt-pa-el/>
- Riksrevisionen, *RiR 2022:18 — Datacenterinvesteringar i Sverige*.
- Europeiska kommissionen, *AI Continent Action Plan* (2025).
