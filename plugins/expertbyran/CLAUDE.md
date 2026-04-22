# Expertbyrån — plugin-intern guide

Denna fil läses när någon arbetar inuti själva pluginet. Den kompletterar repo-rotens [CLAUDE.md](../../CLAUDE.md) med detaljer specifika för plugin-utveckling.

## Plugins enda skill: konsultchefen

Pluginet exponerar **en enda skill**: `expertbyran` (definierad i [skills/expertbyran/SKILL.md](skills/expertbyran/SKILL.md)). Den fungerar som konsultchef/router och har inget eget ämneskunnande.

Lägg **aldrig** till en `SKILL.md` direkt under `skills/<expertnamn>/` för en ny expert. Då blir experten en separat top-level skill, vilket bryter hela arkitekturen (kontextsnålhet, en-skill-UX). Experter är vanliga markdown-filer under `skills/expertbyran/experts/<namn>/EXPERT.md`.

## Lägga till en ny expert (komplett checklista)

1. **Välj namn** i kebab-case ASCII utan å/ä/ö (`affarsjuridik`, inte `affärsjuridik`). Visningsnamnet i EXPERT.md får använda korrekta svenska tecken.
2. **Kopiera mallen:**
   ```Shell
   cp -r skills/expertbyran/experts/_TEMPLATE skills/expertbyran/experts/<namn>
   ```
3. **Fyll i** **`EXPERT.md`** enligt mallens struktur. Behåll alla rubriker — konsultchefen och framtida experter förlitar sig på samma format.
4. **Lägg referensmaterial** i `experts/<namn>/references/` som en eller flera markdown-filer. En fil per logiskt avgränsat område (t.ex. `lagtext.md`, `praxis.md`). Lista alla referensfiler i EXPERT.md:s sista sektion med beskrivning + "Läs när: …".
5. **Registrera experten i** **[skills/expertbyran/INDEX.md](skills/expertbyran/INDEX.md).** Detta är det vanligaste glömda steget — utan det är experten osynlig för konsultchefen.
6. **Verifiera** att inga oavsiktliga `SKILL.md`-filer skapats under `experts/`.
7. **Commit.**

## Designprinciper för experter

* **Profilen är central.** Första-persons-rösten gör att Claude "spelar" rollen istället för att svara generiskt. Investera i den.
* **Skarpt avgränsa "när jag INTE är rätt".** Hjälper konsultchefen att routa korrekt och undviker att en expert tar uppdrag den inte är bäst på.
* **Ingen duplicering mellan experter.** Om två experter behöver samma underlag — lyft det till en gemensam plats (kommer att designas när behovet uppstår; första passet är detta inte aktuellt).

## Versionering och uppdateringsdistribution

Pluginet använder semantic versioning. Versionen lever i **`plugins/expertbyran/.claude-plugin/plugin.json`** och **ingenstans annars** — `marketplace.json` har medvetet inget version-fält (om ett dyker upp där, ta bort det; plugin.json vinner alltid silently per Claude Code-docs och en divergerande marketplace-version blir vilseledande).

**Varför version-bump är obligatorisk:** Claude Code cachar pluginet per version. Om du ändrar innehåll utan att bumpa version, ser inga installerade användare ändringen — de fortsätter köra cachad version.

**Semver-nivåer för Expertbyrån:**

* **PATCH** (`0.1.0 → 0.1.1`) — en expert förfinade sin profil, en INDEX-rad skärptes, en typo fixades, references/-fil uppdaterades. Inga strukturella ändringar.
* **MINOR** (`0.1.0 → 0.2.0`) — ny expert registrerad, expert avregistrerad, ny domäntäckning, betydande routing-omarbetning.
* **MAJOR** (`0.1.0 → 1.0.0`) — breaking. T.ex. `_TEMPLATE/EXPERT.md`-strukturen ändras (kräver att existerande experter migreras), eller pluginets fundamentala beteende ändras.

**Vem bumpar:** **konsultchefen**, alltid. Experter ska aldrig röra `plugin.json` — efter en uppdatering ber experten användaren signalera till konsultchefen om en bump (PATCH räcker för deras typ av ändringar). Konsultchefen kan batcha flera experters uppdateringar i en bump.

**Auto-uppdatering:** Claude Code kör bakgrunds-auto-update vid uppstart. Manuellt triggas med `/plugin marketplace update` (uppdaterar marketplace-katalog) följt av `claude plugin update expertbyran` (uppdaterar pluginet).

## Två lager: EXPERT.md vs references/

Detta är den viktigaste arkitekturprincipen för experter. Den styr hur en expert växer över tid utan att bli ohanterlig.

* **EXPERT.md** är expertens **identitet och arbetssätt** — profil, principer, arbetsmetod, vanliga uppgifter, scope. Läses varje gång konsultchefen routar dit. Bör vara relativt stabil och fokuserad.
* **`references/`** är expertens **djupmaterial** — lagtexter, doktriner, ordlistor, stilguider, citerade källtexter, längre exempel, faktatabeller. Laddas bara on demand när en specifik uppgift kräver dem.

Tumregel: läses *varje gång* experten anropas → EXPERT.md. Läses *vid specifika uppgifter* → `references/`.

**Hur en expert växer över tid:** en försvarsexpert har en kort EXPERT.md som beskriver hens analytiska metod och scope. Hens `references/` växer däremot organiskt: en ny fil när en doktrin ändras, en för svenska försvarsmaktens organisationsstruktur, en för NATO-terminologi, en per relevant konflikt. Varje ny referensfil listas i EXPERT.md:s `## Referensmaterial`-sektion med en konkret "Läs när"-trigger så att konsultchefen kan avgöra relevans utan att öppna filen. Detta är mönstret vi vill se överallt: identitet stabil, fakta växer i `references/` med tydliga pekare härifrån.

När en expert frestas att lägga substantiellt nytt material direkt i EXPERT.md — flagga det. Det hör nästan alltid bättre i en ny referensfil.

## Filer och mappar i plugin-roten

```
plugins/expertbyran/
├── .claude-plugin/plugin.json     # plugin-manifest (auto-discovery för skills/)
├── CLAUDE.md                      # denna fil
└── skills/
    └── expertbyran/
        ├── SKILL.md               # konsultchefen (enda top-level skill)
        ├── INDEX.md               # expertkatalog (uppdateras vid ny expert)
        └── experts/
            ├── _TEMPLATE/         # mall — kopieras till nya experter
            └── <namn>/
                ├── EXPERT.md
                └── references/
```

## Vad du INTE ska göra

* **Skapa flera SKILL.md-filer** under `skills/`. Bryter routing-arkitekturen.
* **Pre-ladda alla experter i konsultchefens body.** Konsultchefen ska bara routa, inte innehålla expertkunnande.
* **Använda svenska tecken i mappnamn.** macOS/Linux klarar det, Windows och vissa verktyg blir griniga.
* **Skriva expertinnehåll på engelska.** Hela byrån är svenskspråkig.

