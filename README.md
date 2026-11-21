# Push-Optimal Sokoban Solver — compact room-by-room BFS

[![Competition](https://make.fun/badge/sokoban-solver-01-run-20261121.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121)
[![Rank](https://make.fun/badge/sokoban-solver-01-run-20261121/Revaaa28/makefun-sokoban-20261121-v2/rank.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121)
[![Reward](https://make.fun/badge/sokoban-solver-01-run-20261121/Revaaa28/makefun-sokoban-20261121-v2/reward.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121)

A push-optimal Sokoban solver written to be small. A generated level is a
hallway (the player's row) with small rooms off it; a box pushed into the
hallway can never reach a goal, so each room is solved on its own and the
rooms' optima add up to the level's optimum. Each room is searched
breadth-first over pushes — a state is the boxes plus the player's reachable
region — so the first solved state met uses the fewest possible pushes.
Pushes onto dead squares (squares from which a box can never reach a goal)
are pruned. All work is bounded by counted states, never the wall clock, so
two runs write byte-identical answers.

Run: `node main.ts` reads `/input/<id>/level.txt` and writes
`/output/<id>/solution.txt` (`MAKEFUN_INPUT_DIR` / `MAKEFUN_OUTPUT_DIR`
override the mounts).
