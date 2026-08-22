# 2026 Fantasy Football Draft Research — 14-Team Half-PPR League

Research corpus and strategy work for a 14-team ESPN redraft league drafting
2026-08-22.

## League settings

| Setting | Value |
|---|---|
| Teams | **14** |
| Roster | 13 active + 1 IR |
| Starters (9) | QB 1, RB 2, WR 2, TE 1, FLEX 1, D/ST 1, K 1 |
| Bench | **4** |
| Draft | Snake, 13 rounds, 182 picks, 90 sec/pick, order randomized 1 hr prior |
| Receptions | **0.5 (half-PPR)** |
| Pass TD | **4** (pass yds 0.04, INT -2) |
| Rush/Rec TD | 6 (yds 0.1) |
| Kicker FG | 0-39: 3, 40-49: 4, 50-59: 5, 60+: 5, miss: -1 |
| D/ST | Scores **both points allowed and yards allowed** (+5 to -7) |
| Waivers | No limit, 1-day period, order resets weekly by inverse standings (not FAAB) |
| Playoffs | **4 of 14 teams**, 2-week matchups, points-for tiebreaker |
| Keepers | None (pure redraft) |

## Structural math (format-derived, no external data required)

- 14 x 13 = **182 picks**. You get 13: two go to K and D/ST, leaving
  **11 real players = 7 starters + 4 bench**.
- Weekly starter demand: 14 QB, 28 RB, 28 WR, 14 TE, 14 FLEX, 14 D/ST, 14 K.
- Replacement level vs a 12-team league: RB ~RB36 (vs RB31), WR ~WR34 (vs WR29),
  QB ~QB16-18 (vs QB14), TE ~TE15-16 (vs TE13).
- **182 rostered here vs 192 in a standard 12-team/16-spot league**, so the waiver
  wire is slightly *richer*, not barren. With only 4 bench spots nobody can stash,
  so injured and slow-developing players get dropped rather than hoarded.
- Consequence: streaming stays viable at RB/WR, but **not** at QB/TE/D/ST, where
  14 teams need 14 starters and the 15th-best option is genuinely bad. Most
  published "wait on QB and TE" advice is written for 12-team leagues and
  under-rates single-slot scarcity here.

## Contents

- `raw/` — verbatim WebSearch result blocks harvested from the research agents.
  217 unique blocks, ~606 KB, captured 2026-08-22 before the session's
  200-search budget was exhausted. **Raw external web content, not verified
  claims** — player names and ADP figures require confirmation before use.

## Known limitations

1. The session web-search budget (200) was exhausted during research. Raising
   `CLAUDE_CODE_MAX_WEB_SEARCHES_PER_SESSION` requires a new session.
2. The egress proxy blocks direct fetches of most fantasy sites (FantasyPros,
   FantasyFootballCalculator, 4for4, team sites) with HTTP 403. Search-result
   summaries were the only working channel.
3. Nothing here has been fact-checked against a second source. Treat every
   player name, team, and ADP figure as unverified.
