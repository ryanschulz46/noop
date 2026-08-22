## READ FIRST — RESEARCH STATUS (HONEST DISCLOSURE)

**I could not perform ANY live web research.** Two independent hard failures:

1. **WebSearch budget was already exhausted** before my first query (200/200 used by this session). Every search returned "Web search was not performed: this session has used its web search budget."
2. **Every WebFetch target was blocked by the network egress proxy** (`EGRESS_BLOCKED`, organizational policy). I tried **15 domains**: fantasypros.com, pro-football-reference.com, espn.com, nfl.com, en.wikipedia.org, teamrankings.com, reddit.com, cbssports.com, sleeper.com, pff.com, 4for4.com, footballguys.com, draftsharks.com, rotowire.com, footballdb.com. All refused. `/root/.ccr/README.md` states policy denials must be reported, not worked around.

**Consequence, stated plainly: I have ZERO verified 2026 data.** No real 2026 kicker names/teams, no 2026 ADP, no 2026 rankings, no 2026 NFL schedule, no verified 2025 team yards-allowed table. **I have not fabricated any of them.**

**What this report is:** a complete, quantified analysis of *your specific scoring system*, derived entirely from the settings you supplied. That math is fully valid despite the blackout — and for K and D/ST, the scoring structure is where nearly all the edge lives, far more than player identity. Sections 0–4, 6, 7, 8, 10 are complete and immediately actionable. Sections 5 and 9 give you a **5-minute live-lookup checklist** to fill the data gap yourself before 2:00 PM. Anything from prior-season memory is tagged **UNVERIFIED**.

---

# 0. THE CONSTRAINT THAT OVERRIDES EVERYTHING

```
TOTAL ROSTER        13 active (+1 IR)
MANDATORY STARTERS   9  (QB, RB, RB, WR, WR, TE, FLEX, D/ST, K)
BENCH                4
```

Position maximums technically allow K 3 and D/ST 3. **Ignore that entirely.** The arithmetic:

- Draft 1 K + 1 D/ST → 4 bench spots for skill players. Correct.
- Draft 2 D/ST + 1 K → 3 bench spots. Already a mistake.
- Draft 2 K + 2 D/ST → **2 bench spots.** Season-ending error.

**HARD RULE: exactly ONE kicker, exactly ONE D/ST, both in the last two rounds.** This is the single highest-value instruction in this document. Every point of edge available from "the right kicker" (~2 pts/game, mostly unpredictable) is dwarfed by one bench WR hitting.

**A 13-man roster means a 13-round draft.** Because all 10 or 12 teams must fill a K and a D/ST slot, **rounds 12–13 will be a near-total K/DST run.** Practical consequence: **Round 11 is your LAST real skill-player pick.** Plan your draft board around that. Do not "wait one more round" on a bench flier in round 11 — there is no round 14.

Pick numbers:
- **10-team:** R11 = picks 101–110, R12 = 111–120, R13 = 121–130
- **12-team:** R11 = picks 121–132, R12 = 133–144, R13 = 145–156

**Order: D/ST in round 12, K in round 13.** D/ST has ~4x the weekly point spread of K and genuinely gets drafted (top units clear the board); kickers are near-interchangeable and 32 exist. Never reverse this.

---

# 1. KICKER SCORING — THE EV MATH (Question 1)

Your brackets: PAT 1 | 0–39 = **3** | 40–49 = **4** | 50–59 = **5** | 60+ = **5** | **Miss = −1**

### 1a. Expected value per attempt by distance

Using approximate modern NFL make rates (historically stable; **UNVERIFIED for 2026** but these move ~1pt/yr):

| Bucket | Approx FG% | Points if made | EV = p·pts − (1−p)·1 |
|---|---|---|---|
| 0–39 | ~95% | 3 | 0.95(3) − 0.05 = **+2.80** |
| **40–49** | ~83% | 4 | 0.83(4) − 0.17 = **+3.15** ← highest |
| 50–59 | ~66% | 5 | 0.66(5) − 0.34 = **+2.96** |
| 60+ | ~38% | 5 | 0.38(5) − 0.62 = **+1.28** ← worst |

### 1b. The counterintuitive headline: this is NOT a pure "big leg" format

Because **60+ pays the same 5 as 50–59**, the 60+ bucket is the *worst* attempt on the board — you take a ~62% chance of −1 for no incremental reward. A 62-yard attempt is worth **less than half** a 45-yard attempt.

**The optimal kicker profile here is a 40–55 yard volume machine with high accuracy — not a record-chasing bomber.** In leagues that pay 6 or 7 for 60-yarders, the moonshot leg is gold; here the bracket is truncated and it is not. This is the most exploitable quirk in your kicker scoring, because most drafters will over-rate leg strength.

Note the leg is still net-positive (+1.28 > 0, since the alternative is a punt), just far less valuable than the bracket table superficially implies. Rank leg strength as a **tiebreaker**, not a primary criterion.

### 1c. Accuracy is worth more than it looks — a miss is a 4–6 point swing

A miss doesn't cost 1 point; it costs the −1 **plus** the 3/4/5 you forfeited. A missed 47-yarder is a **5-point swing**. Over ~32 attempts, a kicker 5 percentage points more accurate saves ~1.6 misses × ~5 = **~8 points/season**, plus he keeps attempting long ones because his coach trusts him (a compounding volume effect).

### 1d. THE dominant driver: FG attempts, not offensive quality

Kicker fantasy points are driven by **stalled drives in FG range**, not by team scoring. Worked example:

- **Elite red-zone offense** (60 RZ trips, 70% TD rate): 42 TD + 18 short FG → ~41 PAT (41) + 18 short FG (~54) + ~12 long attempts (~54) ≈ **149 pts**
- **Stall-prone offense** (55 RZ trips, 50% TD rate): 27 TD + 28 FG → 27 PAT + 28 FG (~84) + ~12 long (~54) ≈ **165 pts**

**The worse red-zone team's kicker scores ~11% MORE.** Every drive that stalls at the 30 instead of scoring a TD is worth **~+2.2 points** to your kicker (3.15 EV vs 1 PAT). Target: **good yardage offense, mediocre red-zone TD rate.**

### 1e. Venue: domes and dry/warm homes

Distance-weighted scoring makes environment matter because the 40+ brackets carry the points. **UNVERIFIED for 2026 alignments** — confirm each team in the ESPN draft room, which displays current team next to every kicker:

- **Indoor/retractable:** ATL, DET, MIN, NO, LV, ARI, IND, DAL, HOU, LAR & LAC (SoFi is roofed), TEN (dome)
- **Warm/dry outdoor:** MIA, TB, JAX
- **Altitude bonus:** DEN — thinner air adds meaningful distance, historically the longest average made-FG distance
- **Avoid as home venues:** BUF, CHI, CLE, NE, PIT, NYG/NYJ, GB, KC (wind/cold; late-season especially)

Eight home games in ideal conditions is worth roughly **+0.5 to +0.8 pts/game** vs. a windy outdoor home — real, and it is also the basis of the streaming rule in §3.

### 1f. Season totals under YOUR scoring (modeled)

| Tier | FGA | Made | 0–39 / 40–49 / 50+ | Misses | PAT | **Season** | **Per game** |
|---|---|---|---|---|---|---|---|
| Elite (K1) | 36 | 33 | 15 / 12 / 6 | 3 | 40 | 45+48+30−3+40 = **160** | **9.4** |
| Solid (K6) | 32 | 29 | 14 / 10 / 5 | 3 | 37 | 42+40+25−3+37 = **141** | **8.3** |
| Median (K12) | 30 | 27 | 14 / 9 / 4 | 3 | 35 | 42+36+20−3+35 = **130** | **7.6** |
| Poor (K24) | 24 | 20 | 12 / 6 / 2 | 4 | 28 | 36+24+10−4+28 = **94** | **5.5** |

**K1 − K12 ≈ 1.8 pts/game. K1 − K24 ≈ 3.9 pts/game.**

**Weekly kicker range:** floor **−2** (two misses, no scores — rare) / realistic bad game **0–2** / median **7–8** / good **12–14** / ceiling **~24** (5 FG incl. three 50+ = 5+5+5+4+4 = 23, plus PAT).

---

# 2. IS DRAFTING A KICKER EARLY EVER JUSTIFIED? (Question 2)

**No. Never. Not in this format, not in any format.** Three compounding reasons:

**(1) The spread is small.** K1 over K12 is ~1.8 pts/game *in hindsight*.

**(2) Preseason kicker rank has near-zero predictive power.** Year-over-year correlation of kicker fantasy points is roughly r ≈ 0.1–0.2 — the weakest of any position. The *realized* expected edge from "drafting the right kicker" is therefore closer to **0.4–0.6 pts/game**, not 1.8. You are paying a real pick for a coin flip.

**(3) The opportunity cost here is uniquely brutal.** With only 4 bench spots, **your round-12 pick IS a bench player.** Spending it on a kicker instead of the 13th round costs you an entire bench slot's worth of skill-player optionality. In a deep-bench league a K in round 12 is a minor sin; here it is a structural one.

### Verdict

- **Kicker: absolute LAST pick. Round 13.** No exceptions.
- **D/ST: round 12.** Also no earlier — see §7.
- **Round 11 is your last skill-player pick.** Use it on the highest-upside RB/WR available.

### Advanced option — punting the K pick entirely

In a **10-team** league, 22 kickers go undrafted. You can take a 13th skill player in round 13 and add a kicker from the free-agent pool before Week 1. Waivers are 1-day, so a Wednesday claim lands Thursday — no timing risk before Sunday. This converts your worst pick into a real lottery ticket.
- **10-team: viable, mildly +EV.** Recommend only if you're comfortable managing it.
- **12-team: do NOT.** 20 kickers remain but the good spots go fast, and ESPN roster-legality/auto-draft behavior can bite you.
- Same logic applies to D/ST but is **more dangerous** there (see §7) — I'd punt the K before the D/ST.

### Best late kicker TARGETS — how to pick one live

**I cannot give you verified 2026 kicker names or teams (see disclosure).** Naming kickers from 2024/2025 memory would risk handing you a player who changed teams, lost a camp battle, or is no longer in the league — exactly the failure mode you told me to avoid. Instead, here is a **screen you can execute in the draft room in 60 seconds**, since ESPN shows each kicker's current 2026 team and projections next to his name:

Rank every available kicker by, in order:
1. **Indoor or warm/dry home stadium** (list in §1e) — biggest single lever
2. **Team projected top-12 in yards but NOT top-8 in points** — the stall-prone profile from §1d. Use the ESPN team projections or Vegas season win totals as a proxy.
3. **Multi-year incumbent with a career FG% ≥ 85%** — misses cost 4–6 point swings
4. **Not in an open camp competition and not a rookie** — check the ESPN player note; job security is worth more than talent at this position
5. **Tiebreak only:** leg strength (and remember 60+ is capped, so do not overweight it)

**Explicit anti-target:** a kicker on a team with an elite red-zone TD rate. His volume is PATs at 1 point each.

---

# 3. KICKER STREAMING VIABILITY (Question 3)

**Verdict: streamable, and you SHOULD stream — but the mechanism is weather and matchup, not talent.**

Your transaction rules make this nearly frictionless:
- **1-day waiver period** — a Tuesday drop clears Wednesday
- **No acquisition limit** — zero cost to churning every single week
- **Waiver order RESETS WEEKLY by inverse standings (not rolling)** — this is the big one, see §8. **Using a claim costs you nothing.** In a rolling-priority league, burning priority on a kicker is unthinkable. Here it is free.

The only real friction is the **roster slot**: with 4 bench spots you cannot carry a K2. You must drop-and-add in the same slot. That works — lineups lock individually at each player's gametime, so hold your current K through his game, then churn Monday night/Tuesday.

### The three streaming rules that actually generate points

**1. WIND IS THE KILLER.** Sustained wind above ~15 mph historically drops FG% by roughly 8–10 percentage points **and** suppresses long attempts (coaches punt instead of trying 48-yarders). Under distance-weighted scoring that is a **double hit**: fewer 4- and 5-point attempts *and* more −1s. A windy game can turn an 8-point kicker into a 2-point kicker. **Check the forecast Saturday night, every week.** This is the highest-ROI 60 seconds in your fantasy week.

**2. Bench any kicker whose team is playing outdoors in December cold/wind; start any kicker in a dome.** In your **Weeks 15–17/18 playoff window**, indoor-venue kickers have a structural, schedule-independent edge. Plan the playoff kicker slot around venue, not name.

**3. Avoid backup-QB games and heavy underdogs.** Backup QBs reduce total drives into FG range. Big underdogs go for it on 4th down and chase points late instead of kicking.

### Honest caveat on kicker streaming

The expected gain from *talent-based* kicker streaming is small (~0.5 pts/game) and noisy. The gain from *weather/venue-based* streaming is larger (~1.0–1.5 pts/game in the ~30% of weeks with adverse conditions) and reliable. **Stream on conditions, not on last week's box score.** Chasing the kicker who just went 4-for-4 is the classic mistake — that is pure noise.

---

# 4. HOW YARDS-ALLOWED CHANGES D/ST VALUE (Question 4)

Your D/ST brackets:

```
POINTS ALLOWED:  0=+5 | 1-6=+4 | 7-13=+3 | 14-17=+1 | 18-27=0 | 28-34=-1 | 35-45=-3 | 46+=-5
YARDS  ALLOWED: <100=+5 | 100-199=+3 | 200-299=+2 | 300-349=0 | 350-399=-1
                400-449=-3 | 450-499=-5 | 500-549=-6 | 550+=-7
PLUS: sack 1 | INT 2 | FR 2 | safety 2 | any TD 6 | block 2
```

### 4a. The structure is brutally asymmetric — this is the key insight

Modeling single-game yards allowed as roughly normal with league mean ≈ **338 yds** and SD ≈ **95** (both stable across recent seasons; **the specific 2025 figures are UNVERIFIED**):

| Bracket | Pts | Approx. share of all team-games |
|---|---|---|
| <100 | **+5** | ~0.6% — essentially unreachable |
| 100–199 | **+3** | ~6.6% |
| 200–299 | **+2** | ~26.9% |
| 300–349 | **0** | ~20.5% |
| 350–399 | **−1** | ~19.3% |
| 400–449 | **−3** | ~14.0% |
| 450–499 | **−5** | ~7.6% |
| 500–549 | **−6** | ~3.2% |
| 550+ | **−7** | ~1.3% |

**Read that table again: ~45% of all D/ST games score NEGATIVE on yardage, ~21% score zero, only ~34% score positive.** The +5 and +3 tiers are lottery tickets (a sub-100-yard game happens maybe once every two or three seasons league-wide). The realistic best case is **+2**. The realistic worst case is **−7**.

**Expected yardage points for a league-average defense: −0.51 per game.** The yardage line is a **net tax**, not a bonus. It is a **downside-skewed penalty box with a capped ceiling.**

### 4b. Bracket score as a function of season YPG allowed

| Season YPG allowed | Approx NFL rank | **Expected yardage pts/game** |
|---|---|---|
| 275 | #1 | **+1.03** |
| 290 | top-3 | **+0.70** |
| 310 | top-8 | **+0.23** |
| 338 | ~16th (median) | **−0.51** |
| 360 | ~25th | **−1.07** |
| 390 | #31–32 | **−1.94** |

**Best-to-worst spread from yardage alone ≈ 3.0 pts/game ≈ 42 points over a 14-week regular season.**

**On the 2025 actuals you asked for:** I could not retrieve pro-football-reference or any other source, so **I will not invent a 2025 team YPG table.** The mapping above is the deliverable — pull the real 2025 "Opponent Yards/Game" leaderboard (PFR `/years/2025/opp.htm`, or the ESPN team-stats page) and read each team's expected bracket score straight off this table. The tiers are what matter and they are stable; the team names change.

### 4c. Comparison: the points-allowed axis

Same modeling, league mean ≈ 22.5 PPG, SD ≈ 10:

| Defense | Expected PA pts/game |
|---|---|
| Good (17 PPG allowed) | **+1.30** |
| Average (22.5) | **+0.40** |
| Bad (29 PPG allowed) | **−0.98** |

Best-to-worst PA spread ≈ **2.3 pts/game**.

### 4d. THE ANSWER: adding yards nearly DOUBLES the "allowed" axis and specifically punishes bend-don't-break

**Combined spread from the two "allowed" brackets: (+0.70 +1.30) vs (−1.94 −0.98) = +2.00 vs −2.92 ≈ 4.9 pts/game**, versus ~2.3 in a points-only league.

Now, does it favor **bend-don't-break** or **sack/turnover** defenses? The answer is unambiguous:

**It punishes bend-don't-break. It rewards sack/turnover defenses. On BOTH axes.** Three reasons:

1. **Bend-don't-break is definitionally the archetype that fails this test.** It means allowing lots of yards while limiting points — so it earns +1 or +3 on PA and simultaneously eats −1 or −3 on yardage. **The two cancel.** In a points-only league that unit looks like a top-10 D/ST. Here it grades out as league-average. This is the exploitable mispricing: **the market prices D/ST on points allowed, your league scores it on both.**

2. **Sacks physically suppress yardage.** A sack is negative yardage on the opponent's total. So a sack **double-dips**: +1 fantasy point *and* it pushes you toward a better yardage bracket. Same for turnovers — a takeaway ends the drive, capping yards. **The yardage bracket is positively correlated with the sack/TO archetype, not opposed to it.**

3. **Big plays still dominate the average score.** Sacks (~2.4/gm = 2.4 pts), turnovers (~1.4/gm × 2 = 2.8 pts), and defensive/ST TDs (~0.22/gm × 6 = 1.3 pts) sum to ~6.5 points. PA (+0.4) and YA (−0.5) roughly **cancel to zero** for an average defense. So sacks/TOs/TDs are essentially *all* of the average D/ST score; the allowed brackets are a **±2 to −5 modifier** on top of it.

**The one genuinely new selection criterion the yardage bracket adds: OPPONENT VOLUME.** Fewer opponent plays = fewer yards. So favor defenses on teams with:
- A **ball-control, positive-game-script offense** (long drives → fewer opponent snaps)
- A **high three-and-out rate** (the single cleanest yardage suppressor)
- **Low yards-per-play allowed** — not merely low points allowed

And **fade** defenses on teams with fast, pass-heavy offenses that score quickly (the opponent gets the ball back constantly and throws), and defenses on bad teams that trail all game and bleed garbage-time yardage.

### 4e. The blowout paradox — a real, non-obvious effect

In a points-only league, your D/ST winning 38–10 is a jackpot. **Here it is only pretty good.** A big lead makes the opponent throw 50+ times to catch up, generating garbage yardage: 10 points allowed = **+3**, but 385 yards = **−1**. Net **+2** from the brackets.

Contrast a defensive slugfest, 13–10 win, opponent held to 265 yards: **+3 and +2 = +5.**

**The ideal D/ST game script under this scoring is a LOW-VOLUME, low-scoring game — not a blowout.** Target: bad weather, run-heavy incompetent opponents, three-and-out machines. This inverts the standard streaming heuristic ("start the huge favorite") and is the second exploitable quirk in your league.

---

# 5. 2026 D/ST RANKINGS, ADP, AND SCHEDULES (Question 5)

**I cannot deliver verified content for this section.** No 2026 D/ST rankings, no 2026 ADP, and critically **no 2026 NFL schedule** — so I cannot tell you which defenses have the best Weeks 1–4 or Weeks 15–17 slates. Every source that carries this (FantasyPros, ESPN, Sleeper, PFF, 4for4, Draft Sharks) was blocked. **Inventing a schedule would be the single most damaging thing I could do here**, so I won't.

### What to do instead — 5-minute pre-draft lookup

**In the ESPN draft room itself (free, live, verified 2026):**
- The D/ST list is sorted by ESPN's own 2026 projection and shows **live ADP** for every unit. That is your ranking and ADP, verified, at 1:55 PM.
- Click any D/ST → the **Outlook/Schedule** tab shows its 2026 opponent list. Check **Weeks 1–3** and **Weeks 15–18**.

**The 90-second screen to run on the top ~12 available D/ST:**
1. Weeks 1–3 opponents: are ≥2 of them bottom-10 offenses? (Proxy: lowest Vegas win totals / ESPN's lowest-projected offenses.)
2. Weeks 15–18: outdoor cold-weather games? **Those are GOOD for D/ST** (suppress both yards and points) — and simultaneously bad for your kicker.
3. Is the unit's own offense ball-control/positive-script? (High team win total + run-lean = fewer opponent snaps = better yardage brackets.)

**Durable, schedule-independent principles you can apply without any lookup:**
- **Weeks 15–18 favor outdoor, cold, windy venues for D/ST.** Wind and cold cut passing yards and scoring. Your playoff D/ST should be playing in the north in December; your playoff **kicker should be in a dome.** These two rules pull in opposite directions and both are free money.
- **Week 18 is a landmine.** With 4 playoff teams and 2-week matchups, your final round is likely Weeks 17–18. In Week 18, playoff-clinched teams rest starters — which is *great* for a D/ST facing a resting team and *terrible* for your K on one. **Confirm your exact playoff weeks in the league settings before the draft** and plan the Week 18 slot deliberately.

**UNVERIFIED priors only — franchises with durable defensive infrastructure in recent seasons, offered strictly as "check these names first on the live board," NOT as 2026 facts:** Baltimore, Philadelphia, Denver, Houston, Pittsburgh, Minnesota, Detroit, Buffalo, Cleveland, Green Bay. Coordinators, personnel and health all change — **verify every one against the 2026 board.** Do not draft off this list.

---

# 6. WEEKLY POINT RANGE, GOOD vs BAD D/ST (Question 7)

Concrete modeled scenarios under your exact scoring:

| Scenario | PA | YA | Sacks | TO | TD | **Total** |
|---|---|---|---|---|---|---|
| **Monster ceiling** — 3 pts, 180 yds, 5 sk, 3 TO, 1 def TD | +4 | +3 | +5 | +6 | +6 | **+24** |
| Absolute ceiling (2 TD + safety) | | | | | | **~+33** |
| **Very good** — 10 pts, 250 yds, 4 sk, 2 TO | +3 | +2 | +4 | +4 | 0 | **+13** |
| **Good** — 17 pts, 300 yds, 3 sk, 2 TO | +1 | 0 | +3 | +4 | 0 | **+8** |
| **Median week** — 23 pts, 340 yds, 2 sk, 1 TO | 0 | 0 | +2 | +2 | 0 | **+4** |
| **Poor** — 27 pts, 380 yds, 2 sk, 0 TO | 0 | −1 | +2 | 0 | 0 | **+1** |
| **Bad** — 31 pts, 420 yds, 1 sk, 0 TO | −1 | −3 | +1 | 0 | 0 | **−3** |
| **Disaster** — 38 pts, 480 yds, 1 sk, 0 TO | −3 | −5 | +1 | 0 | 0 | **−7** |
| **Catastrophe** — 48 pts, 560 yds, 0 sk, 0 TO | −5 | −7 | 0 | 0 | 0 | **−12** |

**Realistic weekly range: −10 to +24. Median ≈ +4–5. Mean ≈ +6.6** (mean exceeds median because defensive TDs are lumpy and right-skew the distribution).

### Season-long expectations

| | PA | YA | Sacks | TO | TDs | **Pts/game** |
|---|---|---|---|---|---|---|
| **Elite D/ST** | +1.3 | +0.7 | 3.3 | 3.6 | 1.8 | **≈ 10.9** |
| **Average D/ST** | +0.4 | −0.5 | 2.4 | 2.8 | 1.3 | **≈ 6.6** |
| **Bad D/ST** | −1.0 | −1.9 | 1.6 | 2.0 | 0.9 | **≈ 1.7** |

**Elite-to-bad spread ≈ 9.2 pts/game ≈ 129 points over 14 weeks** — roughly the gap between WR8 and WR40.

### Does the negative-yardage downside make elite D/ST more valuable? YES — but read the mechanism carefully

Compare your league to a points-allowed-only version of the same settings:
- Ceiling moves from ~+21 to **~+24** (+3)
- Floor moves from ~−4 to **~−12** (−8)

**The yardage bracket roughly DOUBLES the downside tail while barely moving the ceiling.** That is the entire structural story.

Probability of a **negative** D/ST week (a week your D/ST actively costs you points):
- Elite D/ST: **~2–4%**
- Average D/ST: **~8–12%**
- Bad D/ST: **~20–25%** — i.e. **roughly 3 of your 14 regular-season weeks**

This matters doubly because **only 4 teams make the playoffs and the seeding tiebreaker is total points for.** A −7 week hurts your record *and* your tiebreaker.

**So the correct conclusion is precise: the yardage scoring raises the value of D/ST FLOOR and matchup discipline — not the value of a name-brand elite defense per se.** A hard rule — *never start a D/ST against a top-8 offense, no matter how good your defense is* — captures most of the available edge for free, without spending a single extra draft pick.

---

# 7. STREAM OR ROSTER AN ELITE D/ST? (Question 6)

## RECOMMENDATION: **STREAM — but draft for Weeks 1–3, and stream with strict discipline.**

### The head-to-head math

| Approach | Pts/game | Cost |
|---|---|---|
| Elite D/ST drafted R10–11 | **~10.5–11.0** | 2 picks earlier = one fewer bench skill player |
| **Disciplined streamer** (matchup-selected, hard floor rule) | **~9.0–9.5** | Zero. Same roster slot all year. |
| Naive streamer (chasing last week's box score) | ~5.5–6.0 | Zero, but exposed to the −7 tail |

**Gap between elite and disciplined streaming: ~1.5 pts/game ≈ 21 points over the season.** The cost of closing it is moving your D/ST pick from round 12 to round 10 — sacrificing one of your only **four** bench spots. **One bench WR hitting is worth far more than 21 points.** Stream.

### Why streaming works so well *specifically* under this scoring

Counterintuitively, the yardage bracket **helps** the streamer. Single-game yards allowed depends at least as much on the **opponent's offense** as on your defense's quality. Streaming lets you deliberately face bottom-8 offenses every week — which pushes a mediocre unit's expected yardage line from −0.5 up toward **+0.7**, i.e. it simulates having an elite defense. And it lets you **systematically dodge the −5/−6/−7 tail**, which is precisely where this format's pain lives.

### Why your transaction rules make streaming nearly free

- **1-day waiver period** — Tuesday drop clears Wednesday; targets are live within days.
- **No acquisition limit** — churn every single week at zero cost.
- **Waiver order RESETS WEEKLY by inverse standings, and is NOT rolling.** This is the decisive rule. **Using your claim costs you nothing** — you get a fresh priority next week regardless. In a rolling-priority or FAAB league, spending on a D/ST is genuinely expensive. Here it is literally free. **Use your waiver claim every week.**
- **Pool depth:** 22 D/ST unrostered in a 10-team league, 20 in a 12-team. You will never be short of options.

### The one real friction, and how to beat it

Because priority resets by **inverse** standings, **if you are winning you have priority 10th/12th every week** and will lose contested claims. Three counters:

1. **Target the 2nd- or 3rd-best matchup, not the consensus best.** The drop-off between the top and third streaming spot is ~1 point — far less than the cost of losing the claim.
2. **Use free agency, not waivers.** With a 1-day period, unclaimed players hit FA fast and are first-come-first-served. **Set an alarm for when waivers process (typically Wednesday morning on ESPN).** This is the winning manager's tool.
3. **Plan two weeks ahead.** With 4 bench spots you cannot stash next week's streamer, so instead identify your Week N+1 target on Sunday and be first in line Wednesday.

### The one scenario where you should hold instead

If a genuinely elite, sack-and-turnover-heavy D/ST **falls to you in round 12** (it happens — D/ST ADP is soft), **take it and hold it through any week it doesn't face a top-8 offense.** The −7 tail protection is worth real points, and it saves you 14 weeks of management. Even then, **still bench it in bad spots** — matchup beats talent in this format.

### Draft-day framing that actually matters

**Since you are going to churn it anyway, your round-12 D/ST is really just "my Weeks 1–3 streamer." Draft for the opening slate, not for the season-long name.** This is the single most useful reframe for that pick, and it is exactly why §5's live schedule check is worth 90 seconds of your pre-draft time.

### Playoff note — 2-week matchups change the calculus in streaming's favor

Two-week playoff rounds mean **two D/ST games per matchup**. That (a) dilutes the impact of any single −7 disaster, and (b) gives you **two independent chances** to hit a good matchup. You can and should **swap your D/ST between the two weeks of a playoff matchup** — waivers run normally during the playoffs. A "set-and-forget" elite defense captures none of that. **Two-week matchups make streaming strictly better, not worse.**

### Do NOT punt the D/ST draft pick

Unlike the kicker (§2), skip-drafting your D/ST is dangerous: the top units get drafted, and being stuck choosing among the four worst defenses in Week 1 under scoring with a −12 floor is a real risk. **Draft one in round 12.**

---

# 8. THE WAIVER RULE MOST PEOPLE WILL MISS

Worth isolating because it is the biggest structural edge in your league settings:

> **Waiver order resets weekly by inverse standings — it does NOT roll.**

In a rolling-priority league, claiming a streaming D/ST drops you to last priority for weeks, so managers hoard priority and stream reluctantly. **Here, priority is a use-it-or-lose-it weekly resource with zero carryover cost.** Combined with a 1-day waiver period and unlimited acquisitions, this means:

**You should submit a waiver claim essentially every single week of the season, for D/ST and often for K.** There is no reason not to. Most of your leaguemates will instinctively hoard priority out of habit from other formats. That is free edge, compounding across 14 weeks.

---

# 9. WHAT I COULD NOT VERIFY — YOUR 5-MINUTE PRE-DRAFT CHECKLIST

Everything below is unverified for 2026 and must be checked live. All of it is available **inside the ESPN draft room**, which shows 2026 teams, projections and live ADP:

| # | Check | Where | Time |
|---|---|---|---|
| 1 | Confirm **league size** (10 vs 12) and **number of draft rounds** | League settings | 15s |
| 2 | Confirm **exact playoff weeks** and whether Week 18 is included | League settings → Playoffs | 20s |
| 3 | 2026 **D/ST ADP and rankings** | Draft room, filter D/ST | 30s |
| 4 | Top-12 D/ST **Weeks 1–3 opponents** — pick the best opening slate | Player card → Schedule | 90s |
| 5 | Top-12 D/ST **Weeks 15–18** — favor outdoor/cold | Player card → Schedule | 60s |
| 6 | 2026 **kicker teams** — confirm dome/warm homes from §1e | Draft room, filter K | 45s |
| 7 | Kicker **job security** — no open camp battles, no rookies | Player news note | 45s |
| 8 | 2025 **team YPG-allowed leaderboard** — map onto the §4b table | PFR `/years/2025/opp.htm` | 60s |

---

# 10. DRAFT-DAY EXECUTION SUMMARY

1. **Exactly ONE K, exactly ONE D/ST.** All 4 bench spots go to RB/WR upside. Non-negotiable.
2. **Round 11 is your last real skill pick.** Rounds 12–13 will be a leaguewide K/DST run. Plan accordingly.
3. **Round 12: D/ST.** Draft the best **Weeks 1–3 schedule**, not the best season-long name — you're streaming it from Week 4.
4. **Round 13: K.** Last pick, always. Screen: dome/warm home → team with good yardage but mediocre red-zone TD rate → career FG% ≥ 85% → secure job. Leg strength is a tiebreaker only.
5. **60+ FGs are capped at 5 here.** Do not pay up for a bomber; the 40–55 yard volume kicker is the optimal profile (EV +3.15/attempt vs +1.28 for 60+).
6. **The stall-prone offense's kicker outscores the elite offense's kicker** by ~10%. Fade great red-zone teams at K.
7. **Stream D/ST weekly.** Use your waiver claim every week — priority resets, so it is free.
8. **Hard floor rule: never start a D/ST against a top-8 offense.** The −5/−6/−7 yardage tail is where this format kills you. Avoiding the tail is worth more than chasing the ceiling.
9. **Fade bend-don't-break defenses.** The market prices D/ST on points allowed; your league also scores yards, and that archetype's two axes cancel out. Buy sacks + turnovers + low opponent volume.
10. **Prefer low-volume defensive slugfests to blowouts.** A 38–10 win with 385 garbage yards allowed nets +2 from the brackets; a 13–10 win holding 265 yards nets +5.
11. **Weeks 15–18: D/ST outdoors in the cold, K indoors in a dome.** Opposite directions, both free.
12. **Two-week playoff matchups mean you can swap your D/ST mid-round.** Do it — it's two independent matchup bets, not one.
