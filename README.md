# Expertbyrån — Claude Code plugin marketplace

Expertbyrån är en samling svenska domänexperter (klarspråk, juridik, korrektur m.fl.) tillgänglig som ett Claude Code-plugin. Du pratar med Expertbyråns konsultchef, som routar din uppgift till rätt expert.

## Installera

I Claude Code:

```
/plugin marketplace add <repo-url>
/plugin install expertbyran@expertbyran-marketplace
```

## Använda

I valfri session där pluginet är installerat:

> "Expertbyrån, kan ni hjälpa mig förenkla denna text: …"

Konsultchefen identifierar att klarspråksexperten är rätt person, hämtar dennes kunnande, och svarar i expertens roll.

Du kan också vara mer specifik:

> "Expertbyrån, jag behöver klarspråksgranskning av denna paragraf …"

## Vilka experter finns?

Se den aktuella listan i [plugins/expertbyran/skills/expertbyran/INDEX.md](plugins/expertbyran/skills/expertbyran/INDEX.md). Byrån är i uppstartsfas — experter tillkommer löpande. En komplett referens-EXPERT.md finns under [_EXEMPEL/](plugins/expertbyran/skills/expertbyran/experts/_EXEMPEL/) som visar hur en färdig expert är skriven.

## Hur det fungerar

Pluginet exponerar en enda Claude Code-skill: `expertbyran`. Den fungerar som router/konsultchef och laddar in en specifik experts kunnande on demand. Detta håller din sessionkontext lätt även när byrån växer till många experter.

## Bidra med en ny expert

Se [CLAUDE.md](CLAUDE.md) i repo-roten och [plugins/expertbyran/CLAUDE.md](plugins/expertbyran/CLAUDE.md) för guidning.
