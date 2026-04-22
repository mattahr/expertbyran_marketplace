# Expertbyråns expertkatalog

Detta är konsultchefens (`SKILL.md`) källa för vilka experter som finns på byrån. När en ny expert läggs till MÅSTE den listas här — annars är den osynlig för konsultchefen.

## Aktiva experter

*Inga experter är registrerade än.* Byrån är i uppstartsfas — första riktiga experter tillkommer löpande och läggs till här.

Konsultchefen ska säga rakt ut till användaren när ingen expert matchar, snarare än att försöka improvisera utan expertroll.

## Icke-routningsbara mappar

Följande mappar finns under `experts/` men ska **aldrig** routas till. De är mallar och referenser för plugin-utveckling:

| Mapp | Syfte |
|---|---|
| `_TEMPLATE` | Skelettmall som kopieras när en ny expert skapas. |
| `_EXEMPEL` | Färdigskriven referens-EXPERT.md (klarspråksexpert) som visar hur en komplett expert ser ut. Används av `expert-utveckling`-skillen som konkret förebild. |

## Hur konsultchefen använder denna fil

1. Konsultchefen (`SKILL.md`) läser denna fil först varje gång den triggas.
2. Den matchar användarens behov mot raderna ovan.
3. För varje träff läser den `experts/<expertnamn>/EXPERT.md`.

## Lägga till en ny expert

Se `[../../../CLAUDE.md](../../../CLAUDE.md)` på plugin-roten för fullständig checklista. Kortversion:

1. `cp -r experts/_TEMPLATE experts/<nytt-expertnamn>` (ASCII, kebab-case).
2. Fyll i `experts/<nytt-expertnamn>/EXPERT.md`.
3. Lägg eventuella tunga underlag i `experts/<nytt-expertnamn>/references/`.
4. **Lägg till en rad i tabellen ovan.** Detta steg glöms lättast.
5. Commit.
