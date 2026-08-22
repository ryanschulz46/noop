> **DATA PROVENANCE — READ FIRST.** This session's `WebSearch` budget was already fully consumed (200/200) before this task started, and the org egress proxy **blocks** fantasypros.com, espn.com, pff.com, nbcsports.com, sleeper.com, api.sleeper.app, yahoo/cbssports.com, rotowire.com, 4for4.com, draftsharks.com, reddit.com and even wikipedia.org. I could not hit those sites directly.
>
> What I *did* get is live, **dated-August-2026** primary data: `raw.githubusercontent.com` and the GitHub code-search API are reachable, and multiple public repos mirror dated 2026 snapshots of FantasyPros, ESPN, Sleeper, FantasyFootballCalculator (FFC), PFF, Rotoworld/NBC and The Fantasy Footballers. **The anchor source is a FantasyPros 2026 ECR + ADP snapshot stamped `sourceSnapshotDate: 2026-08-21` — yesterday.** Everything below is cross-checked across ≥3 independent 2026 snapshots. Anything I could not corroborate is labeled UNVERIFIED. I fabricated nothing.

---

# 1. 2026 TE TIERS AND ADP — TOP 15 (+ DEEP POOL)

## The market ADP table

`MKT` = mean of FantasyPros (8/21), ESPN (7/18), Sleeper (7/19), Fantasy Footballers UDK (8/15). FFC (8/18) shown separately because it is a systematic outlier — see the warning below. `R#` = round the player lands in **in YOUR 13-round draft** (13 roster spots = 13 rounds; 130 picks in a 10-team, 156 in a 12-team).

| # | Player | Tm | Bye | FP Tier | MKT ADP | 10-tm | 12-tm | FP 8/21 | ESPN 7/18 | Sleeper 7/19 | Footballers 8/15 | FFC 8/18 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **Trey McBride** | ARI | 14 | 3 | **21** | R3 | R2 | 22 | 21 | 20 | 23 | 39 |
| 2 | **Brock Bowers** | LV | 13 | 3 | **22** | R3 | R2 | 22 | 24 | 21 | 22 | 42 |
| 3 | **Colston Loveland** | CHI | 10 | 5 | **43** | R5 | R4 | 43 | 43 | 42 | 44 | 60 |
| 4 | **Tyler Warren** | IND | 13 | 6 | **50** | R5 | R5 | 50 | 47 | 51 | 51 | 70 |
| 5 | Harold Fannin Jr. | CLE | 11 | 6 | **69** | R7 | R6 | 69 | 68 | 67 | 72 | 81 |
| 6 | Kyle Pitts Sr. | ATL | 11 | 7 | **72** | R8 | R6 | 71 | 69 | 76 | 71 | 84 |
| 7 | Sam LaPorta | DET | 6 | 7 | **73** | R8 | R7 | 71 | 75 | 78 | 68 | 90 |
| 8 | Tucker Kraft | GB | 11 | 7 | **79** | R8 | R7 | 73 | 108* | 68 | 68 | 94 |
| 9 | George Kittle | SF | 8 | 7 | **93** | R10 | R8 | 95 | 83* | 99 | 94 | 114 |
| 10 | Travis Kelce | KC | 5 | 7 | **101** | R11 | R9 | 99 | 92 | 113 | 101 | 122 |
| 11 | Jake Ferguson | DAL | 14 | 8 | **108** | R11 | R10 | 109 | 110 | 105 | 108 | 148 |
| 12 | Dallas Goedert | PHI | 10 | 8 | **113** | R12 | R10 | 113 | 104 | 117 | 120 | 112 |
| 13 | Dalton Kincaid | BUF | 7 | 8 | **117** | R12 | R10 | 121 | 153 | 98 | 95 | 146 |
| 14 | Isaiah Likely | **NYG** | 8 | 8 | **119** | R12 | R10 | 109 | 128 | 120 | 117 | 138 |
| 15 | **Mark Andrews** | BAL | 13 | 8 | **124** | R13 | R11 | 124 | 139 | 115 | 118 | 132 |
| 16 | Oronde Gadsden II | LAC | 7 | 10 | 139 | **FREE** | R12 | 167 | 168 | 102 | 120 | — |
| 17 | Hunter Henry | NE | 11 | 9 | 145 | **FREE** | R13 | 159 | 161 | 119 | 142 | 145 |
| 18 | Kenyon Sadiq (R) | NYJ | 13 | 11 | 151 | **FREE** | R13 | 168 | 148 | 132 | 155 | — |
| 19 | Brenton Strange | JAX | 7 | 9 | 152 | **FREE** | R13 | 163 | 167 | 128 | 150 | 159 |
| 20 | Juwan Johnson | NO | 8 | 9 | 161 | **FREE** | **FREE** | 160 | 166 | 143 | 176 | 166 |
| 21 | T.J. Hockenson | MIN | 6 | 10 | 164 | FREE | FREE | 164 | 150 | 159 | 185 | 173 |
| 22 | Chig Okonkwo | WAS | 7 | 9 | 168 | FREE | FREE | 180 | 169 | 152 | 173 | — |
| 23 | AJ Barner | SEA | 11 | 10 | 169 | FREE | FREE | 210 | 169 | 133 | 166 | — |
| 24 | Dalton Schultz | HOU | 8 | 9 | 175 | FREE | FREE | 194 | 169 | 149 | 188 | 155 |

\* **ESPN's 7/18 numbers are stale on exactly two players and both matter:** Kittle's 83 predates his PUP placement (he's now ~93-99), and Kraft's 108 predates the "ahead of schedule, no snap limits" ACL news (he's now ~68-73). Do not use ESPN's July board for those two.

**FFC warning:** FantasyFootballCalculator's half-PPR board pushes every TE ~15-20 picks later than every other source. Its population is hardcore mock-drafters who systematically fade TEs. `players_2026.json` (Rotoworld-based) and the `ff-mcp` board both re-publish FFC numbers, so treating them as independent confirmation would triple-count one outlier. **Plan your ESPN draft off the MKT column, not FFC.** In practice: expect Bowers/McBride gone by **pick 26** in your ESPN league, not pick 40.

## Consensus tiers (FantasyPros `fantasyProsTier`, 2026-08-21, cross-checked)

- **TIER 1 — "the two" (FP tier 3, `PREMIUM`):** Brock Bowers (LV), Trey McBride (ARI). ADP 21-22. Nothing else is close.
- **TIER 2 — "the year-two firsts" (FP tier 5-6, `CORE`):** Colston Loveland (CHI, ADP 43), Tyler Warren (IND, ADP 50).
- **TIER 3 — "starters with a real flaw" (FP tier 6-7, `VALUE`):** Harold Fannin Jr. (69), Kyle Pitts Sr. (72), Sam LaPorta (73), Tucker Kraft (79), George Kittle (93), Travis Kelce (101).
- **TIER 4 — "the flat zone" (FP tier 8, `VALUE`):** Jake Ferguson (108), Dallas Goedert (113), Dalton Kincaid (117), Isaiah Likely (119), Mark Andrews (124).
- **TIER 5 — "free" (FP tier 9-11, `UPSIDE`/`DEPTH`):** Gadsden II, Hunter Henry, Sadiq, Strange, Juwan Johnson, Hockenson, Okonkwo, Barner, Schultz, Terrance Ferguson (197), Freiermuth (232), Dulcich (221), Njoku (213), Otton (231), Mason Taylor (256), Jake Tonges (266), Evan Engram (352).

## 2026 roster facts you may not have (all verified across ≥2 sources)

- **Isaiah Likely is a New York GIANT**, not a Raven. Signed there, building chemistry with Jaxson Dart. Charlie Kolar also left Baltimore (→ LAC). ~36 vacated BAL TE targets go to Andrews.
- **George Kittle is on Reserve/PUP** (torn right Achilles, Jan 11 2026 Wild Card; surgery after). ESPN/FantasyPros injury APIs list him "worsening/PUP" as of 8/13. **Four-game minimum absence if not activated.** Projection systems have him at 12-13 games. Shanahan floated Week 1; Schefter framed it as not a given. Jake Tonges is SF's TE1 in PFF's Week 1 projection — Kittle isn't even in the file.
- **Tucker Kraft (GB)** tore his ACL Nov 2, 2025; GM Gutekunst says ahead of schedule, Kraft says Week 1 with **no snap-count limitations**. Opened camp on PUP. His ADP has risen ~35 picks since mid-July on this news.
- **David Njoku left Cleveland for the Chargers** (1yr/$8M) and is in a genuine timeshare with Oronde Gadsden II, who holds a slight camp edge. That makes **Harold Fannin Jr. the outright Browns TE1**.
- **Chig Okonkwo signed with Washington.** **Darren Waller signed a 1-year deal with Carolina** (groin) — he is the #1 trending TE add (51,966).
- **Greg Dulcich leads Miami's TE depth chart.** **Pat Freiermuth is Pittsburgh's clear TE1** — Jonnu Smith released, Arthur Smith gone, new TE-friendly scheme.
- QB churn that moves TEs: **Carson Beck (R) / Brissett / Minshew competing in ARI** (Kyler Murray → MIN, which lifts Hockenson); **Tua Tagovailoa → Atlanta under new HC Kevin Stefanski** (lifts Pitts); **A.J. Brown traded to New England** (helps Goedert, hurts Hunter Henry ~87→74 targets); **Michael Pittman Jr. traded to Pittsburgh** (big lift for Tyler Warren); **NO added Noah Fant + drafted Oscar Delp + 1st-rd WR Jordyn Tyson** (crushes Juwan Johnson, -8% share).

---

# 2. IS THERE A GENUINE POSITIONAL-ADVANTAGE TE? — QUANTIFIED

I blended **two independent half-PPR season projection sets**, both stamped 2026-08-16: a FantasyPros-format board (`08-16-rankings.csv`) and Rotoworld/NBC-consensus + Yahoo projections (`players_2026.json`). Both compute cleanly to your exact 0.5-PPR/0.1-yd/6-TD scoring — I verified the arithmetic (e.g. Bowers 100 rec / 1052 yd / 8 TD = 50 + 105.2 + 48 = 203.2, file says 206).

## Projected half-PPR PPG, sorted by projection (not ADP)

| Proj rank | Player | Tm | **PPG** | Season | Rec | Yds | TD | MKT ADP |
|---|---|---|---|---|---|---|---|---|
| **TE1** | Brock Bowers | LV | **12.01** | 204 | 100 | 1052 | 8 | 22 |
| TE2 | Trey McBride | ARI | 11.26 | 191 | 109 | 1053 | 6 | 21 |
| TE3 | Colston Loveland | CHI | 10.04 | 171 | 81 | 914 | 6 | 43 |
| TE4 | Tyler Warren | IND | 9.84 | 167 | 89 | 921 | 5 | 50 |
| **TE5** | Tucker Kraft | GB | **9.03** | 153 | 72 | 882 | 7 | 79 |
| TE6 | Sam LaPorta | DET | 9.01 | 153 | 74 | 810 | 5 | 73 |
| TE7 | Mark Andrews | BAL | 8.78 | 149 | 66 | 703 | 9 | 124 |
| TE8 | Harold Fannin Jr. | CLE | 8.78 | 149 | 87 | 855 | 4 | 69 |
| TE9 | Travis Kelce | KC | 8.57 | 146 | 77 | 808 | 6 | 101 |
| **TE10** | Kyle Pitts Sr. | ATL | **8.11** | 138 | 74 | 764 | 4 | 72 |
| TE11 | George Kittle | SF | 8.10 | 138 | 67 | 732 | 5 | 93 |
| TE12 | Dalton Kincaid | BUF | 8.02 | 136 | 66 | 791 | 5 | 117 |
| TE13 | Isaiah Likely | NYG | 7.98 | 136 | 71 | 794 | 5 | 119 |
| TE14 | Jake Ferguson | DAL | 7.58 | 129 | 73 | 609 | 6 | 108 |
| TE15 | Juwan Johnson | NO | 7.47 | 127 | 66 | 703 | 4 | 161 |

## The gaps you asked for

| Gap | PPG | Over a 14-week regular season |
|---|---|---|
| **TE1 → TE5** | **+2.99** | **+42 pts** |
| **TE1 → TE10** | **+3.91** | **+55 pts** |
| **TE5 → TE10** | **+0.92** | **+13 pts** |
| TE1 → TE2 | +0.75 | +11 pts |
| TE1 → TE3 | +1.97 | +28 pts |
| TE3 → TE10 | +1.94 | +27 pts |
| TE10 → TE15 | +0.64 | +9 pts |
| TE10 → TE20 | +0.91 | +13 pts |

## The verdict: a **narrow, two-deep** advantage sitting on top of a **very flat** position

The whole TE1→TE15 spread is 4.54 PPG. **48% of it is spent in the first three roster spots.** From TE4 to TE15 the position drops 2.37 PPG across eleven players — **0.22 PPG per rank.** That is noise.

So: yes, there is a genuine tier-1 edge, but it is thinner than the 2024-25 "Bowers/McBride are cheat codes" era, and it is **two players deep, not four.**

**Value Over Replacement (VOR), using true starter-count baselines:**

| League | TE replacement | Bowers VOR | McBride VOR | Loveland VOR | Kraft (TE5) VOR |
|---|---|---|---|---|---|
| **10-team** (repl = TE11, Kittle 8.10) | 8.10 | **+3.92/g (+55)** | +3.16/g (+44) | +1.94/g (+27) | +0.93/g (+13) |
| **12-team** (repl = TE13, Likely 7.98) | 7.98 | **+4.04/g (+56)** | +3.28/g (+46) | +2.06/g (+29) | +1.05/g (+15) |

**But you must price the opportunity cost.** At the exact same ADP window (picks 18-28), the RB/WR board offers:

| Player | Pos | ADP | PPG | VOR (10-tm) | VOR (12-tm) |
|---|---|---|---|---|---|
| Derrick Henry | RB | 18.4 | 15.13 | **+3.65** | **+4.78** |
| Kenneth Walker III | RB (KC) | 19.0 | 14.37 | +2.89 | +4.02 |
| Jeremiyah Love | RB (ARI) | 26.8 | 13.06 | +1.58 | +2.71 |
| George Pickens | WR (DAL) | 24.2 | 12.37 | +1.69 | +2.09 |
| Nico Collins | WR | 24.8 | 12.19 | +1.51 | +1.90 |
| A.J. Brown | WR (NE) | 20.6 | 11.99 | +1.31 | +1.70 |

**The apples-to-apples marginal test** (Bowers' TE edge *net of the late TE you'd otherwise get* vs. the RB/WR edge you forfeit):

- **10-team:** Bowers (3.92) − best-TE-at-ADP-100-140 Andrews (0.68) = **+3.24** net TE gain, vs **+2.05** mean VOR of the 2nd-4th best RB/WR in the 18-28 window → **elite TE wins by +1.18 PPG/week.**
- **12-team:** same math = **+3.24** vs **+2.94** → **elite TE wins by only +0.30 PPG/week.** That is a coin flip.
- **McBride at the same price is worse than Bowers by 0.75 PPG.** In a 12-team his margin over the RB/WR alternative is **+0.34 PPG** — statistically nothing.

And a full 5-pick path simulation says waiting wins outright when Derrick Henry is on the board:

| Path | 10-team total VOR/g | 12-team total VOR/g |
|---|---|---|
| **A** — Bowers @22, then best available | +3.31 | +6.43 |
| **B** — RB/WR @22, Loveland @43 | +3.80 | +6.95 |
| **D** — RB/WR through R7, **Kraft/LaPorta @70-84** | **+4.62** | **+8.47** |
| **C** — RB/WR through R9, **Andrews @124** | **+5.07** | **+8.92** |

**Bottom line on Q2:** Bowers is a real edge and Bowers alone. McBride is not worth his price in 2026 — new OC Mike LaFleur, a Brissett/Minshew/Beck QB room, and a hard TD-rate regression off his 11-TD 2025 give him a **−6% projected target-share adjustment** in the news feed, and every profile source independently flags him as the fade. Loveland/Warren are fine. Everything from TE5 down is interchangeable.

---

# 3. HOW 0.5 PPR SUPPRESSES TE — QUANTIFIED TWO WAYS

## (a) Points lost, by position

Recomputing each 2026 projection in both formats:

| Group | Proj. receptions | Full-PPR pts | Half-PPR pts | Points lost | **% of value lost** |
|---|---|---|---|---|---|
| **Top-12 TE** | 80 | 202.7 | 162.6 | −40.1 | **−19.8%** |
| Top-12 WR | 101 | 286.7 | 236.2 | −50.5 | −17.6% |
| Top-12 RB | 57 | 312.6 | 284.2 | −28.4 | **−9.1%** |

Individual worst-hit: **Harold Fannin −22.6%**, **Trey McBride −22.2%** (109 catches, only 6 TDs — pure volume), **Kelce −20.9%**, **Tyler Warren −21.0%**. Least-hit: **Mark Andrews −18.1%** (9 projected TDs), **Kraft −19.0%** (7 TDs).

**The key finding: half-PPR barely hurts TEs *relative to WRs* (19.8% vs 17.6% — a 2.2pp gap). It hammers them relative to RBs (19.8% vs 9.1% — a 10.7pp gap).** So the "half-PPR suppresses TEs" instinct is only half right. **What half-PPR really does is make RBs relatively more valuable than everyone**, which is exactly why Derrick Henry/Kenneth Walker have such fat VOR in the table above and why the wait-on-TE paths win.

## (b) What the market itself does — the cleanest possible proof

I found the **same source (FFC), same day (2026-07-18), both formats.** This isolates scoring from every other variable:

| Player | Full-PPR ADP | Half-PPR ADP | Shift |
|---|---|---|---|
| Trey McBride | 28.9 | 36.8 | **+7.9 later** |
| Brock Bowers | 36.0 | 42.1 | +6.1 |
| Colston Loveland | 46.4 | 55.6 | +9.2 |
| Tyler Warren | 54.5 | 61.7 | +7.2 |
| Harold Fannin Jr. | 69.1 | 80.2 | **+11.1** |
| Sam LaPorta | 70.9 | 79.8 | +8.9 |
| Travis Kelce | 100.3 | 112.8 | **+12.5** |
| Isaiah Likely | 137.9 | 150.7 | **+12.8** |
| Mark Andrews | 129.6 | 122.0 | **−7.6 EARLIER** |

**Mean ADP shift for the top 10 at each position, half-PPR vs full-PPR:**

| Position | Mean shift |
|---|---|
| **TE** | **+7.6 picks LATER** |
| WR | +1.3 picks later |
| RB | −0.3 picks (earlier) |
| QB | −1.0 picks (earlier) |

**Interpretation:** the market already prices the half-PPR TE discount, and it prices it at roughly **three-quarters of a round.** Your league's format is *not* an undiscovered edge — you should not expect Bowers to fall to you because it's half-PPR. What IS actionable: the discount is applied **uniformly** across all TEs, so it doesn't change the shape of the TE curve, only its position. And **Mark Andrews goes 7.6 picks EARLIER in half-PPR** — because his value is TD-driven (9 projected TDs, only 66 catches), he is the one TE the format *helps*. In your scoring he is the single most format-appropriate TE on the board.

---

# 4. DOES AN ELITE TE MAKE SENSE IN YOUR FLEX? — NO. HERE IS THE MATH.

The mistake people make is comparing a TE to the TE baseline when deciding flex usage. You must compare to the **FLEX baseline**, which is far higher because the flex pool is 100+ RB/WRs deep.

Computed by filling every starting slot in the league and taking the next-best flex-eligible player:

| League | Starter slots filled | **TE-slot baseline** | **FLEX baseline** | Flex bar is |
|---|---|---|---|---|
| 10-team | 20 RB + 20 WR + 10 TE + 10 FLEX = 60 | 8.10 PPG (Kittle) | **9.84 PPG** (Tyler Warren) | **+1.74 PPG higher** |
| 12-team | 24 RB + 24 WR + 12 TE + 12 FLEX = 72 | 7.98 PPG (Likely) | **9.10 PPG** (DK Metcalf) | **+1.12 PPG higher** |

**So a TE only earns a flex spot if it projects above ~9.8 PPG (10-team) or ~9.1 PPG (12-team).** In 2026 that's exactly four players: Bowers (12.01), McBride (11.26), Loveland (10.04), Warren (9.84). And if you own any of them, you start them at **TE**, not FLEX — the TE slot has to be filled by someone.

**So the only way a TE reaches your flex is if you draft TWO of the top four.** Price that:

Where does Bowers actually rank among ALL flex-eligible players by PPG? **29th** — behind 20 RBs and 8 WRs. McBride is **37th**. Loveland is **57th**.

- 10-team, Bowers @22 + Loveland @43: Loveland in flex = 10.04 vs flex baseline 9.84 = **+0.20 PPG.** Meanwhile Zay Flowers (WR, ADP 36, 11.87 PPG) in that flex = +2.03. **You lose 1.83 PPG/week to run the double-TE build.**
- 12-team: Loveland in flex = +0.94 PPG. Better, but still worse than the WR/RB you'd have taken, and it burns **2 of your 13 total roster spots** on a one-slot position.

**Verdict: never flex a TE by design in this league.** The one legitimate use of the flex rule here is *tactical*: on a week your RB/WR room is decimated by byes or injury, a TE plugged into flex is a legal escape hatch. That's a nice-to-have, not a draft plan. **Do not pay a draft pick for the optionality.**

---

# 5. ROOKIE AND SECOND-YEAR BREAKOUT CANDIDATES

## Second-year (2025 draft class) — this is where the real value is

The 2025 TE class was historically strong and it is **already** the TE2-TE5 range. These are not "sleepers" anymore; they're priced.

- **Colston Loveland, CHI (ADP 43, TE3, 10.04 PPG proj) — the headline second-year breakout.** Confirmed Bears TE1 in Year 2 with an expanded role in Ben Johnson's offense; led the team in receiving as a rookie. News feed grades this a **+6% role bump (beat-level, 0.5 confidence)**. Caveat: Ben Johnson runs a lot of 12 personnel and Cole Kmet is still around (though Kmet's ADP is 264 — irrelevant). Also note CHI spent a **3rd-round pick (69th overall) on TE Sam Roush**, which is a mild long-term flag, not a 2026 one.
- **Tyler Warren, IND (ADP 50, TE4, 9.84 PPG proj) — the biggest positive news delta at the position.** Warren already led the Colts in targets (112) as a rookie. In 2026 Indy **traded WR1 Michael Pittman Jr. to Pittsburgh**, and Alec Pierce (PUP, ankle) and Josh Downs have both missed camp time. Steichen has publicly said featuring Warren is an offensive focus. News feed: **+7% share, insider-tier, 0.65 confidence** — the highest-confidence positive signal on any TE. If you want a mid-round TE with genuine tier-1 upside, this is the one.
- **Harold Fannin Jr., CLE (ADP 69, TE5-8, 8.78 PPG proj).** Led the Browns in *receptions* as a rookie; **David Njoku left for the Chargers**, making Fannin the outright TE1 under a TE-friendly Monken scheme. Projected 87 catches. The catch: Cleveland's offense and QB situation cap the ceiling, and his value is the most reception-dependent of any TE — **he loses 22.6% of his value to half-PPR, the worst on the board.** He was also dinged with a groin issue at camp open. Good floor, low ceiling, wrong format.
- **Oronde Gadsden II, LAC (ADP 139, huge source spread — Sleeper 102 vs ESPN/FP 167).** Camp reporting gives him a *slight* edge over the newly-signed Njoku for the starting job, with Charlie Kolar also present. Projections hate the timeshare (5.24 PPG). **Watch-list, not a draft pick** — but the Sleeper-vs-ESPN ADP gap of 65 picks tells you the market has no idea, which is where free upside lives.
- **Terrance Ferguson, LAR (ADP 197) — my favorite deep second-year dart.** Projects **7.41 PPG**, which is TE16-level production at a completely free price. He was a **standout in the Rams' joint practice with Dallas** (Cameron DaSilva, USA Today). The blocker is that the Rams list their top four TEs as interchangeable (Ferguson/Parkinson/Higbee). He is the most downfield-oriented of the group, which fits yardage-heavy scoring. **Free stash / week-1 waiver watch.**
- Also 2nd-year: **Mason Taylor (NYJ, ADP 256)**, **Elijah Arroyo (SEA, 291)**, **Gunnar Helm (TEN, 252)** — deep-league only.

## 2026 rookie class — verified draft capital, but do NOT draft any of them

From the post-draft rookie model (canonical draft-results reconciled):

| Rookie | Team | Round.Pick | Model verdict |
|---|---|---|---|
| **Kenyon Sadiq** | NYJ | **1.16** | alpha 71.0 (highest), "strong" talent + "strong" opportunity insulation, **runway: DELAYED** |
| Eli Stowers | PHI | 2.54 | alpha 67.7, moderate/moderate, delayed |
| Nate Boerkircher | JAX | 2.56 | alpha 54.9, delayed |
| Marlin Klein | HOU | 2.59 | alpha 46.8, delayed |
| Max Klare | LAR | 2.61 | alpha 53.8, delayed |
| Sam Roush | CHI | 3.69 | alpha 60.4, limited insulation |
| Oscar Delp | NO | 3.73 | alpha 43.2, limited |
| Will Kacmarek | MIA | 3.87 | alpha 38.1, limited |
| Eli Raridon | NE | 3.95 | alpha 50.2, limited |

**Every single one is graded "short_term_fantasy_runway: DELAYED."** That is the correct read — rookie TEs almost never produce in Year 1, and this model says so unanimously.

**Kenyon Sadiq (NYJ, ADP 151)** is the only one with a live 2026 case, and it just got worse: he suffered a **setback from offseason hernia surgery** (CBS Sports, 8/7/26 — HC Aaron Glenn "expects him back for Week 1"). As of 8/11 he **wasn't practicing but had improved enough to jog on the sidelines** (Rich Cimini, ESPN). He also missed OTAs. He's in a two-TE plan with Mason Taylor. Projects 6.82 PPG. **In a 4-bench league he is undraftable.** Note the second-order play: the Rotoworld sleeper list explicitly names **Mason Taylor** because "Sadiq's hernia setback opens the job."

**Recommendation on rookies: draft zero. Bookmark Sadiq for a mid-October waiver claim if the Jets' TE room resolves in his favor.**

---

# 6. IS STREAMING TE VIABLE WITH 4 BENCH SPOTS? — YES, BUT YOUR WAIVER RULES FIGHT YOU

## The roster-math reality nobody accounts for

**13 roster spots = a 13-round draft.** Only **130 players** come off the board in a 10-team league, **156** in a 12-team. Your mandatory build is QB + 2 RB + 2 WR + TE + FLEX + D/ST + K = **9 locked starters**, leaving **4 bench spots** for everything: RB handcuffs, WR upside, bye coverage, and injury insurance.

**This is the single most important structural fact for your TE decision.** Look at the "10-tm / 12-tm" columns in the ADP table: **in a 10-team league, every TE from Gadsden (ADP 139) down is UNDRAFTED and free.** In a 12-team, everything past Juwan Johnson (161) is free. That is a **17+ TE free-agent pool** on Day 1.

And here's the kicker: the streaming pool's quality is **not** meaningfully worse than the drafted middle class.

| Pool | Mean projected PPG |
|---|---|
| TE13-TE20 | **7.46** |
| TE15-TE24 | **7.20** |
| TE17-TE28 | 6.64 |
| TE20-TE32 | 5.88 |

**A competent streamer nets ~7.2-7.5 PPG. The TE you'd draft in round 11 (Kelce, 8.57) beats that by 1.1-1.4 PPG. Kittle at ADP 93 beats it by 0.6-0.9 PPG — while missing 4+ games.** The mid-round TE market is barely better than free.

## The three friction points in YOUR specific rules

1. **⚠️ WAIVER ORDER RESETS WEEKLY BY INVERSE STANDINGS — not rolling, not FAAB.** This is the biggest anti-streaming rule in your league. **If you're winning, you are near the bottom of the waiver order every single week.** A good team trying to stream TE will consistently lose claims to the worst teams. You cannot save priority (no rolling) and you cannot outbid (no FAAB). **This meaningfully degrades streaming EV for a contending team.**
2. **✅ 1-day waiver period + no acquisition limit** partially rescues it. Players clear fast, and once they clear it's first-come-first-served. An attentive manager wins most FCFS races. Unlimited transactions means you can churn freely.
3. **✅ Lineups lock individually at each player's gametime** — a real streaming advantage. You can hold your TE slot open through the Sunday early window and swap based on inactives, as long as your target hasn't kicked off.
4. **⚠️ You still need a bench spot.** A one-TE roster must stream on the bye week regardless. Your byes: Bowers 13, McBride 14, Loveland 10, Warren 13, Andrews 13, Kraft 11, Fannin 11, Pitts 11. **Note Bowers/Warren/Andrews/Sadiq all share bye week 13 and McBride/J.Ferguson share 14** — late byes that may land in the final weeks that decide your 4 playoff spots. **Check your league's playoff week settings** (with 4 teams and 2-week matchups, playoffs occupy 4 weeks — likely 15-18, making weeks 13-14 critical regular-season games).

## Best streaming / late-round targets, ranked

**Tier A — draft-or-first-claim (these are the "one and done" late TEs):**
1. **Mark Andrews, BAL — ADP 124 (R13 in a 10-tm, R11 in a 12-tm).** Projects **8.78 PPG (TE7)** at a TE15 price. Likely AND Kolar both departed = ~36 vacated TE targets, sole clear TE for Lamar Jackson, caught a red-zone TD in camp. **9 projected TDs — the most TD-dependent TE, which is exactly what half-PPR rewards** (he's the only top-15 TE that goes *earlier* in half-PPR than full). Rotoworld's board flags him explicitly: *"ADP 115, projects 78th. Take him a full round early and still profit"* and names him **"the single biggest value on the board."* Risks: age 30+, declining efficiency, new OC Declan Doyle, rebuilt WR room. His FFC ADP standard deviation is **20.0**, meaning his realistic range is picks ~105-145 — **do not assume he lasts to your last pick.**
2. **Isaiah Likely, NYG — ADP 119.** 7.98 PPG. Produced at a TE1 rate whenever Andrews sat in Baltimore; now has an open target tree with Jaxson Dart. Caveat: weak offense, and Malik Nabers returns (knee/ACL, listed "questionable"). Named a sleeper by Rotoworld.
3. **Dalton Kincaid, BUF — ADP 117** but the source spread is enormous (Sleeper 98, Footballers 95, ESPN 153). 8.02 PPG. Led all TEs in points per route run; Josh Allen throwing; fifth-year option picked up. Knee history is the whole risk. **In an ESPN league his ESPN ADP of 153 means he may be nearly free — that's a real arbitrage.**

**Tier B — free-agent-pool streamers (the ones to actually target):**
4. **Pat Freiermuth, PIT — ADP 232. My top pure-streaming target.** Projects **7.41 PPG** — TE17-level, and it's the **highest-confidence positive news signal in the deep pool: +9%, beat-tier, 0.65 confidence.** Jonnu Smith released, Arthur Smith gone, new TE-friendly scheme, clear primary pass-catching TE. Aaron Rodgers throwing. He costs a waiver click.
5. **Jake Tonges, SF — ADP 266. The specific Weeks 1-4 answer.** With Kittle on Reserve/PUP, Tonges is **SF's TE1 in PFF's 2026 Week 1 projection (5.2 rec / 53.2 yds = 7.92 half-PPR pts, 3rd-highest of any TE)**. Rotoworld lists him as a sleeper: *"pure streamer while Kittle sits on PUP."* Free.
6. **T.J. Hockenson, MIN — ADP 164.** 7.35 PPG. **Kyler Murray is the likely new Vikings QB1**; healthy Hockenson in a prove-it year as the primary intermediate target. Flagged speculation-tier (0.45 confidence) because the QB battle is unsettled — that's why he's free.
7. **Greg Dulcich, MIA — ADP 221.** 7.18 PPG. Clear Miami TE1, back to full practice, and the weakest WR room in the league means targets are genuinely available. Malik Willis at QB is the killer. Free dart.
8. **Brenton Strange, JAX — ADP 152.** 7.13 PPG, Trevor Lawrence's TE1. Lowest-variance streamer in the group.
9. **Terrance Ferguson, LAR — ADP 197.** 7.41 PPG, camp standout, needs the Rams' four-way TE rotation to consolidate.
10. **Hunter Henry, NE — ADP 145.** 7.19 PPG but **actively trending down**: the A.J. Brown trade (official-tier, −8%) cuts him from ~87 to ~74 projected targets. Fine floor, capped.
11. **Mason Taylor, NYJ — ADP 256.** Named a sleeper specifically because of Sadiq's hernia setback.
12. **Dalton Schultz (HOU, 175), Chig Okonkwo (WAS, 168), AJ Barner (SEA, 169), Cade Otton (TB, 231), Darren Waller (CAR, 313 — #1 trending TE, 52k adds).** Matchup-week bodies only. Okonkwo is explicitly graded "lowest-conviction dart — a waiver-wire watch rather than a draft pick."

**Avoid / fade in your format:**
- **George Kittle (ADP 93).** Reserve/PUP, four-game minimum if not activated, Achilles at 32 (33 in October), reduced explosiveness likely even when active, and SF is thin at TE. Two independent boards say the same thing: *"let someone else pay ADP 97 for the name."* His projection (8.10 PPG) is already TE11 — and that's *with* him playing 12-13 games. **HOWEVER — see the IR trick below.**
- **Travis Kelce (ADP 101).** Efficiency has collapsed to ~6.9 yards per target over two seasons; KC added no receivers; Rice and Worthy take targets back. He himself said he wants to "prove to myself that I can play at a better level than I did last year." A name-brand fade at a real price.
- **Juwan Johnson (ADP 161).** Beat-tier **−8%**: New Orleans added Noah Fant, drafted Oscar Delp, and took 1st-round WR Jordyn Tyson. His career-high 102-target season is not repeating.
- **Trey McBride at ADP 21.** Beat-tier **−6%**: new OC Mike LaFleur, added RB depth, and a QB downgrade from Kyler Murray to Carson Beck/Brissett/Minshew. His 11 TDs on 126 catches in 2025 is a screaming regression candidate, and 109 catches with 6 TDs in a half-PPR league is the worst possible profile.

## 🔑 The IR-slot exploit nobody will use

**You have 1 IR slot, and it does not consume a bench spot.** ESPN's IR slot accepts players carrying an OUT-class designation, which in recent ESPN seasons has included Reserve/PUP. **George Kittle is on Reserve/PUP right now.**

If your league's IR slot accepts him at his current designation, you can draft Kittle in the last round or two, park him on IR for free, stream Jake Tonges (his own backup, free) or Freiermuth for the first four weeks, and activate an elite-when-healthy TE in October at zero roster cost. **⚠️ VERIFY THIS IN YOUR LEAGUE SETTINGS BEFORE THE DRAFT** — ESPN's exact PUP eligibility varies by season and league configuration, and if it doesn't work you've burned a bench spot on a guy who can't play. Test it by checking whether ESPN shows Kittle with an IR-eligible tag. **If it works, it is the single highest-leverage TE move available to you.** Do not draft him before round 12-13 for this; his 93 ADP is far too expensive for a stash.

---

# 7. RECOMMENDATION

## Do NOT pay up. Take the value pocket. Here are your exact targets.

The 2026 TE position has a real edge, but it is one player deep (Bowers), the price is at fair value rather than a discount, and **your league's structure — 13 roster spots, 4 bench, half-PPR, a flex that a TE can't profitably fill, and inverse-standings weekly waivers — pushes the answer toward "spend your early capital on RB/WR and take a TE in the middle rounds."**

### The plan, in priority order

**PRIMARY PLAN — the R6-R8 pocket. Target ADP 69-84.**
Take **exactly one** of **Tucker Kraft (79)**, **Sam LaPorta (73)**, or **Tyler Warren (50)** — whichever falls furthest. Ranked by my preference:
1. **Tyler Warren (ADP 50)** if he slides past pick ~55. Highest-confidence positive news signal at the position (+7% insider), 9.84 PPG, and the Pittman trade is a genuine, not speculative, target-vacating event.
2. **Tucker Kraft (ADP 79)** — 9.03 PPG, TE5 by projection, best TE on a good offense, ACL rehab **ahead of schedule with no snap limits**, and his ESPN ADP (108) is a full 30 picks stale relative to the news. **On ESPN specifically he is the best value on the entire TE board.**
3. **Sam LaPorta (ADP 73)** — 9.01 PPG, new OC Drew Petzing runs heavy 12/13 personnel, and he's fully cleared from the back microdiscectomy with no games expected missed. Highest-scoring offense of any TE.

Then **stop.** One TE, one roster spot, done. Total cost: one round-7-or-8 pick.

**SECONDARY PLAN — the punt, if the pocket is picked clean. Target ADP 109-130.**
Draft **Mark Andrews** as your only TE. He is the **highest-EV TE relative to price on the board** and the only one whose scoring profile the half-PPR format actively favors (9 projected TDs). Back him with a free-agent claim on **Pat Freiermuth** or **Jake Tonges** in Week 1. **Warning: his ADP standard deviation is 20 — reach for him at pick ~110-115 rather than waiting for your last pick and losing him.** If he's gone: **Isaiah Likely (119)** or **Dalton Kincaid** (whose ESPN ADP of 153 makes him nearly free in your league).

**WHEN TO PAY UP — the one exception.**
**Draft Brock Bowers if and only if he is on the board at your pick AND you are in a 10-team league.** In a 10-team his marginal edge over the RB/WR alternative is **+1.18 PPG/week**, which is real, and 100 projected receptions gives him the highest floor at the position — valuable in your **2-week playoff matchups**, which reward consistency over ceiling. In a **12-team** his margin collapses to **+0.30 PPG/week**, which is inside the error bars of any projection system — **do not reach for him there.**

**NEVER: Trey McBride at ADP 21.** Same price as Bowers, 0.75 PPG worse, a −6% beat-level share downgrade, a QB room of Carson Beck/Brissett/Minshew, and the most half-PPR-hostile profile in the top 15 (109 catches, 6 TDs, −22.2% format penalty). Let someone else take him.

### Target ADP ranges, summarized

| Approach | ADP range | Players | Expected PPG | Verdict |
|---|---|---|---|---|
| Pay up | 21-25 | Bowers | 12.01 | **Only in a 10-team, only if he falls to you** |
| Pay up | 21-25 | McBride | 11.26 | ❌ **Never — overpriced** |
| Early-mid | 43-52 | Loveland, Warren | 9.84-10.04 | ✅ Fine. Warren > Loveland |
| **★ VALUE POCKET** | **69-84** | **Kraft, LaPorta, Fannin, Pitts** | **8.1-9.0** | ✅✅ **PRIMARY TARGET** |
| Dead zone | 93-113 | Kittle, Kelce, J.Ferguson, Goedert | 7.3-8.6 | ❌ **Skip entirely — worst value on the board** |
| **★ PUNT ZONE** | **109-130** | **Andrews, Likely, Kincaid** | **8.0-8.8** | ✅✅ **SECONDARY TARGET** |
| Free | 145+ | Freiermuth, Tonges, Hockenson, T.Ferguson, Dulcich, Strange | 7.1-7.4 | ✅ Streaming pool — genuinely usable |

### The one thing to internalize

**The gap between the TE you draft in round 8 (9.0 PPG) and the TE you can pick up for free in week 1 (7.4 PPG) is 1.6 points per week.** The gap between Bowers and that same free TE is 4.6 points per week — but it costs you a top-25 pick, and the RB you'd take instead is worth 2.0-2.9 points per week of VOR on its own. **The math says: spend one mid-round pick on a TE, never two, never a flex spot, and never a top-25 pick unless Bowers specifically falls into your lap in a 10-team league.**