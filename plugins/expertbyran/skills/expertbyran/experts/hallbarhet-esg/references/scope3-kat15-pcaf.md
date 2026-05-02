# Scope 3 kategori 15 (Investments) och PCAF-standarden

## Vad kategorin täcker

Scope 3 kategori 15 avser växthusgasutsläpp kopplade till ett företags **finansiella investeringar** som inte redan ingår i Scope 1 eller 2. Det är den enda Scope 3-kategorin som riktar sig specifikt till **finansiella institutioner** (banker, pensionsfonder, försäkringsbolag, kapitalförvaltare).

**Fyra investeringstyper:**

| Typ | Beskrivning |
|-----|-------------|
| Egetkapitalinvesteringar | Ägarandelar i dotterbolag, intressebolag och JV:s |
| Skuldinstrument | Lån och obligationer till specifika bolag |
| Projektfinansiering | Långsiktig finansiering av infrastruktur/energiprojekt |
| Förvaltade investeringar | Kapital förvaltade å kunders vägnar |

---

## Beräkningsmetoder (GHG Protocol kap. 15)

### Primär metod — investeringsspecifik

1. Samla in Scope 1+2-data från portföljbolagen (investees)
2. Beräkna **attribution factor** = ägarandel (equity) / totalt eget kapital + skuld (**EVIC** — Enterprise Value Including Cash) för egetkapitalinvesteringar; eller utestående lånebelopp / EVIC för skuldinstrument
3. Portföljbolagets utsläpp × attribution factor = institutionens andel

**Praktisk notering:** EVIC ska beräknas per mätdatum (t.ex. 31 dec). Gammal data ger systematisk underskattning om portföljvärden förändrats under rapporteringsperioden.

### Fallback — genomsnittsdatametod (EEIO)

Används när investee inte rapporterar Scope 1+2:
- Portföljbolagets omsättning × branschgenomsnittlig utsläppsintensitet (ekonomisk input-output-data)
- Lägre precision — skapar risk för systematisk underskattning i kapitalintensiva sektorer

**Rekommendation:** Identifiera de 20–30 % av portföljinnehaven som sannolikt svarar för 80–90 % av utsläppen (fossila bränslen, stål, cement, flyg) och prioritera investeringsspecifik metod för dessa.

---

## PCAF-standarden

**Bakgrund:**
- PCAF (Partnership for Carbon Accounting Financials) grundades 2015
- Global standard lanserades november 2020 (v1), v2 2022, v3 2025
- Bygger på GHG Protocol Scope 3 kat. 15 men utökar och specificerar per tillgångsklass
- Första utgåvan fick GHG Protocols "Built on GHG Protocol"-märkning; senare utgåvor har inte omgranskats (GHG Protocols granskningsservice lades ned)

**Standardens tre delar:**

| Del | Täckning |
|-----|----------|
| **Part A — Financed Emissions** | 7 tillgångsklasser: noterade aktier + företagsobligationer, företagslån + onoterade aktier, projektfinansiering, kommersiell fastighet, bolån, billån, statsobligationer |
| **Part B — Facilitated Emissions** | Kapitalmarknadstransaktioner, M&A-rådgivning |
| **Part C — Insurance-Associated Emissions** | Utsläpp kopplade till försäkrade tillgångar |

---

## PCAF:s datakvalitetspoäng — direkt revisionsverktyg

| Poäng | Datakälla | Tillförlitlighet |
|-------|-----------|-----------------|
| 1 | Verifierad primärdata direkt från investee | Högst |
| 2 | Rapporterade men overifierade Scope 1+2 från investee | Hög |
| 3 | PCAF-modellerade data baserade på ekonomiska data | Medel |
| 4 | Sektorgenomsnitt per produktionsenhet | Låg |
| 5 | Sektorgenomsnitt per omsättning (EEIO) | Lägst |

**Revisionsimplikation:** Hög andel poäng 4–5 signalerar materiell osäkerhet. CSRD kräver att finansiella institutioner redovisar genomsnittlig datakvalitetspoäng per tillgångsklass. Revisorn måste bedöma om vald metod är rimlig och dokumenterad — och om omdömets avgränsning speglar faktisk datakvalitet (begränsad säkerhet vid poäng 4–5 för stora delar av portföljen).

---

## Svenska implikationer

**AP-fonderna (AP1–4, AP7):** Alla är PCAF-signatörer. Rapporterar portföljutsläpp per tillgångsklass i sina hållbarhetsredovisningar. Riksdagens mål för AP-fonderna inkluderar klimatrelaterade riktlinjer.

**Banker och försäkringsbolag (CSRD fas 1):** SEB, Handelsbanken, Swedbank m.fl. är PCAF-signatörer och i CSRD-scope. Financed emissions (kat. 15) är ofta den dominerande Scope 3-källan för banker.

**Revisionsagenda vid granskning av finansiellt institut:**
1. Har institutionen motiverat val av metod (investeringsspecifik vs. EEIO) per tillgångsklass?
2. Används EVIC konsekvent och med aktuell data?
3. Redovisas genomsnittlig PCAF-poäng per tillgångsklass?
4. Är Scope 1+2 som ingår i finansierade utsläpp inte redan redovisade i institutionens egna Scope 1+2 (dubbeltäckning)?

---

## Primärkällor

| Källa | Typ | Relevanta avsnitt |
|-------|-----|-------------------|
| GHG Protocol Corporate Value Chain (Scope 3) Standard | Standard | Kap. 15 (Investments), s. 136–146; kap. 5 (attribution) |
| PCAF Global GHG Accounting Standard v3 (2025) | Standard | Part A (Financed Emissions), Annex datakvalitetspoäng |
| ESRS E1 | EU-standard | Krav på Scope 3 inklusive kat. 15 disclosure |
| carbonaccountingfinancials.com | Webb (PCAF) | Standard, signatärlista, implementeringsvägledning |
