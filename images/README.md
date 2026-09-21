# Screenshots

Real captures of the apps running against a database seeded with invented data.
No client record here is real. Each file is listed in the `SHOTS` manifest in
`mock.html`, keyed by app; the first entry is a card's cover, the rest fill its
gallery.

| file                        | app             | screen                           |
|-----------------------------|-----------------|----------------------------------|
| `onday-terminal.png`        | OnDay           | worker selection on the terminal |
| `planner-resumo.png`        | Pro Planner     | planning summary                 |
| `planner-dicionario.png`    | Pro Planner     | CSV dictionary import            |
| `tintas-combinacoes.png`    | OnDay Tintas    | colour combinations dialog       |
| `tintas-stock.png`          | OnDay Tintas    | stock table                      |
| `logistics-transporte.png`  | OnDay Logistics | containers in transit            |
| `logistics-stock.png`       | OnDay Logistics | warehouse stock table            |
| `logistics-menu.png`        | OnDay Logistics | back office menu                 |

## Reproducing

The Qt apps run standalone against a local SQLite database. OnDay and Pro Planner
need `OnDay_Webservice` up first, plus a row in `ENTERPRISE` and one in
`CONNECTED_MACHINES` for the machine id they report - without those, every
endpoint answers 404 and the Planner shows "Sem ligacao ao OnDay".

Two screens are still missing. OnDay's work area cannot be reached by scripting:
the app handles touch itself and ignores synthetic X11 clicks, so only the
worker-selection screen can be captured. The Planner's planning table fills from
the webservice but resolves names from a cache that never loads here, so every
row reads "Colaborador nao encontrado".
