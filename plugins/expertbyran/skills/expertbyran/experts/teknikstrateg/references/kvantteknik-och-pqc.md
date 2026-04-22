# Kvantteknik och Post-Quantum Cryptography 2026 — Referensmaterial

*Källa: omvärldsbevakning april 2026. Data från Google, IBM, IonQ, Xanadu, NIST, ScienceDaily, IEEE Spectrum, The Quantum Insider.*

---

## Status April 2026: "Transistormoment"

Vetenskapare och industrianalytiker konstaterar 2026 att kvantteknik nått sitt "transistormoment": funktionella system existerar och levererar verifierade övertag på specifika problem, men skalning till generell praktisk relevans kräver ytterligare engineering-genombrott — precis som transistorn krävde decennier av miniaturisering för att nå massproduktion.

Global kvantdatormarknad 2026: **>$10 miljarder USD**.

---

## Tekniska Genombrott och Milstolpar

### Google Quantum Echoes

- **Algoritm**: Out-of-order time correlator
- **Prestanda**: 13 000x snabbare på Willow-chip jämfört med bästa klassiska superdator
- **Signifikans**: Första verifierbara quantum advantage demonstration som uppfyller peer-review-kriterier för veriferbar övertag (inte bara "quantum supremacy" på kontroversiella benchmarks)

### Hardware-teknikraser

| Teknik | Ledande aktör | Status april 2026 |
|--------|-------------|------------------|
| Superconducting qubits | Google (Willow), IBM | Ledande fidelity, kräver nära absoluta nollpunktens kylning (-273°C) |
| Trapped ion | IonQ | Hög fidelity, långsammare gates, rumstemperatur-kompatibelt vid periferutrustning |
| Photonic/Boson sampling | Xanadu | Rumstemperatur-möjlig, svårt att uppnå universell kvantberäkning |
| Neutral atom | Atom Computing, Pasqal | 2026 "big leap" enl. IEEE Spectrum — skalningsfördelar |
| Topological | Microsoft (Station Q) | Ännu ej bevisat i praktiken men teoretiska fördelar i felkorrektion |

**Neutralatom-genombrott (IEEE Spectrum 2026):** neutral atom computing presterar rekordstort antal qubits med hög fidelity i 2026. Skalningsfördelar jämfört med superconducting kan förändra race-ordningen.

### IonQ Rumstemperatur

IonQ:s "trapped ion"-teknologi kräver kryostatisk kylning vid jonkällan men periferutrustning kan vid rumstemperatur. I 2026 demonstrerar IonQ att hela systemet kan operera med minimala kylkrav — potentiellt disruptivt för datacenter-deployment (eliminerar den kostsamma specialinfrastrukturen).

### Xanadu Fotonik

Fotonikbaserade qubits opererar med ljuspartiklar vid rumstemperatur. Xanadu:s PennyLane-plattform möjliggör hybrid quantum-classical computing. Svårighet: fotoner är svåra att lagra — begränsar djupa kretsar.

---

## Kvantmoln — Tillgänglighet 2026

Pay-as-you-go kvanttillgång:

| Leverantör | Plattform | Backend-teknik |
|-----------|---------|--------------|
| IBM | IBM Quantum (Qiskit) | Superconducting (Eagle, Falcon) |
| Amazon AWS | Amazon Braket | Superconducting + Ion (IonQ) + Neutral (Aquila) |
| Microsoft Azure | Azure Quantum | Trapped ion (Honeywell/Quantinuum) |
| Google | Google Cloud Quantum AI | Superconducting (Willow) |

Prismodell: per-qubit-shot, sekunder av QPU-tid, hybrid-workload-prissättning.

---

## Praktiska Tidshorisonter Per Applikationsdomän

### Nu (0–12 månader)

- **Hybrid quantum-classical**: kvantinspirerade klassiska algoritmer ger förbättringar utan full NISQ-hårdvara
- **Drug discovery-simulering**: kvantsimuleringsexperiment på molekyler (inte klassiskt lösliga) i tidig pilot
- **Optimering**: VQE (Variational Quantum Eigensolver) och QAOA för portföljoptimering i finans — pilot-scale

### Kort sikt (1–3 år)

- **Meningsfull kvantövertag** inom:
  - Molekylsimulering för läkemedelsutveckling (kvantskaleöverlägsenhet vs klassisk)
  - Portföljoptimering, riskanalys (finanssektorn)
  - Supply chain och logistik (TSP-typ problem)
- **Bredare kvantmoln**: fler qubits med högre fidelity, lägre kostnad per operation

### Medellång sikt (3–7 år)

- **PQC-migration kritisk** (se nedan) — befintlig PKI-infrastruktur hotad
- Kvantfördel för kemi och material science ger verkliga produktutvecklingsvärden
- Kvantnätverk (quantum key distribution, QKD) i finansiella institutioner

### Lång sikt (7+ år)

- **Broad cryptographic disruption**: RSA-2048 och ECC knäckbara av tillräckligt stora kvantdatorer (Shor's algorithm)
- Kvantinternet-infrastruktur
- Kvantsimulatorer som designverktyg för materialteknik och farmaceutik

---

## Post-Quantum Cryptography (PQC) — Strategisk Prioritet

### Varför Nu?

"Harvest now, decrypt later" (HNDL) attacker pågår redan 2024–2026: statsaktörer samlar krypterad trafik idag för att dekryptera med kvantteknik om 5–10 år. Känslig data med lång sekretessperiod (statshemligheter, sjukvårdsdata, finansiella transaktioner) är i riskzonen redan idag.

### NIST PQC-Standarder (Antagna 2024)

NIST publicerade finala standarder för post-quantum kryptografi 2024:

| Standard | Algoritm | Syfte |
|---------|---------|-------|
| FIPS 203 / ML-KEM | CRYSTALS-Kyber | Key encapsulation mechanism (ersätter Diffie-Hellman, ECDH) |
| FIPS 204 / ML-DSA | CRYSTALS-Dilithium | Digital signatur (ersätter RSA, ECDSA) |
| FIPS 205 / SLH-DSA | SPHINCS+ | Alternativ signatursstandard (hash-baserad) |

Ytterligare algoritmer under granskning: FALCON (kompaktare signaturer), HQC (alternativt KEM).

### Migrationsstrategi — Steg-för-steg

1. **Inventering** (börja nu): kartlägg vilka system, protokoll och applikationer som använder klassisk PKI (RSA, ECC, ECDH, ECDSA, DH)
2. **Klassificering**: vilken data har lång sekretessperiod? Prioritera dessa system
3. **Hybrid-kryptografi** (mellansteg): kör PQC och klassisk kryptografi parallellt under transition
4. **Leverantörsdialog**: när stödjer TLS-bibliotek, HSMs, PKI-infrastruktur FIPS 203/204/205?
5. **Pilotmigration**: börja med icke-kritiska system, bygg kompetens
6. **Full migration**: mål 2028–2030 för kritisk infrastruktur

### Svenska och EU PQC-Initiativ

- NCSC-SE (Nationellt Cybersäkerhetscenter): rekommenderar PQC-inventering 2024+
- ENISA: publicerat vägledning för EU-myndigheter
- NATO: kräver PQC-compliance för certain classified systems
- NIS2: cybersäkerhetskrav inkluderar krypteringsuppfräschning

### Kryptografiska Primitiv att Ersätta

| Nuvarande | PQC-ersättning | Användning |
|---------|-------------|----------|
| RSA-2048/4096 | ML-KEM + ML-DSA | TLS, email-signering, kodsignering |
| ECDSA (P-256, P-384) | ML-DSA | JWT, certifikat, blockchain |
| ECDH (X25519) | ML-KEM | TLS key exchange, end-to-end kryptering |
| AES-128 | AES-256 | Symmetrisk kryptering (Grover halverar effektiv nyckellängd) |

**OBS:** Symmetrisk kryptering (AES) är robust mot kvantattentat om nyckellängd dubbleras. AES-256 är "quantum safe". AES-128 är ej det.

---

## Kvantteknologins Aktörslandskap

### Nationella Program

| Region | Program | Investering |
|--------|--------|------------|
| EU | Quantum Flagship | €1 miljard (10 år) |
| USA | National Quantum Initiative Act | $1,2 miljarder |
| Kina | Nationellt kvantprogram | ~$15 miljarder estimat |
| UK | National Quantum Strategy | £2,5 miljarder |

### Startuplandskap

- **IonQ** (börsnoterat): ledande trapped ion, enterprise-kunder
- **Quantinuum** (Honeywell): trapped ion + quantum software
- **PsiQuantum**: fotonik, fokus på fel-tolerant skalning
- **Atom Computing**: neutral atom, rekordantal qubits 2023+
- **QuEra**: neutral atom arrays
- **Xanadu**: fotonik + PennyLane ecosystem

### Konsolidering

M&A-aktivitet ökar: Honeywell + Cambridge Quantum → Quantinuum. Förvänta ytterligare konsolidering 2026–2028.
