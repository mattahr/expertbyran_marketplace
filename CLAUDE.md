# Expertbyrån marketplace

## Vad detta repo är

Detta repo är en **Claude Code plugin marketplace** som distribuerar **ett enda plugin**: `expertbyran` ("Expertbyrån"). Marketplacen är paketeringen — själva produkten är pluginet under [plugins/expertbyran/](plugins/expertbyran/).

## Konceptet Expertbyrån

Expertbyrån är ett fiktivt konsultbolag med ~20 specialister inom olika domäner: klarspråk, juridik, korrektur, UX, säkerhet, m.fl. Varje expert förkovrar sig löpande och förfinar sin egen kunskap. När en användare ber Expertbyrån om hjälp ska rätt expert (eller team av experter) plockas fram för uppdraget — utan att användaren behöver veta vem som finns.

## Arkitektur: konsultchef-router + experter som filer

**Nyckelvalet, motiverat:** vi exponerar **endast en skill** (`expertbyran`) — konsultchefen. Hen har inget eget ämneskunnande utan routar uppdraget till rätt expert genom att läsa interna markdown-filer på begäran. Experterna är alltså **inte egna skills** utan filer under [plugins/expertbyran/skills/expertbyran/experts/](plugins/expertbyran/skills/expertbyran/experts/).

Varför så:

| Problem med 20 syskon-skills | Vår lösning |
|---|---|
| Användarens skill-lista fylls med 20 rader. | Endast `expertbyran` syns. |
| ~2–3K tokens skill-beskrivningar laddas i varje session. | ~150 tokens (bara konsultchefens beskrivning). |
| Routing sker via Claudes auto-matchning på beskrivningar — svår att kontrollera. | Explicit routing i konsultchefens body, baserat på `INDEX.md`. |
| Modulariteten lider om vi proppar in alla experter i en fil. | Varje expert har egen mapp med EXPERT.md + references/. |

Verifierat mot officiell Claude Code-dokumentation: skill-upptäckt sker bara för `skills/<name>/SKILL.md` direkt under `skills/`. Filer djupare ner är vanliga markdown-filer som vår konsultchef-skill läser med Read-verktyget on demand. Skill-bodies laddas bara när skillen invokeras, och `references/`-filer laddas bara när Claude läser dem explicit — så hela kedjan utnyttjar progressive disclosure.

## Repo-struktur

```
expertbyran_marketplace/
├── .claude-plugin/marketplace.json        # marketplace-katalog
├── plugins/expertbyran/                   # det enda pluginet
│   ├── .claude-plugin/plugin.json
│   ├── CLAUDE.md                          # plugin-intern guide (läs vid plugin-arbete)
│   └── skills/expertbyran/
│       ├── SKILL.md                       # konsultchefen (router)
│       ├── INDEX.md                       # expertkatalog (tom i startläget)
│       └── experts/
│           ├── _TEMPLATE/EXPERT.md        # mall för ny expert
│           └── _EXEMPEL/                  # färdig referens-EXPERT.md (icke-routningsbar)
│               ├── EXPERT.md
│               └── references/riktlinjer.md
├── CLAUDE.md                              # denna fil
└── README.md                              # användarinstallation
```

## Lägga till en ny expert

Se detaljerad checklista i [plugins/expertbyran/CLAUDE.md](plugins/expertbyran/CLAUDE.md). Kortversion:

1. Kopiera `_TEMPLATE/` till ny mapp under `experts/<namn>/` (ASCII kebab-case).
2. Fyll i `EXPERT.md` enligt mallens struktur.
3. Lägg referensmaterial i `references/` och beskriv när varje fil ska läsas.
4. **Registrera experten i `INDEX.md`** — annars är den osynlig.
5. Commit.

## Konventioner

- **Språk:** allt innehåll skrivs på svenska med korrekta tecken (å, ä, ö, Å, Ä, Ö). Detta gäller SKILL.md, EXPERT.md, INDEX.md, references, dokumentation och commit-meddelanden. Ingen "raksmorgas" när det ska vara "räksmörgås".
- **Filnamn och mappnamn:** ASCII kebab-case. `klarsprak` (inte `klarspråk`), `affarsjuridik` (inte `affärsjuridik`). Visningsnamn i markdown-innehållet får och bör använda svenska tecken.
- **Versionering:** semver i [.claude-plugin/marketplace.json](.claude-plugin/marketplace.json) och [plugins/expertbyran/.claude-plugin/plugin.json](plugins/expertbyran/.claude-plugin/plugin.json). Båda hålls i sync.
- **Inga emojis** i kod eller dokumentation om inte uttryckligen efterfrågat.

## Testa lokalt

1. I Claude Code (annan session/projekt):
   ```
   /plugin marketplace add /Users/mattias/source/expertbyran_marketplace
   /plugin install expertbyran@expertbyran-marketplace
   ```
2. Starta ny session. Verifiera att `expertbyran` listas som tillgänglig skill, och att ingen expert syns som separat top-level skill.
3. **Tomt-läge-test (uppstartsfas):** *"expertbyrån, kan ni hjälpa mig förbättra klarspråket i: Beslut om avslag på er ansökan om bygglov föreligger härmed."*
   - Förvänta att konsultchefen läser `INDEX.md`, ser att inga experter är registrerade, och säger det rakt ut. Den ska inte improvisera klarspråksgranskning utan expertroll.
4. **Test efter att första expert lagts till:** när en riktig expert finns i `INDEX.md` (skapad av en agent via `expert-utveckling`-skillen), upprepa scenariot ovan och förvänta att rätt expert väljs och konsulteras.

`_EXEMPEL/` är medvetet inte registrerad i `INDEX.md` och ska inte routas till — den finns som referensförebild för agenter som utvecklar nya experter.

## Vad som INTE hör hemma här

- **Affärslogik eller kod utanför plugin-strukturen.** Detta repo är enbart en plugin-distribution.
- **Generella skills som inte hör till Expertbyrån-koncept.** Om du vill bygga en separat skill (t.ex. ett verktyg utan expertroll), gör det i ett eget plugin — inte i `expertbyran`.
