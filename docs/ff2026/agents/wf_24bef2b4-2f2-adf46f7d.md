> **Research-method disclosure — read this first.** My own live web tools were unavailable this session: the shared WebSearch budget (200/200) was exhausted before my turn, and the egress proxy blocked every direct fetch I attempted (fantasypros.com, espn.com, pff.com, 4for4.com, footballguys.com, underdogfantasy.com, api.sleeper.app, reddit.com, wikipedia.org). **However**, sibling agents in this same workflow had already harvested live 2026 data into the shared scratchpad before the budget ran out, and I built my analysis on that. Everything below traces to dated 2026 artifacts:
> - **Fantasy Football Calculator half-PPR ADP, fetched 2026-08-19** (2,828 mock drafts run 2026-08-17→08-22) — the freshest and most format-matched source. `ffc_half_0818.csv`, 221 players.
> - **ESPN ADP, fetched 2026-07-18** (400 players) — your actual platform, but ~5 weeks stale.
> - **Sleeper half-PPR ADP, fetched 2026-07-19**; **Yahoo ADP**; **FantasyPros consensus ADP/ECR dated 2026-08-21**.
> - A merged 6-source board (`board/top170.md`) and a dated camp-injury file (`inj.json`, retrieved 2026-08-15).
>
> Where a claim is not in those artifacts I label it **UNVERIFIED**. In particular: **I could not retrieve any published 2026 article specifically about "best draft position," "picking from the 1 spot," or "wheel strategy."** Section 3 says so plainly and substitutes my own simulation rather than inventing a consensus.
>
> One team note to sanity-check on the clock: the live ADP feeds list **A.J. Brown on NE** (FFC 8/18, ADP 19.4). One older search snippet in the corpus called him "Eagles" — almost certainly a stale 2025 article. DeVonta Smith is still PHI in all feeds. Trust the live feed.

---

# PART 0 — What this league actually rewards (this drives every slot)

Your settings are unusual in four ways that change draft strategy more than your slot does.

### 0.1 — 13 roster spots, 4 bench. This is a STARTERS league.

9 starters + 4 bench + 1 IR. Draft is **13 rounds** (156 picks in a 12-team, 130 in a 10-team). Two of those 13 go to K and D/ST. **You get 11 usable skill picks for 7 skill starters.** That is a 4-pick cushion, total.

Consequences, all of which are non-negotiable:
- **No handcuffs.** You cannot afford a Blake Corum or a Tyler Allgeier taking one of four bench spots.
- **One QB. One TE. One D/ST. One K.** Position maximums (QB 4, RB 8, WR 8, TE 3, D/ST 3, K 3) are irrelevant — the bench is the binding constraint, not the max.
- **Realistic final roster:** QB×1, RB×4-5, WR×4-5, TE×1, D/ST×1, K×1.
- Published shallow-bench guidance in the corpus matches: *"Draft strong starters, use the bench for fast-moving value... fill out your bench with breakout candidates, rather than handcuffs at running back."*

### 0.2 — The waiver system punishes you for winning

Waivers are **priority-based (not FAAB), 1-day period, order RESETS WEEKLY by inverse standings**, unlimited acquisitions.

This is the single most under-appreciated setting. If your draft works and you go 5-1, **you hold the worst waiver priority in the league every single week.** You will not be the team that lands the Week 4 breakout RB. Meanwhile the 1-6 team gets first crack every week.

**Therefore: Zero-RB is actively wrong in this league.** Zero-RB is a strategy that borrows against future waiver acquisitions — and this waiver system charges winners the highest interest rate. Anchor your RBs on draft day.

### 0.3 — D/ST yardage scoring is a real, mispriced edge

Most leagues score D/ST on points allowed only. Yours **also** scores yards allowed, on a brutal curve:

| Yds allowed | <100 | 100-199 | 200-299 | 300-349 | 350-399 | 400-449 | 450-499 | 500-549 | 550+ |
|---|---|---|---|---|---|---|---|---|---|
| Pts | +5 | +3 | +2 | 0 | -1 | -3 | -5 | -6 | -7 |

Stack that on points allowed (+5 to -5) and the **matchup component alone swings 12+ points**. A D/ST that holds an opponent to 280 yards / 17 points banks +3 before a single sack. One facing a 420-yard, 30-point offense starts at **-4**.

Two implications: (a) **never spend real draft capital on D/ST** — matchup dominates identity; (b) **stream aggressively every week**, targeting defenses facing low-yardage, run-heavy, inefficient offenses. The 1-day waiver period makes weekly streaming trivially easy. Cost of a D/ST pick before round 12: roughly one full-time skill contributor, for nothing.

### 0.4 — 4 playoff teams, 2-week playoff matchups, total-points tiebreaker

- **Only 4 of 10 or 12 make it.** You must finish top-33-40%. That is a high bar — it rewards weekly floor and roster-wide reliability over boom/bust lottery tickets.
- **2-week playoff matchups halve playoff variance.** The better roster wins more often. That is an argument for maximizing total roster strength, not for "getting hot."
- **Seeding tiebreaker is total points for.** Never punt a week. Never start a player on bye because you "already won." This also argues against ever carrying dead weight on a 4-man bench.
- **UNVERIFIED:** the exact playoff weeks. If the 2-week rounds extend into Week 18, players on teams likely to clinch and rest starters carry a small ding. I could not verify the 2026 schedule.

### 0.5 — Bye weeks are a genuine roster-construction hazard here

With 9 starters and 4 bench spots, **four starters on the same bye is an automatic loss** — and a loss to your total-points tiebreaker. The 2026 board is dangerously concentrated:

| Bye | Count in top 80 | Headliners |
|---|---|---|
| **11** | **17** | Bijan, Nacua, JSN, Drake London, A.J. Brown, Kyren, Jacobs, Judkins, Davante, Drake Maye, TreVeyon Henderson, Jadarian Price, Fannin, Watson, Pitts, Kraft, Stevenson |
| **10** | 12 | Barkley, DeVonta Smith, Egbuka, Loveland, Bucky Irving, Waddle, Swift, Burden, Odunze, Hurts, Caleb Williams |
| **6** | 10 | Gibbs, Chase, St. Brown, Achane, Jefferson, Chase Brown, Higgins, Burrow, Jamo Williams, LaPorta |
| 7 | 10 | Cook, Hampton, Josh Allen, McConkey, DJ Moore, McLaurin, Tuten, Daniels, Parker Washington, BTJ |

**Week 11 is the 2026 trap.** A Bijan + Nacua + JSN start is a beautiful three rounds and a guaranteed zero in Week 11. Track byes from round 3 onward; hard-cap yourself at **3 starters per bye week**.

---

# PART 1 — The 2026 board: tier map and cliffs

Consensus ADP (FantasyPros 8/21) with the true breaks marked. This tier map is your draft; the slot is just where you enter it.

### Overall tiers

| Tier | Picks | Players | Note |
|---|---|---|---|
| **1** | 1-2 | **Jahmyr Gibbs** (RB, DET, 1.0), **Bijan Robinson** (RB, ATL, 2.0) | Genuinely separated. Tiny stdev (0.7 each on FFC). Elite volume *and* receiving. |
| **2** | 3-4 | **Ja'Marr Chase** (WR, CIN, 3.0), **Puka Nacua** (WR, LAR, 4.0) | The two WRs you'd take over any RB not named Gibbs/Bijan. |
| **3** | 5-12 | McCaffrey (RB, SF, 5.6), JSN (WR, SEA, 6.0), Jonathan Taylor (RB, IND, 6.4), Amon-Ra St. Brown (WR, DET, 8.2), James Cook III (RB, BUF, 10.2), Ashton Jeanty (RB, LV, 11.2), De'Von Achane (RB, MIA, 11.4), CeeDee Lamb (WR, DAL, 12.0) | **8 players, essentially flat.** This is why mid-round-1 slots are near-interchangeable. |
| **4** | 13-24 | Jefferson (12.4), Barkley (14.2), Chase Brown (15.2), Drake London (17.4), Hampton (17.6), Derrick Henry (18.4), Kenneth Walker III (19.0), A.J. Brown (20.6), **McBride (21.6)**, **Bowers (22.4)**, Josh Allen (23.8), Pickens (24.2) | **12 more, also flat.** Both elite TEs and the QB1 live here. |
| **5** | 25-36 | Nico Collins (24.8), Rashee Rice (25.8), Jeremiyah Love (26.8), Olave (27.4), Nabers (28.6), Kyren (30.0), Javonte (31.2), Breece Hall (31.4), Jacobs (31.8), DeVonta Smith (35.0), Zay Flowers (36.2), Skattebo (38.0) | Where drafts get lost. See dead zones. |

### Positional cliffs (gaps ≥4 ADP within position)

**RB** — Gibbs 1.0, Bijan 2.0, CMC 5.6, JT 6.4, Cook 10.2, Jeanty 11.2, Achane 11.4, Barkley 14.2, Chase Brown 15.2, Hampton 17.6, Henry 18.4, Walker 19.0 → **CLIFF (12.4)** → Love 26.8, Kyren 30.0, Javonte 31.2, Breece 31.4, Jacobs 31.8 → **CLIFF** → Skattebo 38.0, Etienne 40.6 → Irving 45.8, Judkins 46.4, Swift 49.8, Montgomery 51.2 → Henderson 55.2, Tuten 57.8, Price 62.8 → **CLIFF (10.6)** → Warren 73.4, Stevenson 79.4, Pollard 80.0, Dowdle 81.8, Harvey 85.6, Hubbard 89.2, Brooks 91.8 → **CLIFF (13)** → Gainwell 102.4.
**The RB1 pool is exactly 12 deep and ends at pick ~19.** After that every RB has a committee, an injury, or both.

**WR** — Chase 3.0, Nacua 4.0, JSN 6.0, St. Brown 8.2, Lamb 12.0, Jefferson 12.4 → London 17.4, A.J. Brown 20.6 → Pickens 24.2, Collins 24.8, Rice 25.8, Olave 27.4, Nabers 28.6 → **CLIFF (6.4)** → DeVonta 35.0, Flowers 36.2, T-Mac 38.8, Egbuka 39.0, Garrett Wilson 40.8, Higgins 41.6, McConkey 46.0, Waddle 49.0, Davante 50.0, DJ Moore 52.4, McLaurin 54.0, Burden 54.0, Jamo 57.0, Odunze 61.4, Evans 64.8 → Watson 70.4, Tate 71.2, MHJ 74.0, Parker Washington 74.2, BTJ 78.6 → **CLIFF (21.2)** → Godwin 99.8.
**WR is 33 deep before the first real cliff.** This is the position you can wait on — and the reason WR is where your middle rounds go.

**TE** — **McBride 21.6, Bowers 22.4 → CLIFF (20.8) →** Loveland 43.2, Warren 50.0 → **CLIFF (19.4)** → LaPorta 70.6, Pitts 71.0, Kraft 72.8 (+Fannin 69.4) → **CLIFF (22)** → Kittle 95.2, Kelce 99.0 → Ferguson/Likely 109.2, Goedert 112.8, Kincaid 121.2, Andrews 124.4.
Three islands. With one TE roster spot, this is a binary decision — see §7.3.

**QB** — Allen 23.8 → **CLIFF (18.0)** → Lamar 41.8 → **CLIFF (11.0)** → Maye 52.8, Burrow 54.6, Daniels 61.4, Hurts 64.8 → Dak 76.4, Caleb 75.6 → Herbert 89.6, Lawrence 88.6, Dart 92.6 → Stafford 95.2, Mahomes 105.8, Purdy 108.6, Nix 110.0.
Your scoring (**4-pt pass TD, 0.04/yd, -2 INT**) is low-value passing. Rushing QBs are worth disproportionately more (0.1/rush yd, **6-pt rush TD**). But the QB1-QB12 spread is small in this format. Corpus VORP has **Hurts (ADP 64.8, VORP 27.9) grading better than Maye (52.8, 24.5) and Daniels (61.4, 18.7)** — Hurts is the best QB value on the board.

---

# PART 2 — ⚠️ ESPN-vs-consensus ADP gaps (your biggest single edge)

You are drafting on **ESPN**, and ESPN's default rankings push the room in predictable directions. Below is the ESPN ADP snapshot (2026-07-18) minus consensus (2026-08-21).

**Caveat:** the ESPN snapshot is ~5 weeks old, so some gaps are staleness, not bias. Stefon Diggs's +55.1 is entirely explained by his 2026-08-07 signing with Washington, which post-dates the ESPN pull. The **structural** biases below (K/DST early, elite TE early, QB late, veteran-name RB/WR late) are real ESPN-default effects and should hold today.

### ESPN drafters REACH on these (let them)

| Δ vs consensus | Player | ESPN ADP | Consensus |
|---|---|---|---|
| **-26.1** | Cameron Dicker (K) | 108.5 | 134.6 |
| **-20.1** | Denver D/ST | 91.9 | 112.0 |
| **-19.8** | Seattle D/ST | 100.0 | 119.8 |
| **-19.0** | Jaxson Dart (QB) | 73.6 | 92.6 |
| **-16.1** | Brandon Aubrey (K) | 83.9 | 100.0 |
| **-13.8** | Houston D/ST | 86.0 | 99.8 |
| **-13.8** | Jason Myers (K) | 122.6 | 136.4 |
| **-12.2** | George Kittle (TE, post-Achilles/PUP) | 83.0 | 95.2 |
| **-10.9** | Carnell Tate (WR) | 60.3 | 71.2 |
| **-8.2** | Jeremiyah Love (RB, high ankle) | 18.6 | 26.8 |

**Also structural: ESPN takes the elite TEs ~2 rounds earlier than the market.** ESPN has McBride 21.1 / Bowers 23.6; FFC half-PPR has them at **38.6 / 42.5**. That is a 17-20 pick gap. **In your ESPN league, plan for McBride and Bowers to be gone by pick ~25**, not pick ~40.

**The K/D-ST run is your gift.** Expect a K/D-ST run starting around **pick 84-100** in an ESPN league. Every manager who takes Aubrey at 84 or the Texans D/ST at 86 is handing you a full-time RB/WR. Do not join.

### ESPN drafters LET THESE FALL (buy-low)

| Δ | Player | ESPN ADP | Consensus |
|---|---|---|---|
| **+35.6** | Tucker Kraft (TE, GB) | 108.4 | 72.8 |
| **+33.4** | Justin Herbert (QB) | 123.0 | 89.6 |
| **+31.5** | Parker Washington (WR, JAX) | 105.7 | 74.2 |
| **+29.9** | Rhamondre Stevenson (RB, NE) | 109.3 | 79.4 |
| **+29.5** | RJ Harvey (RB, DEN) | 115.1 | 85.6 |
| **+27.7** | Trevor Lawrence (QB) | 116.3 | 88.6 |
| **+24.9** | Christian Watson (WR, GB) | 95.3 | 70.4 |
| **+24.4** | Caleb Williams (QB) | 100.0 | 75.6 |
| **+23.1** | Brian Thomas Jr. (WR, JAX) | 101.7 | 78.6 |
| **+21.3** | Dak Prescott (QB) | 97.7 | 76.4 |
| **+21.3** | Luther Burden III (WR, CHI) | 75.3 | 54.0 |
| **+40.8** | Jordan Mason (RB, MIN) | 150.0 | 109.2 |

Also ESPN-cheap earlier: **Chase Brown ESPN 27.2 vs consensus 15.2** (+12), **Kenneth Walker III ESPN 28.2 vs 19.0** (+9.2), **A.J. Brown ESPN 27.3 vs 20.6** (+6.7). In an ESPN room, **Chase Brown at the 2/3 turn is the best structural value on the board.**

**Net ESPN plan:** wait on QB (they fall ~20-30 picks), wait on K/D-ST (2 rounds later than everyone else), pay ESPN's TE tax only if you want an elite TE, and pounce on Chase Brown / Walker / A.J. Brown / Burden / Watson / BTJ.

---

# PART 3 — Is an early or late pick better in 2026?

### 3.1 — What I could and could not verify

**I could not retrieve any 2026 published article on "best draft position," "picking from the 1 spot," "picking from the turn," or "wheel strategy."** The web-search budget was spent before those queries ran, and every direct fetch was blocked. I will not invent a consensus.

What the corpus **does** verify about 2026 draft-strategy consensus:
- *"The big theme of 2026's fantasy football landscape is **running back thirst**, with roughly 12 of the first 20 picks expected to be running backs. However, while it's close between RBs and wide receivers in the first couple of rounds, **it is not close in the early/middle and middle rounds.**"*
- *"It is a recommended strategy to draft **at least one RB in the first two rounds** this season."*
- Confirmed count: **10 RBs among the first 20 overall picks.**
- *"Scarcity is an issue with running backs; there wasn't a single back last year who averaged 20 carries a game, only four backs had 300 carries, and only 10 backs had even 300 touches."*
- PFF's 2026 hero-RB blueprint names **Gibbs as the top first-round target**, and says *"it is generally safer to secure your hero back in the first round and then avoid the position for several rounds,"* with the advantage being *"it allows you to prioritize tight end and quarterback early."*
- Consensus tier language: *"Gibbs and Bijan sit alone in Tier 1... Chase leads a loaded group of four wide receivers in the elite tier."*

### 3.2 — My own simulation (4,000 drafts per league size)

I ran a Monte Carlo: each simulated draft draws a board order from consensus ADP perturbed by each player's real FFC standard deviation, teams pick best-available off that noisy board, and each slot is scored on the total value of its first five picks (value curve `100·e^-(rank-1)/38`, calibrated to standard fantasy VOR decay).

**12-team, picks 1-5, indexed to the best slot:**

| Slot | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Index | **100.0** | 99.5 | 98.9 | 98.7 | 98.1 | 97.6 | 97.2 | 96.2 | 95.1 | 94.8 | 94.7 | 94.8 |

**10-team:**

| Slot | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|---|---|---|---|---|---|---|---|---|---|---|
| Index | **100.0** | 98.9 | 97.9 | 96.9 | 96.0 | 95.6 | 95.7 | 95.3 | 94.4 | **93.7** |

### 3.3 — Verdict

**In raw board value, 2026 favors the early pick — but only by ~5%, and the mechanism is specific: Gibbs and Bijan are a genuinely separated two-man tier.** In a flat year the curve is flat; in 2026 there's a real drop from #2 to #3 and from #4 to #5. Picks 1-2 buy a unique asset; nobody else can.

**Three important qualifications that flatten this:**

1. **The model scores raw value, not roster construction.** The turn's advantage is structural: back-to-back picks let you *take both sides of a cliff* rather than gamble on one surviving. That's worth more in 2026 than usual because Tier 3 is 8-deep and flat — from slot 11/12 you can take **two** of {Jeanty, Achane, Lamb, Jefferson, Barkley, Chase Brown} at picks 12-13 and lock a top-tier core with zero survival risk.
2. **Tier 3 being 8 wide means slots 5-12 are near-interchangeable in round 1.** The index spread from slot 5 to slot 12 is 3.3 points. Do not feel robbed by any slot in that range.
3. **The genuinely weakest zone is slots 8-10 in a 12-team** (index 96.2 → 94.8). You get the bottom of the flat Tier 3, your R2 lands at picks 15-17 (fine), but you have neither the unique Tier 1 asset nor the true turn.

**Ranking of 2026 slots, 12-team:** `1 ≈ 2 > 3 ≈ 4 > 12 ≈ 11 (construction-adjusted) > 5 ≈ 6 ≈ 7 > 8 > 9 ≈ 10`.
**10-team:** `1 > 2 > 3 > 10 ≈ 9 (construction-adjusted) > 4 ≈ 5 ≈ 7 ≈ 6 ≈ 8`.

**Bottom line: no slot is bad. Preparation gap >> slot gap.** A 5% board-value edge is roughly one mid-round pick. Botching one 90-second clock costs more.

---

# PART 4 — Slot-by-slot plans

Probabilities below are from the simulation: **P = probability that player is still on the board at that exact pick.** All 13-round pick sets are listed so you can compute survival for yourself on the clock.

---

## SLOT 1 — *applies to both 10-team and 12-team*

**12-team picks:** 1, 24, 25, 48, 49, 72, 73, 96, 97, 120, 121, 144, 145
**10-team picks:** 1, 20, 21, 40, 41, 60, 61, 80, 81, 100, 101, 120, 121

**R1 (pick 1):** **Jahmyr Gibbs** (RB, DET, 1.0). Bijan (2.0) is right there if you prefer him.
- *Live decision:* the corpus flags a **Gibbs contract hold-in (listed "resolved" on the 8/21 board)** plus earlier back tightness and soft-tissue history; the 8/05 note said *"if the hold-in drags into late August, Bijan is the safer top pick,"* and Bijan has **zero camp flags**. **Verify Gibbs practiced this week before submitting.** If anything is off — take Bijan. There is no meaningful production gap.
- *Bye note:* Gibbs = bye 6, Bijan = bye **11** (the crowded one).

**R2 (12-team pick 24 / 10-team pick 20):** you are on the reverse turn with picks 24+25 back-to-back.
- 12-team @24: A.J. Brown 15%, **McBride 38%**, **Bowers 44%**, Josh Allen 51%, Pickens 60%, **Nico Collins 71%**, **Rashee Rice 86%**, Jeremiyah Love 77%, **Olave 94%**, **Nabers 93%**, Kyren 97%, Javonte 96%.
- 10-team @20: Hampton 29%, Henry 21%, Walker 44%, **A.J. Brown 65%**, McBride 62%, Bowers 64%, Allen 73%, **Pickens 96%**, Love 95%.
- ⚠️ **On ESPN, discount the McBride/Bowers numbers hard** — ESPN ADP has them at 21/24, so realistically ~20-25% each at pick 24.

**R3 (12-team pick 25 / 10-team pick 21):** McBride 33%, Bowers 39%, Allen 45%, Pickens 45%, Collins 55%, Rice 73%, Love 69%, **Olave 88%**, **Nabers 88%**, **Kyren 95%**, **Javonte 94%**, **Breece Hall 98%**.

**Blueprint (12-team):**
| | Primary | Pivot |
|---|---|---|
| 1.01 | **Gibbs** (or Bijan if news) | — |
| 2.12 (24) | **Bowers or McBride** if either survives — elite TE + elite RB is the best-shaped core available to slot 1 | **Nico Collins** or **Rashee Rice** |
| 3.01 (25) | **Best WR: Olave (88%) / Nabers (88%) / Rice (73%)** | If you got a WR at 24, take **Kyren (95%)** or **Javonte (94%)** as RB2 |
| 4.12 (48) | Waddle 49.0, **Davante Adams** 50.0, DJ Moore 52.4, **Tyler Warren TE 50.0** | D'Andre Swift 49.8 |
| 5.01 (49) | Same window — take the other side | Drake Maye 52.8 |
| 6.12 (72) | **Jalen Hurts QB 64.8** if he lasts; else Kraft/Pitts/LaPorta TE cluster | Jaylen Warren RB 73.4 |

**Why:** slot 1's structural advantage is the elite RB *plus* an early-3rd that's really a late-2nd. The 24/25 back-to-back is the best elite-TE window in the draft. Do **not** take a second RB at 24-25 unless both elite TEs and the top WRs are gone — the RB tier that lives there (Love 26.8, Kyren 30.0, Javonte 31.2, Breece 31.4, Jacobs 31.8) is Dead Zone 1.

**10-team variant:** at 20/21 you'll likely get **A.J. Brown (65%) + Pickens (96%)** or **Bowers/McBride + a WR**. Same logic.

---

## SLOT 2 — *both formats*

**12-team picks:** 2, 23, 26, 47, 50, 71, 74, 95, 98, 119, 122, 143, 146
**10-team picks:** 2, 19, 22, 39, 42, 59, 62, 79, 82, 99, 102, 119, 122

**R1 (pick 2):** Gibbs 23%, **Bijan 76%**, Chase 93%. You get one of the two Tier-1 RBs ~99% of the time. **Take the RB.** Chase at 2 is defensible but you're passing a genuinely scarce asset for a fungible one — Nacua/JSN/St. Brown are all close to Chase.

**R2 (12-team 23 / 10-team 19):**
- @23: Walker 16%, A.J. Brown 24%, McBride 44%, **Bowers 49%**, Allen 57%, **Pickens 74%**, **Collins 84%**, **Rice 94%**, Love 83%, **Olave 97%**, **Nabers 96%**.
- @19 (10-tm): London 23%, Hampton 40%, Henry 47%, **Walker 55%**, **A.J. Brown 77%**, McBride 67%, Bowers 68%, Allen 77%, **Love 97%**.

**R3 (12-team 26 / 10-team 22):** McBride 28%, Bowers 34%, Allen 40%, Pickens 30%, Collins 38%, **Rice 55%**, **Love 61%**, **Olave 78%**, **Nabers 81%**, **Kyren 91%**, **Javonte 91%**, **Breece 96%**.

**Blueprint (12-team):** **Bijan (2) → Bowers/McBride or A.J. Brown/Pickens (23) → best WR of Rice/Olave/Nabers (26) → Bucky Irving 45.8 / McConkey 46.0 / Judkins 46.4 (47) → Tyler Warren 50 or Waddle 49 (50) → Hurts / TE cluster (71).**

**Slot-2 specific note:** Bijan's bye is **11**. From slot 2 you should actively avoid Nacua/JSN/London/A.J. Brown/Kyren/Jacobs/Judkins/Davante in the next two rounds unless the value is overwhelming — you can easily end up with 5 Week-11 starters.

---

## SLOT 3 — *both formats*

**12-team picks:** 3, 22, 27, 46, 51, 70, 75, 94, 99, 118, 123, 142, 147
**10-team picks:** 3, 18, 23, 38, 43, 58, 63, 78, 83, 98, 103, 118, 123

**R1 (pick 3):** Bijan 23%, **Ja'Marr Chase 69%**, **McCaffrey 97%**. Take **Chase**. If Bijan somehow slides, take Bijan.
- CMC is the fallback but he is **age-30 on SF** with a documented durability history; the corpus flags him as a projection outlier (VORP 96.2 despite ADP 5.6 — a bet, not a floor).

**R2 (12-team 22 / 10-team 18):** Hampton 13%, Walker 24%, A.J. Brown 37%, **McBride 50%**, **Bowers 54%**, Allen 63%, **Pickens 85%**, **Collins 92%**, **Rice 97%**, Love 88%, **Nabers 98%**.
**R3 (12-team 27 / 10-team 23):** McBride 23%, Bowers 30%, Allen 34%, Pickens 18%, Collins 22%, Rice 36%, **Love 52%**, **Olave 64%**, **Nabers 73%**, **Kyren 85%**, **Javonte 87%**, **Breece 93%**, **Jacobs 96%**.

**Blueprint (12-team):** **Chase (3) → McBride/Bowers (22, ~52% one is there) or Kenneth Walker III (24%, ESPN-cheap at 28.2) → RB2 from Love/Kyren (27) → Bucky Irving 45.8 / Judkins 46.4 (46) → Montgomery 51.2 / DJ Moore 52.4 (51) → Fannin 69.4 / LaPorta 70.6 / Kraft 72.8 (70).**

**Slot-3 problem:** taking Chase at 3 means your first RB comes at pick 22 or 27 — right at the top of Dead Zone 1. **Mitigation:** make pick 22 an RB (Walker at 24%, Hampton at 13%, or Love at 88%) rather than a TE, and be aggressive about RB again at 46-51 where Irving/Judkins/Swift/Montgomery live. Do not end round 4 with fewer than 2 RBs.

---

## SLOT 4 — *both formats*

**12-team picks:** 4, 21, 28, 45, 52, 69, 76, 93, 100, 117, 124, 141, 148
**10-team picks:** 4, 17, 24, 37, 44, 57, 64, 77, 84, 97, 104, 117, 124

**R1 (pick 4):** Chase 30%, **Puka Nacua 84%**, **McCaffrey 90%**, **JSN 97%**. Take **Nacua** (WR, LAR, consensus 4.0, FFC 3.0 — FFC actually has him WR1). Bye 11.
**R2 (12-team 21 / 10-team 17):** Hampton 21%, **Walker 33%**, **A.J. Brown 51%**, **McBride 56%**, **Bowers 59%**, Allen 68%, **Pickens 92%**, **Collins 96%**, **Love 92%**.
**R3 (12-team 28 / 10-team 24):** McBride 18%, Bowers 26%, Allen 29%, Rice 20%, **Love 43%**, **Olave 48%**, **Nabers 62%**, **Kyren 77%**, **Javonte 81%**, **Breece 88%**, **Jacobs 93%**.

**Blueprint (12-team):** **Nacua (4) → Kenneth Walker III or Hampton or A.J. Brown (21) → Jeremiyah Love / Kyren / Javonte (28) → Judkins 46.4 / McConkey 46.0 (45) → Montgomery 51.2 / Drake Maye 52.8 (52) → Fannin/Kraft/Pitts (69).**

**Slot-4 note:** pick 21 is the single best "grab the RB tier before it cliffs" spot in the draft. The RB1 pool ends at Walker (19.0). Taking A.J. Brown or an elite TE at 21 is fine, but you then need **two** RBs from picks 28 and 45, and the Dead Zone 1 names all carry flags (see §5).

---

## SLOT 5 — *both formats*

**12-team picks:** 5, 20, 29, 44, 53, 68, 77, 92, 101, 116, 125, 140, 149
**10-team picks:** 5, 16, 25, 36, 45, 56, 65, 76, 85, 96, 105, 116, 125

**R1 (pick 5):** Nacua 15%, **McCaffrey 75%**, **JSN 87%**, **Jonathan Taylor 92%**.
- **Recommended: Jonathan Taylor** (RB, IND, 6.4). Corpus VORP has him **3rd overall (108.2)** — the highest-graded RB after Gibbs/Bijan, and he's the safest volume bet in Tier 3. Bye 13.
- **JSN** (WR, SEA, 6.0) if you prefer WR. **Fade CMC here** unless you're comfortable with age-30 SF risk.

**R2 (12-team 20 / 10-team 16):** Hampton 29%, Henry 21%, **Walker 44%**, **A.J. Brown 65%**, **McBride 62%**, **Bowers 64%**, Allen 73%, **Pickens 96%**, **Love 95%**.
**R3 (12-team 29 / 10-team 25):** McBride 15%, Bowers 22%, Love 34%, Olave 32%, **Nabers 51%**, **Kyren 67%**, **Javonte 74%**, **Breece 81%**, **Jacobs 87%**, **DeVonta Smith 97%**, **Egbuka 98%**.

**Blueprint (12-team):** **Jonathan Taylor (5) → A.J. Brown or Bowers/McBride (20) → DeVonta Smith 35.0 / Nabers (29) → Colston Loveland 43.2 or Ladd McConkey 46.0 (44) → DJ Moore 52.4 / Terry McLaurin 54.0 / Drake Maye 52.8 (53) → Jalen Hurts 64.8 (68).**

**Slot-5 note:** picks 20 and 29 straddle a cliff. If you take a WR/TE at 20, your RB2 at 29 comes from Dead Zone 1. Preferred shape: **RB at 5, best-available at 20, RB or WR at 29** — and if the RBs at 29 look ugly (they will), take the WR and get your RB2 from the **Irving 45.8 / Judkins 46.4 / Swift 49.8 / Montgomery 51.2** cluster at 44/53. That's a modified Hero-RB and it's the cleanest fit for slot 5.

---

## SLOT 6 — *both formats*

**12-team picks:** 6, 19, 30, 43, 54, 67, 78, 91, 102, 115, 126, 139, 150
**10-team picks:** 6, 15, 26, 35, 46, 55, 66, 75, 86, 95, 106, 115, 126

**R1 (pick 6):** **McCaffrey 52%**, **JSN 64%**, **Jonathan Taylor 75%**, **Amon-Ra St. Brown 96%**, **Jeanty 97%**.
- Best pick: **Jonathan Taylor** if he's there; else **JSN**; else **Amon-Ra St. Brown** (WR, DET, 8.2, bye 6 — a near-lock to be available and a top-4 WR).

**R2 (12-team 19 / 10-team 15):** London 23%, **Hampton 40%**, **Henry 47%**, **Walker 55%**, **A.J. Brown 77%**, McBride 67%, Bowers 68%, Allen 77%, **Love 97%**.
**R3 (12-team 30 / 10-team 26):** Bowers 18%, Allen 20%, Love 26%, **Nabers 39%**, **Kyren 56%**, **Javonte 66%**, **Breece 71%**, **Jacobs 78%**, **DeVonta Smith 94%**, **Egbuka 97%**, **Lamar Jackson 90%**, **Loveland 95%**.

**Blueprint (12-team):** **Jonathan Taylor / JSN (6) → Kenneth Walker III or Derrick Henry or Omarion Hampton (19) → DeVonta Smith 35.0 / Zay Flowers 36.2 (30) → Loveland 43.2 or Bucky Irving 45.8 (43) → McLaurin 54.0 / Burden 54.0 / Burrow 54.6 (54) → Fannin/LaPorta/Pitts/Kraft (67).**

**Slot-6 note:** if you open WR (JSN or St. Brown), pick 19 is your last shot at a true RB1 — **Walker (55%) or Henry (47%) or Hampton (40%)**. Take one. Do not go WR-WR from slot 6; the RB you'd get at 30 is a Dead Zone 1 name.

---

## SLOT 7 — *both formats*

**12-team picks:** 7, 18, 31, 42, 55, 66, 79, 90, 103, 114, 127, 138, 151
**10-team picks:** 7, 14, 27, 34, 47, 54, 67, 74, 87, 94, 107, 114, 127

**R1 (pick 7):** McCaffrey 28%, JSN 35%, **Jonathan Taylor 46%**, **Amon-Ra St. Brown 87%**, **James Cook III 96%**, **Ashton Jeanty 94%**.
- Best: **Jonathan Taylor** (46%) → else **Amon-Ra St. Brown** (87%) → else **James Cook III** (96%, RB, BUF, 10.2 — FFC has him 8.9, the market is higher on him than ESPN's 13.3).

**R2 (12-team 18 / 10-team 14):** Barkley 13%, Chase Brown 18%, **London 47%**, **Hampton 51%**, **Henry 73%**, **Walker 66%**, **A.J. Brown 86%**, **McBride 72%**, **Bowers 72%**, Allen 81%.
- **Pick 18 is arguably the best round-2 spot in a 12-team.** Henry at 73%, A.J. Brown at 86%, and both elite TEs at ~72% — you almost always get a top-8 positional asset.

**R3 (12-team 31 / 10-team 27):** Bowers 15%, Love 20%, Nabers 28%, **Kyren 43%**, **Javonte 56%**, **Breece 60%**, **Jacobs 67%**, **DeVonta Smith 90%**, **Skattebo 97%**, **Egbuka 95%**, **Lamar 88%**, **Loveland 93%**, **Tyler Warren 98%**.

**Blueprint (12-team):** **Jonathan Taylor or St. Brown (7) → Derrick Henry or A.J. Brown or Bowers/McBride (18) → DeVonta Smith / Zay Flowers / Egbuka (31) → Tee Higgins 41.6 / Garrett Wilson 40.8 / Loveland 43.2 (42) → McLaurin/Burden/Burrow/Henderson (55) → Mike Evans 64.8 or Jalen Hurts 64.8 (66).**

---

## SLOT 8 — *both formats*

**12-team picks:** 8, 17, 32, 41, 56, 65, 80, 89, 104, 113, 128, 137, 152
**10-team picks:** 8, 13, 28, 33, 48, 53, 68, 73, 88, 93, 108, 113, 128

**R1 (pick 8):** JSN 12%, JT 19%, **Amon-Ra St. Brown 67%**, **James Cook III 91%**, **Jeanty 89%**, **Achane 97%**, **CeeDee Lamb 97%**, **Jefferson 98%**.
- Best: **Amon-Ra St. Brown** (67%) → else **James Cook III** or **De'Von Achane**. Note Achane's corpus VORP is **93.2 (7th overall)** at ADP 11.4 — the best value in the back half of round 1.

**R2 (12-team 17 / 10-team 13):** Barkley 22%, Chase Brown 30%, **London 72%**, **Hampton 62%**, **Henry 91%**, **Walker 75%**, **A.J. Brown 92%**, **McBride 77%**, **Bowers 76%**, Allen 85%.
**R3 (12-team 32 / 10-team 28):** Kyren 32%, **Javonte 47%**, **Breece 48%**, **Jacobs 54%**, **DeVonta Smith 84%**, **Zay Flowers 96%**, **Skattebo 95%**, **T-Mac 97%**, **Egbuka 93%**, **Etienne 97%**.

**Blueprint (12-team):** **St. Brown or Achane (8) → Derrick Henry (91%) or Drake London (72%) or A.J. Brown (92%) (17) → Zay Flowers 36.2 / DeVonta Smith 35.0 / T-Mac 38.8 (32) → Etienne 40.6 / Garrett Wilson 40.8 / Loveland 43.2 (41) → Burrow 54.6 / Henderson 55.2 / Jamo 57.0 (56) → Mike Evans / Hurts (65).**

**Slot-8 note:** the sim's weakest 12-team slot after 9/10. Your R1 is the bottom of a flat 8-man tier and your R2 at 17 is good but not special. **The fix: go RB-RB or RB-WR early and refuse to touch RB again until pick 41+.** From slot 8 the RB2 you'd take at pick 32 (Javonte/Breece/Jacobs) is strictly worse than Etienne/Irving/Judkins 10-14 picks later.

---

## SLOT 9 — *both formats (10-team: this is the pre-turn)*

**12-team picks:** 9, 16, 33, 40, 57, 64, 81, 88, 105, 112, 129, 136, 153
**10-team picks:** 9, 12, 29, 32, 49, 52, 69, 72, 89, 92, 109, 112, 129

**R1 (pick 9):** St. Brown 42%, **James Cook III 80%**, **Jeanty 82%**, **Achane 92%**, **Lamb 94%**, **Jefferson 95%**, **Barkley 97%**.
- Best: **De'Von Achane** (92%, VORP 93.2) or **CeeDee Lamb** (94%) or **Justin Jefferson** (95%). All three are Tier-3/4 boundary players at a discount.
- ⚠️ Achane has a coaching-change/offense-uncertainty flag on MIA in the corpus. Lamb is coming off a down year (75/1,077/3 TD) but was WR11 in PPG and WR9 excluding two limited-snap games; TD regression is the bull case.

**R2 (12-team 16 / 10-team 12):** Barkley 33%, **Chase Brown 45%**, **London 89%**, **Hampton 72%**, **Henry 98%**, **Walker 83%**, **A.J. Brown 96%**, **McBride 81%**, **Bowers 80%**, **Allen 88%**.
**R3 (12-team 33 / 10-team 29):** Kyren 22%, Javonte 37%, Breece 36%, **Jacobs 40%**, **DeVonta Smith 76%**, **Zay Flowers 92%**, **Skattebo 92%**, **T-Mac 95%**, **Egbuka 90%**, **Etienne 96%**, **Lamar 83%**, **Loveland 90%**, **Bucky Irving 98%**.

**Blueprint (12-team):** **Achane / Lamb / Jefferson (9) → Derrick Henry (98%) or Kenneth Walker III (83%) or Chase Brown (45%, ESPN-cheap) (16) → Zay Flowers / T-Mac / Egbuka / DeVonta (33) → Etienne 40.6 / Tee Higgins 41.6 / Loveland 43.2 (40) → Jamo 57.0 / Tuten 57.8 (57) → Jadarian Price 62.8 / Mike Evans 64.8 / Hurts 64.8 (64).**

**10-team slot 9 is a near-turn:** picks 9 and 12 are three apart. Treat it like a turn — take **two** of {Achane, Lamb, Jefferson, Barkley, Cook, Jeanty}. That's a top-tier start.

---

## SLOT 10 — *both formats (10-team: THE TURN)*

**12-team picks:** 10, 15, 34, 39, 58, 63, 82, 87, 106, 111, 130, 135, 154
**10-team picks:** 10, 11, 30, 31, 50, 51, 70, 71, 90, 91, 110, 111, 130

**R1 (pick 10):** St. Brown 19%, **James Cook III 63%**, **Jeanty 72%**, **Achane 82%**, **Lamb 87%**, **Jefferson 89%**, **Barkley 94%**, **McBride 96%**, **Bowers 94%**.

**10-TEAM — this is the wheel (picks 10 + 11 back-to-back):**
- @10: Cook 63%, Jeanty 72%, Achane 82%, Lamb 87%, Jefferson 89%, Barkley 94%.
- @11: Cook 44%, Jeanty 59%, Achane 67%, Lamb 75%, **Jefferson 79%**, **Barkley 89%**, **Chase Brown 96%**, **Hampton 97%**.
- **You will get two of {Cook, Jeanty, Achane, Lamb, Jefferson, Barkley, Chase Brown} with near-certainty.** That is a better two-player core than slot 1 gets from picks 1+20.
- Then picks 30/31 give you **Kyren 56%/Javonte 66%/Breece 71%/Jacobs 78%/DeVonta 94%** — a double-dip.

**12-team @15 (R2):** Jeanty 12%, Lamb 12%, Jefferson 18%, **Barkley 46%**, **Chase Brown 60%**, **London 97%**, **Hampton 80%**, **Walker 89%**, **McBride 85%**, **Bowers 83%**, **Allen 91%**.
**12-team @34 (R3):** Kyren 14%, Javonte 28%, Breece 26%, Jacobs 27%, **DeVonta 67%**, **Zay Flowers 85%**, **Skattebo 88%**, **T-Mac 91%**, **Egbuka 86%**, **Etienne 93%**, **Tee Higgins 97%**, **Loveland 88%**.

**Blueprint (12-team slot 10):** **Achane/Lamb/Jefferson (10) → Chase Brown (60%) or Saquon Barkley (46%) or Omarion Hampton (80%) (15) → Zay Flowers / T-Mac / Egbuka (34) → Etienne 40.6 / Tee Higgins 41.6 / Loveland 43.2 (39) → Jamo 57.0 / Tuten 57.8 (58) → Jayden Daniels 61.4 or Hurts 64.8 (63).**

**Blueprint (10-team slot 10, the turn):** **Achane + Jefferson (10, 11) → Kyren/Breece/Jacobs + DeVonta Smith (30, 31) → Waddle/Davante/Warren + Swift/Montgomery (50, 51) → QB + TE (70, 71).**

---

## SLOT 11 — *12-TEAM ONLY* (does not exist in a 10-team)

**12-team picks:** 11, 14, 35, 38, 59, 62, 83, 86, 107, 110, 131, 134, 155

**R1 (pick 11):** **James Cook III 44%**, **Jeanty 59%**, **Achane 67%**, **Lamb 75%**, **Jefferson 79%**, **Barkley 89%**, **Chase Brown 96%**, **Hampton 97%**, **McBride 95%**, **Bowers 93%**, **Allen 97%**.
**R2 (pick 14):** Jeanty 21%, Achane 14%, Lamb 24%, Jefferson 31%, **Barkley 59%**, **Chase Brown 74%**, **Hampton 87%**, **Walker 93%**, **McBride 88%**, **Bowers 86%**, **Allen 93%**.
**R3 (pick 35):** Javonte 21%, Breece 17%, Jacobs 17%, **DeVonta 55%**, **Zay Flowers 74%**, **Skattebo 82%**, **T-Mac 87%**, **Egbuka 82%**, **Etienne 90%**, **Garrett Wilson 97%**, **Tee Higgins 96%**, **Lamar 78%**, **Loveland 85%**, **Bucky Irving 96%**.

**Blueprint:** **Achane or Jeanty (11) → Chase Brown (74%) or Barkley (59%) (14) → Zay Flowers / DeVonta Smith (35) → Garrett Wilson 40.8 / Tee Higgins 41.6 / Etienne 40.6 (38) → Rome Odunze 61.4 / Jayden Daniels 61.4 (59) → Jadarian Price 62.8 / Mike Evans 64.8 / Hurts 64.8 (62).**

**Slot 11 is the best true turn in a 12-team.** Picks 11+14 are only 3 apart and both land inside the flat Tier-3/4 boundary. You get two of {Cook, Jeanty, Achane, Lamb, Jefferson, Barkley, Chase Brown} and can then take **two WRs at 35+38** — a perfectly-shaped RB-RB-WR-WR opening.

---

## SLOT 12 — *12-TEAM ONLY*

**12-team picks:** 12, 13, 36, 37, 60, 61, 84, 85, 108, 109, 132, 133, 156

**R1+R2 = picks 12 and 13, truly back-to-back.**
- @12: Cook 25%, **Jeanty 45%**, **Achane 48%**, **Lamb 58%**, **Jefferson 65%**, **Barkley 81%**, **Chase Brown 92%**, **Hampton 95%**, **Walker 98%**, **McBride 93%**, **Bowers 91%**, **Allen 96%**.
- @13: Cook 12%, Jeanty 32%, Achane 29%, Lamb 41%, Jefferson 48%, **Barkley 71%**, **Chase Brown 85%**, **Hampton 92%**, **Walker 96%**, **McBride 91%**, **Bowers 89%**, **Allen 94%**.

**R3 (pick 36):** Javonte 14%, **DeVonta 44%**, **Zay Flowers 60%**, **Skattebo 74%**, **T-Mac 80%**, **Egbuka 76%**, **Etienne 86%**, **Garrett Wilson 95%**, **Tee Higgins 93%**, **Lamar 74%**, **Loveland 82%**, **Bucky Irving 95%**, **Judkins 96%**, **Tyler Warren 94%**.

**Blueprint:** **Achane or Jeanty or Lamb (12) → Chase Brown (85%) or Barkley (71%) or Hampton (92%) (13) → Zay Flowers 36.2 / T-Mac 38.8 (36) → Garrett Wilson 40.8 / Tee Higgins 41.6 / Egbuka 39.0 (37) → Jayden Daniels 61.4 (60) → Rome Odunze 61.4 / Mike Evans 64.8 (61).**

**The slot-12 catch:** the gap from pick 13 to pick 36 is 22 picks — the longest wait in the draft. **Take the two safest, highest-floor players at 12/13.** This is not the place for Malik Nabers (post-ACL) or a flagged RB. Take volume: Barkley/Hampton/Chase Brown/Jefferson/Lamb.

---

# PART 5 — Turn strategy: what to double up on in 2026

Applies to **12-team slots 11-12** and **10-team slots 9-10** (and, in reverse, the 2/3 turn for slots 1-2).

### 5.1 — The ranked pairs

| Rank | Pair | Why in 2026 | Where |
|---|---|---|---|
| **1** | **RB + RB** from {Jeanty, Achane, Barkley, Chase Brown, Cook, Hampton} | The RB1 pool is **exactly 12 deep and ends at Walker (19.0)**. There is a **12.4-ADP cliff** to the next RB. Owning 2 of the 12 means you never touch Dead Zone 1 or 2. | 12-tm 12+13 or 11+14; 10-tm 10+11 |
| **2** | **RB + WR** (RB from above + Lamb / Jefferson) | Most balanced; best if the WR value at your turn clearly exceeds the RB. | Same |
| **3** | **RB + elite TE** (RB + McBride 21.6 / Bowers 22.4) | Only correct if you're at the **2/3 turn** (slots 1-3, picks 22-27). McBride/Bowers are ~90% available at picks 12-13 — too early there. | 12-tm 22-27 |
| **4** | **WR + WR** at the **3/4 turn** (picks 35-38) | This is the *right* place for a WR-WR double: DeVonta 35.0, Flowers 36.2, T-Mac 38.8, Egbuka 39.0, Garrett Wilson 40.8, Higgins 41.6 — six near-equal WRs in 7 picks. | 12-tm 35+38 or 36+37 |
| **5** ❌ | **WR + WR at the 1/2 turn** | Leaves you starting RB from Dead Zone 1 (Kyren/Javonte/Breece/Jacobs, all flagged). **Avoid.** | — |
| **6** ❌ | **QB + anything, or TE + TE** | Never. One QB, one TE — you have 4 bench spots. | — |

### 5.2 — The turn's real mechanical advantage

At the turn you don't gamble on survival. Mid-slot managers must ask "will he last 12 more picks?" You ask "which two do I want?" **That is worth roughly one tier.** In 2026 specifically, because Tier 3 (picks 5-12) is 8-wide and flat, the turn can harvest the *bottom two* of that tier at picks 12-13 and pay almost nothing for it.

### 5.3 — Turn traps

- **The 22-pick gap.** From slot 12, picks 13→36 is the longest wait in the draft. Take floor, not ceiling, at 12/13.
- **Two byes.** Do not double up on two bye-11 players (Bijan, Nacua, JSN, London, A.J. Brown, Kyren, Jacobs, Judkins, Davante, Maye, Henderson, Price, Fannin, Watson, Pitts, Kraft, Stevenson). Turn picks are half your core.
- **Positional runs start at turns.** If you take two RBs at 12/13, the next 6 managers will panic-take RBs, and the WRs you wanted at 36/37 will actually be *better* than projected. That's a feature — plan for it.

---

# PART 6 — The 2026 dead zones and how each slot navigates them

### DEAD ZONE 1 — RB, picks 26-40 (12-team rounds 3-4)
**Names:** Jeremiyah Love 26.8, Kyren Williams 30.0, Javonte Williams 31.2, Breece Hall 31.4, Josh Jacobs 31.8, Cam Skattebo 38.0, Travis Etienne Jr. 40.6.

**Why it's a dead zone — every one of these has a documented flag** (dated camp reporting from the corpus):
- **Jeremiyah Love** (ARI) — **high ankle sprain, ~4 weeks.** Also drafted into a room with Tyler Allgeier and James Conner. ESPN drafters push him 8 picks early (18.6).
- **Josh Jacobs** (GB) — **groin since ~8/6 + possible suspension.** Board flag is explicit.
- **Breece Hall** (NYJ) — **groin, 2-3 weeks.**
- **Kyren Williams** (LAR) — Blake Corum split.
- **Javonte Williams** (DAL) — committee, and the 2026 dead-zone analysis in the corpus names him specifically as a concern.
- **Cam Skattebo** (NYG) — post serious leg/ankle injury, now sharing the top of the depth chart with Tyrone Tracy Jr.

**Base rate:** *"Of the RB2 picks (RB13-RB24) last year, only James Cook, D'Andre Swift, and RJ Harvey matched or beat their ADP — well below the base rate."* **3 of 12.**

**Navigation by slot:**
- **Slots 1-4:** your pick 21-30 lands here. **Don't take these RBs.** Take an elite TE or a WR (Collins/Rice/Olave/Nabers) and get your RB2 from the 45-52 band (Irving/Judkins/Swift/Montgomery), which is 15 picks cheaper for a similar player.
- **Slots 5-8:** your pick 29-33 lands here. Same answer — go WR (DeVonta 35.0, Flowers 36.2 are ~75-95% available) and buy RB at 41-51.
- **Slots 9-12 / turn:** you skip this zone entirely by owning two top-12 RBs. **This is the turn's biggest edge in 2026.**

### DEAD ZONE 2 — RB, picks 45-92 (12-team rounds 4-8) — the classic RB2 dead zone
**Names:** Bucky Irving 45.8, Quinshon Judkins 46.4, D'Andre Swift 49.8, David Montgomery 51.2, TreVeyon Henderson 55.2, Bhayshul Tuten 57.8, Jadarian Price 62.8, Jaylen Warren 73.4, Rhamondre Stevenson 79.4, Tony Pollard 80.0, Rico Dowdle 81.8, RJ Harvey 85.6, Chuba Hubbard 89.2, Jonathon Brooks 91.8.

Corpus definition: *"the part of the ADP that produces bad running back picks at cost, often coming between the fourth and seventh rounds. A common theme tends to be bull cases that are propped up by volume projection."*

**Published 2026 targets within it:** D'Andre Swift (*"stable RB2 profile"* — and he's been *"one of the brightest stars of training camp"* per ESPN), **David Montgomery** (*"path to his largest workload in years with Houston"*), **Rhamondre Stevenson** (*"New England's clear lead back in camp, shaping up as a rock-solid fantasy starter"* — and ESPN lets him fall 30 picks to 109.3), Tony Pollard, Rico Dowdle.
**Published 2026 avoids:** **Chuba Hubbard** — *"in the sixth is flagged as a red flag, given the history of sixth-round running backs being unsuccessful,"* plus a current **hamstring, week-to-week**, plus he lost his job to Dowdle last year.

**Navigation:** you cannot skip this zone — you need 4-5 RBs. **The rule: take the volume-certain ones (Swift, Montgomery, Stevenson) and skip the committee ones (Hubbard, Brooks, Harvey/Dobbins).** Note **J.K. Dobbins has returned from Lisfranc surgery as the first RB on Denver's depth chart ahead of RJ Harvey** — that's a real, dated change most boards haven't caught.

### DEAD ZONE 3 — QB, picks 24-42
Josh Allen at 23.8 → an **18-pick gap** to Lamar at 41.8. Paying pick 24 for a QB in a 4-pt-pass-TD, 0.04/yd league costs you an entire round-2 asset for maybe 4-5 pts/week over Hurts.
**Navigation: every slot waits.** Target **Jalen Hurts 64.8** (best QB VORP on the board at 27.9) or **Jayden Daniels 61.4**. In an ESPN room, **Dak (falls to 97.7), Caleb Williams (100.0), Herbert (123.0), Lawrence (116.3)** are 20-33 picks cheaper than consensus — you can genuinely wait until round 8-9.

### DEAD ZONE 4 — TE, picks 43-50
**Colston Loveland 43.2 and Tyler Warren 50.0.** You pay a round-4/5 price for a TE who might finish TE6. Note Warren's VORP (32.6) beats Loveland's (27.9) despite going 7 picks later — if you play here, **take Warren, not Loveland**.
**Navigation:** either pay for **McBride/Bowers** (in an ESPN league, by pick ~25) or wait for the **69-73 cluster: Fannin 69.4, LaPorta 70.6, Pitts 71.0, Kraft 72.8.** **Sam LaPorta is the standout** — *"enters the season without restrictions after back surgery... a chance to outperform his TE5 ADP and rejoin the top tier."* And **Tucker Kraft falls 35.6 picks on ESPN (108.4).** Getting Kraft in round 9 of an ESPN league is a steal.

### DEAD ZONE 5 — ⚠️ ESPN K/D-ST, picks 84-125 (the biggest one)
ESPN ADP: **Brandon Aubrey K at 83.9. Texans D/ST at 86.0. Denver D/ST at 91.9. Cameron Dicker K at 108.5. Rams/Seattle D/ST at 100.0.**
Every one of those picks is a full-time RB/WR set on fire. **Navigation: identical for all 12 slots — K in round 13, D/ST in round 12, no exceptions.** Let the run happen and take Christian Watson / Brian Thomas Jr. / Rhamondre Stevenson / Tucker Kraft while others take kickers.

### NOT a dead zone — the WR "flat zone," picks 50-65
Davante Adams 50.0, DJ Moore 52.4, McLaurin 54.0, Burden 54.0, Jamo Williams 57.0, Odunze 61.4, Mike Evans 64.8. Seven WRs in 15 picks, near-identical value. **Don't reach into it — but this is where you fill, not where you lose.** From any slot, plan to take 2 WRs from this band.

---

# PART 7 — Position-by-position rules for this format

### 7.1 — RB
Get **one** of the top 12 (ends at Walker, 19.0) minimum; **two** if you're at a turn. Then skip to the 45-62 band for RB3/FLEX. **Never draft a pure handcuff** — 4 bench spots, and the 1-day waiver makes in-season backfield news actionable within 24 hours.

### 7.2 — WR
WR is **33 deep before a real cliff**. You can wait. Target 4-5 total. Best structural values: **A.J. Brown (NE, 20.6 — ESPN 27.3), Zay Flowers (36.2 — FFC has him 24.4), Tetairoa McMillan (38.8), Emeka Egbuka (39.0 — but see injury list), Christian Watson (70.4 — ESPN 95.3), Brian Thomas Jr. (78.6 — ESPN 101.7), Parker Washington (74.2 — ESPN 105.7).**

### 7.3 — TE (the binary decision)
You will roster exactly **one**. VORP gap is real: **McBride 71.8 / Bowers 61.2** vs **Fannin 22.1 / Kraft 19.6 / LaPorta 19.0** — a ~45-point VORP edge, roughly **3 pts/game** in a 9-starter league.
Three legitimate plays, in order of preference for this format:
1. **McBride or Bowers** at your round 2/3 turn (slots 1-3 especially). In an ESPN room, this means by ~pick 25.
2. **Tyler Warren at ~50** (better VORP than Loveland).
3. **Wait for LaPorta / Kraft / Pitts / Fannin at 69-73** — and on ESPN, Kraft falls to ~108, which is nearly free.
❌ Do not roster two TEs.

### 7.4 — QB
**Wait.** Take **Hurts (64.8) or Daniels (61.4)**; in an ESPN room you can wait to Dak/Caleb/Herbert at 97-123. **One QB only.** Rushing production is where the value is in this scoring.

### 7.5 — D/ST (round 12)
Draft the best **Week 1 matchup**, not the best name, then stream weekly on the 1-day waiver. Corpus Week-1 projection order: **Denver 8.3, Washington 8.0, Rams 7.8, Pittsburgh 7.6, Cincinnati 7.2, Arizona 7.2, Philadelphia 7.1, Chicago 7.0, Minnesota 6.9, SF 6.8.**
Weekly streaming rule for **your** scoring: pick the defense facing the offense with the lowest projected **total yards** (run-heavy, inefficient, backup QB), not merely the lowest projected points. The yards tier is worth up to 12 points of swing on its own.

### 7.6 — K (round 13, last pick)
Note the quirk: **60+ FG = 5 pts, same as 50-59**, and **missed FG = -1**. So there is no premium on a monster leg, and there *is* a penalty for volume kickers who miss. Prefer **accurate kickers on good offenses that stall in the 40-49 range (4 pts)**. Corpus projections: **Aubrey (DAL) 153.0, Jason Myers (SEA) 150.4, Fairbairn (HOU) 144.5, Dicker (LAC) 144.1, Mevis (LAR) 136.9, Bates (DET) 135.9.** Take whoever is left at 13.13. **Do not pay ESPN's 84th-pick price for Aubrey.**

### 7.7 — Your 1 IR slot
It's free real estate — use it. **Jordyn Tyson (WR, NO)** has a **hamstring, ~2 months, "likely opens on IR"** and is the standout stash: consensus 111 but ESPN drafters take him at **91.1**, so on ESPN he isn't cheap enough — only take him if he lasts into round 12+. **George Kittle (SF, Achilles, on PUP, "out 4+ weeks if he stays on PUP")** is the other candidate. ESPN requires an official IR/PUP designation to occupy the slot — verify before drafting for that purpose.

---

# PART 8 — Do-not-draft list (dated 2026 camp intel)

**Out for season — do not draft at any price:**
- **Ricky Pearsall** (WR, SF) — knee, PCL surgery
- **Chris Brazzell** (WR, CAR) — knee, LCL

**Avoid at current cost:**
| Player | ADP | Reason |
|---|---|---|
| **Josh Jacobs** (RB, GB) | 31.8 | Groin since ~8/6 **+ possible suspension** |
| **Chuba Hubbard** (RB, CAR) | 89.2 (ESPN 83.8) | Hamstring week-to-week; published 2026 "red flag"; lost job to Dowdle in 2025 |
| **George Kittle** (TE, SF) | 95.2 (**ESPN 83.0**) | Achilles, on PUP, age 32. *"Let someone else pay for the name."* |
| **Emeka Egbuka** (WR, TB) | 39.0 | **Toe, week-to-week — "availability genuinely uncertain, notable at his draft cost"** |
| **Jordyn Tyson** (WR, NO) | 111 (**ESPN 91.1**) | Hamstring ~2 months, likely opens on IR. IR-stash only, and only late. |
| **Zach Charbonnet** (RB, SEA) | 134.2 | On PUP. *"Don't draft for the handcuff role until he's practicing."* |
| **Kyle Monangai** (RB, CHI) | 114.7 (ESPN 116.5) | Hyperextended knee, doubtful Week 1 |
| **Kenyon Sadiq** (TE, NYJ) | — | Hernia surgery setback, doubtful Week 1 |
| **Patrick Mahomes** (QB, KC) | 105.8 | Questionable tag in camp; the Dak/Purdy/Nix tier is free anyway |
| **Any K before pick 130 / any D/ST before pick 120** | — | See Dead Zone 5 |

**Verify before drafting (news-sensitive):**
- **Jahmyr Gibbs** — contract hold-in listed resolved on the 8/21 board; confirm he practiced.
- **Malik Nabers** (28.6) — post-ACL (January tear), *"trending towards playing in Week 1... still being undervalued,"* but lost ~2 weeks to a back tweak.
- **Bucky Irving** (45.8) — cleared post-shoulder.
- **Quinshon Judkins** (46.4), **Cam Skattebo** (38.0) — both listed cleared.
- **Luther Burden III** (54.0) — groin, misses preseason. ESPN lets him fall to 75.3, which prices it.
- **Jeremiyah Love** (26.8) — high ankle sprain, ~4 weeks.
- **Mike Evans** (64.8) — quad, sitting 49ers practices on a new team; rookie De'Zhaun Stribling rising behind him.

---

# PART 9 — Surviving the 90-second clock

90 seconds is enough **only if you never do analysis on the clock.** All thinking happens between picks.

### 9.1 — The hour before the draft (order revealed ~1:00 PM)
1. **Open this document to your slot section.** Write your 13 pick numbers on paper.
2. **Recheck news.** It's Saturday of preseason Week 3 — Friday-night preseason injuries are the #1 source of a blown top-3 pick. Check Gibbs, Egbuka, Love, Jacobs, Hall, Hubbard, Nabers, Irving specifically.
3. **Load the ESPN queue 40-60 deep, in tier order** (see 9.2).
4. **Note who drafts immediately before and after you.** At a turn, you care about the two managers between your back-to-back picks — nobody else.

### 9.2 — The queue is your insurance policy (most important single item)
**If your clock expires, ESPN autopicks from your queue. If your queue is empty, it autopicks from ESPN's own rankings — which will hand you Brandon Aubrey in round 8.** That is the single worst outcome available to you.

Rules:
- **Never let the queue drop below 15 names.** Refill it during other people's picks, every round.
- **Order it by *your* tiers, not by ADP** — the queue is what you'd take, in order.
- **Purge it constantly.** A drafted player still sitting in your queue is wasted slots.
- If ESPN lets you import custom rankings pre-draft, do it — it also fixes the autopick fallback.

### 9.3 — The tier sheet (second most important)
Print or open on a second screen: **each position, grouped by tier, with a hard line between tiers.** On the clock you never compare two players — you ask one question: **"Is a tier about to break?"** If yes, take the last player in the scarce tier. If no, take the best player available. The cliff list in Part 1 is your sheet.

### 9.4 — The rule of three
**Before your turn arrives, have exactly three names ranked.** When the clock starts you're only checking which of the three got taken. Decision time: ~10 seconds. Rebuild the three immediately after picking.

### 9.5 — The scripted if-then
For each of your first 5 picks, write a one-line rule now. Example, slot 7, 12-team:
> `7: JT → else St. Brown → else Cook`
> `18: Henry → else A.J. Brown → else Bowers/McBride`
> `31: best of {DeVonta, Flowers, Egbuka} → else Skattebo`
> `42: Higgins/G.Wilson/Loveland`
> `55: McLaurin/Burden/Burrow/Henderson`

### 9.6 — Clock hygiene
- **Mute the chat.** It is the #1 clock thief.
- **Do all research during other managers' picks**, never your own.
- **Do not draft for need before round 8.** Need-based thinking is slow; best-available with a tier check is fast.
- **When a run starts, don't join it** — the corpus warns explicitly: *"Do not chase bad picks just because a run starts."* Runs create value at the positions nobody is taking.
- **Have your last two rounds pre-decided** (a D/ST and a K from the lists in §7.5-7.6) so you never think about them.

### 9.7 — Pre-draft prep, ranked by value
1. **Tier sheet with hard breaks** (Part 1)
2. **Queue loaded 40-60 deep and constantly refilled**
3. **Do-not-draft list** (Part 8)
4. **Your 13 pick numbers memorized**
5. **Bye-week grid — hard cap of 3 starters per bye, Week 11 above all**
6. **K/D-ST names pre-picked for rounds 12-13**

---

# PART 10 — The universal skeleton (works from any slot)

| Round | Target | Notes |
|---|---|---|
| 1 | **RB** (top 12) or elite WR | From slots 1-2, always RB |
| 2 | **RB or WR** — whichever tier is breaking | At a turn, this is your second top-12 RB |
| 3 | **WR** | Avoid Dead Zone 1 RBs |
| 4 | **WR or elite-adjacent TE (Warren)** | The 35-46 WR band is deep |
| 5 | **RB2/RB3** from Irving/Judkins/Swift/Montgomery (45-52) | Volume-certain only |
| 6 | **QB (Hurts 64.8 / Daniels 61.4)** or **TE (LaPorta/Kraft/Pitts/Fannin 69-73)** | Whichever cliff is closer |
| 7 | The other of QB/TE | |
| 8 | **WR** — Watson 70.4, BTJ 78.6, Parker Washington 74.2 (all ESPN-cheap) | |
| 9 | **RB** — Stevenson 79.4, Pollard 80.0, Dowdle 81.8 (Stevenson falls to 109 on ESPN) | |
| 10 | **Best-available upside WR/RB** | Bench spot 3 |
| 11 | **Best-available upside WR/RB** | Bench spot 4 |
| 12 | **D/ST** — best Week 1 matchup | |
| 13 | **K** | |

**Target final shape: QB 1 · RB 4-5 · WR 4-5 · TE 1 · D/ST 1 · K 1 = 13.**
