# Kvantdatorer och CRQC-tidshorisonter

Referensmaterial för bedömning av kvantdatormognad och tidsfönstret för en kryptografiskt relevant kvantdator (CRQC). Kompletterar `references/kvantteknik-och-pqc.md` med ett tydligare *när-perspektiv*: när måste PQC-migration ske för att inte vara sent ute?

## Kärnresonemang

CRQC-frågan är inte binär. För prioritering av PQC-migration räcker det inte att räkna fysiska qubits eller notera demonstrationsresultat. Tre saker måste vägas mot varandra:

1. **Teknikmodalitet** — olika hårdvaruspår utvecklas i olika takt.
2. **Operationsgapet (logical-operations-gap)** — demonstrerade fysiska qubits är inte samma sak som uthållig, felfri beräkningskapacitet mot verkliga kryptosystem. En logisk qubit kräver i pessimistiska scenarier i storleksordningen 10 000 fysiska qubits; dagens fysiska felgrad (~0,1–1 %) ligger fortfarande över den ~0,01 % som krävs för effektiv felkorrektion.
3. **Informationslivslängd** — *harvest-now-decrypt-later* gör data med lång sekretesshorisont riskutsatt redan idag.

## IBM-roadmap som referens

IBM Technology Atlas Quantum Roadmap (juni 2025) anger:

- **Loon (2025), Kookaburra (2026), Cockatoo (2027)** — mellansteg.
- **Starling (2029)** — ~200 logiska qubits, ~100 miljoner grindar.
- **Blue Jay (2033+)** — >2 000 logiska qubits, miljardgrindnivå.

Detta är *en* leverantörs estimat. Använd inte som ensam prognos — väg mot oberoende bedömningar (ENISA, NIST, CEPS, McKinsey, Riverlane).

## Mosca-formeln

$X + Y > Z$, där:

- $X$ = hur länge informationen måste vara skyddad
- $Y$ = migrationstid till PQC
- $Z$ = tid tills en CRQC finns

Om $X + Y > Z$ är organisationen redan sent ute. Detta är den enklaste falsifierbara tröskeln för migrationsbeslut. Mosca (IEEE Security & Privacy, 2018).

## Teknikmodaliteter (flerfrontslopp, ingen ensam vinnare)

| Modalitet | Exempelaktörer | Strategisk observation |
|-----------|----------------|------------------------|
| Supraledande qubits | Google, IBM | Hög utvecklingstakt; tung kyl- och felkorrektionsbörda |
| Trapped ion | IonQ, Quantinuum | Hög fidelity; intressant för kvalitativa genombrott |
| Neutral atom | Atom Computing, QuEra, Pasqal | Skalningsspår, möjligt race-skifte 2026 |
| Fotonik | Xanadu, PsiQuantum | Rumstemperaturpotential; svårare väg till generell beräkning |

CRQC-tidshorisonten är beroende av modalitet, felkorrektion och nyttolast — luta inte styrning mot ett enskilt prognostal.

## Riskhorisont i fyra lager

- **Nu**: hybrid quantum-classical och kvantinspirerade arbetssätt — operativa piloter.
- **1–3 år**: domänspecifika kvantfördelar inom simulering och optimering.
- **3–7 år**: PKI-beroenden börjar bli styrningsproblem, inte FoU-spår.
- **7+ år**: bred kryptografisk disruption blir realistiskt planeringsscenario (osäkerhetsband ~15 år).

## Skilja på begrepp

- **Quantum advantage** — kvantdator slår klassisk på en specifik uppgift. *Inte* samma som CRQC.
- **Kryptografiskt relevant kvantdator (CRQC)** — kapacitet att bryta dagens asymmetriska kryptografi (RSA, ECC) inom rimlig tid med Shors algoritm. Kräver miljonordningens fysiska qubits eller motsvarande logisk kapacitet.

Övertolkning av advantage-rubriker som CRQC-signal är ett vanligt granskningsfynd.

## Granskningsfrågor (revisionsperspektiv)

- Har myndigheten prioriterat PQC efter **informationslivslängd** eller efter mediala rubriker om qubitantal?
- Finns dokumenterad bedömning av **vilka kryptoberoenden som inte kan bytas sent** (HSM, PKI, leverantörslåsning)?
- Används kvantroadmaps som strategiskt underlag på ett sätt som skiljer **demonstrerad kapacitet** från **kryptografiskt relevant kapacitet**?
- Är Mosca-formelns parametrar ($X$, $Y$, $Z$) explicit dokumenterade per kryptoberoende, eller används en odifferentierad migrationstidplan?

## Källor

- IBM Newsroom, *IBM Sets the Course to Build World's First Large-Scale, Fault-Tolerant Quantum Computer* (2025-06-10). <https://newsroom.ibm.com/2025-06-10-IBM-Sets-the-Course-to-Build-Worlds-First-Large-Scale,-Fault-Tolerant-Quantum-Computer>
- IBM Technology Atlas — Quantum Roadmap. <https://www.ibm.com/roadmaps/quantum/>
- M. Mosca, *Cybersecurity in an era with quantum computers: will we be ready?* IEEE Security & Privacy 2018. Preprint: <https://eprint.iacr.org/2015/1075>
- IonQ, *Demystifying Logical Qubits and Fault Tolerance*. <https://www.ionq.com/resources/demystifying-logical-qubits-and-fault-tolerance>
- McKinsey, *Quantum error correction for fault-tolerant quantum computing*.
- Riverlane, *Quantum Error Correction: 2025 trends and 2026 predictions*.
- ENISA, *Post-Quantum Cryptography — Current state and quantum mitigation* (2021).
- CEPS, *EU quantum-safe* (2024).
