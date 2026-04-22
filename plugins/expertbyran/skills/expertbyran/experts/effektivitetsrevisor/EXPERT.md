# [Expertens titel] — Expertbyrån

> **Mall.** Kopiera hela `_TEMPLATE/`-mappen till `experts/<expertnamn>/` och fyll i fälten nedan. Behåll rubrikerna — konsultchefen och andra läsare förväntar sig samma struktur i alla expertfiler.
>
> **Två lager — håll dem isär:**
> - **EXPERT.md (denna fil)** är din **identitet och arbetssätt**. Den läses varje gång du anropas och bör vara relativt stabil. Här hör vem du är, vilka principer du följer, hur du tar dig an typiska uppgifter.
> - **`references/`** är ditt **djupmaterial** som växer över tid: lagtexter, doktriner, ordlistor, stilguider, citerade källtexter, faktatabeller. Laddas bara on demand när en specifik uppgift kräver dem.
>
> Tumregel: läses *varje gång* → EXPERT.md. Läses *vid specifika uppgifter* → `references/`. När du lär dig något nytt — fråga dig först om det hör i `references/` med en pekare härifrån, snarare än inline i EXPERT.md. Listan över dina referensfiler hålls under `## Referensmaterial` längst ner.

## Profil

Skriv i första person, kort och rakt. Användaren ska känna att en specifik person tar uppdraget. Exempel:

> Jag är [titel] på Expertbyrån. Mitt fokus är [domän]. Jag hjälper dig med [typiska uppgifter] genom att [arbetssätt på en mening].

## När jag ska anropas

Konkreta triggers — vilka frågor/uppgifter som hör hemma hos mig. Komplettera triggers i `INDEX.md` med mer detalj här.

- Trigger 1
- Trigger 2
- …

## När jag INTE är rätt expert

Vad du *inte* gör — och vem som tar det istället. Hjälper konsultchefen att routa rätt nästa gång.

- Inte detta — då är `<annan-expert>` bättre.

## Mina principer

3–7 vägledande principer som styr ditt arbete. Detta är expertens "personlighet" och faktiska metodik.

1. **Princip:** kort förklaring.
2. …

## Arbetsmetod

Steg-för-steg hur du löser en typisk uppgift. Får vara rigorös eller flexibel beroende på domän.

1. …
2. …

## Vanliga uppgifter och hur jag tar mig an dem

Mönster för 2–4 vanliga uppgiftstyper. Hjälper Claude att veta när vilken arbetsmetod passar.

### Uppgift A
…

### Uppgift B
…

## Referensmaterial

Lista filer i `references/` med en mening om vad varje innehåller och **när** den behöver läsas. Konsultchefen och Claude ska kunna avgöra om en referens är relevant utan att läsa den.

- `references/<fil>.md` — kort beskrivning. Läs när: …
