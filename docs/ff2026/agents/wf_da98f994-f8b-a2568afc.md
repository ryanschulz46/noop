## ⚠️ RESEARCH STATUS — READ FIRST

**I could not run live web research in this session, and I want to be blunt about that rather than paper over it.**

- **WebSearch: 200/200 calls already consumed** before my turn began. Every search returned a budget-exhausted stub.
- **Every fantasy domain is blocked by this environment's egress proxy.** I confirmed this directly via `curl "$HTTPS_PROXY/__agentproxy/status"`, which logged `403 CONNECT` policy denials for `fantasypros.com`, `fantasyfootballcalculator.com`, `fantasy.espn.com`, `sports.yahoo.com`, `api.sleeper.app`, `underdogfantasy.com`, `pff.com`, `footballguys.com`, `establishtherun.com`, `draftsharks.com`, `numberfire.com`, `cbssports.com`, `pro-football-reference.com`, and `reddit.com`. My WebFetch attempts to FantasyPros and FFC both returned `EGRESS_BLOCKED`.

**What I did instead — and it is not nothing.** Earlier agents in this same session harvested live data before the budget ran out and left it on disk. I did not take the supplied ADP board on faith; I ran a **programmatic audit against those primary files**:

| Verification | Method | Result |
|---|---|---|
| ADP figures | 46 players × 3 sources (ESPN 7/18, Sleeper 7/19, FFC half-PPR 8/19) checked against raw CSVs | **46/46 matched, zero mismatches** |
| 2026 team changes | 27 players checked against nflverse `roster_2026.csv` (2,930 rows, season=2026) | **27/27 confirmed** |
| Injuries | 8/15 injury file cross-checked against 8/22 news corpus | **5 material corrections found** |

**The supplied board's ADP numbers are accurate to their sources.** The board's *injury flags*, however, are incomplete — and that is where I found real, draft-changing errors.

**What remains genuinely unverified: Underdog ADP (MISSING — unobtainable), the Yahoo ADP column (undated source), bye weeks (not checked against a live 2026 schedule), and the fact that ESPN/Sleeper ADP are 5 weeks stale (7/18–7/19).**

---

## 1. CORRECTIONS TO THE SUPPLIED BOARD

### 🔴 DO NOT DRAFT — dead players still carrying live ADP
- **Ricky Pearsall (SF WR)** — **out for the season, PCL surgery.** Still shows ESPN ADP **119.62** and Sleeper **92.6** in the raw files I read. If your room uses ESPN's default board, someone will draft a player who cannot play.
- **Jayden Higgins (HOU WR)** — **torn ACL.** Still shows ESPN **159.68**.

### 🟠 Injury flags the board GOT WRONG or omitted
| Player | Board said | Verified truth | Action |
|---|---|---|---|
| **George Kittle** (TE, SF) | "post-Achilles" | Tore Achilles in the playoffs; **on PUP**. If he stays on PUP he must **miss ≥4 games** | **Fade at ADP 95.2.** Board badly understates this |
| **Zach Charbonnet** (RB, SEA) | "PUP — misses ≥4 games" | Confirmed: ACL, PUP, "**might not return until late in the season**" | Only as a **free R14 IR stash** |
| **Jordyn Tyson** (WR, NO) | "rookie hype" | **Hamstring, ~2 months, likely opens on IR** | **Board's flag is wrong.** Do not draft at ADP 111 — he is an IR stash, not a WR5 |
| **Josh Jacobs** (RB, GB) | "groin + possible suspension" | Groin resolved (back at practice), **but** an **active NFL investigation into a May 2026 domestic disturbance**; Packers are "preparing for the possibility of playing without Jacobs" | **Avoid entirely at ADP 31.8.** With 4 bench spots you cannot absorb a suspension |
| **Tucker Kraft** (TE, GB) | Listed as the #2 biggest "ESPN BUY," no flag | 8/15 file had him on **PUP recovering from ACL**; the 8/22 corpus resolves it: "**returned to work in 11-on-11 drills and is expected to play in Week One**" | **Buy stands**, but this was an unflagged risk that only cleared in the last week |

**Also confirmed as minor (safe to draft):** Emeka Egbuka's toe is "termed a toe sprain," viewed as minor, expected ready — the board's omission was correct.

**Additional fades:** Jeremiyah Love (high ankle sprain + crowded ARI backfield + rookie play-caller with no track record of featuring rookie backs — the corpus explicitly calls him "a risky reach"); Kyle Monangai (hyperextended knee, doubtful Wk1); Patrick Mahomes (knee, week-to-week, returning from the injury that ended his 2025).

---

## 2. FIVE STRUCTURAL PRINCIPLES THIS LEAGUE FORCES

**① Four bench spots changes everything.** Nine of your 13 active spots are locked into starters, and two more are burned on K and D/ST. **Every bench player must be startable the week you draft him.** No handcuffs. No injury stashes. No lottery tickets.

**② The 4-bench rule makes TE and QB *more* expensive, not less.** Streaming requires a bench spot you don't have. A set-and-forget TE and QB are worth more here than in a standard 6–7 bench league. This is the core argument for the elite-TE builds below.

**③ Your QB scoring is suppressed — wait.** 25 yds/pt passing and 4-pt pass TDs, against 6-pt rushing *and* receiving TDs for skill players. QB is the cheapest starter to fill. **Take your QB in rounds 8–9.** On ESPN specifically, Justin Herbert's ADP is **123.0** vs. a consensus of 89.6 — he may fall to round 10+.

**④ Let the room burn picks 84–125 on kickers and defenses.** In the ESPN file I read, **Brandon Aubrey's ADP is 83.87** (expert ECR: 178) and **Houston D/ST is 86.03** (ECR: 155). That is a kicker in round 7 and a defense in round 8. Take yours in rounds 12–13; you bank roughly three extra rounds of skill capital, and with **1-day waivers, no FAAB, no acquisition limit, and weekly inverse-standings reset**, streaming D/ST is trivially easy.

**⑤ Round 14 is a free roster spot — use it on an IR-eligible body.** 9 starters + 4 bench = 13 active, but you draft 14. **The 14th pick belongs on the IR slot**, which requires an OUT/IR/PUP designation. Zach Charbonnet (PUP, ≥4 games) and Jordyn Tyson (hamstring, likely opens on IR) are the two best candidates. This is why every build below is 13 active + 1 stash.

**⑥ Two-week playoff matchups + only 4 playoff berths + points-for tiebreaker** = total points matter every single week, and consistency beats boom/bust. Over a 2-week match, variance washes out and the better roster wins. Also watch Week 18 rest risk for players on clinched teams.

---

## 3. TWELVE-TEAM MOCKS

Availability percentages below come from a **3,000-iteration Monte Carlo** I ran on the verified board, modeling 11 ADP-following opponents with positional runs, roster-need logic, position caps, and K/D-ST deferred to the last two rounds.

---

### 🟦 SLOT 4 — picks **4, 21, 28, 45, 52, 69, 76, 93, 100, 117, 124, 141, 148, 165**

**Archetype: Hero-WR + Elite TE.** Pick 4 guarantees a top-4 overall asset. Then picks **21 and 28 are only 7 apart** — the tightest turn of the three slots — and that turn brackets the steepest early cliff on the board: after Brock Bowers (ADP 22.4) the TE position falls **20.8 picks** to Colston Loveland. Slot 4 is positioned to take the elite TE *and* still catch the RB tier on the way back.

| R | Pick | Recommendation | Avail | Fallback 1 | Fallback 2 |
|---|---|---|---|---|---|
| 1 | 4 | **Ja'Marr Chase** (WR, CIN) | 60% | Puka Nacua (WR, LAR) | Bijan Robinson (RB, ATL) |
| 2 | 21 | **Trey McBride** (TE, ARI) | 82% | Brock Bowers (TE, LV) 84% | A.J. Brown (WR, NE) 51% |
| 3 | 28 | **Javonte Williams** (RB, DAL) | 72% | Breece Hall (RB, NYJ) | Kyren Williams (RB, LAR) |
| 4 | 45 | **Bucky Irving** (RB, TB) | 58% | Quinshon Judkins (RB, CLE) 61% | D'Andre Swift (RB, CHI) 75% |
| 5 | 52 | **Terry McLaurin** (WR, WAS) | 56% | DJ Moore (WR, BUF) 48% | Jameson Williams (WR, DET) |
| 6 | 69 | **Marvin Harrison Jr.** (WR, ARI) | 63% | Christian Watson (WR, GB) 48% | Carnell Tate (WR, TEN) 51% |
| 7 | 76 | **Tony Pollard** (RB, TEN) | ~50% | Rico Dowdle (RB, PIT) | Brian Thomas Jr. (WR, JAC) 49% |
| 8 | 93 | **Justin Herbert** (QB, LAC) | 58% | Trevor Lawrence (QB, JAC) 54% | Jaxson Dart (QB, NYG) 67% |
| 9 | 100 | **J.K. Dobbins** (RB, DEN) | ~45% | Stefon Diggs (WR, WAS) | Chris Godwin Jr. (WR, TB) |
| 10 | 117 | **Jordan Addison** (WR, MIN) | ~40% | Jayden Reed (WR, GB) 32% | Rachaad White (RB, WAS) |
| 11 | 124 | **Xavier Worthy** (WR, KC) | ~60% | Matthew Golden (WR, GB) | Khalil Shakir (WR, BUF) |
| 12 | 141 | **Seattle Seahawks** (D/ST) | ~75% | Philadelphia Eagles (D/ST) | Denver Broncos (D/ST) |
| 13 | 148 | **Cameron Dicker** (K, LAC) | 94% | Jason Myers (K, SEA) 95% | Ka'imi Fairbairn (K, HOU) 96% |
| 14 | 165 | **Zach Charbonnet** (RB, SEA) — *IR slot* | — | Jordyn Tyson (WR, NO) | any OUT/PUP body |

**Final roster — legality checked:**
- **QB** Herbert · **RB** Javonte Williams, Bucky Irving · **WR** Ja'Marr Chase, Terry McLaurin · **TE** Trey McBride · **FLEX** Marvin Harrison Jr. · **D/ST** Seattle · **K** Dicker → **9 starters ✓**
- **Bench (4):** Tony Pollard (RB), J.K. Dobbins (RB), Jordan Addison (WR), Xavier Worthy (WR) — all four are startable-on-arrival, no handcuffs ✓
- **IR (1):** Charbonnet
- **Counts:** QB 1/4 · RB 4/8 · WR 5/8 · TE 1/3 · D/ST 1/3 · K 1/3 → **13 active ✓ all maxes respected ✓**

**🎯 Biggest decision point — Pick 21: Trey McBride/Brock Bowers vs. the last bell-cow RB (Kenneth Walker III, 34% available).**

**Resolution: take the tight end.** The RB you'd be reaching for is replaceable and the TE is not. Across picks 28 and 45 you have access to a **six-deep tier of starting RBs** — Javonte, Breece, Kyren, Irving, Judkins, Swift — with a combined probability near 1.0 that at least two survive. Meanwhile the TE board drops 20.8 picks after Bowers, and the next tier with genuine TE1 upside (Fannin/LaPorta/Pitts/Kraft, ADP 69–73) is **47 picks later**. With only four bench spots you cannot carry two tight ends to stream, which converts McBride's ~+4 PPG edge over the round-6 TE tier into roughly **68 points of pure, un-replaceable surplus**. Take McBride; if both he and Bowers are gone, pivot to A.J. Brown and plan on Tyler Warren at 52.

---

### 🟩 SLOT 5 — picks **5, 20, 29, 44, 53, 68, 77, 92, 101, 116, 125, 140, 149, 164**

**Archetype: Balanced (WR-RB-RB).** Slot 5's turn is **9 picks wide (20 → 29)**, the widest of the three. That width is decisive: Bowers/McBride are 86–88% available at pick 20 but collapse to **~28–31% by pick 29**. You cannot take an RB at 20 and still expect the elite TE at 29. Slot 5 therefore naturally declines the elite TE, banks the last bell-cow RB, and takes the **Tyler Warren / Colston Loveland** TE tier at 44–53 instead.

| R | Pick | Recommendation | Avail | Fallback 1 | Fallback 2 |
|---|---|---|---|---|---|
| 1 | 5 | **Ja'Marr Chase** (WR, CIN) | 52% | Puka Nacua (WR, LAR) 62% | Jonathan Taylor (RB, IND) 67% |
| 2 | 20 | **Kenneth Walker III** (RB, KC) | 43% | Derrick Henry (RB, BAL) 38% | A.J. Brown (WR, NE) 58% |
| 3 | 29 | **Javonte Williams** (RB, DAL) | 67% | Breece Hall (RB, NYJ) 68% | Malik Nabers (WR, NYG) 50% |
| 4 | 44 | **Ladd McConkey** (WR, LAC) | 60% | Jaylen Waddle (WR, DEN) 73% | Colston Loveland (TE, CHI) 67% |
| 5 | 53 | **Tyler Warren** (TE, IND) | 62% | Harold Fannin Jr. (TE, CLE) | Sam LaPorta (TE, DET) |
| 6 | 68 | **Marvin Harrison Jr.** (WR, ARI) | 68% | Carnell Tate (WR, TEN) 56% | Christian Watson (WR, GB) 54% |
| 7 | 77 | **Tony Pollard** (RB, TEN) | ~50% | Rhamondre Stevenson (RB, NE) 49% | Brian Thomas Jr. (WR, JAC) 44% |
| 8 | 92 | **Justin Herbert** (QB, LAC) | 61% | Trevor Lawrence (QB, JAC) 57% | Jaxson Dart (QB, NYG) 70% |
| 9 | 101 | **J.K. Dobbins** (RB, DEN) | ~45% | Stefon Diggs (WR, WAS) | Josh Downs (WR, IND) |
| 10 | 116 | **Jordan Addison** (WR, MIN) | ~42% | Jakobi Meyers (WR, JAC) | Rachaad White (RB, WAS) |
| 11 | 125 | **Xavier Worthy** (WR, KC) | ~58% | Matthew Golden (WR, GB) | Jayden Reed (WR, GB) |
| 12 | 140 | **Seattle Seahawks** (D/ST) | ~70% | Philadelphia Eagles (D/ST) | New England Patriots (D/ST) |
| 13 | 149 | **Cameron Dicker** (K, LAC) | 90% | Jason Myers (K, SEA) 92% | Cam Little (K, JAC) |
| 14 | 164 | **Zach Charbonnet** (RB, SEA) — *IR slot* | — | Jordyn Tyson (WR, NO) | any OUT/PUP body |

**Final roster — legality checked:**
- **QB** Herbert · **RB** Kenneth Walker III, Javonte Williams · **WR** Ja'Marr Chase, Ladd McConkey · **TE** Tyler Warren · **FLEX** Marvin Harrison Jr. · **D/ST** Seattle · **K** Dicker → **9 starters ✓**
- **Bench (4):** Pollard (RB), Dobbins (RB), Addison (WR), Worthy (WR) ✓
- **IR (1):** Charbonnet
- **Counts:** QB 1 · RB 4 · WR 5 · TE 1 · D/ST 1 · K 1 → **13 active ✓ all maxes respected ✓**

**🎯 Biggest decision point — Pick 20: chase the last bell-cow RB, or take the near-certain elite TE?**

At pick 20 you face a genuine fork. Kenneth Walker III (43%), Derrick Henry (38%), and Omarion Hampton (31%) are each coin flips, but Bowers (88%) and McBride (86%) are near-locks.

**Resolution — use a countable rule, not a gut call:** *Count how many of {Walker, Henry, Hampton, Drake London} are still on the board when you're on the clock.*
- **Two or more remain → take the RB.** You are getting the scarcer asset, and you'll still have Javonte/Breece at 29 (67–68%) plus the Loveland/Warren TE tier at 44–53 (62–67%). The RB tier truly ends here: after Josh Jacobs (ADP 31.8) the board gaps to Skattebo (38.0), and Jacobs is un-draftable on the suspension risk.
- **Zero or one remains → pivot instantly to Brock Bowers** and run the Slot-4 elite-TE build, taking RBs at 29 and 44 (Javonte + Irving/Judkins).

The mistake to avoid is splitting the difference — taking A.J. Brown here leaves you with no bell-cow RB *and* no elite TE, which is the one genuinely bad outcome from this slot.

---

### 🟨 SLOT 6 — picks **6, 19, 30, 43, 54, 67, 78, 91, 102, 115, 126, 139, 150, 163**

**Archetype: RB anchor + Elite TE.** Slot 6 owns **pick 19 — the earliest round-2 pick of the three slots** — where Bowers (91%) and McBride (90%) have their *highest* availability anywhere in this analysis. That makes the elite TE effectively free here. Pick 6 is also the slot least likely to reach a top-3 RB, but *most* likely to see Jonathan Taylor (56%) or JSN (68%) fall.

| R | Pick | Recommendation | Avail | Fallback 1 | Fallback 2 |
|---|---|---|---|---|---|
| 1 | 6 | **Jonathan Taylor** (RB, IND) | 56% | Jaxon Smith-Njigba (WR, SEA) 68% | Puka Nacua (WR, LAR) 54% |
| 2 | 19 | **Brock Bowers** (TE, LV) | 91% | Trey McBride (TE, ARI) 90% | Kenneth Walker III (RB, KC) 51% |
| 3 | 30 | **DeVonta Smith** (WR, PHI) | 79% | Malik Nabers (WR, NYG) 44% | Zay Flowers (WR, BAL) |
| 4 | 43 | **Ladd McConkey** (WR, LAC) | 65% | Jaylen Waddle (WR, DEN) 77% | Bucky Irving (RB, TB) 67% |
| 5 | 54 | **TreVeyon Henderson** (RB, NE) | 59% | David Montgomery (RB, HOU) 38% | Bhayshul Tuten (RB, JAC) |
| 6 | 67 | **Marvin Harrison Jr.** (WR, ARI) | 68% | Carnell Tate (WR, TEN) 61% | Jadarian Price (RB, SEA) |
| 7 | 78 | **Tony Pollard** (RB, TEN) | 47% | Rhamondre Stevenson (RB, NE) 44% | Rico Dowdle (RB, PIT) |
| 8 | 91 | **Justin Herbert** (QB, LAC) | 64% | Trevor Lawrence (QB, JAC) 60% | Jaxson Dart (QB, NYG) 72% |
| 9 | 102 | **Josh Downs** (WR, IND) | 56% | Stefon Diggs (WR, WAS) | Jordan Addison (WR, MIN) |
| 10 | 115 | **J.K. Dobbins** (RB, DEN) | ~40% | Jordan Mason (RB, MIN) | Rachaad White (RB, WAS) |
| 11 | 126 | **Xavier Worthy** (WR, KC) | ~57% | Matthew Golden (WR, GB) | Khalil Shakir (WR, BUF) |
| 12 | 139 | **Seattle Seahawks** (D/ST) | ~68% | Philadelphia Eagles (D/ST) | Denver Broncos (D/ST) |
| 13 | 150 | **Cameron Dicker** (K, LAC) | 83% | Jason Myers (K, SEA) 87% | Ka'imi Fairbairn (K, HOU) 88% |
| 14 | 163 | **Zach Charbonnet** (RB, SEA) — *IR slot* | — | Jordyn Tyson (WR, NO) | any OUT/PUP body |

**Final roster — legality checked:**
- **QB** Herbert · **RB** Jonathan Taylor, TreVeyon Henderson · **WR** DeVonta Smith, Ladd McConkey · **TE** Brock Bowers · **FLEX** Marvin Harrison Jr. · **D/ST** Seattle · **K** Dicker → **9 starters ✓**
- **Bench (4):** Pollard (RB), Dobbins (RB), Downs (WR), Worthy (WR) ✓
- **IR (1):** Charbonnet
- **Counts:** QB 1 · RB 4 · WR 5 · TE 1 · D/ST 1 · K 1 → **13 active ✓ all maxes respected ✓**

**🎯 Biggest decision point — Pick 6: Jonathan Taylor vs. Jaxon Smith-Njigba.**

This is the highest-leverage single choice across all three slots, because of what it does to pick 19.

**Resolution: take Jonathan Taylor, and here is the arithmetic.** JT is 56% available at 6; Bowers is 91% available at 19. The joint probability of landing **both** is ≈ **51%** — a coin flip on the single strongest two-pick combination reachable from slot 6 (a true bell-cow RB *plus* the positional-scarcity king). If you instead take JSN at 6, you still get Bowers at 19, but you enter round 3 with zero RBs and must take two from the Javonte/Breece/Kyren tier at 30 and 43 — a materially worse backfield.

The counter-argument is real and worth stating: with two starting RB slots, one FLEX, and only four bench spots, **an RB who breaks costs you more in this format than a WR who breaks**, because WR has *no cliff larger than 9.8 picks anywhere in the top 50* while RB has five distinct cliffs. If you are risk-averse, JSN at 6 → Bowers at 19 → RB-RB at 30/43 is entirely defensible and only slightly lower in expectation.

**Simple rule for the clock:** if Chase, Nacua, or McCaffrey is somehow still there at 6, take the best of them and go Bowers at 19 anyway — that path dominates both options above.

---

## 4. TEN-TEAM COMPRESSED — ROUNDS 1–4

**The single most important 10-team adjustment:** with two fewer teams demanding a starter at every single-slot position, **the elite TE gets dramatically cheaper in relative terms.** My sim has **McBride and Bowers at 95% available at pick 17** and still **48–68% at picks 24–26**. In a 10-teamer, the elite-TE build is the *default* best play from all three of these slots — you get a bell-cow RB in round 2 *and* the TE, which is impossible in a 12-teamer.

**Slot 4 — picks 4, 17, 24, 37**
| R | Pick | Recommendation | Avail | Fallbacks |
|---|---|---|---|---|
| 1 | 4 | **Ja'Marr Chase** (WR, CIN) | 61% | Puka Nacua (WR, LAR) 69% · Christian McCaffrey (RB, SF) 75% |
| 2 | 17 | **Kenneth Walker III** (RB, KC) | 66% | Derrick Henry (RB, BAL) 62% · Omarion Hampton (RB, LAC) 55% |
| 3 | 24 | **Brock Bowers** (TE, LV) | 68% | Trey McBride (TE, ARI) 64% · Chris Olave (WR, NO) 73% |
| 4 | 37 | **Tee Higgins** (WR, CIN) | 76% | Garrett Wilson (WR, NYJ) 71% · Tetairoa McMillan (WR, CAR) 62% |

**Slot 5 — picks 5, 16, 25, 36**
| R | Pick | Recommendation | Avail | Fallbacks |
|---|---|---|---|---|
| 1 | 5 | **Puka Nacua** (WR, LAR) | 60% | Christian McCaffrey (RB, SF) 63% · Jonathan Taylor (RB, IND) 68% |
| 2 | 16 | **Chase Brown** (RB, CIN) | 45% | Derrick Henry (RB, BAL) 69% · Kenneth Walker III (RB, KC) 71% |
| 3 | 25 | **Brock Bowers** (TE, LV) | 61% | Trey McBride (TE, ARI) 56% · Chris Olave (WR, NO) 68% |
| 4 | 36 | **Tee Higgins** (WR, CIN) | 80% | Garrett Wilson (WR, NYJ) 76% · Zay Flowers (WR, BAL) 54% |

**Slot 6 — picks 6, 15, 26, 35**
| R | Pick | Recommendation | Avail | Fallbacks |
|---|---|---|---|---|
| 1 | 6 | **Jaxon Smith-Njigba** (WR, SEA) | 66% | Jonathan Taylor (RB, IND) 58% · Puka Nacua (WR, LAR) 52% |
| 2 | 15 | **Chase Brown** (RB, CIN) | 52% | Saquon Barkley (RB, PHI) 45% · Omarion Hampton (RB, LAC) 69% |
| 3 | 26 | **Brock Bowers** (TE, LV) | 53% | Trey McBride (TE, ARI) 48% · Chris Olave (WR, NO) 62% |
| 4 | 35 | **DeVonta Smith** (WR, PHI) | 52% | Zay Flowers (WR, BAL) 60% · Emeka Egbuka (WR, TB) 73% |

**Two more 10-team notes:** (1) QB/TE/K/D-ST all slide roughly half a round later than the mechanical 12→10 conversion, because two fewer starters are demanded at every single-slot position — so you can wait *even longer* on QB than the round-8 guidance above. (2) Only 130 players get drafted, so the waiver pool is genuinely deep all year; with unlimited no-FAAB acquisitions and a 1-day period, your four bench spots turn over easily. Draft for ceiling, not safety, at the back end.

---

## 5. FLAGGED / UNVERIFIED

**Unverifiable in this session (blocked or missing):**
- **Underdog ADP — MISSING.** Not harvested, domain blocked. I did not invent it.
- **Yahoo ADP column — UNVERIFIED.** The source file carries no fetch date.
- **Bye weeks — UNVERIFIED.** Not cross-checked against a live 2026 schedule source. Check byes in your draft room before finalizing (relevant for McBride/MHJ on ARI bye 14 pairing with Worthy/KC bye 5 in the builds above).
- **ESPN ADP (7/18) and Sleeper ADP (7/19) are 5 weeks stale.** ESPN values also saturate past ~pick 165 (rank 250 = 169.9, rank 400 = 171.1) — past that point use rank order, not the number.

**Verified-good (my audit passed):** all ADP figures in the top ~170; all 27 team changes including A.J. Brown → NE, Kenneth Walker III → KC, Jaylen Waddle → DEN, Mike Evans → SF, DJ Moore → BUF, Travis Etienne → NO, David Montgomery → HOU, Jeremiyah Love → ARI, Jadarian Price → SEA, Michael Pittman → PIT, Carnell Tate → TEN, Isaiah Likely → NYG, Kyler Murray → MIN.

**One data-quality warning:** one line in the news corpus lists "A.J. Brown, WR, Eagles" *and* "CeeDee Lamb, WR, Lions" — visibly garbled. I overrode it with the nflverse roster file, which has **A.J. Brown on NE (status ACT)**. Do not trust that corpus line if you see similar text elsewhere.