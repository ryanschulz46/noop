> # ⚠️ READ THIS FIRST — PROVENANCE & WHAT I COULD NOT VERIFY
>
> **I was not able to run live web research in this session.** The session's WebSearch budget was already fully consumed (200/200) before I started, and *every* outbound domain — fantasypros.com, fantasyfootballcalculator.com, fantasy.espn.com, api.sleeper.app, even wikipedia.org — is blocked by this environment's egress proxy. I verified this directly; nothing I could do would restore live access.
>
> **What I used instead:** earlier agents in this same session (running ~2026-08-22 16:09–16:23, i.e. this morning) *did* successfully harvest live data before the budget ran out, and left it on disk. Everything below is computed from those dated snapshots. **I did not write a single ADP figure from memory.** Every number traces to a file I read, and I give each file's fetch date.
>
> **The one deliverable I cannot provide: Underdog ADP.** It was not harvested and I cannot reach it. I am not going to invent it. Treat Underdog as **UNVERIFIED / MISSING** throughout.

---

## 0. Source inventory (with dates — read the dates, they matter)

| Source | What it gives | Fetched / snapshot | Freshness |
|---|---|---|---|
| **FantasyPros** — `2026_Draft_ALL_Rankings` + `2026_Overall_ADP_Rankings` export (717 players) | **ECR** + **consensus ADP** (the spine of this board) | **2026-08-21** | ✅ 1 day old |
| **FantasyPros via ffverse/nflverse `fpecr` scrape** (6,011 rows, 31 ranking pages) | raw ECR average, best, worst, **std-dev** | **2026-08-21** | ✅ 1 day old |
| **Fantasy Football Calculator** — half-PPR, **12-team**, real drafts | true half-PPR ADP + `times_drafted` | **2026-08-19** | ✅ 3 days old |
| Fantasy Football Calculator — half-PPR, 12-team | same, earlier snapshot (used as a drift control) | 2026-07-18 | control |
| **ESPN ADP** (400 players) | **ESPN-specific ADP** | **2026-07-18** | ⚠️ **5 weeks stale** |
| **Sleeper** half-PPR ADP | Sleeper ADP | 2026-07-19 | ⚠️ 5 weeks stale |
| **Yahoo ADP** (`ADP (Y!)` column, 400 rows) | Yahoo ADP | **undated — UNVERIFIED** | ⚠️ |
| Fantasy Footballers Ultimate Draft Kit | ADP round.pick + overall | 2026-08-15 | ✅ |
| Rotoworld/NBC top-200 consensus | tier structure | 2026-08-16 | ✅ |
| Harvested web-search corpus (5,610 lines, 4 files) | injury/news verification | 2026-08-22 | ✅ today |

### Four caveats that change how you read the numbers

1. **The ECR column is PPR, not half-PPR.** I verified this by cross-checking the FantasyPros export against the ffverse scrape: the ECR ordering matches `/nfl/rankings/ppr-cheatsheets.php` exactly (Chase 1.51, Gibbs 2.93, Nacua 3.47, Bijan 3.71…). FantasyPros' *half*-PPR ECR page was not captured. Practical effect is small but real: half-PPR nudges **high-reception/low-yardage** types (Kyren Williams, Wan'Dale Robinson, Josh Downs, Rachaad White, Alvin Kamara) **down** a few spots, and **TD/rush-heavy** types (Derrick Henry, Chuba Hubbard, David Montgomery, Tony Pollard) **up** a few spots, versus what the ECR column shows.
2. **The "FP ADP" spine is FantasyPros' *overall* ADP composite**, not their half-PPR-specific page. My two genuinely half-PPR sources are **FFC** and **Sleeper** — both are shown as separate columns so you can see the format effect yourself.
3. **ESPN ADP saturates.** ESPN's values compress asymptotically past ~pick 165: rank 190 = 168.1, rank 250 = 169.9, rank 300 = 169.99, rank 400 = 171.1. **ESPN ADP values are only meaningful to about pick 165.** Past that, use ESPN's *rank order*, not the number.
4. **ESPN data is from July 18.** I measured actual market drift using FFC's own 7/18 vs 8/18 snapshots: **median absolute drift = 5.5 picks over 5 weeks.** So for most players ESPN staleness is minor — but for a specific set it is huge, and in §4 I *statistically separate* staleness from genuine ESPN platform bias.

---

## 1. Consensus overall ADP — top 170, 2026 half-PPR redraft

Spine = **FantasyPros consensus ADP, 2026-08-21**. `12tm` = round.pick in a 12-team snake. Columns: ESPN (7/18), Slpr = Sleeper half-PPR (7/19), FFC = Fantasy Football Calculator half-PPR 12-team (8/19), Yah = Yahoo, ECR = FantasyPros expert consensus **rank** (PPR).

| # | 12tm | Player | Pos | Tm | Bye | FP ADP | ESPN | Slpr | FFC | Yah | ECR | Flag |
|--:|:--|:--|:--|:--|--:|--:|--:|--:|--:|--:|--:|:--|
| 1 | 1.01 | Jahmyr Gibbs | RB1 | DET | 6 | 1.0 | 1.9 | 2.9 | 1.5 | 1 | 2 | camp hold-in, resolved |
| 2 | 1.02 | Bijan Robinson | RB2 | ATL | 11 | 2.0 | 2.3 | 1.5 | 2.1 | 2 | 4 | |
| 3 | 1.03 | Ja'Marr Chase | WR1 | CIN | 6 | 3.0 | 4.7 | 3.7 | 4.1 | 3 | **1** | |
| 4 | 1.04 | Puka Nacua | WR2 | LAR | 11 | 4.0 | 3.6 | 4.8 | 3.0 | 4 | 3 | |
| 5 | 1.05 | Christian McCaffrey | RB3 | SF | 8 | 5.6 | 5.5 | 5.7 | 6.8 | 5 | 9 | |
| 6 | 1.06 | Jaxon Smith-Njigba | WR3 | SEA | 11 | 6.0 | 6.3 | 7.3 | 5.4 | 7 | 5 | |
| 7 | 1.07 | Jonathan Taylor | RB4 | IND | 13 | 6.4 | 8.5 | 6.4 | 5.8 | 8 | 11 | |
| 8 | 1.08 | Amon-Ra St. Brown | WR4 | DET | 6 | 8.2 | 7.8 | 8.6 | 7.8 | 6 | 6 | |
| 9 | 1.09 | James Cook III | RB7 | BUF | 7 | 10.2 | 13.3 | 8.2 | 8.9 | 10 | 17 | |
| 10 | 1.10 | Ashton Jeanty | RB5 | LV | 13 | 11.2 | 13.7 | 11.9 | 15.8 | 13 | 14 | |
| 11 | 1.11 | De'Von Achane | RB8 | MIA | 6 | 11.4 | 12.1 | 13.6 | 11.3 | 18 | 21 | MIA rebuild |
| 12 | 1.12 | CeeDee Lamb | WR5 | DAL | 14 | 12.0 | 11.2 | 10.3 | 12.6 | 9 | 7 | |
| 13 | 2.01 | Justin Jefferson | WR6 | MIN | 6 | 12.4 | 12.5 | 12.4 | 14.0 | 11 | 8 | |
| 14 | 2.02 | Saquon Barkley | RB10 | PHI | 10 | 14.2 | 15.4 | 15.4 | 17.9 | 12 | 26 | |
| 15 | 2.03 | Chase Brown | RB6 | CIN | 6 | 15.2 | **27.2** | 19.1 | 14.8 | 15 | 15 | ESPN 12 picks late |
| 16 | 2.04 | Drake London | WR7 | ATL | 11 | 17.4 | 20.3 | 17.6 | 12.1 | 17 | 10 | |
| 17 | 2.05 | Omarion Hampton | RB9 | LAC | 7 | 17.6 | 20.6 | 14.7 | 22.4 | 16 | 25 | |
| 18 | 2.06 | Derrick Henry | RB12 | BAL | 13 | 18.4 | 18.6 | 22.0 | **10.6** | 19 | 36 | FFC loves him |
| 19 | 2.07 | Kenneth Walker III | RB11 | **KC** | 5 | 19.0 | 28.2 | 16.8 | 22.1 | 14 | 28 | new team |
| 20 | 2.08 | A.J. Brown | WR8 | **NE** | 11 | 20.6 | 27.3 | 24.4 | 19.4 | 23 | 12 | new team |
| 21 | 2.09 | Trey McBride | TE2 | ARI | 14 | 21.6 | 21.1 | 20.3 | 38.6 | 25 | 20 | |
| 22 | 2.10 | Brock Bowers | TE1 | LV | 13 | 22.4 | 23.6 | 20.6 | 42.5 | 21 | 16 | |
| 23 | 2.11 | Josh Allen | QB1 | BUF | 7 | 23.8 | 23.8 | 24.2 | 31.5 | 26 | 27 | |
| 24 | 2.12 | George Pickens | WR11 | DAL | 14 | 24.2 | 27.6 | 27.1 | 19.2 | 22 | 19 | |
| 25 | 3.01 | Nico Collins | WR9 | HOU | 8 | 24.8 | 23.8 | 23.7 | 21.5 | 20 | 13 | |
| 26 | 3.02 | Rashee Rice | WR12 | KC | 5 | 25.8 | 25.4 | 34.8 | 16.9 | 34 | 22 | |
| 27 | 3.03 | Jeremiyah Love | RB14 | **ARI** | 14 | 26.8 | 18.6 | 17.1 | 31.7 | 27 | 41 | **high ankle sprain** |
| 28 | 3.04 | Chris Olave | WR10 | NO | 8 | 27.4 | 33.4 | 31.8 | 24.3 | 29 | 18 | |
| 29 | 3.05 | Malik Nabers | WR14 | NYG | 8 | 28.6 | 30.2 | 24.6 | 27.7 | 31 | 24 | post-ACL |
| 30 | 3.06 | Kyren Williams | RB15 | LAR | 11 | 30.0 | 38.2 | 32.7 | 27.2 | 30 | 42 | committee talk |
| 31 | 3.07 | Javonte Williams | RB16 | DAL | 14 | 31.2 | 37.8 | 35.7 | 34.1 | 37 | 43 | |
| 32 | 3.08 | Breece Hall | RB13 | NYJ | 13 | 31.4 | 34.0 | 33.0 | 28.4 | 33 | 40 | |
| 33 | 3.09 | Josh Jacobs | RB17 | GB | 11 | 31.8 | 26.7 | 25.2 | 27.2 | 36 | 44 | **groin since 8/6 + possible suspension** |
| 34 | 3.10 | DeVonta Smith | WR13 | PHI | 10 | 35.0 | 36.9 | 41.4 | 31.3 | 24 | 23 | |
| 35 | 3.11 | Zay Flowers | WR15 | BAL | 13 | 36.2 | 45.0 | 46.8 | **24.4** | 32 | 29 | |
| 36 | 3.12 | Cam Skattebo | RB19 | NYG | 8 | 38.0 | 43.0 | 44.4 | 34.6 | 46 | 55 | cleared |
| 37 | 4.01 | Tetairoa McMillan | WR17 | CAR | 5 | 38.8 | 41.8 | 37.2 | 33.9 | 41 | 32 | |
| 38 | 4.02 | Emeka Egbuka | WR21 | TB | 10 | 39.0 | 49.6 | 48.0 | 37.5 | 38 | 39 | |
| 39 | 4.03 | Travis Etienne Jr. | RB18 | **NO** | 8 | 40.6 | 44.6 | 33.8 | 42.8 | 44 | 48 | new team |
| 40 | 4.04 | Garrett Wilson | WR16 | NYJ | 13 | 40.8 | 38.4 | 40.5 | 30.9 | 40 | 30 | |
| 41 | 4.05 | Tee Higgins | WR20 | CIN | 6 | 41.6 | 50.5 | 37.8 | 35.0 | 28 | 35 | |
| 42 | 4.06 | Lamar Jackson | QB2 | BAL | 13 | 41.8 | 37.0 | 39.6 | 56.2 | 48 | 31 | |
| 43 | 4.07 | Colston Loveland | TE3 | CHI | 10 | 43.2 | 43.4 | 42.1 | 59.6 | 39 | 38 | |
| 44 | 4.08 | Bucky Irving | RB21 | TB | 10 | 45.8 | 54.6 | 37.6 | 47.5 | 59 | 60 | cleared, shoulder |
| 45 | 4.09 | Ladd McConkey | WR19 | LAC | 7 | 46.0 | 58.4 | 41.0 | 40.9 | 42 | 34 | |
| 46 | 4.10 | Quinshon Judkins | RB23 | CLE | 11 | 46.4 | 57.0 | 49.6 | 51.7 | 52 | 62 | cleared |
| 47 | 4.11 | Jaylen Waddle | WR18 | **DEN** | 10 | 49.0 | 60.8 | 45.5 | 47.0 | 35 | 33 | new team |
| 48 | 4.12 | D'Andre Swift | RB20 | CHI | 10 | 49.8 | 69.5 | 58.6 | 43.2 | 47 | 57 | |
| 49 | 5.01 | Davante Adams | WR24 | LAR | 11 | 50.0 | 45.5 | 55.0 | 37.4 | 51 | 49 | |
| 50 | 5.02 | Tyler Warren | TE4 | IND | 13 | 50.0 | 46.8 | 51.2 | 69.5 | 49 | 52 | |
| 51 | 5.03 | David Montgomery | RB22 | **HOU** | 8 | 51.2 | 71.7 | 53.5 | 55.1 | 53 | 61 | traded from DET |
| 52 | 5.04 | DJ Moore | WR25 | **BUF** | 7 | 52.4 | 67.5 | 61.2 | 51.0 | 56 | 50 | new team |
| 53 | 5.05 | Drake Maye | QB3 | NE | 11 | 52.8 | 50.2 | 54.0 | 52.2 | 60 | 37 | |
| 54 | 5.06 | Terry McLaurin | WR22 | WAS | 7 | 54.0 | 53.8 | 58.8 | 44.9 | 45 | 45 | |
| 55 | 5.07 | Luther Burden III | WR23 | CHI | 10 | 54.0 | **75.3** | 44.9 | 60.0 | 43 | 47 | **groin, out preseason** |
| 56 | 5.08 | Joe Burrow | QB4 | CIN | 6 | 54.6 | 56.6 | 58.2 | 55.4 | 61 | 46 | |
| 57 | 5.09 | TreVeyon Henderson | RB24 | NE | 11 | 55.2 | 60.4 | 41.3 | 58.7 | 65 | 66 | |
| 58 | 5.10 | Jameson Williams | WR27 | DET | 6 | 57.0 | 68.4 | 52.2 | 39.9 | 58 | 54 | |
| 59 | 5.11 | Bhayshul Tuten | RB25 | JAC | 7 | 57.8 | 76.2 | 54.1 | 53.7 | 54 | 68 | |
| 60 | 5.12 | Jayden Daniels | QB5 | WAS | 7 | 61.4 | 53.0 | 64.1 | 71.3 | 62 | 51 | |
| 61 | 6.01 | Rome Odunze | WR28 | CHI | 10 | 61.4 | 74.9 | 62.6 | 45.8 | 57 | 56 | |
| 62 | 6.02 | Jadarian Price | RB26 | **SEA** | 11 | 62.8 | 67.1 | 63.0 | 78.6 | 66 | 70 | rookie |
| 63 | 6.03 | Mike Evans | WR26 | **SF** | 8 | 64.8 | 81.5 | 57.0 | 52.8 | 55 | 53 | new team; practice absences |
| 64 | 6.04 | Jalen Hurts | QB6 | PHI | 10 | 64.8 | 59.6 | 68.4 | 78.5 | 64 | 59 | |
| 65 | 6.05 | Harold Fannin Jr. | TE5 | CLE | 11 | 69.4 | 68.1 | 66.7 | 80.8 | 80 | 71 | |
| 66 | 6.06 | Christian Watson | WR29 | GB | 11 | 70.4 | **95.3** | 63.3 | 56.4 | 50 | 58 | |
| 67 | 6.07 | Sam LaPorta | TE8 | DET | 6 | 70.6 | 75.0 | 78.4 | 90.0 | 75 | 84 | cleared, back surgery |
| 68 | 6.08 | Kyle Pitts Sr. | TE7 | ATL | 11 | 71.0 | 68.5 | 76.2 | 83.6 | 84 | 79 | |
| 69 | 6.09 | Carnell Tate | WR31 | **TEN** | 9 | 71.2 | 60.3 | 62.5 | 72.9 | 68 | 65 | |
| 70 | 6.10 | Tucker Kraft | TE6 | GB | 11 | 72.8 | **108.4** | 68.0 | 93.9 | 71 | 75 | |
| 71 | 6.11 | Jaylen Warren | RB27 | PIT | 9 | 73.4 | 93.5 | 66.6 | 62.3 | 73 | 73 | |
| 72 | 6.12 | Marvin Harrison Jr. | WR32 | ARI | 14 | 74.0 | 80.5 | 76.9 | 64.1 | 69 | 67 | |
| 73 | 7.01 | Parker Washington | WR30 | JAC | 7 | 74.2 | **105.7** | 87.4 | 64.5 | 63 | 63 | |
| 74 | 7.02 | Caleb Williams | QB7 | CHI | 10 | 75.6 | 100.0 | 86.5 | 86.0 | 72 | 64 | |
| 75 | 7.03 | Dak Prescott | QB10 | DAL | 14 | 76.4 | 97.7 | 97.8 | 66.4 | 83 | 78 | |
| 76 | 7.04 | Courtland Sutton | WR37 | DEN | 10 | 76.6 | 89.4 | 83.1 | 61.1 | 100 | 82 | |
| 77 | 7.05 | Brian Thomas Jr. | WR33 | JAC | 7 | 78.6 | 101.7 | 65.6 | 69.9 | 70 | 72 | |
| 78 | 7.06 | Rhamondre Stevenson | RB28 | NE | 11 | 79.4 | 109.3 | 73.7 | 69.7 | 67 | 80 | |
| 79 | 7.07 | DK Metcalf | WR35 | PIT | 9 | 80.0 | 86.2 | 78.1 | 63.8 | 81 | 77 | |
| 80 | 7.08 | Tony Pollard | RB29 | TEN | 9 | 80.0 | 91.5 | 82.1 | 64.7 | 77 | 83 | |
| 81 | 7.09 | Rico Dowdle | RB30 | PIT | 9 | 81.8 | 101.3 | 83.2 | 75.7 | 89 | 87 | |
| 82 | 7.10 | RJ Harvey | RB31 | DEN | 10 | 85.6 | 115.1 | 69.3 | 88.4 | 97 | 89 | behind Dobbins |
| 83 | 7.11 | Trevor Lawrence | QB9 | JAC | 7 | 88.6 | **116.3** | 93.8 | 95.4 | 82 | 74 | |
| 84 | 7.12 | Chuba Hubbard | RB33 | CAR | 5 | 89.2 | 83.8 | 73.0 | 71.7 | 78 | 93 | **hamstring, week-to-week** |
| 85 | 8.01 | Justin Herbert | QB8 | LAC | 7 | 89.6 | **123.0** | 85.7 | 107.7 | 74 | 69 | |
| 86 | 8.02 | Michael Wilson | WR40 | ARI | 14 | 89.8 | 118.2 | 82.6 | 75.1 | 91 | 88 | |
| 87 | 8.03 | Jonathon Brooks | RB32 | CAR | 5 | 91.8 | 127.3 | 112.0 | 108.9 | 90 | 90 | cleared, 2× ACL |
| 88 | 8.04 | Alec Pierce | WR42 | IND | 13 | 92.4 | 90.3 | 81.8 | **54.5** | 79 | 98 | |
| 89 | 8.05 | Jaxson Dart | QB12 | NYG | 8 | 92.6 | 73.6 | 88.8 | 120.7 | 95 | 92 | |
| 90 | 8.06 | J.K. Dobbins | RB35 | DEN | 10 | 93.2 | 106.9 | 90.6 | 88.8 | 86 | 102 | DEN RB1 |
| 91 | 8.07 | George Kittle | TE10 | SF | 8 | 95.2 | 83.0 | 99.2 | 114.1 | 94 | 96 | post-Achilles |
| 92 | 8.08 | Matthew Stafford | QB15 | LAR | 11 | 95.2 | 95.8 | 116.7 | 78.2 | 112 | 103 | |
| 93 | 8.09 | Michael Pittman Jr. | WR36 | **PIT** | 9 | 97.4 | 86.9 | 98.0 | 81.2 | 104 | 81 | new team |
| 94 | 8.10 | Wan'Dale Robinson | WR38 | **TEN** | 9 | 98.8 | 111.0 | 102.0 | 94.6 | 126 | 85 | |
| 95 | 8.11 | Travis Kelce | TE9 | KC | 5 | 99.0 | 92.2 | 112.6 | 122.2 | 113 | 95 | |
| 96 | 8.12 | Chris Godwin Jr. | WR34 | TB | 10 | 99.8 | 104.4 | 93.0 | 78.3 | 87 | 76 | |
| 97 | 9.01 | **Houston Texans** | DST1 | HOU | 8 | 99.8 | **86.0** | — | 98.1 | 141 | 155 | ESPN takes 69 picks early |
| 98 | 9.02 | Kyle Monangai | RB38 | CHI | 10 | 100.0 | 116.5 | 78.8 | 114.7 | 103 | 111 | injury; Swift up |
| 99 | 9.03 | **Brandon Aubrey** | K1 | DAL | 14 | 100.0 | **83.9** | — | 128.4 | 165 | 178 | ESPN takes 94 picks early |
| 100 | 9.04 | Kenny Gainwell | RB34 | TB | 10 | 102.4 | 107.6 | 109.8 | 100.6 | — | 97 | |
| 101 | 9.05 | Patrick Mahomes II | QB14 | KC | 5 | 105.8 | 113.1 | 101.0 | 100.8 | 111 | 100 | |
| 102 | 9.06 | Josh Downs | WR39 | IND | 13 | 106.8 | 129.5 | 121.0 | 84.2 | 88 | 86 | groin |
| 103 | 9.07 | Blake Corum | RB37 | LAR | 11 | 106.8 | 124.0 | 90.8 | 121.4 | 93 | 110 | |
| 104 | 9.08 | Quentin Johnston | WR41 | LAC | 7 | 107.4 | 137.6 | 102.5 | 84.6 | 85 | 94 | |
| 105 | 9.09 | Stefon Diggs | WR44 | **WAS** | 7 | 107.4 | **162.5** | 134.4 | 95.4 | 101 | 104 | biggest ESPN gap |
| 106 | 9.10 | Jordan Addison | WR46 | MIN | 6 | 107.8 | 128.4 | 98.4 | 90.4 | 96 | 106 | |
| 107 | 9.11 | Brock Purdy | QB11 | SF | 8 | 108.6 | 102.3 | 105.8 | 87.2 | 92 | 91 | |
| 108 | 9.12 | Jake Ferguson | TE12 | DAL | 14 | 109.2 | 109.5 | 105.3 | 148.3 | 136 | 115 | |
| 109 | 10.01 | Jordan Mason | RB41 | MIN | 6 | 109.2 | 150.0 | 124.6 | 115.9 | 107 | 118 | |
| 110 | 10.02 | Isaiah Likely | TE13 | **NYG** | 8 | 109.2 | 127.6 | 120.5 | 137.7 | 119 | 120 | new team |
| 111 | 10.03 | Jakobi Meyers | WR43 | JAC | 7 | 109.4 | 106.5 | 95.9 | 90.2 | 118 | 101 | |
| 112 | 10.04 | Bo Nix | QB13 | DEN | 10 | 110.0 | 119.6 | 114.1 | 116.7 | 99 | 99 | |
| 113 | 10.05 | Makai Lemon | WR47 | PHI | 10 | 110.2 | 109.4 | 77.9 | 109.9 | 102 | 108 | rookie |
| 114 | 10.06 | Rachaad White | RB36 | **WAS** | 7 | 110.6 | 108.7 | 119.0 | 112.1 | 106 | 109 | |
| 115 | 10.07 | Jacory Croskey-Merritt | RB40 | WAS | 7 | 110.8 | 133.6 | 108.0 | 109.4 | 105 | 116 | |
| 116 | 10.08 | Jordyn Tyson | WR52 | **NO** | 8 | 111.0 | 91.1 | 71.6 | 97.4 | 76 | 127 | rookie hype |
| 117 | 10.09 | **Los Angeles Rams** | DST4 | LAR | 11 | 111.4 | 100.0 | — | 106.8 | 148 | 167 | |
| 118 | 10.10 | **Denver Broncos** | DST2 | DEN | 10 | 112.0 | 91.9 | — | 87.9 | 164 | 164 | |
| 119 | 10.11 | Dallas Goedert | TE14 | PHI | 10 | 112.8 | 104.3 | 116.7 | 111.7 | 116 | 122 | |
| 120 | 10.12 | Aaron Jones Sr. | RB39 | MIN | 6 | 116.2 | 98.1 | 107.4 | 98.0 | 122 | 113 | |
| 121 | 11.01 | Jayden Reed | WR45 | GB | 11 | 117.8 | 142.2 | 110.5 | 90.3 | 98 | 105 | |
| 122 | 11.02 | **Seattle Seahawks** | DST3 | SEA | 11 | 119.8 | 100.0 | — | **82.2** | 157 | 166 | |
| 123 | 11.03 | Dalton Kincaid | TE11 | BUF | 7 | 121.2 | **153.1** | 97.5 | 146.0 | 109 | 114 | |
| 124 | 11.04 | Jared Goff | QB16 | DET | 6 | 121.6 | **151.4** | 125.8 | 105.3 | 115 | 107 | |
| 125 | 11.05 | Mark Andrews | TE15 | BAL | 13 | 124.4 | 138.8 | 115.0 | 131.7 | 121 | 130 | |
| 126 | 11.06 | Matthew Golden | WR53 | GB | 11 | 126.0 | 117.0 | 132.2 | 106.8 | 114 | 128 | |
| 127 | 11.07 | KC Concepcion | WR49 | CLE | 11 | 129.6 | 126.3 | 116.0 | 121.2 | 128 | 123 | |
| 128 | 11.08 | De'Zhaun Stribling | WR55 | SF | 8 | 132.6 | 170.5 | 245.2 | 142.0 | 132 | 140 | rising on Pearsall loss |
| 129 | 11.09 | Xavier Worthy | WR51 | KC | 5 | 133.8 | 128.5 | 119.8 | 101.6 | 120 | 126 | |
| 130 | 11.10 | Deebo Samuel Sr. | WR56 | SF | 8 | 134.2 | 169.9 | 158.7 | 107.8 | 141 | 141 | |
| 131 | 11.11 | **Cameron Dicker** | K2 | LAC | 7 | 134.6 | **108.5** | — | 143.3 | 180 | 192 | |
| 132 | 11.12 | **Jason Myers** | K5 | SEA | 11 | 136.4 | 122.6 | — | 132.8 | 190 | 201 | |
| 133 | 12.01 | Romeo Doubs | WR54 | **NE** | 11 | 136.6 | 143.9 | 112.7 | 106.8 | 125 | 129 | |
| 134 | 12.02 | Baker Mayfield | QB18 | TB | 10 | 137.6 | 157.2 | 142.2 | 132.0 | 130 | 117 | |
| 135 | 12.03 | **Ka'imi Fairbairn** | K3 | HOU | 8 | 137.6 | 124.2 | — | 137.3 | 177 | 194 | |
| 136 | 12.04 | Zach Charbonnet | RB48 | SEA | 11 | 138.2 | 139.6 | 123.3 | 134.2 | 140 | 145 | **PUP — misses ≥4 games** |
| 137 | 12.05 | Khalil Shakir | WR48 | BUF | 7 | 139.2 | 134.9 | 130.4 | 105.1 | 144 | 121 | |
| 138 | 12.06 | Kyler Murray | QB17 | **MIN** | 6 | 139.6 | 156.6 | 153.2 | 136.5 | 110 | 112 | new team |
| 139 | 12.07 | **Philadelphia Eagles** | DST5 | PHI | 10 | 139.6 | 132.7 | — | 132.2 | 181 | 171 | |
| 140 | 12.08 | Woody Marks | RB43 | HOU | 8 | 142.0 | 142.7 | 138.6 | 145.9 | 139 | 134 | |
| 141 | 12.09 | Chris Rodriguez Jr. | RB45 | JAC | 7 | 144.0 | 165.2 | 140.6 | 153.7 | 117 | 136 | foot surgery return |
| 142 | 12.10 | Tyrone Tracy Jr. | RB46 | NYG | 8 | 145.0 | 167.8 | 131.4 | 147.4 | 133 | 139 | |
| 143 | 12.11 | Alvin Kamara | RB50 | NO | 8 | 146.2 | 147.2 | 156.8 | 149.7 | 143 | 151 | |
| 144 | 12.12 | Jalen Coker | WR50 | CAR | 5 | 147.4 | 156.3 | 137.8 | 114.7 | 124 | 124 | |
| 145 | 13.01 | Rashid Shaheed | WR58 | **SEA** | 11 | 147.8 | 160.1 | 150.0 | 120.2 | 134 | 146 | |
| 146 | 13.02 | Jordan Love | QB19 | GB | 11 | 149.8 | 162.5 | 133.3 | 150.3 | 127 | 119 | |
| 147 | 13.03 | Tyjae Spears | RB44 | TEN | 9 | 150.4 | 146.0 | 145.6 | 148.6 | 146 | 135 | |
| 148 | 13.04 | **Cam Little** | K4 | JAC | 7 | 151.6 | 134.9 | — | 155.8 | 184 | 195 | |
| 149 | 13.05 | Tyler Shough | QB20 | NO | 8 | 151.8 | 157.2 | 139.1 | 132.6 | 135 | 125 | |
| 150 | 13.06 | Tyler Allgeier | RB42 | **ARI** | 14 | 152.2 | 165.8 | 120.9 | 159.2 | 137 | 133 | |
| 151 | 13.07 | **Pittsburgh Steelers** | DST7 | PIT | 9 | 155.0 | 123.1 | — | 141.0 | 190 | 182 | |
| 152 | 13.08 | Isiah Pacheco | RB52 | **DET** | 6 | 156.6 | 144.4 | 175.3 | 152.0 | 151 | 153 | sprained MCL |
| 153 | 13.09 | **New England Patriots** | DST6 | NE | 11 | 157.4 | 124.7 | — | 122.8 | 178 | 181 | |
| 154 | 13.10 | Hunter Henry | TE19 | NE | 11 | 159.4 | 160.6 | 119.2 | 145.2 | 164 | 154 | |
| 155 | 13.11 | Juwan Johnson | TE16 | NO | 8 | 160.0 | 165.8 | 143.1 | 166.0 | 155 | 132 | |
| 156 | 13.12 | MarShawn Lloyd | RB57 | GB | 11 | 160.0 | 170.4 | — | 165.1 | 172 | 184 | Jacobs handcuff |
| 157 | 14.01 | Brenton Strange | TE17 | JAC | 7 | 162.6 | 167.4 | 128.3 | 159.2 | 157 | 149 | |
| 158 | 14.02 | **Baltimore Ravens** | DST11 | BAL | 13 | 162.6 | 138.3 | — | 161.7 | 201 | 199 | |
| 159 | 14.03 | T.J. Hockenson | TE21 | MIN | 6 | 163.8 | 150.1 | 159.0 | 172.6 | 195 | 172 | |
| 160 | 14.04 | **Minnesota Vikings** | DST8 | MIN | 6 | 164.2 | 155.8 | — | **114.1** | 191 | 185 | |
| 161 | 14.05 | Travis Hunter | WR67 | JAC | 7 | 165.0 | **117.0** | 145.2 | 158.6 | 158 | 176 | ESPN name-brand reach |
| 162 | 14.06 | Denzel Boston | WR57 | CLE | 11 | 166.4 | 168.1 | 144.4 | 138.3 | 163 | 143 | |
| 163 | 14.07 | **Jake Bates** | K9 | DET | 6 | 166.4 | 150.5 | — | 147.0 | 200 | 219 | |
| 164 | 14.08 | Oronde Gadsden II | TE22 | LAC | 7 | 167.0 | 168.4 | 102.2 | — | 167 | 175 | |
| 165 | 14.09 | Keaton Mitchell | RB49 | **LAC** | 7 | 167.4 | 170.4 | 164.9 | 153.8 | 131 | 147 | |
| 166 | 14.10 | Brian Robinson Jr. | RB54 | **ATL** | 11 | 167.4 | 167.9 | 136.9 | 171.2 | 152 | 165 | |
| 167 | 14.11 | **Harrison Mevis** | K11 | LAR | 11 | 167.8 | 137.8 | — | 139.2 | 217 | 222 | |
| 168 | 14.12 | Kenyon Sadiq | TE25 | NYJ | 13 | 168.0 | 147.9 | 131.9 | — | 181 | 211 | rookie |
| 169 | 15.01 | Dylan Sampson | RB47 | CLE | 11 | 168.8 | 170.5 | 151.5 | 175.8 | 166 | 142 | |
| 170 | 15.02 | Malik Willis | QB21 | **MIA** | 6 | 169.0 | 167.8 | 139.7 | 159.4 | 129 | 131 | new team |

### 🚨 Two players carrying LIVE ADP who should NOT be drafted

Both still appear in stale ADP feeds. Verified from the 2026-08-22 news corpus:

- **Ricky Pearsall (SF WR)** — **ruled OUT for the entire 2026 season (PCL surgery).** Still shows ESPN ADP **119.6** and Sleeper **92.6** (both 7/18–7/19 fetches). He has vanished from every August source (FFC, Yahoo, UDK, FantasyPros). If your ESPN draft room is using ESPN's own default board, **someone will draft a player who cannot play.** Do not be that person.
- **Jayden Higgins (HOU WR)** — **torn ACL.** Still shows FFC **118.9** (8/19) and ESPN **159.7**. Confirmed via CBS's TE-tiers piece noting Dalton Schultz's value rose "after Jayden Higgins tore his ACL."

---

## 2a. 12-TEAM round-by-round board (rounds 1–14)

Players typically gone by the **end** of each round, by consensus ADP.

**R1 (1–12):** Gibbs · Bijan · Chase · Nacua · McCaffrey · JSN · J.Taylor · ARSB · Cook · Jeanty · Achane · Lamb
**R2 (13–24):** Jefferson · Barkley · Chase Brown · London · Hampton · Henry · K.Walker · A.J. Brown · **McBride** · **Bowers** · **Josh Allen** · Pickens
**R3 (25–36):** N.Collins · Rice · J.Love · Olave · Nabers · Kyren · Javonte · Breece · Jacobs · DeVonta · Flowers · Skattebo
**R4 (37–48):** McMillan · Egbuka · Etienne · G.Wilson · T.Higgins · **Lamar** · **Loveland** · Irving · McConkey · Judkins · Waddle · Swift
**R5 (49–60):** Adams · **T.Warren** · Montgomery · DJ Moore · **Maye** · McLaurin · Burden · **Burrow** · Henderson · Ja.Williams · Tuten · **J.Daniels**
**R6 (61–72):** Odunze · Price · Evans · **Hurts** · **Fannin** · Watson · **LaPorta** · **Pitts** · Tate · **Kraft** · Ja.Warren · MHJ
**R7 (73–84):** P.Washington · **C.Williams** · **Prescott** · Sutton · BTJ · Stevenson · Metcalf · Pollard · Dowdle · Harvey · **Lawrence** · Hubbard
**R8 (85–96):** **Herbert** · M.Wilson · Brooks · Pierce · **Dart** · Dobbins · **Kittle** · **Stafford** · Pittman · Wan'Dale · **Kelce** · Godwin
**R9 (97–108):** ⚠️ **HOU D/ST** · Monangai · ⚠️ **Aubrey K** · Gainwell · **Mahomes** · Downs · Corum · Q.Johnston · Diggs · Addison · **Purdy** · **Ferguson**
**R10 (109–120):** J.Mason · **Likely** · Meyers · **Nix** · Lemon · R.White · Croskey-Merritt · Tyson · **LAR D/ST** · **DEN D/ST** · **Goedert** · A.Jones
**R11 (121–132):** Reed · **SEA D/ST** · **Kincaid** · **Goff** · **Andrews** · Golden · Concepcion · Stribling · Worthy · Deebo · **Dicker K** · **Myers K**
**R12 (133–144):** Doubs · **Mayfield** · **Fairbairn K** · Charbonnet · Shakir · **K.Murray** · **PHI D/ST** · Marks · C.Rodriguez · Tracy · Kamara · Coker
**R13 (145–156):** Shaheed · **J.Love QB** · Spears · **Little K** · **Shough** · Allgeier · **PIT D/ST** · Pacheco · **NE D/ST** · **H.Henry** · **J.Johnson** · M.Lloyd
**R14 (157–168):** **Strange** · **BAL D/ST** · **Hockenson** · **MIN D/ST** · T.Hunter · Boston · **Bates K** · **Gadsden** · Mitchell · B.Robinson · **Mevis K** · **Sadiq**

## 2b. 10-TEAM round-by-round board (rounds 1–14)

Same ordering, 10 picks per round. **Behavioral adjustment:** in 10-team leagues the last ~2 rounds shown below realistically never happen — only 130 players are drafted at 13 roster spots — and QB/TE/K/D-ST all slide roughly half a round later than the mechanical conversion, because there are two fewer starters demanded at every single-slot position.

**R1 (1–10):** Gibbs · Bijan · Chase · Nacua · McCaffrey · JSN · J.Taylor · ARSB · Cook · Jeanty
**R2 (11–20):** Achane · Lamb · Jefferson · Barkley · Chase Brown · London · Hampton · Henry · K.Walker · A.J. Brown
**R3 (21–30):** McBride · Bowers · Josh Allen · Pickens · N.Collins · Rice · J.Love · Olave · Nabers · Kyren
**R4 (31–40):** Javonte · Breece · Jacobs · DeVonta · Flowers · Skattebo · McMillan · Egbuka · Etienne · G.Wilson
**R5 (41–50):** T.Higgins · Lamar · Loveland · Irving · McConkey · Judkins · Waddle · Swift · Adams · T.Warren
**R6 (51–60):** Montgomery · DJ Moore · Maye · McLaurin · Burden · Burrow · Henderson · Ja.Williams · Tuten · J.Daniels
**R7 (61–70):** Odunze · Price · Evans · Hurts · Fannin · Watson · LaPorta · Pitts · Tate · Kraft
**R8 (71–80):** Ja.Warren · MHJ · P.Washington · C.Williams · Prescott · Sutton · BTJ · Stevenson · Metcalf · Pollard
**R9 (81–90):** Dowdle · Harvey · Lawrence · Hubbard · Herbert · M.Wilson · Brooks · Pierce · Dart · Dobbins
**R10 (91–100):** Kittle · Stafford · Pittman · Wan'Dale · Kelce · Godwin · **HOU D/ST** · Monangai · **Aubrey K** · Gainwell
**R11 (101–110):** Mahomes · Downs · Corum · Q.Johnston · Diggs · Addison · Purdy · Ferguson · J.Mason · Likely
**R12 (111–120):** Meyers · Nix · Lemon · R.White · Croskey-Merritt · Tyson · **LAR D/ST** · **DEN D/ST** · Goedert · A.Jones
**R13 (121–130):** Reed · **SEA D/ST** · Kincaid · Goff · Andrews · Golden · Concepcion · Stribling · Worthy · Deebo
**R14 (131–140):** **Dicker K** · **Myers K** · Doubs · Mayfield · **Fairbairn K** · Charbonnet · Shakir · K.Murray · **PHI D/ST** · Marks

---

## 3. Position-by-position ADP

### Top 40 RB (FP consensus ADP, 8/21)
| # | Player | Tm | ADP | ESPN | FFC | ECR |
|--:|:--|:--|--:|--:|--:|--:|
|1|Jahmyr Gibbs|DET|1.0|1.9|1.5|2|
|2|Bijan Robinson|ATL|2.0|2.3|2.1|4|
|3|Christian McCaffrey|SF|5.6|5.5|6.8|9|
|4|Jonathan Taylor|IND|6.4|8.5|5.8|11|
|5|James Cook III|BUF|10.2|13.3|8.9|17|
|6|Ashton Jeanty|LV|11.2|13.7|15.8|14|
|7|De'Von Achane|MIA|11.4|12.1|11.3|21|
|8|Saquon Barkley|PHI|14.2|15.4|17.9|26|
|9|Chase Brown|CIN|15.2|27.2|14.8|15|
|10|Omarion Hampton|LAC|17.6|20.6|22.4|25|
|11|Derrick Henry|BAL|18.4|18.6|10.6|36|
|12|Kenneth Walker III|KC|19.0|28.2|22.1|28|
|13|Jeremiyah Love|ARI|26.8|18.6|31.7|41|
|14|Kyren Williams|LAR|30.0|38.2|27.2|42|
|15|Javonte Williams|DAL|31.2|37.8|34.1|43|
|16|Breece Hall|NYJ|31.4|34.0|28.4|40|
|17|Josh Jacobs|GB|31.8|26.7|27.2|44|
|18|Cam Skattebo|NYG|38.0|43.0|34.6|55|
|19|Travis Etienne Jr.|NO|40.6|44.6|42.8|48|
|20|Bucky Irving|TB|45.8|54.6|47.5|60|
|21|Quinshon Judkins|CLE|46.4|57.0|51.7|62|
|22|D'Andre Swift|CHI|49.8|69.5|43.2|57|
|23|David Montgomery|HOU|51.2|71.7|55.1|61|
|24|TreVeyon Henderson|NE|55.2|60.4|58.7|66|
|25|Bhayshul Tuten|JAC|57.8|76.2|53.7|68|
|26|Jadarian Price|SEA|62.8|67.1|78.6|70|
|27|Jaylen Warren|PIT|73.4|93.5|62.3|73|
|28|Rhamondre Stevenson|NE|79.4|109.3|69.7|80|
|29|Tony Pollard|TEN|80.0|91.5|64.7|83|
|30|Rico Dowdle|PIT|81.8|101.3|75.7|87|
|31|RJ Harvey|DEN|85.6|115.1|88.4|89|
|32|Chuba Hubbard|CAR|89.2|83.8|71.7|93|
|33|Jonathon Brooks|CAR|91.8|127.3|108.9|90|
|34|J.K. Dobbins|DEN|93.2|106.9|88.8|102|
|35|Kyle Monangai|CHI|100.0|116.5|114.7|111|
|36|Kenny Gainwell|TB|102.4|107.6|100.6|97|
|37|Blake Corum|LAR|106.8|124.0|121.4|110|
|38|Jordan Mason|MIN|109.2|150.0|115.9|118|
|39|Rachaad White|WAS|110.6|108.7|112.1|109|
|40|Jacory Croskey-Merritt|WAS|110.8|133.6|109.4|116|

### Top 45 WR
| # | Player | Tm | ADP | ESPN | FFC | ECR |
|--:|:--|:--|--:|--:|--:|--:|
|1|Ja'Marr Chase|CIN|3.0|4.7|4.1|1|
|2|Puka Nacua|LAR|4.0|3.6|3.0|3|
|3|Jaxon Smith-Njigba|SEA|6.0|6.3|5.4|5|
|4|Amon-Ra St. Brown|DET|8.2|7.8|7.8|6|
|5|CeeDee Lamb|DAL|12.0|11.2|12.6|7|
|6|Justin Jefferson|MIN|12.4|12.5|14.0|8|
|7|Drake London|ATL|17.4|20.3|12.1|10|
|8|A.J. Brown|NE|20.6|27.3|19.4|12|
|9|George Pickens|DAL|24.2|27.6|19.2|19|
|10|Nico Collins|HOU|24.8|23.8|21.5|13|
|11|Rashee Rice|KC|25.8|25.4|16.9|22|
|12|Chris Olave|NO|27.4|33.4|24.3|18|
|13|Malik Nabers|NYG|28.6|30.2|27.7|24|
|14|DeVonta Smith|PHI|35.0|36.9|31.3|23|
|15|Zay Flowers|BAL|36.2|45.0|24.4|29|
|16|Tetairoa McMillan|CAR|38.8|41.8|33.9|32|
|17|Emeka Egbuka|TB|39.0|49.6|37.5|39|
|18|Garrett Wilson|NYJ|40.8|38.4|30.9|30|
|19|Tee Higgins|CIN|41.6|50.5|35.0|35|
|20|Ladd McConkey|LAC|46.0|58.4|40.9|34|
|21|Jaylen Waddle|DEN|49.0|60.8|47.0|33|
|22|Davante Adams|LAR|50.0|45.5|37.4|49|
|23|DJ Moore|BUF|52.4|67.5|51.0|50|
|24|Terry McLaurin|WAS|54.0|53.8|44.9|45|
|25|Luther Burden III|CHI|54.0|75.3|60.0|47|
|26|Jameson Williams|DET|57.0|68.4|39.9|54|
|27|Rome Odunze|CHI|61.4|74.9|45.8|56|
|28|Mike Evans|SF|64.8|81.5|52.8|53|
|29|Christian Watson|GB|70.4|95.3|56.4|58|
|30|Carnell Tate|TEN|71.2|60.3|72.9|65|
|31|Marvin Harrison Jr.|ARI|74.0|80.5|64.1|67|
|32|Parker Washington|JAC|74.2|105.7|64.5|63|
|33|Courtland Sutton|DEN|76.6|89.4|61.1|82|
|34|Brian Thomas Jr.|JAC|78.6|101.7|69.9|72|
|35|DK Metcalf|PIT|80.0|86.2|63.8|77|
|36|Michael Wilson|ARI|89.8|118.2|75.1|88|
|37|Alec Pierce|IND|92.4|90.3|54.5|98|
|38|Michael Pittman Jr.|PIT|97.4|86.9|81.2|81|
|39|Wan'Dale Robinson|TEN|98.8|111.0|94.6|85|
|40|Chris Godwin Jr.|TB|99.8|104.4|78.3|76|
|41|Josh Downs|IND|106.8|129.5|84.2|86|
|42|Quentin Johnston|LAC|107.4|137.6|84.6|94|
|43|Stefon Diggs|WAS|107.4|162.5|95.4|104|
|44|Jordan Addison|MIN|107.8|128.4|90.4|106|
|45|Jakobi Meyers|JAC|109.4|106.5|90.2|101|

### Top 20 QB
| # | Player | Tm | ADP | ESPN | FFC | ECR |
|--:|:--|:--|--:|--:|--:|--:|
|1|Josh Allen|BUF|23.8|23.8|31.5|27|
|2|Lamar Jackson|BAL|41.8|37.0|56.2|31|
|3|Drake Maye|NE|52.8|50.2|52.2|37|
|4|Joe Burrow|CIN|54.6|56.6|55.4|46|
|5|Jayden Daniels|WAS|61.4|53.0|71.3|51|
|6|Jalen Hurts|PHI|64.8|59.6|78.5|59|
|7|Caleb Williams|CHI|75.6|100.0|86.0|64|
|8|Dak Prescott|DAL|76.4|97.7|66.4|78|
|9|Trevor Lawrence|JAC|88.6|116.3|95.4|74|
|10|Justin Herbert|LAC|89.6|123.0|107.7|69|
|11|Jaxson Dart|NYG|92.6|73.6|120.7|92|
|12|Matthew Stafford|LAR|95.2|95.8|78.2|103|
|13|Patrick Mahomes II|KC|105.8|113.1|100.8|100|
|14|Brock Purdy|SF|108.6|102.3|87.2|91|
|15|Bo Nix|DEN|110.0|119.6|116.7|99|
|16|Jared Goff|DET|121.6|151.4|105.3|107|
|17|Baker Mayfield|TB|137.6|157.2|132.0|117|
|18|Kyler Murray|MIN|139.6|156.6|136.5|112|
|19|Jordan Love|GB|149.8|162.5|150.3|119|
|20|Tyler Shough|NO|151.8|157.2|132.6|125|

### Top 20 TE
| # | Player | Tm | ADP | ESPN | FFC | ECR |
|--:|:--|:--|--:|--:|--:|--:|
|1|Trey McBride|ARI|21.6|21.1|38.6|20|
|2|Brock Bowers|LV|22.4|23.6|42.5|16|
|3|Colston Loveland|CHI|43.2|43.4|59.6|38|
|4|Tyler Warren|IND|50.0|46.8|69.5|52|
|5|Harold Fannin Jr.|CLE|69.4|68.1|80.8|71|
|6|Sam LaPorta|DET|70.6|75.0|90.0|84|
|7|Kyle Pitts Sr.|ATL|71.0|68.5|83.6|79|
|8|Tucker Kraft|GB|72.8|108.4|93.9|75|
|9|George Kittle|SF|95.2|83.0|114.1|96|
|10|Travis Kelce|KC|99.0|92.2|122.2|95|
|11|Jake Ferguson|DAL|109.2|109.5|148.3|115|
|12|Isaiah Likely|NYG|109.2|127.6|137.7|120|
|13|Dallas Goedert|PHI|112.8|104.3|111.7|122|
|14|Dalton Kincaid|BUF|121.2|153.1|146.0|114|
|15|Mark Andrews|BAL|124.4|138.8|131.7|130|
|16|Hunter Henry|NE|159.4|160.6|145.2|154|
|17|Juwan Johnson|NO|160.0|165.8|166.0|132|
|18|Brenton Strange|JAC|162.6|167.4|159.2|149|
|19|T.J. Hockenson|MIN|163.8|150.1|172.6|172|
|20|Oronde Gadsden II|LAC|167.0|168.4|—|175|

### Top 12 D/ST
| # | Team | ADP | **ESPN** | FFC | ECR | ESPN−ECR |
|--:|:--|--:|--:|--:|--:|--:|
|1|Houston Texans|99.8|**86.0**|98.1|155|−69|
|2|Los Angeles Rams|111.4|100.0|106.8|167|−67|
|3|Denver Broncos|112.0|91.9|87.9|164|−72|
|4|Seattle Seahawks|119.8|100.0|82.2|166|−66|
|5|Philadelphia Eagles|139.6|132.7|132.2|171|−38|
|6|Pittsburgh Steelers|155.0|123.1|141.0|182|−59|
|7|New England Patriots|157.4|124.7|122.8|181|−56|
|8|Baltimore Ravens|162.6|138.3|161.7|199|−61|
|9|Minnesota Vikings|164.2|155.8|114.1|185|−29|
|10|Los Angeles Chargers|175.4|163.7|143.0|193|−29|
|11|Jacksonville Jaguars|178.0|157.6|154.5|189|−31|
|12|Detroit Lions|187.4|156.8|131.2|228|−71|

*Also note FantasyPros' separate best-ball D/ST ECR page (8/21) ranks: HOU 1, DEN 2, SEA 3, LAR 4, PHI 5.43.*

### Top 12 K
| # | Player | Tm | ADP | **ESPN** | FFC | ECR | ESPN−ECR |
|--:|:--|:--|--:|--:|--:|--:|--:|
|1|Brandon Aubrey|DAL|100.0|**83.9**|128.4|178|−94|
|2|Cameron Dicker|LAC|134.6|108.5|143.3|192|−84|
|3|Jason Myers|SEA|136.4|122.6|132.8|201|−78|
|4|Ka'imi Fairbairn|HOU|137.6|124.2|137.3|194|−70|
|5|Cam Little|JAC|151.6|134.9|155.8|195|−60|
|6|Jake Bates|DET|166.4|150.5|147.0|219|−69|
|7|Harrison Mevis|LAR|167.8|137.8|139.2|222|−84|
|8|Eddy Pineiro|SF|183.4|147.4|—|208|−61|
|9|Tyler Loop|BAL|185.4|161.4|151.5|207|−46|
|10|Harrison Butker|KC|197.4|155.6|172.5|241|−85|
|11|Andy Borregales|NE|203.7|170.4|176.6|225|−55|
|12|Will Reichard|MIN|208.8|165.1|159.2|269|−104|

---

## 4. ESPN ADP vs expert consensus — the arbitrage

### 4a. Method note (this is why my numbers differ from a naive comparison)
A raw "ESPN ADP minus ECR" conflates two different things: genuine ESPN-platform bias, and five weeks of market movement (ESPN data = 7/18, ECR = 8/21). I separated them using **FFC's own 7/18 and 8/18 snapshots as a drift control**:

> `ESPN bias ≈ (ESPN₇⁄₁₈ − FP_ADP₈⁄₂₁) − (FFC₇⁄₁₈ − FFC₈⁄₁₈)`

Median absolute market drift was only 5.5 picks, so most of the gap **is** real platform bias — but for a dozen players it isn't, and those are exactly the ones you'd otherwise misplay.

### 4b. 🟢 Genuine ESPN BUYS — the room lets these fall
| Player | Pos | ESPN | FP ADP | raw gap | drift | **true bias** |
|:--|:--|--:|--:|--:|--:|--:|
|**Justin Herbert**|QB8|123.0|89.6|+33.4|−29.7|**+63.1**|
|**Tucker Kraft**|TE6|108.4|72.8|+35.6|−16.7|**+52.3**|
|**Jared Goff**|QB16|151.4|121.6|+29.8|−12.5|**+42.3**|
|**Trevor Lawrence**|QB9|116.3|88.6|+27.7|−8.6|**+36.3**|
|**Dalton Kincaid**|TE11|153.1|121.2|+31.9|−3.4|**+35.3**|
|**Luther Burden III**|WR23|75.3|54.0|+21.3|−13.9|**+35.2**|
|**Jordan Mason**|RB41|150.0|109.2|+40.8|+5.8|**+35.0**|
|**Patrick Mahomes**|QB14|113.1|105.8|+7.3|−26.1|**+33.4**|
|Jayden Reed|WR45|142.2|117.8|+24.4|−7.6|+32.0|
|Kyle Monangai|RB38|116.5|100.0|+16.5|−15.1|+31.6|
|Rhamondre Stevenson|RB28|109.3|79.4|+29.9|+2.1|+27.8|
|Jordan Love|QB19|162.5|149.8|+12.7|−15.1|+27.8|
|Dak Prescott|QB10|97.7|76.4|+21.3|−4.6|+25.9|
|Michael Wilson|WR40|118.2|89.8|+28.5|+3.6|+24.8|
|Mark Andrews|TE15|138.8|124.4|+14.4|−9.7|+24.1|
|RJ Harvey|RB31|115.1|85.6|+29.5|+5.9|+23.6|

**The pattern is unmistakable: ESPN drafters systematically wait too long on QB and TE.** Seven of the top eight biggest ESPN values are QBs or TEs. Herbert, Lawrence, Goff and Mahomes are all available 25–65 picks later on ESPN than experts rank them.

*Also large on the raw (undrifted) comparison, worth knowing:* Stefon Diggs (ESPN 162.5 vs FP 107.4, **+55**), Kyler Murray (+45), Quentin Johnston (+44), Josh Downs (+44), Parker Washington (+43), Christian Watson (+37), Jonathon Brooks (+37).

### 4c. 🔴 ESPN FADES — the room reaches
| Player | Pos | ESPN | FP ADP | raw gap | drift | **true bias** |
|:--|:--|--:|--:|--:|--:|--:|
|**Travis Hunter**|WR67|117.0|165.0|−48.0|+8.4|**−56.4**|
|Jalen McMillan|WR63|163.0|189.3|−26.3|+2.5|−28.8|
|Dallas Goedert|TE14|104.3|112.8|−8.5|+19.0|−27.5|
|Brock Purdy|QB11|102.3|108.6|−6.3|+20.0|−26.3|
|Matthew Stafford|QB15|95.8|95.2|+0.6|+26.6|−26.0|
|**Jaxson Dart**|QB12|73.6|92.6|−19.0|+6.7|−25.7|
|Jalen Hurts|QB6|59.6|64.8|−5.2|+18.7|−23.9|
|Jayden Daniels|QB5|53.0|61.4|−8.4|+12.0|−20.4|
|Chuba Hubbard|RB33|83.8|89.2|−5.4|+10.8|−16.2|
|Aaron Jones Sr.|RB39|98.1|116.2|−18.1|−2.3|−15.8|
|Zach Charbonnet|RB48|139.6|138.2|+1.4|+16.5|−15.1|
|Drake Maye|QB3|50.2|52.8|−2.6|+10.6|−13.2|
|Kyle Pitts Sr.|TE7|68.5|71.0|−2.5|+10.6|−13.1|

Also reaching on raw ECR comparison: **Kenyon Sadiq** (ESPN 147.9 vs ECR 211, −63), **Jordyn Tyson** (−36), **Jeremiyah Love** (ESPN 18.6 vs ECR 41, −22 — and he has a high ankle sprain), **Derrick Henry** (−17), **Josh Jacobs** (−17).

### 4d. 🏆 The single biggest ESPN edge: kickers and defenses
This is the largest, most systematic, most exploitable distortion on the board — and it is worth more to you than any individual player call:

| | ESPN ADP | Expert ECR | ESPN takes them… |
|:--|--:|--:|:--|
|Brandon Aubrey (K1)|**83.9**|178|**94 picks early** |
|Cameron Dicker (K2)|108.5|192|84 picks early|
|Harrison Mevis (K7)|137.8|222|84 picks early|
|Jason Myers (K3)|122.6|201|78 picks early|
|Denver D/ST|91.9|164|72 picks early|
|Houston D/ST|86.0|155|69 picks early|
|LA Rams D/ST|100.0|167|67 picks early|
|Seattle D/ST|100.0|166|66 picks early|

**On ESPN, the K1 comes off the board in round 7 of a 12-teamer and the top four defenses go rounds 8–9.** Experts say both belong after pick 155. In your league — where K and D/ST are *mandatory* and you have only **4 bench spots** — this is a structural gift: let the room burn picks 84–125 on kickers and defenses while you take the QB/TE/WR values from §4b, then take your K and D/ST in the last two rounds. Your K/D-ST will be ~90% as good and you will have banked roughly **three extra rounds of skill-position capital**.

---

## 5. Tier cliffs — the exact ADP after which each position falls off

Measured as the gap in consensus ADP to the next player at that position.

### QB — three cliffs, and the first is enormous
- **Cliff 1: after QB1 Josh Allen (ADP 23.8) → Lamar Jackson (41.8). GAP 18.0.** Allen is on an island.
- **Cliff 2: after QB2 Lamar (41.8) → Drake Maye (52.8). GAP 11.0.**
- **Cliff 3: after QB8 Dak Prescott (76.4) → Trevor Lawrence (88.6). GAP 12.2.**
- **Cliff 4 (the real one for your build): after QB15 Bo Nix (110.0) → Jared Goff (121.6), then QB16 Goff → Baker Mayfield (137.6). GAP 11.6 then 16.0.** In a 10- or 12-team single-QB league, **QB9–QB15 is the sweet spot** — Lawrence/Herbert/Dart/Stafford/Mahomes/Purdy/Nix all land between ADP 88 and 110, and on ESPN they fall even further (§4b).
- Final cliff: after QB20 Shough (151.8) → Malik Willis (169.0). **GAP 17.2.** Past QB20 it is genuinely bad.

### TE — the steepest positional structure on the board
- **Cliff 1: after TE2 Brock Bowers (22.4) → Colston Loveland (43.2). GAP 20.8.** McBride/Bowers are a two-man tier.
- **Cliff 2: after TE4 Tyler Warren (50.0) → Harold Fannin (69.4). GAP 19.4.**
- **Cliff 3: after TE8 Tucker Kraft (72.8) → George Kittle (95.2). GAP 22.4.** ← **This is the one that decides your draft.** Fannin/LaPorta/Pitts/Kraft (ADP 69–73) are the last cluster with genuine TE1 upside.
- **Cliff 4: after TE15 Mark Andrews (124.4) → Hunter Henry (159.4). GAP 35.0 — the largest single cliff at any position.** If you do not have a TE by ~pick 125, you are streaming a replacement-level tight end all year.

### RB
- **Cliff 1: after RB12 Kenneth Walker III (19.0) → Jeremiyah Love (26.8). GAP 7.8.** The bell-cow tier ends at pick 19.
- **Cliff 2: after RB17 Josh Jacobs (31.8) → Cam Skattebo (38.0). GAP 6.2.**
- **Cliff 3: after RB26 Jadarian Price (62.8) → Jaylen Warren (73.4). GAP 10.6.** End of standalone-starter RBs.
- **Cliff 4: after RB34 J.K. Dobbins (93.2) → Kyle Monangai (100.0). GAP 6.8.**
- **Cliff 5: after RB41 Aaron Jones (116.2) → Zach Charbonnet (138.2). GAP 22.0.** Past RB41 you are drafting handcuffs and PUP bodies.

### WR — remarkably smooth, which is itself the finding
WR has **no cliff larger than 9.8 picks** in the top 50. The largest are: after **WR35 DK Metcalf (80.0)** → Michael Wilson (89.8), GAP 9.8; after **WR48 Jayden Reed (117.8)** → Matthew Golden (126.0), GAP 8.2; after **WR40 Godwin (99.8)** → Josh Downs (106.8), GAP 7.0; and a minor one after **WR13 Nabers (28.6)** → DeVonta Smith (35.0), GAP 6.4.

**Implication:** WR is the position you can *always* wait on. There is no point at which the WR board falls off a ledge, which means every pick you spend early on a WR is a pick you did not spend on the steep-cliff positions (TE, RB). This is the strongest structural argument on the entire board for attacking RB and TE early and letting WR come to you.

### D/ST
- **Cliff 1: after DST1 Houston (99.8) → LA Rams (111.4). GAP 11.6.**
- **Cliff 2: after DST4 Seattle (119.8) → Philadelphia (139.6). GAP 19.8.** ← The top 4 (HOU, LAR, DEN, SEA) are a real tier; everyone else is streamable.
- **Cliff 3: after DST5 Philadelphia (139.6) → Pittsburgh (155.0). GAP 15.4.**
- ⚠️ Your league scores **yards allowed** (−7 for 550+, +5 for <100) on top of points allowed. That double-counts defensive quality and makes the elite units meaningfully more valuable *in your format specifically* than a generic ADP implies. It does not, however, justify paying ESPN's pick-86 price.

### K
- **Cliff 1: after K1 Brandon Aubrey (100.0) → Cameron Dicker (134.6). GAP 34.6** — the biggest gap at any position. Aubrey is genuinely a tier of one on ADP.
- **Cliff 2: after K4 Fairbairn (137.6) → Cam Little (151.6). GAP 14.0.**
- Realistically: K2–K7 (Dicker, Myers, Fairbairn, Little, Bates, Mevis) are interchangeable. Take whoever is left in your final round.
