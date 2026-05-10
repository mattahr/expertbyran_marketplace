# Modellvalidering och fairness-metodik för offentlig AI

Källor: ISF 2018 "Riskbaserade urvalsprofiler och likabehandling" (s. 6–12), Mitchell et al. 2019 "Model Cards for Model Reporting", ISF 2026:1 s. 132–133, EU AI Act Art. 9, 11, 13, 14.

## Kärninlärning

En modell kan ha hög träffsäkerhet i snitt men systematiskt diskriminera mot specifika grupper — detta kallas indirekt diskriminering och är förbjudet enligt diskrimineringslagen oavsett avsikt. I offentlig förvaltning är fairness ett rättssäkerhetskrav: RF 1:1 (likhetsprincipen) kräver att myndigheter behandlar lika fall lika.

**Paradoxen:** att inte inkludera t.ex. kön i en modell kan paradoxalt nog *skapa* indirekt diskriminering via proxy-variabler (postnummer, lön) som korrelerar med kön.

## Sex fairness-kriterier (ISF 2018)

ISF:s rapport "Riskbaserade urvalsprofiler och likabehandling" (2018) är det svenska referensverket.

| # | Kriterium | Formel | ISF:s bedömning |
|---|-----------|--------|-----------------|
| 1 | Ovetskap | Exkludera skyddade attribut | Enkelt men svagt — proxy-variabler kringgår |
| 2 | Demografisk jämlikhet | P(Ŷ\|D=0) = P(Ŷ\|D=1) | Enkel men manipulerbar |
| 3 | Lika förutsättningar | P(Ŷ\|D=0,Y=1) = P(Ŷ\|D=1,Y=1) | **Rekommenderat för FK:s urvalsprofiler** |
| 4 | Individuell rättvisa | Liknande individer → liknande prediktioner | Kräver matchningsdata |
| 5 | Kontrafaktisk rättvisa | Prediktionen ändras inte om skyddat attribut ändras | Kräver kausal graf |
| 6 | Likabehandling (ISF-metod) | Demografisk profil faktiska fel = slumpmässiga kontrolldata | Starkast, kräver stickprovskontroller |

## Automation bias — den dolda risken

Forskning visar att handläggare tenderar att följa AI-rekommendationer okritiskt, särskilt under hög arbetsbelastning. Human-in-the-loop är inte samma sak som meningsfull mänsklig kontroll — EU AI Act Art. 14 kräver att tillsynen är reell, inte rubber-stämpling.

## Model Cards (Mitchell et al. 2019)

Googles standard, nu branschnorm för ansvarsfull AI. Dokumenterar:
1. Modelldetaljer, version, ansvarig organisation
2. Avsedd och icke-avsedd användning
3. Prestanda-mätvärden nedbrutet per demografisk grupp
4. Kända bias-risker och begränsningar

EU AI Act Art. 11 (teknisk dokumentation) och Art. 13–14 (transparens) täcker i praktiken Model Card-informationen.

## Granskningschecklista

**A. Grundläggande validering**
- [ ] Dokumentation om träningsdata (ursprung, period, urvalsprincip)?
- [ ] Testad på data utanför träningen?
- [ ] Prestanda-mätvärden dokumenterade (precision, recall, AUC)?
- [ ] Datadrift-analys genomförd?

**B. Fairness-validering**
- [ ] Testats om utfall varierar längs kön, etnicitet, ålder?
- [ ] Vilken fairness-definition? Konsekvent med likabehandlingskravet?
- [ ] Proxy-variablers korrelation med skyddade attribut analyserad?

**C. Mänsklig kontroll (EU AI Act Art. 14)**
- [ ] Är human-in-the-loop meningsfull, eller rubber-stämpling?
- [ ] Automation bias analyserad?

**D. Kontinuerlig monitorering (MLOps)**
- [ ] Rutiner för att upptäcka prestanda-försämring i produktion?
- [ ] Ansvarig funktion (MLOps-team)?

## Läs när

Anropa denna fil när du: ska bedöma om ett AI-systems beslutsunderlag behandlar grupper lika, granskar om human-in-the-loop är meningsfull, utvärderar om en myndighets AI-dokumentation uppfyller Model Card-standarden, eller ska formulera fairness-granskningsfrågor.
