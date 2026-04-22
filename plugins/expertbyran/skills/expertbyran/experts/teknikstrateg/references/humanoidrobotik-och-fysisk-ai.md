# Humanoidrobotik och Fysisk AI 2026 — Referensmaterial

*Källa: omvärldsbevakning april 2026. Data från Boston Dynamics, Figure AI, Agility Robotics, Google DeepMind, Robotics 24/7, Automate.org.*

---

## TRL-Bedömning: Humanoidrobotik April 2026

| Applikationsdomän | TRL | Motivering |
|---|---|---|
| Avgränsade industriuppgifter (materialhantering, montering) | 7–8 | Produktion startad, pilot-deployments verifierade |
| Fordonstillverkning (logistik, montering) | 7 | BMW, Hyundai, Toyota deployments aktiva |
| Generalist humanoid — dynamiska miljöer | 5–6 | Demo-kapabelt, inte kommersiellt produktionsklart |
| Sjukvård och hem-assistans | 4–5 | Tidig forskning, inga kommersiella deployments |

---

## Produktionsdeployments — Verifierade April 2026

### Boston Dynamics Atlas

**Specifikationer:**
- Elektrisk (ersätter hydraulisk generation)
- Enterprise-grade, produktionsversion
- Byter egna batterier autonomt → fortsatt drift utan mänsklig intervention
- Lyftkapacitet: tung last, uthållig takt

**Partnerships och deployments:**
- **Hyundai RMAC** (Robotics Metaplant Application Center, Georgia, USA): primär produktionspartner. Alla 2026-leveranser utbokade.
- **Google DeepMind**: dedikerad Atlas-flotta för Gemini Robotics-forskning. Kapabilitetsutveckling + kommersialiseringsbana.

**Gemini Robotics-integration:**
- Google DeepMind integrerar Gemini Robotics foundation models direkt i Atlas
- Ger kognitiv kapabilitet och uppgiftsgeneralisering cross environments
- Potentiellt: Atlas lär sig nya uppgifter via naturspråksinstruktioner

**Prissättning/affärsmodell:** enterprise-kontrakt, ej offentlig prislista.

### Figure AI — Figure 03

**Status:** Nästa generations platform efter Figure 01/02.

**Ekonomi:**
- Värdering: **$39 miljarder** (H1 2026)
- Investerare: OpenAI, Microsoft, NVIDIA, Amazon, Jeff Bezos m.fl.
- BMW Spartanburg-pilot: **>30 000 fordon** stöttade

**Kapabiliteter:**
- Generell-purpose humanoid med stark industriell tyngdpunkt
- AI-driven autonomi i realtid
- Skalbar produktionslinje i uppbyggnad

**Marknadsmål:** logistik, tillverkning, kommersiella miljöer.

### Agility Robotics — Digit

**Status:** Kommersiellt tillgänglig via RaaS (Robot-as-a-Service).

**Deployments:**
- **Toyota Motor Manufacturing Canada** (Woodstock): 7+ enheter aktiva för RAV4-logistik (februari 2026)
- Validerat i produktionsmiljö för tunga repetitiva uppgifter

**RaaS-modell:** månadsvis prenumerationsavgift, Agility ansvarar för underhåll och uppdateringar. Lägre tröskel för adoption.

### Kinesiska Humanoidrobotar

**Händelse:** Beijing E-Town Halvmaraton, april 2026
- Kinesiska humanoidrobotar deltog i officiell halvmaratontävling
- Demonstrerar uthållighet (21 km) och auton dynamisk navigering i realtid i folkrika miljöer
- Deltagande aktörer inkluderar: UBTech, Fourier Intelligence, Unitree Robotics

**Strategisk kontext:** Kina investerar massivt i humanoidrobotik som strategisk industri. Kombinerat med AI-modeller från Alibaba/Zhipu/Moonshot skapas komplett stack utan beroende av västliga leverantörer.

---

## Teknologidrivkrafter — Vad Möjliggör 2026

### Foundation Models för Robotik

**Gemini Robotics** (Google DeepMind): multimodal foundational model tränad på rörelsedata, videoinstruktioner och naturspråk. Möjliggör:
- Zero-shot generalisering till nya uppgifter
- Naturspråksinstruktion av robotar
- Transfer learning från simulering till fysisk miljö (sim-to-real)

**RT-2** (Google DeepMind, föregångare): visade att vision-language-action models kan generalisera till osedda uppgifter. Gemini Robotics är nästa generation.

**OpenVLA, Octo** (open-source): demokratiserar tillgång till robot foundation models.

### Hardware-genombrott

- **Aktuatorer**: elektriska linjäraktuatorer ersätter hydraulik. Tystare, mer precisa, lättare att underhålla.
- **Batteriteknologi**: uthållighet förbättras — Atlas kan byta egna batterier och återgå till arbete utan operatör
- **Sensorer**: förbättrad LiDAR + depthmaps + force-torque-sensorer i händer
- **Compute**: on-board edge AI möjliggör realtids-inferens utan cloud-beroende

---

## Ekonomisk Logik och Marknadsdynamik

### Varför Nu?

1. **Arbetsbristen** (demografisk): 10+ miljoner tillverkningsjobb i USA ensamt utan kandidater. Humanoidrobotar konkurrerar med frånvaro av alternativ, inte med mänsklig lönearbetare.
2. **AI-mognad**: foundation models når kapabilitetströskel för generaliserade fysiska uppgifter
3. **Kostnadsfall**: hardware-komponentkostnader följer liknande kurva som solar/batteries
4. **RaaS-modellen**: eliminerar capex-barriären för SMEs

### Prissättning — Riktmärken

- **Figure 03**: prissättning ej publik men referensramarna är $150–200k/enhet för industriell humanoid
- **Agility Digit (RaaS)**: ~$70–100k/år (uppskattning baserat på publicerade partnerskapstermer)
- **Boston Dynamics Atlas**: enterprise-prissättning, multi-unit kontrakt

### Konkurrenskraftig hotbild mot mänsklig arbetskraft

Humanoidrobotar är inte direkt billigare än mänsklig arbetskraft idag (2026). Fördelarna är:
- Skiftkontinuitet (24/7 drift utan övertidsersättning)
- Konsistent kvalitet
- Noll personalrörlighet i segmentet
- Skalerbarhet (beställ 100 enheter, leverans 6 månader)

Breakeven mot mänsklig arbetstagare i tillverkning: analytiker estimerar 3–5 år vid $80–120k/enhet och $15–25/tim mänsklig lönekostnad.

---

## Riskbild

### Tekniska risker

- Sim-to-real gap: modeller tränade i simulering underperformar i oordnade verkliga miljöer
- Felsäkerhet: vad händer när robot-agent gör fel i farlig industriell miljö?
- Batterihälsa och uptime: kommersiell threshold är >95% uptime

### Regulatoriska risker

- EU Machinery Regulation (ny 2023, applicerbar 2027): kräver säkerhetsbedömning för AI-driven maskineri
- CE-märkning för autonoma robotar: process pågår
- Arbetsrätt: inga etablerade regler för robotens juridiska ansvar vid skadestånd

### Geopolitiska risker

- Export av humanoid-AI till Kina: USA-exportkontroller kan komplicera internationell marknadsföring
- Kinesiska humanoidrobotar i västerländska fabriker: supply chain security-frågor
