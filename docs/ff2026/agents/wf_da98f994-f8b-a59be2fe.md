## ⚠️ READ FIRST — I could NOT run live web research this session

You asked me to verify everything against live sources. **I was unable to, and you should know exactly why before you trust a single number below.**

- **WebSearch is exhausted.** The session hit its cap (200/200 calls) before I started. Every search I attempted returned the budget error.
- **WebFetch is blocked at the network layer.** `fantasypros.com`, `fantasyfootballcalculator.com`, `fantasy.espn.com`, `sports.yahoo.com`, `api.sleeper.app`, `underdogfantasy.com`, `pff.com` — all return `EGRESS_BLOCKED` / 403 at the proxy. I confirmed this directly via `curl "$HTTPS_PROXY/__agentproxy/status"`, which logs the rejected CONNECTs.

**What I used instead:** earlier agents in this same session (16:09–16:37 today, 2026‑08‑22) *did* successfully harvest live data before the budget ran out and left it on disk. I re‑derived everything from those primary files rather than trusting the prose board you pasted. **I did not write one ADP figure from memory.**

**Crucially, I did not take the pasted board at face value — and it was wrong in three places.** See §1.

---

## 1. Verification pass — what I checked, and what the pasted board got wrong

I rebuilt the board from the raw harvested files (`board2.json`, merged from the FantasyPros 8/21 export; `ffc_half_0818.csv`; `adp_espn_half_ppr.csv`; `adp_sleeper_half_ppr.csv`; `inj.json`).

**Confirmed correct:** every ADP figure I spot‑checked matched the primaries exactly (Chase FP 3.0 / ESPN 4.7 / Sleeper 3.7 / FFC 4.1 / ECR 1; McBride FP 21.6 / FFC 38.6; Allen FP 23.8). Team changes verified in the 8/22 news corpus: **Kenneth Walker III → KC** (3yr/$43M, Super Bowl MVP), **Jaylen Waddle → DEN** (traded for 1st + 3rd), **Travis Etienne → NO**, **David Montgomery → HOU**, **Jeremiyah Love → ARI** (3rd overall pick), **Isiah Pacheco → DET**.

### 🔴 Three corrections the pasted board missed

| Player | Board said | Reality (inj.json, retrieved 8/15) | Why it matters |
|---|---|---|---|
| **Breece Hall** RB NYJ | no injury flag, ADP 31.4 | **Groin, 2–3 weeks** | A 3rd‑round RB with an unpriced soft‑tissue injury. FFC 8/19 still has him 28.4 — the market has *not* repriced. **Let him go.** |
| **Emeka Egbuka** WR TB | no injury flag, ADP 39.0 | **Toe sprain, week‑to‑week** (8/22 corpus softens this: "viewed as minor… should be ready") | Draftable, but not at 39 with 4 bench spots. |
| **Jordyn Tyson** WR NO | "rookie hype," ADP 111, no flag | **Hamstring, ~2 months, likely opens on IR** | Board treats him as a normal pick. He is an *IR stash*, not a roster player. |

### Also confirmed from the corpus (board had these right)
Ricky Pearsall **out for season** (PCL surgery) — and FFC 8/19 has already dropped him. Jayden Higgins **torn ACL** — but **FFC 8/19 STILL lists him at 118.9**, so a room drafting off a stale board will take a player who cannot play. Chris Brazzell (CAR) out for season. Josh Jacobs groin since ~8/6, no timeline, backup taking first‑team reps. Kittle on PUP (Achilles). Charbonnet on PUP. Kraft on PUP (ACL).

### 🚩 UNVERIFIED — flag these
- **A.J. Brown on NE.** The FantasyPros 8/21 export says NE. But one line in the news corpus lists him as an Eagle. That same corpus line also says "CeeDee Lamb, WR, **Lions**," which is definitively false — so I judged the line garbled and went with the FantasyPros export. **Confirm A.J. Brown's team in your draft room before picking him.**
- **Underdog ADP** — never harvested, unreachable. **MISSING**, not estimated.
- **"Anthony Lloyd"** appears in the corpus as the GB back taking first‑team reps during Jacobs' injury; the board calls the Jacobs handcuff **MarShawn Lloyd**. Likely the same player, transcribed wrong. UNVERIFIED.
- **2026 Week 15–17 schedules** — not in the harvested data, so I could not optimize for your 2‑week playoff matchups.
- ESPN/Sleeper ADP are **5 weeks stale** (7/18–7/19). ESPN values saturate past pick ~165 — I dropped them above that threshold rather than treating 171.1 as meaningful.

---

## 2. My method (so you can audit it)

**Room ADP = weighted blend:** FantasyPros consensus 8/21 (0.35) · FFC half‑PPR 8/19 (0.25) · ESPN 7/18 (0.20) · Sleeper half‑PPR 7/19 (0.15) · Yahoo (0.05), renormalized when a source is missing.

**One important modeling choice:** I deliberately **did NOT apply injury discounts to the room's ADP.** FFC 8/19 is three days old and still prices Jacobs at 27.2, Hall at 28.4, Tyson at 97.4 — the market hasn't repriced them, so the room *will* draft them there. Injury knowledge shapes **my** valuations only. (My first sim run applied the penalties to the room and produced wrong fallbacks; I corrected it.)

**Simulation:** 800–900 Monte Carlo drafts per slot. Each player drawn as ADP + Gaussian noise using **real FFC standard deviations** (Gibbs σ=0.7, Bowers σ=8.0, Kittle σ=19.3). The 11 AI managers pick on noisy ADP plus positional‑need bonuses, respect position maxima, and — per your instruction — **take K and D/ST only in the last two rounds.** Every percentage below is *P(player is on the board when you pick)*.

---

## 3. Format priors that drive every recommendation

1. **Fade QB hard.** Pass TD = 4 (not 6), INT = −2, one QB slot. Josh Allen at ADP 24 is unplayable value here. The QB9–QB15 band (Lawrence, Herbert, Dart, Stafford, Mahomes, Purdy, Nix) all land picks 88–115, and **ESPN drafters wait even longer** — Herbert's true ESPN bias is **+63 picks**. Take your QB in R9.
2. **You cannot stream TE.** Four bench spots, and waiver order **resets weekly by inverse standings** — win games and you pick *last* every week. Lock a tight end.
3. **WR is the wait position.** No cliff larger than 9.8 picks in the top 50. RB cliffs at picks 19, 32, 63, 93. TE cliffs at 22, 50, 73, and a monstrous **35‑pick cliff after Mark Andrews (~127)**.
4. **Elite D/ST is worth more here than generic ADP implies** — your league scores *yards allowed* on top of points allowed, double‑counting defensive quality.
5. **4‑of‑12 playoffs + 2‑week matchups** = variance is suppressed, so the better roster wins. Points‑for tiebreaker means never punt a week. Favor stars over depth — you can't roster depth anyway.

### 🧮 The roster-math trap nobody will tell you about

**14 rounds, but only 13 active spots (9 starters + 4 bench).** You draft 14 players and can only keep 13. So **one pick must be IR-eligible** (officially OUT/PUP) or you're force-cutting a player before Week 1.

I've built that into all three rosters: **R11 is a designated IR stash — Zach Charbonnet.** He's on PUP, so he's IR‑eligible, and he returns into a **Seattle backfield that Kenneth Walker just vacated for Kansas City.** That is a real asset occupying zero active roster space.

### 🧠 The structural edge for early slots: take D/ST at R12, K at R13

You're picking near the top, so your R14 pick is at the *very end* of the draft. With 12 teams needing 12 K + 12 D/ST across rounds 13–14, **exactly one kicker remains at pick 168.** But all three slots own a **R12/R13 turn** — and since the room takes no K/D‑ST before R13, every defense and kicker is still available at your R12 pick.

**So: D/ST at R12, K at R13, and your R14 pick becomes a completely free upside dart.** You get Houston's defense *and* Brandon Aubrey instead of the last kicker on the board. This is strictly better and costs nothing.

---

# 12‑TEAM MOCKS

## SLOT 1 — picks 1, 24, 25, 48, 49, 72, 73, 96, 97, 120, 121, 144, 145, 168

**Archetype: Elite‑TE Balanced.** The 1.01 gives you the format's best asset; the 23‑pick wait to 24/25 is brutal, but the back‑to‑back is the whole draft — it's where you buy the TE edge *and* an RB2 in one turn.

| R | Pick | **Recommendation** | Avail | Fallback 1 | Fallback 2 |
|---|---|---|---|---|---|
| 1 | 1 | **Jahmyr Gibbs** RB DET | 100% | Bijan Robinson RB ATL | Ja'Marr Chase WR CIN |
| 2 | 24 | **Trey McBride** TE ARI | 96% | Brock Bowers TE LV (93%) | Malik Nabers WR NYG (83%) |
| 3 | 25 | **Kyren Williams** RB LAR | 97% | Javonte Williams RB DAL (99%) | Cam Skattebo RB NYG (98%) |
| 4 | 48 | **Terry McLaurin** WR WAS | 70% | Jaylen Waddle WR DEN (45%) | DJ Moore WR BUF (86%) |
| 5 | 49 | **Rome Odunze** WR CHI | 97% | Jameson Williams WR DET (84%) | Luther Burden III WR CHI (86%) |
| 6 | 72 | **Tony Pollard** RB TEN | 65% | Jaylen Warren RB PIT (48%) | Rhamondre Stevenson RB NE (87%) |
| 7 | 73 | **DK Metcalf** WR PIT | 70% | Courtland Sutton WR DEN (76%) | Brian Thomas Jr. WR JAC (79%) |
| 8 | 96 | **J.K. Dobbins** RB DEN | 47% | Jonathon Brooks RB CAR (75%) | Chris Godwin Jr. WR TB (46%) |
| 9 | 97 | **Justin Herbert** QB LAC | 40% | Brock Purdy QB SF (48%) | Patrick Mahomes II QB KC (62%) |
| 10 | 120 | **Rashid Shaheed** WR SEA | 93% | Khalil Shakir WR BUF (50%) | Deebo Samuel Sr. WR SF (63%) |
| 11 | 121 | **Zach Charbonnet** RB SEA → **IR** | 54% | George Kittle TE SF | Tyrone Tracy Jr. RB NYG (78%) |
| 12 | 144 | **Houston Texans D/ST** | ~100% | Denver Broncos D/ST | Seattle Seahawks D/ST |
| 13 | 145 | **Brandon Aubrey** K DAL | ~100% | Cameron Dicker K LAC | Ka'imi Fairbairn K HOU |
| 14 | 168 | **De'Zhaun Stribling** WR SF | 59% | Jalen McMillan WR TB (88%) | Jerry Jeudy WR (86%) |

**Final roster — validated LEGAL (13 active, 4 bench, 1 IR, no position max exceeded)**

- **QB** Justin Herbert (LAC, bye 7) · **RB** Jahmyr Gibbs (DET, 6) · **RB** Kyren Williams (LAR, 11)
- **WR** Terry McLaurin (WAS, 7) · **WR** Rome Odunze (CHI, 10) · **TE** Trey McBride (ARI, 14)
- **FLEX** DK Metcalf (PIT, 9) · **D/ST** Houston (8) · **K** Brandon Aubrey (DAL, 14)
- **Bench (4):** Tony Pollard (TEN, 9) · J.K. Dobbins (DEN, 10) · Rashid Shaheed (SEA, 11) · De'Zhaun Stribling (SF, 8)
- **IR (1):** Zach Charbonnet (SEA, 11)

Counts: QB1 RB4 WR5 TE1 DST1 K1 = 13 active. Max bye overlap = 2. Every bench player is a startable flex piece — no dead handcuffs.

> **🎯 Biggest decision: pick 24 — do you spend it on Trey McBride?**
> **Yes.** McBride is available 96% of the time and Bowers 93%, but the cliff behind them is 20+ ADP points, and with four bench slots and a weekly‑resetting waiver order you cannot stream the position. One harvested projection has McBride at **14.9 half‑PPR PPG vs ~10 for the TE4–TE8 tier** — roughly a 5 PPG weekly edge nobody else in your league will have. Take the TE at 24, then the best RB at 25 (Kyren/Javonte/Skattebo are all ~97%+ — no need to reach).
> **The counter-argument, honestly:** that same projection lists **Tucker Kraft at 12.6 PPG (ADP 84)** and **Kittle at 12.1 (ADP 98)**. If true, TE is best attacked in R6–R8 and pick 24 is better spent on Nabers. I rejected it because **both Kraft and Kittle are on PUP** — Kraft's ACL gives him only "a shot at Week 1," Kittle's Achilles means 4+ weeks if he stays on the list. With 4 bench spots, a TE who misses a month is a roster hole you cannot absorb. You're paying pick 24 to buy out that risk.

---

## SLOT 2 — picks 2, 23, 26, 47, 50, 71, 74, 95, 98, 119, 122, 143, 146, 167

**Archetype: Balanced "elite trio."** The tight 23→26 turn (only 3 picks apart) is the best structural asset of the three slots — it lets you take an elite WR *and* an elite TE across the turn with minimal bleed.

| R | Pick | **Recommendation** | Avail | Fallback 1 | Fallback 2 |
|---|---|---|---|---|---|
| 1 | 2 | **Bijan Robinson** RB ATL | 66% | Jahmyr Gibbs RB DET (56%) | Ja'Marr Chase WR CIN (90%) |
| 2 | 23 | **Malik Nabers** WR NYG | 91% | Rashee Rice WR KC (70%) | Chris Olave WR NO (78%) |
| 3 | 26 | **Trey McBride** TE ARI | 92% | Brock Bowers TE LV (90%) | Kyren Williams RB LAR (90%) |
| 4 | 47 | **D'Andre Swift** RB CHI | 59% | Quinshon Judkins RB CLE (43%) | TreVeyon Henderson RB NE (75%) |
| 5 | 50 | **Terry McLaurin** WR WAS | 60% | DJ Moore WR BUF (84%) | Jameson Williams WR DET (82%) |
| 6 | 71 | **Tony Pollard** RB TEN | 63% | Jaylen Warren RB PIT (61%) | Rhamondre Stevenson RB NE (92%) |
| 7 | 74 | **DK Metcalf** WR PIT | 66% | Courtland Sutton WR DEN (72%) | Marvin Harrison Jr. WR ARI (38%) |
| 8 | 95 | **J.K. Dobbins** RB DEN | 51% | Jonathon Brooks RB CAR (76%) | Chris Godwin Jr. WR TB (51%) |
| 9 | 98 | **Justin Herbert** QB LAC | 43% | Brock Purdy QB SF (49%) | Patrick Mahomes II QB KC (62%) |
| 10 | 119 | **Deebo Samuel Sr.** WR SF | 67% | Khalil Shakir WR BUF (60%) | Rashid Shaheed WR SEA (95%) |
| 11 | 122 | **Zach Charbonnet** RB SEA → **IR** | 47% | Tyrone Tracy Jr. RB NYG (74%) | Woody Marks RB HOU (75%) |
| 12 | 143 | **Houston Texans D/ST** | ~100% | Denver Broncos D/ST | Seattle Seahawks D/ST |
| 13 | 146 | **Brandon Aubrey** K DAL | ~100% | Cameron Dicker K LAC | Ka'imi Fairbairn K HOU |
| 14 | 167 | **Denzel Boston** WR CLE | 44% | De'Zhaun Stribling WR SF (60%) | Jalen McMillan WR TB (88%) |

**Final roster — validated LEGAL**

- **QB** Justin Herbert (7) · **RB** Bijan Robinson (ATL, 11) · **RB** D'Andre Swift (CHI, 10)
- **WR** Malik Nabers (NYG, 8) · **WR** Terry McLaurin (WAS, 7) · **TE** Trey McBride (ARI, 14)
- **FLEX** DK Metcalf (PIT, 9) · **D/ST** Houston (8) · **K** Brandon Aubrey (14)
- **Bench (4):** Tony Pollard (TEN, 9) · J.K. Dobbins (DEN, 10) · Deebo Samuel Sr. (SF, 8) · Denzel Boston (CLE, 11)
- **IR (1):** Zach Charbonnet (SEA, 11)

Counts: QB1 RB4 WR5 TE1 DST1 K1 = 13. Worst bye = Week 8 (Nabers, Deebo, HOU D/ST) — one of those is a defense you stream for free.

> **🎯 Biggest decision: the ORDER of picks 23 and 26 — WR first, TE second.**
> This is the sharpest edge my simulation found. Both Nabers and McBride are on the board at 23. But look at how they decay across the three‑pick turn:
> - **Malik Nabers: 91% available at 23 → 65% at 26** (−26 pts)
> - **Trey McBride: 96% at 23 → 92% at 26** (−4 pts)
>
> **The tight end holds; the receiver does not.** Take Nabers at 23 and McBride at 26 and you capture both roughly 60% of the time. Reverse the order and you lose Nabers a third of the time for essentially zero gain. Same logic applies to Bowers (95%→90%) as the TE fallback.
> On Nabers specifically: he's post‑ACL, but the 8/15 report has him **practicing and ahead of expectations** — that's a *recovery on track* flag, materially different from Hall's or Jacobs' active soft‑tissue injuries.

---

## SLOT 3 — picks 3, 22, 27, 46, 51, 70, 75, 94, 99, 118, 123, 142, 147, 166

**Archetype: WR‑heavy / modified Zero‑RB.** This isn't a stylistic choice — it's what the board forces. Gibbs and Bijan are gone by pick 3, and the RB tier sitting at 22–27 is barely better than the one at 46–51, while the WR tier collapses across that same span.

| R | Pick | **Recommendation** | Avail | Fallback 1 | Fallback 2 |
|---|---|---|---|---|---|
| 1 | 3 | **Ja'Marr Chase** WR CIN | 74% | Puka Nacua WR LAR (78%) | Christian McCaffrey RB SF (95%) |
| 2 | 22 | **Nico Collins** WR HOU | 54% | George Pickens WR DAL (61%) | Malik Nabers WR NYG (94%) |
| 3 | 27 | **Trey McBride** TE ARI | 85% | Brock Bowers TE LV (87%) | Malik Nabers WR NYG (49%) |
| 4 | 46 | **Quinshon Judkins** RB CLE | 51% | D'Andre Swift RB CHI (70%) | TreVeyon Henderson RB NE (83%) |
| 5 | 51 | **TreVeyon Henderson** RB NE | 58% | David Montgomery RB HOU (67%) | Bhayshul Tuten RB JAC (84%) |
| 6 | 70 | **Tony Pollard** RB TEN | 67% | Jaylen Warren RB PIT (62%) | Rhamondre Stevenson RB NE (92%) |
| 7 | 75 | **Courtland Sutton** WR DEN | 65% | DK Metcalf WR PIT (60%) | Brian Thomas Jr. WR JAC (66%) |
| 8 | 94 | **J.K. Dobbins** RB DEN | 55% | Jonathon Brooks RB CAR (79%) | Chris Godwin Jr. WR TB (51%) |
| 9 | 99 | **Justin Herbert** QB LAC | 43% | Brock Purdy QB SF (48%) | Patrick Mahomes II QB KC (60%) |
| 10 | 118 | **Khalil Shakir** WR BUF | 66% | Deebo Samuel Sr. WR SF (74%) | Rashid Shaheed WR SEA (96%) |
| 11 | 123 | **Zach Charbonnet** RB SEA → **IR** | 46% | Tyrone Tracy Jr. RB NYG (64%) | Woody Marks RB HOU (67%) |
| 12 | 142 | **Houston Texans D/ST** | ~100% | Denver Broncos D/ST | Seattle Seahawks D/ST |
| 13 | 147 | **Brandon Aubrey** K DAL | ~100% | Cameron Dicker K LAC | Ka'imi Fairbairn K HOU |
| 14 | 166 | **De'Zhaun Stribling** WR SF | 57% | Denzel Boston WR CLE (44%) | Jalen McMillan WR TB (88%) |

**Final roster — validated LEGAL**

- **QB** Justin Herbert (7) · **RB** Quinshon Judkins (CLE, 11) · **RB** TreVeyon Henderson (NE, 11)
- **WR** Ja'Marr Chase (CIN, 6) · **WR** Nico Collins (HOU, 8) · **TE** Trey McBride (ARI, 14)
- **FLEX** Tony Pollard (TEN, 9) · **D/ST** Houston (8) · **K** Brandon Aubrey (14)
- **Bench (4):** J.K. Dobbins (DEN, 10) · Courtland Sutton (DEN, 10) · Khalil Shakir (BUF, 7) · De'Zhaun Stribling (SF, 8)
- **IR (1):** Zach Charbonnet (SEA, 11)

Counts: QB1 RB4 WR5 TE1 DST1 K1 = 13. *(I rejected David Montgomery at R5 despite the better fallback odds — he'd have created a four‑player Week 8 bye stack with Collins, Stribling and the Houston defense. Henderson keeps the max overlap at 2 real players.)*

> **🎯 Biggest decision: pick 22 — resist the urge to reach for RB.**
> With Chase in hand and no RB, taking Kyren Williams or Javonte Williams at 22 feels correct. **It isn't.** Compare the tiers by expert rank:
> - **RB at 22–27:** Kyren (ECR 42), Javonte (43), Jacobs (44), Skattebo (55)
> - **RB at 46–51:** Swift (57), Montgomery (61), Judkins (62), Henderson (66)
> — a drop of only **~15–20 ECR spots.**
> - **WR at 22–27:** Nico Collins (ECR 13), Pickens (19), Rice (22), Nabers (24)
> - **WR at 46–51:** Waddle (33), McLaurin (45), DJ Moore (50), Jameson Williams (54)
> — a drop of **~25–30 ECR spots.**
>
> **The WR tier falls off faster than the RB tier across exactly the span you're bridging.** Take the receiver at 22, the tight end at 27 (85%), then take *three* running backs at 46/51/70 — my sim says two of Judkins/Swift/Henderson/Montgomery survive to your R4/R5 turn in the large majority of drafts. You end with a stronger starting lineup than the RB‑reach path.

---

# 10‑TEAM COMPRESSED (Rounds 1–4)

Two fewer teams pushes every single‑slot position (QB/TE/K/D‑ST) later, because the league demands two fewer of each.

**Slot 1** — picks 1, 20, 21, 40, 41 …
| R | Pick | Recommendation | Avail | Fallbacks |
|---|---|---|---|---|
| 1 | 1 | **Jahmyr Gibbs** RB DET | 100% | Bijan Robinson RB ATL · Ja'Marr Chase WR CIN |
| 2 | 20 | **A.J. Brown** WR NE ⚠️*team unverified* | 71% | Nico Collins WR HOU (85%) · George Pickens WR DAL (85%) |
| 3 | 21 | **Trey McBride** TE ARI | 99% | Brock Bowers TE LV (99%) · Rashee Rice WR KC (97%) |
| 4 | 40 | **Bucky Irving** RB TB | 77% | Quinshon Judkins RB CLE (91%) · Ladd McConkey WR LAC (88%) |

**Slot 2** — picks 2, 19, 22, 39, 42 …
| R | Pick | Recommendation | Avail | Fallbacks |
|---|---|---|---|---|
| 1 | 2 | **Bijan Robinson** RB ATL | 67% | Jahmyr Gibbs RB DET (57%) · Ja'Marr Chase WR CIN (90%) |
| 2 | 19 | **A.J. Brown** WR NE ⚠️ | 79% | Nico Collins WR HOU (94%) · George Pickens WR DAL (94%) |
| 3 | 22 | **Trey McBride** TE ARI | 97% | Brock Bowers TE LV (96%) · Malik Nabers WR NYG (97%) |
| 4 | 39 | **Bucky Irving** RB TB | 80% | Quinshon Judkins RB CLE (94%) · Ladd McConkey WR LAC (91%) |

**Slot 3** — picks 3, 18, 23, 38, 43 …
| R | Pick | Recommendation | Avail | Fallbacks |
|---|---|---|---|---|
| 1 | 3 | **Ja'Marr Chase** WR CIN | 75% | Puka Nacua WR LAR (79%) · Jonathan Taylor RB IND (98%) |
| 2 | 18 | **Kenneth Walker III** RB KC | 74% | Omarion Hampton RB LAC (55%) · A.J. Brown WR NE (93%) |
| 3 | 23 | **Trey McBride** TE ARI | 95% | Brock Bowers TE LV (96%) · Malik Nabers WR NYG (92%) |
| 4 | 38 | **Bucky Irving** RB TB | 87% | Cam Skattebo RB NYG (46%) · Ladd McConkey WR LAC (94%) |

> **The 10‑team headline: do NOT take a tight end in round 2.** McBride and Bowers survive to **R3 at 95–99% in all three slots** — two fewer teams means the two‑man elite tier simply doesn't get picked over. Spend R2 on a premium WR and take the same tight end one round later, free.
> Second finding: **Kenneth Walker III at pick 18** is the standout 10‑team value — a Super Bowl MVP on a fresh 3yr/$43M Kansas City deal, going as RB12 while ESPN's stale board still has him at 28.2.

---

## 4. Contingency you must read before 2:00 PM: the ESPN‑default room

Your mocks assume — per your instruction — that K and D/ST go in the last two rounds. **On ESPN's own default draft board, they emphatically do not:**

| | ESPN ADP | Expert ECR | ESPN drafts them… |
|---|---|---|---|
| Brandon Aubrey (K1) | **83.9** | 178 | **94 picks early** |
| Houston D/ST | **86.0** | 155 | 69 picks early |
| Denver D/ST | 91.9 | 164 | 72 picks early |
| Cameron Dicker (K2) | 108.5 | 192 | 84 picks early |

**If your leaguemates are autodrafting or following ESPN's default queue, the K1 goes in round 7 and the top four defenses go rounds 8–9.** My R12/R13 plan collapses.

**How to tell, and what to do:** watch picks 80–100. If you see a kicker or defense come off the board there, the room is on ESPN defaults. Then: **let them burn picks 84–125 on K/D‑ST while you take the QB/TE/WR values**, and grab your own D/ST around pick 130 and K in the final round. Your kicker will be ~90% as good and you'll have banked roughly three extra rounds of skill‑position capital. **Do not panic‑match their reaches** — that's the trap the distortion sets.

## 5. Do‑not‑draft list

- **Ricky Pearsall** (SF) — **out for season**, PCL surgery. Still shows ESPN ADP 119.6 / Sleeper 92.6 on stale feeds.
- **Jayden Higgins** (HOU) — **torn ACL**. Still listed at **FFC 118.9 as of 8/19**. Someone in your league will draft him.
- **Breece Hall** (~28–34) — active groin injury, completely unpriced by the market.
- **Josh Jacobs** (~27–32) — groin since Aug 6, no timeline, backup taking first‑team reps.
- **Jordyn Tyson** (~96–110) — elite talent, but a ~2‑month hamstring. **Only** draft him as your R14 IR stash if he somehow falls that far; never as a roster player.
- **Chuba Hubbard** (~81) — hamstring, week‑to‑week. His injury is precisely why **Jonathon Brooks** is a good R8 fallback.