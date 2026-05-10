# EBA bankspecifika hållbarhetskrav — GAR, BTAR och Pelare 3 ESG

## Regleringsram

Banker och stora kreditinstitut i EU omfattas av parallella hållbarhetsrapporteringskrav under CRR2 (Capital Requirements Regulation, förordning (EU) 575/2013 med ändringar via (EU) 2019/876), skilda från CSRD. Art. 449a CRR2 ger EBA mandat att ta fram bindande tekniska standarder (ITS) för ESG-upplysningar.

**Bindande standard:** EBA/ITS/2022/09 — "ITS on Pillar 3 disclosures on ESG risks"  
**Gäller från:** 2023-06-28 (stora börsnoterade institut med >500 anställda)  
**Full referens:** https://www.eba.europa.eu/regulation-and-policy/transparency-and-pillar-3/its-pillar-3-disclosures-esg-risks

---

## Green Asset Ratio (GAR)

### Definition och formel

GAR mäter hur stor andel av bankens utlåning som är taxonomiförenlig (taxonomy-aligned) enligt EU-taxonomin.

```
GAR = Taxonomiförenliga tillgångar i bankboken
      ─────────────────────────────────────────
      Totala in-scope-tillgångar i bankboken
```

### In-scope-tillgångar (ingår i nämnaren)

- Bolån och bostadslån till hushåll
- Kommersiella fastighetsfinansiering
- Företagslån till stora börsnoterade bolag som rapporterar EU-taxonomi
- Finansiering av kommuner och lokala myndigheter

### Out-of-scope-tillgångar (undantagna från nämnaren)

- Lån till SME (< 250 anställda OCH < 50 MEUR omsättning — båda villkoren)
- Lån till icke-EU-företag
- Derivat, handelsportfölj, interbanklån, interbankexponeringar
- Centralbanksexponeringar och statsexponeringar mot EU-stater

### Praktiska konsekvenser för nordiska banker

Den stora majoriteten av nordiska bankers utlåning är till SME och privatpersoner. Täljaren (taxonomiförenliga) är liten; nämnaren (in-scope) är begränsad — men GAR uppfattas ändå som nyckeltal av investerare och tillsynsmyndigheter. Banker med stor andel SME-utlåning (t.ex. Handelsbanken, Swedbank, SEB) får strukturellt låg GAR utan att det speglar faktisk hållbarhetsprestanda.

**Revisorfokus:**
- Verifiera att DNSH-kriterierna (Do No Significant Harm) är uppfyllda för varje taxonomiförenlig tillgång
- Kontrollera att kundernas taxonomirapportering (täljaren) är korrekt inhämtad och validerad
- GAR-beräkning kräver granulär data per lånekategori — stickprovsgranskning av låneklassificering
- Verifiering av in-scope/out-of-scope-gränsen (SME-definition per EU-rekommendation 2003/361/EC)

---

## Banking Book Taxonomy Alignment Ratio (BTAR)

### Definition

BTAR är ett kompletterande nyckeltal som inkluderar tillgångar undantagna från GAR-nämnaren — främst SME-lån och lån till icke-EU-företag. Syftet är att ge en bredare bild av bankens exponering mot taxonomiförenliga aktiviteter.

```
BTAR = Taxonomiförenliga tillgångar (inkl. SME-estimat och non-EU-proxy)
       ───────────────────────────────────────────────────────────────────
       Totala tillgångar i bankboken (inkl. out-of-scope)
```

### Skillnad GAR vs BTAR

| Aspekt | GAR | BTAR |
|--------|-----|------|
| SME-lån i nämnaren | Nej | Ja |
| Non-EU-lån | Nej | Ja |
| Dataunderlag (täljaren) | Kundrapportering | Uppskattning/proxy |
| Representativitet för nordiska banker | Lägre (strukturellt) | Högre |
| Bindande krav | Ja (Pelare 3 mall 5–6) | Ja (Pelare 3 mall 7) |

**Revisorfokus för BTAR:**
- Dokumentation och validering av proxy/estimat-antaganden för SME-lån
- Konsistens i estimatmetodik över tid (jämförbarhet)
- Tydlig redovisning av osäkerheten i BTAR-beräkningen

---

## Pelare 3 ESG-upplysningar — nio mallar

EBA/ITS/2022/09 specificerar nio standardiserade mallar:

| Mall | Innehåll |
|------|----------|
| Template 1 | Kvalitativ information om ESG-risker (klimat, miljö, socialt, styrning) |
| Template 2 | Banking book — exponeringar mot klimatriskutsatta sektorer (NACE-kod) |
| Template 3 | CRREM-analys för fastighetsexponeringar (Carbon Risk Real Estate Monitor) |
| Template 4 | Exponeringar mot toppcounterparts med höga GHG-utsläpp (top 20) |
| Template 5 | GAR — stockposition (utestående tillgångar) |
| Template 6 | GAR — flödesposition (ny utlåning under rapportperioden) |
| Template 7 | BTAR |
| Template 8 | Exponeringar mot fysiska klimatrisker (Kotz et al.-klassificering) |
| Template 9 | Åtgärder för klimatriskhantering och gröna tillgångsmål |

---

## Skillnad mot CSRD Art. 8 (EU-taxonomin)

| Dimension | Pelare 3 (CRR2/EBA) | CSRD Art. 8 (EU-taxonomin) |
|-----------|---------------------|----------------------------|
| Reglerare | EBA (bankregulator) | EFRAG/EU-kommissionen |
| Tillämpning | Kreditinstitut (CRR-reglerade) | Alla stora bolag (CSRD-scope) |
| Format | Standardiserade mallar (fasta) | Flexibelt (rekommenderat format) |
| Fokus | Kreditriskexponering | Omsättning/capex/opex per aktivitet |
| Tillsyn | ECB/nationell finansinspektion | Extern revisor + finansinspektionen |
| Koppling | Kapitalreglering | Hållbarhetsrapportering |

**Viktig konsekvens:** Banker måste hantera *båda* regelverken parallellt — med delvis överlappande men inte identiska krav. GAR (Pelare 3) och Art. 8-nyckeltal kan ge olika siffror för samma bank beroende på beräkningsbas och scope.

---

## Revisionsimplikationer — sammanfattning

1. **In-scope vs. out-of-scope:** Verifiera att gränsen dras rätt (SME-definition, non-EU-kriterium)
2. **DNSH-verifiering:** Per taxonomiförenlig tillgång — kräver kunddata som kan vara svår att inhämta
3. **Täljaren:** Validera att kundernas taxonomirapportering faktiskt stödjer alignment-klassificeringen
4. **BTAR-estimat:** Dokumentation och konsistens i proxy-antaganden
5. **Dubbel rapportering:** Säkerställ att Pelare 3-upplysningar och Art. 8-upplysningar är konsistenta eller att skillnader förklaras
6. **Malljustering:** Kontrollera att bankens mallar följer EBA/ITS/2022/09 formatspecifikation — avvikelser är vanliga

---

## Primärkällor

- EBA/ITS/2022/09: https://www.eba.europa.eu/regulation-and-policy/transparency-and-pillar-3/its-pillar-3-disclosures-esg-risks
- CRR2 Art. 449a: Förordning (EU) 575/2013 med ändringar via (EU) 2019/876
- EU-taxonomiförordningen (EU) 2020/852 — DNSH-kriterier och tekniska screeningkriterier
- EU-rekommendation 2003/361/EC — SME-definition (används för in-scope/out-of-scope-gränsen)
- EBA Q&A-databas för GAR/BTAR-tolkningsfrågor: https://www.eba.europa.eu/single-rule-book-qa
