> ## How this was verified — read this line, then trust the rest
>
> **WebSearch was hard-capped at 200/200 before my first query** (I tried; it refused), and **WebFetch is egress-blocked for every football media domain** (fantasypros.com returned `EGRESS_BLOCKED` on a live attempt). So I did not use search summaries at all.
>
> Instead I pulled the **authoritative machine-readable layer**, which does resolve, and checked every claim against it myself:
> - **`nflverse-data` `draft_picks.csv`** — all **257 picks** of the 2026 draft, sourced from Pro-Football-Reference. Every name / position / college / team / round / pick below is read directly out of this file.
> - **`nflverse-data` `depth_charts_2026.csv`** — 155 daily ESPN depth-chart snapshots, **latest = 2026-08-22T07:26:29Z (this morning)**. I re-downloaded it at 16:39 UTC today to confirm that is the newest snapshot.
> - **`roster_2026.csv`** — Week 1 rosters with `status` and `draft_number`.
> - **DynastyProcess `db_fpecr_latest.csv`** — FantasyPros Expert Consensus Rankings, **scraped 2026-08-21 (yesterday)**.
> - **2006–2025 weekly player stats** — I computed the historical base rates myself, in *your exact scoring*, rather than quoting anyone.
>
> **The one gap:** I have **no live ADP**. FantasyPros/ESPN/Sleeper/Underdog are all blocked. My price column is **ECR (expert consensus), not ADP.** For hyped rookies, real draft-room ADP typically runs **half a round to a full round ahead of ECR**. Adjust upward accordingly, and treat my "walk-away price" as the hard line.
>
> **Two errors in the material I was handed, which I caught and corrected — both change the board:**
> 1. The WR report (and the fact-check that blessed it) claims **"Cleveland threw 398 times in 2025, dead last in the NFL."** **That is false.** I recomputed it: **Cleveland threw 558 times (15th)** — Shedeur Sanders 212 + Dillon Gabriel 185 + Joe Flacco 160 + 1. The actual league low is **Baltimore at 422.** The "Concepcion and Boston have a role but no volume" thesis was built on a fabricated number.
> 2. Every prior report used a **blended Round-1 base rate** for rookie WRs (~44%). Split by pick range, **top-10 WRs hit at 60%**, picks 11–32 at 31.5%. That is a large upgrade for Tate and Tyson and a large downgrade for Lemon, Concepcion and Cooper.
>
> Everything else the fact-check flagged, I independently re-confirmed: **Price has been Seattle's RB2 in every snapshot since April 24** (Charbonnet is RB1); **Love has been Arizona's RB1 in every snapshot since April 24** (the "Allgeier is out-carrying him" claim has zero support in the data); **Kenyon Sadiq is the Round 1 TE** all four reports missed.

---

# 1. THE 2026 ROOKIE BOARD

All 60 drafted 2026 skill-position rookies who appear in the consensus rankings, sorted by price. **Draft round is computed from ECR ordinal**, assuming you burn rounds 12–13 on K + D/ST — so **rounds 1–11 are your only offensive picks** (132 picks in a 12-team, 110 in a 10-team). "UD" = falls outside your draftable range at consensus price.

### Draftable at consensus price

| # | Player | Pos | NFL Team | 2026 Capital | ECR (ordinal) | Depth chart today | 12-tm round | 10-tm round | Walk-away price |
|---|---|---|---|---|---|---|---|---|---|
| **1** | **Jeremiyah Love** | RB | **ARI** | **R1, #3** | 40.2 (40th) | **RB1** — every snapshot since 4/24 | **Rd 4** | **Rd 4** | Do not pay before **Rd 3** |
| **2** | **Carnell Tate** | WR | **TEN** | **R1, #4** | 66.9 (65th) | **WR1** — every snapshot since 4/24 | **Rd 6** | **Rd 7** | Do not pay before **Rd 5** |
| **3** | **Jordyn Tyson** | WR | **NO** | **R1, #8** | 124.5 (126th) | WR2 — every snapshot since 4/24 | **Rd 11** | UD (Rd 13 dart) | Do not pay before **Rd 9** |
| 4 | Jadarian Price | RB | **SEA** | R1, #32 | 74.4 (70th) | **RB2** — never once RB1 | Rd 6 → **fade** | Rd 7 → **fade** | Do not pay before **Rd 9** |
| 5 | Makai Lemon | WR | **PHI** | R1, #20 | 106.6 (107th) | WR3 (slipped WR2→WR3 on 8/11) | Rd 9 → **fade** | Rd 11 → **fade** | Do not pay before **Rd 11** |
| 6 | KC Concepcion | WR | **CLE** | R1, #24 | 122.1 (123rd) | WR2 (rose WR3→WR2 on 4/26) | Rd 11 | UD | Fine at Rd 11, never earlier |

### Off your board at consensus price — waiver-watch list only

| Player | Pos | Team | Capital | ECR ord. | Depth chart | Why he's off |
|---|---|---|---|---|---|---|
| De'Zhaun Stribling | WR | SF | R2, #33 | 143rd | WR4 | Buried behind Evans / Deebo / Kirk / Kittle / CMC |
| Denzel Boston | WR | CLE | R2, #39 | 146th | WR3 | Splits a Watson-led pie with Concepcion |
| Jonah Coleman | RB | DEN | R4, #108 | 153rd | **RB3** | Behind Dobbins + RJ Harvey. **Already priced as nothing — the "fade the hype" advice you were given targets a price that does not exist** |
| Omar Cooper Jr. | WR | NYJ | R1, #30 | 172nd | WR3 | Geno Smith, behind Garrett Wilson + Adonai Mitchell |
| Emmett Johnson | RB | KC | R5, #161 | 191st | RB3 (**fell RB2→RB3 on 8/13**) | Kenneth Walker III is KC's RB1 |
| **Mike Washington Jr.** | RB | **LV** | R4, #122 | 200th | **RB2** | **The Ashton Jeanty handcuff.** Free |
| Nicholas Singleton | RB | TEN | R5, #165 | 209th | RB3 | Behind Pollard + Spears |
| **Kenyon Sadiq** | TE | **NYJ** | **R1, #16** | 225th | **TE1** — every snapshot since 4/24 | **The R1 TE everyone missed.** R1 capital + TE1 role at a free price. Best pure waiver watch in the class |
| Caleb Douglas | WR | MIA | R3, #75 | 229th | WR3 (rose 8/12) | Malik Willis / Quinn Ewers at QB |
| Zachariah Branch | WR | ATL | R3, #79 | 230th | WR4 | Behind London + Dotson |
| Antonio Williams | WR | WAS | R3, #71 | 235th | WR4 | Diggs signing buried him |
| Kaytron Allen | RB | WAS | R6, #187 | 236th | RB3 | Behind Croskey-Merritt + Rachaad White |
| Germie Bernard | WR | PIT | R2, #47 | 238th | WR4 | Metcalf + Pittman ahead |
| Demond Claiborne | RB | MIN | R6, #198 | 248th | RB3 | Behind Aaron Jones + Jordan Mason |
| Malachi Fields | WR | NYG | R3, #74 | 249th | WR5 | Fell to WR5 in July, never recovered |
| Ja'Kobi Lane | WR | BAL | R3, #80 | 251st | WR3 (rose 8/13) | Baltimore threw **422** times — actual league low |
| **Kaelon Black** | RB | **SF** | R3, #90 | 258th | **RB2 — promoted 8/20, two days ago** | **The Christian McCaffrey handcuff.** Free. See §5 |
| Fernando Mendoza | QB | LV | **R1, #1** | 266th | **QB2 behind Kirk Cousins** | The #1 overall pick is a backup |
| Eli Stowers | TE | PHI | R2, #54 | 302nd | TE2 behind Goedert | — |
| Adam Randall | RB | BAL | R5, #174 | 320th | RB4 | — |
| Seth McGowan | RB | IND | R7, #237 | 317th | RB3 | — |
| Brenen Thompson | WR | LAC | R4, #105 | 378th | **Reserve list (`RES`)** | **Not active. Do not draft under any circumstance** |
| Carson Beck (QB, ARI, R3 #65), Ty Simpson (QB, LAR, R1 #13), Cade Klubnik (QB, NYJ, R4 #110) | QB | — | — | 391st / 455th / 472nd | QB3 / QB3 / QB2 | None is a Week 1 starter |
| All remaining Rd 3–7 WRs and every rookie TE not named Sadiq | — | — | — | 300th+ | — | Below replacement |

---

# 2. TIERS

### TIER A — Draft with confidence
- **Jeremiyah Love (RB, ARI, R1 #3) — Rd 4.** The only rookie in this class who belongs on a real draft board. Pick-3 RBs are the **single strongest predictive bucket in fantasy football**: 2006–2025, top-10 rookie RBs finished top-24 in **9 of 12 cases (75%)** and **top-12 in 8 of 12 (67%)** — with Trent Richardson's 2012 dropped by a data join, the true rate is closer to 10/12. He has been RB1 in **all 119 ESPN snapshots since April 24, without a single day of demotion**. The room behind him is thin in reality, not just on paper: Tyler Allgeier was a backup (143 carries), **James Conner played 3 games in 2025** and turns 31, Trey Benson played 4. Arizona threw a league-high 649 times in 2025 with Kyler Murray — **Murray is now in Minnesota and Jacoby Brissett is QB1**, which points the offense toward the run. That is Love's volume.
- **Carnell Tate (WR, TEN, R1 #4) — Rd 6 (12-tm) / Rd 7 (10-tm).** The prior reports undersold him with a blended base rate. Correctly split, **top-10 rookie WRs hit top-36 60% of the time and top-24 36%** (n=25). Tate has been **WR1 in all 120 snapshots since April 24 — never moved**. Tennessee threw 570 times (12th), Cam Ward is a 2nd-year starter, and Tate is an X, not a slot — the archetype half-PPR does *not* tax. Real caveat, honestly stated: **Wan'Dale Robinson is now Tennessee's WR2 and drew 140 targets in 2025.** "No alpha in the room" is no longer true. Tate is a WR3/FLEX with WR2 upside, not a league-winner-by-default.

### TIER B — Draft only at a discount
- **Jordyn Tyson (WR, NO, R1 #8) — Rd 11 (12-tm).** He belongs here because he is **the cheapest top-10 draft-capital WR on the board and the market has mispriced him relative to Lemon.** Compare: Tyson went #8 (60% bucket), is depth-chart **WR2** since day one, and plays in an offense that threw **591 times (6th)**. Lemon went #20 (31.5% bucket), is **WR3**, slipped on Aug 11, and plays in a 497-attempt run-first offense — and costs **two rounds more**. Tyson is the better player at the lower price. The real cap: Chris Olave commanded 156 targets and Juwan Johnson 102, and Tyler Shough is the QB. Take him in Rd 11; take him in Rd 12–13 in a 10-teamer if he's somehow there.
- **KC Concepcion (WR, CLE, R1 #24) — Rd 11, and only in a 12-teamer.** Upgraded from the material you were handed, because **the "Cleveland threw 398 times, dead last" claim is factually wrong — they threw 558, 15th in the league.** He rose to WR2 on April 26 and has held it four months. Pick-24 capital puts him in the 31.5% bucket, and Deshaun Watson is a genuine drag. Fine as your last offensive pick. Never earlier.

### TIER C — Late dart-throw only (i.e., you will not draft them in this format)
Every one of these is a **Week-1 waiver add, not a pick**, because they fall past your last offensive pick at consensus price:
- **Kaelon Black (RB, SF)** and **Mike Washington Jr. (RB, LV)** — the two most valuable free assets in the class (see §5).
- **Kenyon Sadiq (TE, NYJ)** — R1 capital, TE1 since April, ECR 225. If you end up streaming TE, he is the first name on the watch list.
- Denzel Boston, De'Zhaun Stribling, Omar Cooper Jr., Ja'Kobi Lane, Caleb Douglas, Nicholas Singleton, Kaytron Allen.

### TIER D — Avoid entirely in redraft
- **Every rookie QB.** Mendoza (#1 overall) is **QB2 behind Kirk Cousins**; Simpson, Beck and Klubnik are QB2/QB3. My computed rate: R1 rookie QBs hit top-12 **14.8%** of the time (9/61), R2 **0 for 22**, R4–7 **1 of 123**. And in a 1-QB league with 1-day unlimited waivers, "top-12 QB" *is* the streaming baseline — the successful outcome returns nothing.
- **Every rookie TE except as a free waiver watch.** My computed rates: R1 TEs **31.6%** top-12, R2 **7.9%**, R3 **2.1%**, **R4–7 = 0 for 184**. Nine TEs went in rounds 1–3 of this class; only Sadiq is even a TE1, and he's ECR 225.
- **Jadarian Price at his current price.** This is the sharpest fade on the board. He is priced at ECR 74 (Rd 6–7) — a *starter's* price — for a player who has been **RB2 behind Zach Charbonnet in all 119 snapshots since April 24 and has never once been listed RB1**. Late-R1 RBs (picks 11–32) hit top-24 only **40%**, and that's for guys who win the job. You are paying Rd 6 for the Seattle handcuff.
- **Makai Lemon at his current price.** WR3 on a 497-attempt run-first offense, *falling* (WR2→WR3 on Aug 11), pick-20 capital, and a slot role — the exact archetype half-PPR punishes.
- **Jonah Coleman.** RB3 in Denver behind Dobbins and RJ Harvey. Already free; no action required.
- **Brenen Thompson (LAC)** — on the **Reserve list**, not active.

---

# 3. THE SHALLOW-BENCH RULE

## Answer: end the draft with **exactly 1 rookie**. Two is the absolute ceiling, and only if Love AND Tate both fall to you at or past their ECR. **Zero speculative rookie stashes — not one.**

Here is the arithmetic that forces it.

**Your bench is 56 player-weeks, total.** 4 spots × 14 regular-season weeks. That is the entire inventory you have for byes, injuries, streaming and upside — for the whole year.

**Your waiver wire is not a bench substitute — it is strictly better than your bench.** Unlimited acquisitions, 1-day period, no FAAB. Replacement level regenerates every single day at zero cost.

**And the hit announces itself early.** I computed this from every R1/R2 rookie RB and WR, 2006–2025, in your exact scoring:

| Rookie status through Week 7 | Finished as a positional starter |
|---|---|
| RB **inside** top-40 (n=47) | **31 → 66.0%** |
| RB **outside** top-40 (n=39) | **3 → 7.7%** |
| WR **inside** top-60 (n=64) | **43 → 67.2%** |
| WR **outside** top-60 (n=108) | **6 → 5.6%** |

**A rookie who has not shown up by Week 7 hits about 6–8% of the time.** You do not need to pre-buy that. You can watch it happen for free and claim it in Week 4.

**Now price the bench spot.** With 4 playoff teams:

| | 12-team (P=33%) | 10-team (P=40%) |
|---|---|---|
| Week-1 contributor | 15.3 effective weeks | 15.6 |
| Week-10 breakout | 6.3 → **41% of face value** | 6.6 → **42%** |
| Playoff-only breakout | 1.3 → **9%** | 1.6 → **10%** |

Multiply it out: **a speculative rookie stash is worth 7.7% × 0.42 ≈ 3.2% of a season-long RB2** (2.4% for a WR). Streaming that same spot — rotating the best available FLEX/TE matchup weekly — returns 1.5–3 points a week over replacement, realized nearly every week: **21–42 points, versus roughly 4.** That is a 5–10× gap, and it is not close.

**Roster construction that follows:**
- Rounds 1–11 = 11 offensive players for 7 offensive starting slots + 4 bench.
- **Every one of those 11 must be someone you would plausibly start.** There is no stash budget.
- Bench should be: 1–2 genuinely startable FLEX bodies, **1 direct handcuff to an RB you actually roster**, and at most 1 upside swing — and that swing should be a veteran with a defined role, not a rookie with a projected one.
- **Cut discipline:** if the one rookie you drafted is not producing by Week 6, cut him. A Week-10 breakout is worth 41% of face value; holding a non-contributor past midseason on a 4-man bench is indefensible.

**The one honest counterweight:** your waiver order **resets by inverse standings, not FAAB**, so a winning team picks last every week. The mid-season backfield inheritance is exactly the asset a first-place team cannot claim. That is a real argument — and it is why the answer is "draft Love," not "draft nobody." But it argues for **one** rookie, not two, and it argues for that rookie being an **RB**, because RB is the only position where one injury converts a bench body into an every-week starter inside a single week. Mitigation for everything else: with a 1-day period and unlimited moves, most breakouts clear waivers and become first-come-first-served. Monitor daily.

---

# 4. BEST-BALL vs WIN-NOW — and who is "too slow to matter"

**First, the good news: the rookie "slow start" is much smaller than folklore claims.** Across every R1/R2 rookie RB and WR, 2006–2025, I measured per-week scoring:

- Weeks 1–7: **5.63 pts/week**
- Weeks 8–14: **6.24 pts/week**
- Weeks 15–17: **6.28 pts/week**
- **Ratio: 1.107×.** Rookies improve about **11%** in the second half. That is a real effect, and it is *small*. It is not "nothing until Week 8, then explosion."

**But the 11% ramp is not the issue. The issue is that only 4 of 10–12 teams make your playoffs.** Weeks 1–7 are half your regular season. In a 12-team league you have a 33% shot at a four-team field with a points-for tiebreaker — you cannot spot the field seven weeks of a dead roster spot and expect to be one of the four. **A Week-10 breakout is worth 41% of a Week-1 contributor. A playoff-week breakout is worth 9%,** because six times out of ten you never get to start him. And 2-week playoff matchups *reduce* variance, which further rewards the objectively better roster over the volatile one.

**Adjusted board for win-now:**

| Rookie | Adjustment | Why |
|---|---|---|
| **Jeremiyah Love** | **No discount. Full price.** | RB1 since April 24, no committee threat visible in 119 snapshots. He is a Week-1 contributor, not a rookie bet. |
| **Carnell Tate** | **No discount.** | WR1 since April 24. Week-1 starter with real volume. |
| **Jordyn Tyson** | **Small discount** (already priced in) | WR2 behind a 156-target alpha. Immediate FLEX-adjacent role, real weekly floor. |
| KC Concepcion | Small discount | WR2, will play Week 1, ceiling capped by Watson. |
| **Jadarian Price** | **Heavy discount — 2+ rounds** | **Too slow to matter.** His entire case requires Charbonnet to fail or get hurt. That is a Week-6-to-10 event. Paying Rd 6 for a 41%-value outcome is the single worst allocation on this board. |
| Makai Lemon | Heavy discount | WR3 and falling. Needs a target-share change that has not happened in four months of camp. |

### "Too slow to matter" — the explicit list
These rookies' realistic paths all require a **mid-season role change**, which caps them at ~41% of face value in your format. Do not draft any of them; watch them on the wire:

**Jadarian Price** (needs Charbonnet to fail) · **Kaelon Black** (needs a McCaffrey injury) · **Mike Washington Jr.** (needs a Jeanty injury) · **Jonah Coleman** (RB3, needs two things to go wrong) · **Emmett Johnson** (falling, behind K. Walker) · **Kaytron Allen, Nicholas Singleton, Demond Claiborne, Seth McGowan, Adam Randall** (all RB3+) · **Denzel Boston, Omar Cooper Jr., De'Zhaun Stribling, Ja'Kobi Lane, Caleb Douglas, Germie Bernard, Zachariah Branch, Antonio Williams, Malachi Fields** (all WR3+, and rookie WR ramps are gradual, meaning you can watch them develop and claim in time) · **Kenyon Sadiq and every other rookie TE** (rookie TE is the slowest ramp in football) · **every rookie QB**.

**The best-ball inversion, stated plainly:** in a best-ball or 8-bench redraft league, Price at Rd 7 and Sadiq as a free TE dart are perfectly reasonable — you hold them for free and bank the late spike weeks. **In a 4-bench, 4-playoff-spot, points-for-tiebreaker league they are actively bad**, because you must pay in weekly roster space for a payoff you will only collect a third of the time.

---

# 5. THREE MOST LIKELY TO WIN A LEAGUE / THREE MOST LIKELY TO BE WASTED

### Most likely to win you the league

**1. Jeremiyah Love (RB, ARI, R1 #3) — Rd 4.** He is priced as **RB14** and sits in the bucket that produced a **top-12 RB two-thirds of the time (8 of 12 since 2006).** That is the best price-to-base-rate gap on the entire draft board, not just among rookies. Everything that would break the thesis is absent from the data: he has never been demoted, the incumbents are a career backup and a 31-year-old who played three games, and Arizona's QB downgrade from Kyler Murray to Jacoby Brissett points volume at the run game. If he returns RB6, you paid Rd 4 for the difference between 286 and 219 points — that is a league.

**2. Carnell Tate (WR, TEN, R1 #4) — Rd 6.** Top-10 rookie WRs hit top-24 **36%** of the time. He is the WR1 on a 570-attempt offense, has never moved off that line in four months, and is a boundary X — the profile half-PPR *rewards*. At Rd 6 you need him to be WR30 to break even; his realistic ceiling is WR12–15.

**3. Jordyn Tyson (WR, NO, R1 #8) — Rd 11.** The best surplus-value pick in the class. Same 60%/36% draft-capital bucket as Tate, locked WR2 since April, on the 6th-highest-volume passing offense in football — for **five rounds less than Tate and two rounds less than Price.** The market is paying for depth-chart slot instead of draft capital, and it has it backwards.

> **Free bonus, and I want this on the record even though it is not a draft pick: Kaelon Black (RB, SF, R3 #90) is the most valuable un-drafted asset in this class.** He was **promoted to RB2 behind Christian McCaffrey on 2026-08-20 — two days ago.** McCaffrey is entering his age-30 season off **311 carries and 129 targets (366 half-PPR points, RB1 overall)**. If McCaffrey misses time, whoever holds Black inherits the single highest-value backfield role in football. At ECR 258 he costs nothing. **Add him in Week 1 off free agency, not with a draft pick.** Same logic, one notch down: **Mike Washington Jr. (LV, R4 #122), RB2 behind Ashton Jeanty (266 carries).**

### Most likely to be a wasted pick

**1. Jadarian Price (RB, SEA, R1 #32) — ECR 74, Rd 6–7.** The worst cost-to-role mismatch on the board. **119 straight snapshots at RB2.** Zach Charbonnet is RB1 and took 184 carries for 171 points in 2025 as the *complement*. Yes, Kenneth Walker III left for Kansas City and that volume is genuinely vacated — but **Charbonnet, not Price, is sitting in it**, and the market has already paid a starter's price for Price anyway. You are spending a Round 6 pick on a handcuff. Everything the RB report told you about him being "the top value target in the class" was built on a depth chart nobody checked.

**2. Makai Lemon (WR, PHI, R1 #20) — ECR 107, Rd 9.** Pick-20 capital (31.5% bucket), **WR3 and falling** (demoted Aug 11), a slot role in a league that pays 0.5/reception, and the **24th-highest pass volume in the NFL (497)** attached to a Saquon Barkley run game. You are paying Round 9 for a WR5 who needs two players ahead of him to disappear.

**3. Any rookie TE or rookie QB — but if you insist on a name, Omar Cooper Jr. (WR, NYJ, R1 #30), ECR 172.** He is the archetype that kills you in this format: **the Round-8-to-11 rookie you are "supposed to be patient with."** R1 name recognition will pull his ADP well above his ECR in a live room. He is WR3 behind Garrett Wilson and Adonai Mitchell, in a slot role, with Geno Smith throwing. Patience is bought with bench spots, and you have four.

---

# 6. VERIFIED-FACTS APPENDIX

**Source of truth:** `nflverse-data/draft_picks.csv` (Pro-Football-Reference-sourced, all 257 picks of the 2026 draft) + `depth_charts_2026.csv` (ESPN, snapshot **2026-08-22T07:26:29Z**) + `roster_2026.csv` + FantasyPros ECR (**scraped 2026-08-21**). Read the exact spelling and team at your draft — this is what will actually be on the ESPN board.

### 2026 Round 1 — complete and verified, pick for pick

| # | Team | Player | Pos | College |
|---|---|---|---|---|
| 1 | LV | Fernando Mendoza | QB | Indiana |
| 2 | NYJ | David Bailey | OLB | Texas Tech |
| **3** | **ARI** | **Jeremiyah Love** | **RB** | Notre Dame |
| **4** | **TEN** | **Carnell Tate** | **WR** | Ohio St. |
| 5 | NYG | Arvell Reese | LB | Ohio St. |
| 6 | KC | Mansoor Delane | CB | LSU |
| 7 | WAS | Sonny Styles | LB | Ohio St. |
| **8** | **NO** | **Jordyn Tyson** | **WR** | Arizona St. |
| 9 | CLE | Spencer Fano | OT | Utah |
| 10 | NYG | Francis Mauigoa | OT | Miami (FL) |
| 11 | DAL | Caleb Downs | S | Ohio St. |
| 12 | MIA | Kadyn Proctor | OT | Alabama |
| 13 | LAR | Ty Simpson | QB | Alabama |
| 14 | BAL | Olaivavega Ioane | OG | Penn St. |
| 15 | TB | Rueben Bain Jr. | DE | Miami (FL) |
| **16** | **NYJ** | **Kenyon Sadiq** | **TE** | Oregon |
| 17 | DET | Blake Miller | OT | Clemson |
| 18 | MIN | Caleb Banks | DT | Florida |
| 19 | CAR | Monroe Freeling | OT | Georgia |
| **20** | **PHI** | **Makai Lemon** | **WR** | USC |
| 21 | PIT | Max Iheanachor | OT | Arizona St. |
| 22 | LAC | Akheem Mesidor | DE | Miami (FL) |
| 23 | DAL | Malachi Lawrence | DE | Central Florida |
| **24** | **CLE** | **KC Concepcion** | **WR** | Texas A&M |
| 25 | CHI | Dillon Thieneman | S | Oregon |
| 26 | HOU | Keylan Rutledge | G | Georgia Tech |
| 27 | MIA | Chris Johnson | CB | San Diego St. |
| 28 | NE | Caleb Lomu | OT | Utah |
| 29 | KC | Peter Woods | DT | Clemson |
| **30** | **NYJ** | **Omar Cooper Jr.** | **WR** | Indiana |
| 31 | TEN | Keldric Faulk | DE | Auburn |
| **32** | **SEA** | **Jadarian Price** | **RB** | Notre Dame |

### Every RB drafted in 2026 — complete (13 including one FB)
Love (ARI, R1 #3) · Price (SEA, R1 #32) · **Kaelon Black** (SF, R3 #90) · **Jonah Coleman** (DEN, R4 #108) · **Mike Washington Jr.** (LV, R4 #122) · **Emmett Johnson** (KC, R5 #161) · **Nicholas Singleton** (TEN, R5 #165) · **Adam Randall** (BAL, R5 #174) · **Kaytron Allen** (WAS, R6 #187) · **Demond Claiborne** (MIN, R6 #198) · **Eli Heidenreich** (PIT, R7 #230 — listed **FB**) · **Seth McGowan** (IND, R7 #237) · **Jam Miller** (NE, R7 #245).

### Every TE drafted in rounds 1–3 — complete
Sadiq (NYJ #16) · Eli Stowers (PHI #54) · Nate Boerkircher (JAX #56) · Marlin Klein (HOU #59) · Max Klare (LAR #61) · Sam Roush (CHI #69) · Oscar Delp (NO #73) · Will Kacmarek (MIA #87) · Eli Raridon (NE #95).

### Every 2026 rookie who is a depth-chart **#1 or #2** at a skill position today
**RB1:** Jeremiyah Love (ARI). **WR1:** Carnell Tate (TEN). **TE1:** Kenyon Sadiq (NYJ). **QB1:** none.
**#2s:** Jordyn Tyson (WR2 NO), KC Concepcion (WR2 CLE), Jadarian Price (RB2 SEA), Kaelon Black (RB2 SF), Mike Washington Jr. (RB2 LV), Fernando Mendoza (QB2 LV), Cade Klubnik (QB2 NYJ), Eli Stowers (TE2 PHI), Nate Boerkircher (TE2 JAX), Will Kacmarek (TE2 MIA), Eli Raridon (TE2 NE).
**That is the whole list. Any 2026 rookie not named above is a #3 or worse on his own depth chart.**

### Class-shape facts — all independently confirmed
257 total picks · **36 WRs** drafted (position high) · **12 RBs + 1 FB** · 22 TEs · 10 QBs · **only 2 RBs in Round 1** and **only 3 RBs inside the top 100** (Love #3, Price #32, Black #90) · **5 WRs in Round 1** · 1 TE in Round 1 · 9 TEs in rounds 1–3 · Ohio State went Tate #4, Reese #5, Styles #7, Downs #11.

### 🚩 NOT VERIFIED — read these warnings before you act on anything you hear today

1. **ADP is not verified.** Every number in my price column is **FantasyPros ECR (2026-08-21)**, not ADP. FantasyPros, ESPN, Sleeper and Underdog are all egress-blocked to me and WebSearch was capped at 200/200 before my first query. **Real ADP for rookies typically runs half a round to a full round ahead of ECR.** Use my walk-away prices as the hard line.
2. **Jeremiyah Love's reported preseason ankle injury is UNVERIFIED.** No 2026 preseason game data, injury report, or snap counts exist in any source I can reach. Counter-evidence: he is `status=ACT` on the Week 1 roster and **RB1 on this morning's depth chart**. **This is your single highest-value manual check before 2:00 PM** — open the Cardinals' injury report or any Arizona beat feed and confirm his practice status. If he is limited or out, drop him to a Round 6 price.
3. **Every beat-writer quote and camp report in the material you were given is UNCORROBORATED** — "8 days of camp," the "Allgeier majority of first-team carries" claim (contradicted by 119 straight snapshots), the Titans' "clear guy for us," "biggest steal of the draft" pieces on Coleman, Love's "$53M guaranteed" contract, Kenneth Walker III as "Super Bowl LX MVP." None of it is reachable. Treat all camp narrative as unsourced.
4. **"Cleveland threw 398 times in 2025, dead last in the NFL" is FALSE.** I recomputed it from weekly stats: **Cleveland threw 558 (15th)**. The league low is Baltimore at 422. If anyone repeats the 398 figure today, it's wrong.
5. **NAME-COLLISION TRAP.** There is a real 2026 rookie named **Justin Jefferson — LB, Alabama, Cleveland, R5 #149.** The Vikings WR is unrelated and is still Minnesota's WR1. If any tool or board surfaces "Justin Jefferson, 2026 rookie," it is the linebacker.
6. **Two players who may confuse you:** the depth chart shows **Stefon Diggs as Washington's WR2** and **Keenan Allen as Indianapolis's WR3**, but neither appears in the Week 1 roster file — likely late signings. Treat their depth-chart placement as current but note the file disagreement.
7. **Brenen Thompson (WR, LAC, R4 #105) is on the Reserve list (`RES`)** — not active. Do not draft him under any circumstance.

---

## THE ONE-PARAGRAPH VERSION FOR 2:00 PM

Draft **Jeremiyah Love in Round 4** — confirm his ankle first. If **Carnell Tate** is there in **Round 6** (12-tm) or **Round 7** (10-tm), take him; do not reach into Round 5. If you want a third and you're in a 12-teamer, **Jordyn Tyson in Round 11** is the best surplus in the class and is two rounds cheaper than the market's preferred Lemon. **Stop there.** Fade Price, Lemon, Coleman and Cooper Jr. at their prices. Do not draft a rookie QB or a rookie TE. On Sunday of Week 1, put **Kaelon Black (SF), Mike Washington Jr. (LV) and Kenyon Sadiq (NYJ)** on your watch list and add them off free agency the moment anything moves — with unlimited 1-day waivers, that is strictly better than spending a pick on them today.