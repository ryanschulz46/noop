# Roster Construction for a 13-Man, 4-Bench League — 2026

## 0. Research-provenance note (read this first)

My own live `WebSearch` budget for this session was **already exhausted (200/200 calls)** by earlier agents in this workflow, and the egress proxy **blocks** fantasypros.com, espn.com, sleeper.com, reddit.com, pff.com, rotowire.com, nfl.com, 4for4, footballguys, establishtherun, numberfire, cbssports and pro-football-reference (403 policy denials — confirmed via `curl -sS "$HTTPS_PROXY/__agentproxy/status"`). I did **not** fabricate around this. Instead I used real 2026 data already on disk in this session's shared scratchpad:

| Source | Date | What it gave me |
|---|---|---|
| **nflverse-data `games.csv`** (github.com/nflverse/nflverse-data) | full 2026 REG schedule, 272 games | **The verified 2026 bye weeks** — computed, not remembered |
| **FantasyFootballCalculator half-PPR ADP** (`ffc_half_0818.csv`) | fetched **2026-08-19** | Live redraft ADP, 221 players incl. K/DST |
| **FantasyPros/DynastyProcess ECR** (`values.csv`) | scraped **2026-08-21** | Cross-check (⚠️ this file is **dynasty**, it contains rookie picks — I did *not* use it as redraft ADP) |
| **Harvested WebSearch corpus**, 111 result blocks | **2026-08-22** | Published strategy quotes (FantasyPros, PFF, Establish The Run, Yahoo, CBS) |
| **Yahoo/FantasyLife camp injury report** (`inj.json`) | retrieved **2026-08-15** | Current injury/PUP designations |
| nflverse weekly stats 2023–2025 | — | All scoring math run under **your exact rules** |

Everything below labelled with a number is computed from those files. Items I could not verify are marked **UNVERIFIED**.

---

## 1. The single most important number: **you only get 11 skill players**

This is the fact everything else falls out of, and most managers in your league will not have done this arithmetic.

- 13 roster spots. Two are permanently K and D/ST. → **11 skill players, total, for the whole draft.**
- 7 skill starting slots (QB, RB, RB, WR, WR, TE, FLEX). → **4 skill bench players.**
- Draft is **13 rounds**, not the usual 15–16.

**Consequence — the waiver pool is enormous on day one.** Computed against live FFC ADP:

| | Total picks | Skill players drafted | Last skill player taken | First skill player left on waivers |
|---|---|---|---|---|
| **10-team** | 130 | **110** | Jonathon Brooks (RB, ADP 108.9) | Jacory Croskey-Merritt (RB, 109.4) |
| **12-team** | 156 | **132** | Jalen McMillan (WR, 133.9) | Zach Charbonnet (RB, 134.2) |

A normal 12-team/16-round league consumes ~192 players. Yours consumes 132 skill players. **~60 players who would be rostered in a normal league are free agents here.** That single fact drives sections 4, 5, 6 and 7.

Positional composition of the drafted pool (12-team): RB 41, WR 61, QB 18, TE 12. So the **best free agent after the draft is roughly RB42 / WR62 / QB19 / TE13.**

---

## 2. Published strategy on shallow benches

From the harvested 2026-08-22 search corpus (these are summarised search results; the summariser did not always name the URL, so treat the attributions as publisher-level):

> "Shallow fantasy football leagues favor **stronger top-end starters, active waiver management, and benches built for short-term utility rather than long-shot stashes** that sit idle for weeks."

> "In a shallow format, it is easier to prioritize immediate production because **replacement options are more likely to appear later**... Because the benches are smaller, **the waiver wire will be much bigger**."

> "Rather than holding players just for depth, you can fill out your bench with **breakout candidates, rather than handcuffs at running back** or mid-tier, moderate-floor players."

> "**If you cannot envision a scenario where someone can come in and make an immediate impact if given a starting opportunity, they go back to the waiver wire.**"

This is consistent with what my simulations found independently. The one place I'll *diverge* from it is section 3 — the published advice frames the shallow bench as a bye-week problem, and the math says it mostly isn't.

**2026-specific archetype sourcing** from the same corpus:
- **Establish The Run (Adam Levitan):** "the big theme of this year's landscape is **running back thirst, with roughly 12 of the first 20 picks expected to be running backs**"; he "advocates strongly for a **barbell approach** at running back — spending a lot of draft capital on RBs early, then **spraying at ambiguous situations and one-injury-away guys late**."
- **PFF 2026 (10-team blueprint):** "a clear tier break emerges after the top group of running backs, making it **important to secure two early**, with roughly 12 or 13 of the first 22 picks being running backs."
- **PFF 2026 (hero-RB blueprint):** Gibbs is the top hero-RB target; "the primary advantage of a hero-RB build is that it allows you to **prioritize tight end and quarterback early, eliminating the need to spend additional draft capital on backups at either position**." ← *This line is the single most format-relevant sentence I found, for reasons in §7.*
- **FantasyPros robust-RB 2026:** RB in round 1 mandatory; "Chase Brown and Derrick Henry are excellent second-round ADP running back targets."

---

## 3. Bye-week math — and why the conventional worry is 98% wrong

### 3a. The verified 2026 bye schedule

Computed from the nflverse 2026 schedule (each of the 32 teams has exactly one bye; totals check out):

| Week | # teams | Teams |
|---|---|---|
| 5 | 2 | CAR, KC |
| 6 | 4 | CIN, DET, MIA, MIN |
| 7 | 4 | BUF, JAX, LAC, WAS |
| 8 | 4 | HOU, NO, NYG, SF |
| 9 | 2 | PIT, TEN |
| 10 | 4 | CHI, DEN, PHI, TB |
| **11** | **6** | **ATL, CLE, GB, LAR, NE, SEA** |
| **12** | **0** | *(all 32 teams play — no byes)* |
| 13 | 4 | BAL, IND, LV, NYJ |
| 14 | 2 | ARI, DAL |

Byes run **Week 5 → Week 14 only. Week 11 is the trap (6 teams). Week 12 is completely clean.**

### 3b. How many starters can share a bye before you're forced to stream?

I ran a bipartite lineup-matching simulation (40,000 seasons per shape) that checks, week by week, whether all 9 starting slots can be filled from your own 13 players. A "hole" = a starting slot you cannot fill.

**Result for the natural shape (QB1 / RB4 / WR5 / TE1 / D1 / K1): 4.09 hole-weeks per season. Decomposed:**

| Slot | Hole-weeks/season |
|---|---|
| QB | **1.00** (you have one QB; he has one bye) |
| TE | **1.00** |
| K | **1.00** |
| D/ST | **1.00** |
| RB+RB+WR+WR+FLEX (5 slots, 9 bodies) | **0.089** |

**→ 98% of your bye pain comes from the four singleton slots (QB/TE/K/D-ST). Your RB/WR corps almost never breaks: with 9 RB+WR bodies you have only an 8.2% chance of *ever* having an RB/WR/FLEX hole all season.**

Sensitivity on RB/WR body count (P(any hole all season)):

| Bodies | Shape | Hole-weeks | P(any hole) |
|---|---|---|---|
| **9** | RB4/WR5 | 0.087 | **8.1%** |
| 8 | RB4/WR4 | 0.186 | 16.3% |
| 8 | RB3/WR5 | 0.414 | 37.5% |
| 7 | RB4/WR3 | 0.637 | 51.9% |
| 7 | RB3/WR4 | 0.643 | 52.4% |

### 3c. The rules that actually follow

**RULE 1 — Get to 9 RB+WR bodies and stop worrying.** RB4/WR5 or RB5/WR4. Do **not** draft a marginal RB/WR "for bye coverage." It is already covered. Below 8 bodies (RB3/WR4 etc.) the failure rate jumps past 50% — that's the real cliff.

**RULE 2 — Your QB, TE, K and D/ST should sit on four *different* bye weeks.** You get 4 forced streams no matter what; spreading them means one transaction per week instead of three in one week, which is what actually breaks a lineup.

**RULE 3 — Grade the four forced streams by cost, not by count.**
- K bye → drop your K, add a K. **Cost ≈ 0.**
- D/ST bye → drop, add. **Cost ≈ 0.**
- QB bye → **cost ≈ 0 if you drafted a streaming-tier QB**; costs you a bench asset if you drafted Josh Allen (you can't drop Allen, so you must cut a bench RB/WR to hold a one-week QB).
- TE bye → same asymmetry with McBride/Bowers.
- **This is the hidden tax on elite QB + elite TE in this format**, and it is the thing nobody prices. It is small (§1 says the replacement you re-add is nearly as good as the guy you cut) but it is real.

**RULE 4 — Don't stack the top of your draft.** A bye-blind drafter has a **21.8%** chance that 3+ of his first six picks share one bye week, and a **6.5%** chance that 3+ share **Week 11** specifically. Week 11 holds **21 of the top-110 ADP skill players** — 18% of the pool.

Top-110 ADP players by bye week (counts): W5:7, W6:13, W7:16, W8:11, W9:7, W10:16, **W11:21**, W13:11, W14:8.

The Week 11 landmines: **Bijan Robinson (2.1), Puka Nacua (3.0), Jaxon Smith-Njigba (5.4), Drake London (12.1), A.J. Brown (19.4), Kyren Williams (27.2), Josh Jacobs (27.2), Davante Adams (37.4), Quinshon Judkins (51.7), Drake Maye (52.2), Christian Watson (56.4), TreVeyon Henderson (58.7), Rhamondre Stevenson (69.7), Matthew Stafford (78.2), Jadarian Price (78.6), Harold Fannin Jr. (80.8), Kyle Pitts (83.6), Jayden Reed (90.3), Tucker Kraft (93.9), Romeo Doubs (106.8), Matthew Golden (106.8).**

Practical version: **if your first two picks are both Week 11, actively break the tie toward a non-W11 player in rounds 3–5.** Don't reach — just use bye week as your tiebreaker inside a tier.

### 3d. ⚠️ The playoff wrinkle nobody will check

4 playoff teams × 2-week matchups = **4 playoff weeks**. Two configurations are possible and they have very different implications:

- **Scenario A (most likely): regular season W1–13, semis W14–15, final W16–17.** Then **Week 14 byes land inside your semifinal**: **ARI and DAL**. Affected: **CeeDee Lamb, George Pickens, Jeremiyah Love, Javonte Williams, Trey McBride, Marvin Harrison Jr., Dak Prescott, Michael Wilson** — plus **Brandon Aubrey (K, DAL)**. A two-week matchup halves their contribution in round one.
- **Scenario B: regular season W1–14, semis W15–16, final W17–18.** No byes in the playoffs at all, but **your championship includes Week 18**, when playoff-bound teams rest starters — a much worse problem.

**Action item before 2:00 PM: open your ESPN league settings and read the playoff week numbers.** If it's Scenario A, apply a modest fade to ARI/DAL players you'd be starting in the semis (mainly **Trey McBride** and **CeeDee Lamb**). If Scenario B, fade nothing for byes but prefer players on teams likely to still be playing for seeding in Week 18. Also note **Week 12 has zero byes** — a clean week in either configuration.

---

## 4. Which archetype? Zero-RB is the worst fit here.

### From first principles

Zero-RB has two engines. The shallow bench damages both:

1. **Engine 1 — hoard cheap RB darts and wait for one to hit.** You have 4 skill bench spots, and a Zero-RB team must *start* 2 RBs + often the FLEX from a group it deliberately bought late. With 11 skill players total you'd be at roughly RB4/WR5 — meaning only **two** RB darts on the bench, versus the 5–7 a real Zero-RB build carries. **This engine is largely disabled.**
2. **Engine 2 — capture the breakout RB off waivers.** This engine is *enhanced* by the huge free-agent pool (§1) — but it is **partially disabled by your waiver system**: priority resets weekly by **inverse standings**, so if Zero-RB is working and you're winning, you have the **worst** waiver priority every single week. The payoff mechanism is exactly the one a winning team can't reliably use via claims. (Mitigated, not eliminated — see §6.)

Meanwhile the FLEX + shallow bench means early RB capital gets *used*: a third good RB always has a home in your FLEX, whereas in a deep-bench league he'd rot.

### From simulation

I built a 13-round snake-draft sim (10- and 12-team, ADP-driven opponents with noise, players valued by mapping their ADP positional rank onto the **2025 actual points-per-game curve computed under your exact scoring**, byes modelled, injuries modelled at literature rates: P(miss ≥1 game) = RB 0.55 / WR 0.45 / TE 0.45 / QB 0.35, mean ~2.6 weeks). Score = mean weekly *starting-lineup* PPG.

**12-team, no injuries (420 drafts each):**

| Strategy | Lineup PPG | vs best |
|---|---|---|
| Robust-RB (RB,RB,RB early) | **93.51** | — |
| Hero-RB (RB1 then WR) | 93.07 | −0.44 |
| Hero-RB + elite QB + elite TE | 92.60 | −0.91 |
| Balanced + elite TE | 92.57 | −0.94 |
| Zero-RB | 91.55 | −1.96 |
| Balanced BPA | 91.25 | −2.26 |
| **RB-heavy, punt QB *and* TE to R10/R11** | **89.63** | **−3.88** |

10-team ordering was identical (Robust-RB 97.74, Hero-RB 97.19, Zero-RB 95.60, punt-both 94.04).

**Honest caveat, stated plainly:** this sim values every player at his ADP rank, so it *cannot* reward Zero-RB's actual thesis (that late RBs beat their ADP because injuries hand them volume). It is **structurally biased against Zero-RB**. What it *does* legitimately show is (a) the RB value curve is steeper than WR at the top under your scoring, and (b) **punting both QB and TE into rounds 10–11 is catastrophic (−3.9 PPG)** — that result is not ADP-biased, it's a direct read of the positional curves.

I also tested whether **bench size itself flips the ranking** (4 bench vs 7 bench, injuries on). It largely does not — deltas were ±0.5 PPG and inconsistent between 10- and 12-team, i.e. inside noise. **That is itself the finding: the 4-bench constraint changes how you spend picks 8–13 and how you manage the season far more than it changes picks 1–6.**

### Verdict

**Hero-RB / light-Robust-RB — "front-load the starters, then let the waiver wire be your bench."** Secure two of the top ~14 RBs if the board allows; take your RB1 in round 1 essentially always. **Zero-RB is the worst-fitting mainstream archetype in this specific league** and I'd avoid it outright. Pure Balanced-BPA underperformed too, mostly because it drifts into too many QBs/TEs.

---

## 5. Handcuffs and stashes

### 5a. Do not draft handcuffs. They are free.

This is the cleanest exploit in your league, and it falls straight out of §1. Every real handcuff sits **beyond your draft's cutoff**:

| Handcuff | ADP | 12-team (cutoff ~134) | 10-team (cutoff ~109) |
|---|---|---|---|
| Zach Charbonnet (SEA) | 134.2 | **free agent** | free agent |
| Woody Marks (HOU) | 145.9 | **free agent** | free agent |
| Tyrone Tracy Jr. (NYG) | 147.4 | **free agent** | free agent |
| Tyjae Spears (TEN) | 148.6 | **free agent** | free agent |
| Alvin Kamara (NO) | 149.7 | **free agent** | free agent |
| Ray Davis (BUF) | 150.7 | **free agent** | free agent |
| Keaton Mitchell (LAC) | 153.8 | **free agent** | free agent |
| Tank Bigsby (PHI) | 163.2 | **free agent** | free agent |
| Dylan Sampson (CLE) | 175.8 | **free agent** | free agent |
| Jordan James (SF), Trey Benson (ARI), Kimani Vidal (LAC) | outside FFC top-221 | **free agent** | free agent |
| Blake Corum (LAR) | 121.4 | drafted | **free agent** |
| Jordan Mason (MIN) | 115.9 | drafted | **free agent** |

Note this includes the exact names FantasyPros flagged as 2026's must-own handcuffs — *"the top priority handcuffs are Blake Corum, Jordan James, and Tank Bigsby"* — two of which are undrafted in both formats.

**The math:** a handcuff scores ~0 for you while the starter is healthy. My marginal-value curve (§5b) says your 4th bench spot is worth ~0.00 PPG anyway. So a handcuff isn't "cheap insurance" — it's **paying a real roster spot for a player you can add on a one-day waiver claim the moment the news breaks**, in a league where a 1-day waiver period means you'd have him for the very next game regardless.

**The one exception:** handcuffs with **standalone flex value** — those aren't handcuffs, they're just RBs, and you evaluate them normally. The corpus flags exactly this test: *"the key is to look for handcuffs that carry standalone value with a role even when the starter is healthy."* **Blake Corum** ("already has enough of a role to flex") is the 2026 archetype.

**Do not handcuff your own RB1** unless he is a genuinely brittle, genuinely irreplaceable workhorse *and* the backup is undisputed. Even then, prefer to wait: with unlimited transactions you can add him in week 1 if you still want him.

### 5b. The marginal value of each bench spot — the key quantitative result

BPA build, injuries + byes modelled, varying bench size:

**12-team:**

| Bench | Roster | Lineup PPG | Marginal gain |
|---|---|---|---|
| 0 | 9 | 87.35 | — |
| 1 | 10 | 88.21 | **+0.85** |
| 2 | 11 | 88.80 | **+0.59** |
| 3 | 12 | 89.26 | **+0.47** |
| **4** | **13 ← you** | **89.26** | **−0.00** |
| 5 | 14 | 89.21 | −0.05 |
| 6 | 15 | 89.10 | −0.11 |

**10-team:** +1.49 / +0.65 / +0.35 / **+0.20** for spots 1–4.

**Interpretation — this is the thesis of the whole league:** bench spots 1–3 buy real insurance. **Bench spot #4 is worth approximately nothing in expected starting-lineup points**, because the player occupying it barely outperforms the free agent you could add instead.

**→ Therefore bench spot #4 is a FREE OPTION. Its expected value is ~0 whatever you put in it, so buy the highest-variance thing on the board.** A league-winning dart, not a safety blanket. Concretely: an ambiguous-backfield RB, a rookie WR one injury from a target share, a QB-change beneficiary. Never a kicker, never a second D/ST, never a handcuff to a healthy bell-cow.

### 5c. Injured/suspended stashes — and the IR slot

**The IR slot is worth more in your league than in any normal one.** It is a **25% expansion of your bench** (4 → 5 effective). An IR-eligible player costs **zero** of your 13 active spots.

From the Aug 15 2026 Yahoo/FantasyLife camp report on disk:

| Player | ADP | Status | Verdict |
|---|---|---|---|
| **Jordyn Tyson (WR, NO)** | 97.4 | Hamstring ~2 months, *"likely opens on IR"* | **The premier IR stash.** If he's designated IR he is a free 14th roster spot with WR2 upside. |
| **George Kittle (TE, SF)** | 114.1 | Achilles, on PUP, *"out 4+ weeks if he stays on PUP"* | Viable IR stash; camp reports "ahead of schedule" cut both ways |
| **Tucker Kraft (TE, GB)** | 93.9 | ACL recovery, on PUP, *"has a shot at Week 1 but not a lock"* | Only if he lands on Reserve/PUP; too expensive otherwise |
| **Zach Charbonnet (RB, SEA)** | 134.2 | Knee, on PUP | Free agent anyway — don't draft |
| **Ricky Pearsall (SF), Chris Brazzell (CAR)** | — | **OUT FOR SEASON** | Do not draft. Not stashes; dead spots. |

**Rules:**
1. **Draft exactly one IR-eligible player, and only with your last skill pick (R11).** Not two — you only have one IR slot, and the second one eats a live bench spot.
2. **Verify the ESPN designation before you draft him.** ESPN's IR slot requires an official IR/PUP-regular-season status in *ESPN's* system. "Questionable" and "Doubtful" do **not** qualify. If your target isn't flagged IR-eligible in the ESPN app at 1:55 PM, he is a normal player occupying a normal bench spot — and at that point the pick is bad.
3. **Never stash a merely week-to-week player.** Emeka Egbuka (toe, *"availability genuinely uncertain — notable at his draft cost"*, ADP 37.5), Josh Jacobs (groin), Patrick Mahomes (knee), Chuba Hubbard (hamstring) are *not* IR-eligible — they'd sit on your 4-man bench producing zero. In a 4-bench league that is the worst possible outcome.
4. **Suspensions:** same logic — suspended players are generally **not** IR-eligible on ESPN. A suspended player is a live bench spot producing zero. Avoid.

---

## 6. Exploiting unlimited waivers + 1-day period + weekly-resetting inverse-standings priority

Three properties, three different exploits.

### 6a. Priority is a *perishable* good — spend it every single week

Unlike **FAAB** (a depleting season-long budget) and unlike **rolling/continual waivers** (where a successful claim drops you to last for the rest of the season), **weekly-resetting inverse-standings priority is recomputed from scratch every week from the standings.** Using your claim this week costs you **nothing** next week.

**→ There is never a reason to "save" your priority. If there is any positive-value player available, claim him.** Managers who instinctively hoard priority because they're used to FAAB or rolling waivers are simply leaving free options on the table every week. This is probably the most exploitable habit in your league.

### 6b. But winning destroys your waiver access — so draft to not need it

The flip side that most write-ups miss: **priority is inverse standings, reset weekly.** If you start 5–0, you are picking **10th or 12th on waivers every week, all season.** You cannot plan to "fix it on waivers" — success removes the tool.

**→ Roster-construction consequence: your *drafted* starting nine has to be able to win games on its own.** This is a second, independent argument (alongside §5b) for front-loading premium starters and against a bench full of speculative darts that need waiver reinforcement to pay off. It is also the strongest single argument against Zero-RB here.

### 6c. The 1-day waiver period converts most of the market to first-come free agency

A 1-day period is very short. Players clear waivers almost immediately and become **free agents — first-come, first-served, priority irrelevant.** So:

- **Speed beats priority for 80% of adds.** Set alerts. The Sunday-evening and Tuesday-morning windows are where a vigilant manager beats a high-priority one.
- **Save your actual *claim* for the one contested player** each week (the newly-anointed starting RB everyone wants) — and expect to lose that one while you're winning.
- **Because the pool is so deep (§1), you'll usually be fine.** The best free agent is ~RB42/WR62 on day one, and improves as roles clarify.

### 6d. Churn K and D/ST relentlessly — your D/ST scoring makes this unusually profitable

Your D/ST rules include a **yards-allowed** component, which is rare and severe. I computed the real distribution over 1,632 team-games (2023–2025):

| Yards allowed | Points | Frequency |
|---|---|---|
| <100 | +5 | 0.1% |
| 100–199 | +3 | 3.2% |
| 200–299 | +2 | 23.9% |
| 300–349 | 0 | 23.7% |
| 350–399 | −1 | 22.4% |
| 400–449 | −3 | 16.9% |
| 450–499 | −5 | 6.7% |
| 500–549 | −6 | 2.5% |
| 550+ | −7 | 0.7% |

- Median team-game = **348 yards** — right on the 0 / −1 boundary.
- **Mean yards-allowed score: −0.69/week.** Mean points-allowed score: **+0.22/week.**
- **Combined "allowed" baseline: −0.46 points per week *before* any sacks, turnovers or TDs.** Your D/ST must generate ~3–4 points of sacks and takeaways just to reach zero.
- Matchup spread on the yards component alone (2025, by offense faced): **3.47 points/week** between the best and worst matchup.

**→ D/ST is a pure streaming position in this league, and streaming it is worth real points.** Never draft one early — note **Seattle D/ST has an ADP of 82.2**, i.e. round 7 in a 12-team league. Someone in your draft will burn a top-100 pick on a defense in a 13-round draft. Let them; it's one of the largest single mistakes available.

**Kicker.** Your rules are 3/4/5/**5** with **−1 per miss** and **no extra credit for 60+**. So this scoring rewards *accuracy and volume*, not leg strength. I computed K scoring under your exact rules:

| | K1 | K3 | K6 | K12 | K1 − K12 |
|---|---|---|---|---|---|
| 2025 | 12.7 | 10.6 | 9.8 | 8.5 | **4.20 ppg (≈71 pts/season)** |
| 2024 | 11.1 | 10.4 | 9.5 | 8.3 | **2.81 ppg (≈48 pts/season)** |

Mild surprise worth acting on: **the top kickers repeated.** Brandon Aubrey (11.0 → 10.6), Ka'imi Fairbairn (10.4 → 12.7) and Cameron Dicker (10.4 → 9.8) were top-5 in **both** years under your rules. A ~3 PPG edge is not nothing. Since you are *forced* to spend a pick on a kicker anyway, **spend it on a good one** — 2026 K ADP: Aubrey 128.4, Jason Myers 132.8, Fairbairn 137.3, Chase McLaughlin 142.9, Dicker 143.3. (Harrison Mevis is listed at LAR at ADP 139.2 — **UNVERIFIED** team assignment.)

⚠️ **Do not plan to skip K or D/ST at the draft.** In a 12-team league, 12 kickers + 12 defenses = 24 players must come out of exactly 24 picks in rounds 12–13. You cannot gain a roster spot by punting them — you'd just have to drop two skill players before Week 1. Take them in R12 and R13, in that order or reversed depending on which run starts first.

---

## 7. Injury risk: how much to discount

### The data

2025 games played among top finishers, under your scoring:

| Cohort | Avg games | Played all 17 | Missed 3+ |
|---|---|---|---|
| Top-12 RB | 16.7 | 75% | 0% |
| Top-24 RB | 16.6 | 67% | 0% |
| Top-36 RB | 16.1 | 58% | 11% |
| Top-12 WR | 16.2 | 50% | 8% |
| Top-36 WR | 15.9 | 44% | 11% |
| Top-12 TE | 16.2 | 67% | 8% |
| Top-36 TE | 14.6 | 33% | 33% |
| Top-12 QB | 16.5 | 67% | 8% |
| Top-36 QB | 13.7 | 28% | 53% |

Corroborating literature from the corpus: *"NFL running backs have only a 27% chance of playing a full season"*; *"the average injury that causes a player to miss at least 1 game has a mean length of 3.1 games."* Note also the counterintuitive finding in that corpus: *"running backs with 300+ carries tend to play longer, suffer fewer concussions, and miss fewer games the following season compared to backs with 150–250 carries"* — i.e. **do not apply a workload-fear discount to true bell-cows.** That aligns with the top-12 RB row above (0% missed 3+ games).

### How much to discount

**Less than your instinct says, for a specific structural reason.** The cost of an injury = (points lost) − (points from the replacement you add). §1 says your replacement is unusually good here (best FA ≈ RB42/WR62), and §6 says you can add him within a day. **A shallow bench does not amplify injury cost to your *starters* — it amplifies the cost of *pre-paying* for injuries.**

So, concretely:

1. **Do NOT discount healthy elite players for "injury history."** Christian McCaffrey (ADP 6.8) is priced with his history; the replacement math is forgiving. Take the points.
2. **DO heavily discount players who are injured *right now* and are *not* IR-eligible.** These are the genuine landmines, because they occupy one of only four bench spots while scoring zero. From the Aug 15 report: **Emeka Egbuka** (toe, *"availability genuinely uncertain — notable at his draft cost"*, ADP 37.5) is the most dangerous name on the board at his price. Also **Kyle Monangai** (doubtful W1), **Kenyon Sadiq** (hernia setback, doubtful W1), **Chuba Hubbard**, **Josh Jacobs** (groin), **Patrick Mahomes** (knee), **Michael Pittman Jr.** (leg).
3. **Apply a modest positive adjustment to players whose *replacement* is already yours** — irrelevant here, since §5a says don't handcuff.
4. **Mildly upgrade "recovery on track" guys the market has already discounted.** **Malik Nabers** (ADP 27.7, ACL, *"practicing; reported ahead of expectations"*) — the ADP already prices the risk.
5. **Watch the two draft-day contract situations** from the Aug 5 notes: **Jahmyr Gibbs** ("back tightness... AND holding in over contract talks — watching practice, not participating"). If the hold-in is unresolved at 2:00 PM, **Bijan Robinson (ADP 2.1) is the cleaner 1.01.** Confirm before your pick.

**Rule of thumb:** discount a currently-injured, non-IR-eligible player by roughly **(expected weeks missed ÷ 17) × his value, plus a further ~15–20% penalty for the bench spot he sterilises.** In a 7-bench league you'd skip the second term. Here you can't.

---

## 8. Recommended end-of-draft roster shape

### Target (both formats)

**QB 1 · RB 4 · WR 5 · TE 1 · D/ST 1 · K 1 = 13** — with **RB 5 / WR 4** an equally good variant if the board pushes you that way.

Non-negotiables, from the math above:
- **RB + WR ≥ 9 bodies** (§3b: 8.1% failure at 9, 52% at 7).
- **Exactly 1 QB and exactly 1 TE.** A QB2 or TE2 drops you to 8 RB/WR bodies (16% failure) and buys you a bye week you can stream for free.
- **Exactly 1 K, exactly 1 D/ST**, taken in rounds 12–13 and churned all season.
- **Bench spot #4 = maximum variance** (§5b), ideally an **IR-eligible** body so it costs nothing.

### 12-team, 13 rounds (your picks: R1 #1–12 … R13 #145–156)

| Round | Plan |
|---|---|
| **1** | **RB.** Gibbs (1.5) / Bijan (2.1) — or if you pick 3–5, take the best of Nacua (3.0) / Chase (4.1) / JSN (5.4) / J. Taylor (5.8) / CMC (6.8). Don't overthink the top 8. |
| **2** | Best of RB/WR. From picks 13–24 the board is Henry (10.6), Achane (11.3), London (12.1), Lamb (12.6), Jefferson (14.0), Chase Brown (14.8), Jeanty (15.8), Rice (16.9), Barkley (17.9). **Aim to leave R2 with 1 RB + 1 WR, or 2 RB.** |
| **3** | Fill the other of RB/WR. Pickens (19.2), A.J. Brown (19.4), Nico Collins (21.5), K. Walker (22.1), Hampton (22.4), Olave (24.3). |
| **4** | **Elite TE window** — McBride (38.6) or Bowers (42.5). If both gone, skip TE entirely until R10+ and take WR/RB. Do **not** take TE3–TE6 here (§ VOR: TE1 +6.2 → TE3 +3.4 → TE5 +1.7). |
| **5–6** | **QB window.** Maye (52.2), Burrow (55.4), Lamar (56.2), Dak (66.4). **Allen at 31.5 is too expensive** in a format where QB1 is only +6.9 VOR. Take one QB here and never think about it again. Plus WR3. |
| **7–8** | RB3 and WR4. Real roles only — Judkins (51.7), Tuten (53.7), Montgomery (55.1), Henderson (58.7), Warren (62.3). |
| **9–10** | RB4 / WR5. Start weighting upside over floor. |
| **11** | **The free option.** Highest-variance dart on the board, or your **one IR stash** (Jordyn Tyson 97.4 if he's IR-designated — he'll likely be gone by here, so more realistically an ambiguous-backfield RB). |
| **12** | **D/ST** — pick on Weeks 1–3 matchup, not on name. |
| **13** | **K** — Aubrey / Myers / Fairbairn / Dicker tier. |

### 10-team, 13 rounds (picks R1 #1–10 … R13 #121–130)

Same shape, three adjustments:

1. **Replacement level is even higher** (best FA ≈ **RB37 / WR53 / QB15 / TE9**). Elite-onesie VOR shrinks accordingly: **TE1 +5.7, QB1 +6.0, TE12 is actually −0.4** — i.e. a mid-TE is literally worse than the free agent. **Lean harder into streaming QB and TE**; the elite-TE window in R4 is optional rather than valuable.
2. **Bench spot #4 is worth +0.20 PPG here vs −0.00 in 12-team** — marginally more real, but still the smallest thing on your board. Same conclusion: buy variance.
3. **More handcuffs are free** — Blake Corum (121.4), Jordan Mason (115.9), Croskey-Merritt (109.4), Kyle Monangai (114.7), Rachaad White (112.1) all go undrafted in a 10-team 13-rounder. Even less reason to draft depth.
4. Brandon Aubrey at ADP 128.4 falls right at pick 130 — you can have the K1 with your **last** pick.

### Positional maximums — ignore them

Your caps (QB 4, RB 8, WR 8, TE 3, D/ST 3, K 3) are all far above what 13 spots allow. They will never bind. The binding constraint is 13, and it binds hard.

---

## 9. Ten-second version

The bench isn't a bench — it's **four slots, of which the fourth is worth zero**. Byes are a **QB/TE/K/D-ST** problem, not an RB/WR problem. Handcuffs are **free on waivers**. Priority is **use-it-or-lose-it**, but **winning takes it away**, so your drafted nine must stand on its own. Front-load, take one QB and one TE, get to nine RB+WR bodies, spend your last pick on a lottery ticket, and churn K/D-ST every week.

---

## 10. Verification checklist before 2:00 PM

- [ ] **Playoff week numbers** in league settings (§3d) — Scenario A vs B changes ARI/DAL treatment.
- [ ] **League size** — 10 vs 12 shifts your waiver cutoff by 22 players.
- [ ] **Jahmyr Gibbs' hold-in/back status** — if unresolved, Bijan is the 1.01.
- [ ] **Emeka Egbuka's toe** — at ADP 37.5 he is the format's biggest landmine.
- [ ] **ESPN IR-eligibility flag** on your intended stash. No flag = don't draft him.
- [ ] ⚠️ **Travis Etienne Jr.'s 2026 team** — my ADP file (Aug 19) lists him at **NO**, but the Aug 22 search corpus says he "has strengthened his case to lead **Jacksonville's** backfield." **UNVERIFIED / conflicting.** Check before drafting him at ADP 42.8.
- [ ] Several other 2026 team assignments come only from the Aug 19 ADP feed and I could not independently confirm them: **Kenneth Walker→KC, A.J. Brown→NE, Jaylen Waddle→DEN, Mike Evans→SF, Davante Adams→LAR, Jordyn Tyson→NO, Carnell Tate→TEN, Michael Pittman→PIT, Stefon Diggs→WAS, Kyler Murray→MIN, Jadarian Price→SEA, Jeremiyah Love→ARI, Harrison Mevis→LAR, Tyreek Hill→FA.** Glance at the ESPN app's team labels during the draft.