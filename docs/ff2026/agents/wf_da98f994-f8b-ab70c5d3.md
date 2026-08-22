> **Sourcing note.** `WebFetch` was blocked at the network egress proxy for every fantasy domain attempted (FantasyPros, CBS, NBC, PFF, Footballguys, SI, ESPN, DraftSharks, FTN, DirecTV, Yahoo). All external facts below come from live **WebSearch** result summaries run today (Aug 22, 2026), and the session's search budget was exhausted at 200 calls. Every ADP and stat is attributed. Figures I computed myself are labeled **[my calc]**. Anything I could not confirm is labeled **UNVERIFIED**.

---

## 1. The 2026 elite TE landscape and real ADP

**Verified 2026 ADP — note the wide platform spread, which matters a lot for you:**

| TE | Team | Underdog ADP | Market/consensus | CBS composite |
|---|---|---|---|---|
| Brock Bowers | LV | **20** | 21–22 (TE1) | 27.6 |
| Trey McBride | ARI | **24.5** | 23–27 | 27.2 |
| Colston Loveland | CHI | — | **41** (TE3) | 46.7 |
| Tyler Warren | IND | — | **59** (TE4) | 55.9 |
| Sam LaPorta | DET | — | — | **70.4** |
| Kyle Pitts | *team UNVERIFIED* | — | — | **71.1** |
| Tucker Kraft | GB | — | — | **76.3** |
| Jake Ferguson | DAL | — | **TE12**, ~Round 10 | — |

Bleacher Nation (8/19/26) has Bowers climbing seven spots to **No. 21 overall**, passing McBride at **No. 27**.

**This is the single most actionable ADP fact for you:** best-ball/Underdog rooms take these TEs at 20–24; ESPN-flavored composites take them at **27–28**. You are in an **ESPN redraft**. Plan for McBride/Bowers to be there around **25–30**, not 20.

**Verified 2025 actuals (the basis for everything below):**
- **Trey McBride** — 126 rec / 1,239 yds / 11 TD on 169 targets, 17 games. **18.7 PPR PPG, led all TEs** (ESPN/Bowen). Set the single-season TE reception record. Half-PPR that season = **14.9 PPG** — confirmed independently by a half-PPR PPG leaderboard that also lists Kraft 12.6, Kittle 12.1, Bowers 12.0, Goedert 10.3.
- **Brock Bowers** — 64 rec / 680 yds / 7 TD on 86 targets, **12 games** (Week 1 knee injury lingered all year). 14.7 PPR PPG, ~11.8–12.0 half-PPR.
- **Colston Loveland** — 10.3 PPR PPG as a rookie; **Weeks 9–18: 63 targets in 10 games, 47 rec / 597 yds / 6 TD.**
- **Tyler Warren** — top-five TE as a rookie, led IND with 112 targets; **10.5+ half-PPR points in 6 of 10 games with a healthy Daniel Jones.**
- **Dallas Goedert** — **led all TEs with 11 TDs**, finished **TE6 from a TE16 ADP**.
- **Jake Ferguson** — finished **fantasy TE5**.
- LaPorta 9.1 half-PPR PPG in 9 games (back). Kincaid 8.4 half-PPR PPG. Juwan Johnson finished TE12 in PPR PPG.

**Health, verified as of Aug 2026:** Bowers practiced at full speed through OTAs/minicamp, went full-go in Texans joint practices with **no knee brace or compression tape**, caught a red-zone TD. McBride: no reported issues. Loveland: clean bill of health entering Year 2.

### The PPG gap under YOUR scoring (0.5/rec, 0.1/yd, 6-pt TD) — [my calc]

I built 2026 projections off verified 2025 usage with standard TD regression, then scored them in your exact format:

| Slot | Player / band | Proj line | Half-PPR total | **PPG** |
|---|---|---|---|---|
| TE1 | McBride | 108/1,150/8 | 217.0 | **12.8** |
| TE2 | Bowers | 105/1,150/7 | 209.5 | **12.3** |
| TE3 | Loveland | 78/900/7 | 171.0 | **10.1** |
| TE4 | Warren | 78/850/6 | 160.0 | **9.4** |
| TE6 | LaPorta/Kraft/Pitts band | 70/780/6 | 149.0 | **8.8** |
| TE12 | Ferguson/Schultz/Henry band | 60/640/5 | 124.0 | **7.3** |
| TE13 (12-tm baseline) | — | 58/620/5 | 121.0 | **7.1** |
| TE16+ (waiver pool) | — | 52/540/4 | 104.0 | **6.1** |

**Gaps:** TE1−TE3 = 2.7 · TE1−TE6 = **4.0** · TE1−TE12 = **5.5** · TE1−waiver = **6.7** · **TE4−TE12 = only 2.1** · **TE6−TE12 = only 1.5**.

**Sanity check against published data:** FantasyPros' 2026 half-PPR VORP work reports that **only McBride, Bowers and Loveland clear 50 half-PPR VORP points**, and that **the projection gap from TE4 (Warren) to TE14 (Ferguson) is under 30 points** — i.e. **under 1.8 PPG across a full season.** My model puts that band at ~36 points. My curve is, if anything, *more* generous to TEs than consensus. The shape is identical: **a two-man cliff, a one-man shelf, then a swamp.**

---

## 2. Does the elite-TE edge survive half-PPR? Yes — but it loses ~29% of it

The prompt's framing ("a 90-reception TE loses 45 points") is arithmetically right but **measures the wrong thing.** 90 rec × 0.5 = 45 points lost = 2.6 PPG. McBride at 108 projected catches loses **54 points = 3.2 PPG**. But you don't play McBride against zero — you play him against the TE you'd otherwise be forced to start. **What matters is the differential haircut.** [my calc]:

| | Elite | Baseline | Rec gap | Half-PPR points removed from the *gap* |
|---|---|---|---|---|
| TE | McBride 108 rec | TE13 58 rec | 50 | **25.0 pts = 1.47 PPG** |
| WR | A.J. Brown 95 rec | WR30 70 rec | 25 | **12.5 pts = 0.74 PPG** |

Half-PPR strips **1.47 PPG** off the elite TE's edge but only **0.74 PPG** off the elite WR's. **Net relative penalty to the elite TE: 0.73 PPG.**

Run end-to-end [my calc]:

| Format | McBride VBD | A.J. Brown VBD | **TE-over-WR edge** |
|---|---|---|---|
| Full PPR | +7.12 PPG | +4.59 PPG | **+2.53 PPG** |
| **Half PPR (your league)** | **+5.64 PPG** | **+3.85 PPG** | **+1.79 PPG** |

**The elite-TE edge shrinks by 29.2% in half-PPR — and survives.** It does not vanish.

**Why it survives:** TE13 catches ~58 balls to McBride's ~108, so scaling receptions down cuts a big chunk out of that gap. But WR30 catches ~70 to A.J. Brown's ~95 — the WR curve is much flatter in reception volume, so the WR gap barely moves either way. The elite TE keeps most of his structural advantage because **his baseline is genuinely awful in a way no WR baseline is.**

**The nuance almost everyone gets wrong:** half-PPR is not specifically anti-TE relative to WR — elite TEs and elite WRs catch nearly the same number of passes (108 vs 95), so the *absolute* haircut is nearly identical (54 vs 47.5 points). **Half-PPR is anti-pass-catcher relative to RB.** The real format effect in your league is that it quietly promotes RBs, not that it demotes TEs versus WRs.

---

## 3. TE + TE-in-flex: no. And here is the formal reason.

**Published 2026 work exists.** Fantasy Alarm ran a **"Double Elite TE Strategy 2026: Should You Draft Two Elite Tight Ends?"** piece, plus a companion **"Yin & Yang Tight End Strategy 2026"** (late-round blueprint) and **"Elite Tight End Strategy 2026."** Critically, the double-elite article frames the build as **situational and exploitative** — a way to "discipline" opponents who get overconfident about punting TE — **not as a default recommendation.** FantasyPros' TE-Premium guide is explicit that **"in TE Premium it is almost a given to start 2 TE"** — and your league is **not** TE-premium. There is no TE bonus anywhere in your scoring; a TE reception is worth exactly what a WR reception is worth.

**The formal argument against it:** *positional scarcity generates value only inside a slot restricted to that position.* The moment a TE occupies your FLEX, he stops competing against TE13 and starts competing against the entire RB/WR pool. **His scarcity premium evaporates completely.** A TE scoring 10.1 in your flex is worth exactly as much as a WR scoring 10.1 in your flex — not one point more.

So a second TE must beat the WR/RB you'd otherwise take **on raw points**, not on VBD. Test it at Loveland's ADP [my calc]:

- Loveland at pick ~41: **10.1 half-PPR PPG**
- A WR taken at pick ~41 (roughly WR20–24): **~10.2–10.5 PPG**
- An RB taken at pick ~41 (roughly RB22–26): **~10.0–10.5 PPG**

**Dead even at best, with worse weekly floor variance** (TEs are lower-volume and more TD-dependent, and your 6-pt TDs amplify that swing). The Footballguys community consensus on this exact question lands in the same place: in standard PPR "you should still prioritize top-notch running backs and receivers," and **"avoid passing on better receivers or running backs just to draft mediocre tight ends."**

**Then add your specific constraint:** with only 4 bench spots and 2 already burned on K/D-ST, a double-TE build spends **2 of 11 skill roster spots** on a position with **1 mandatory start.** That is a structural waste.

**The one legitimate case:** if you land McBride/Bowers *and* Loveland falls past 45, you'd own 2 of the only 3 TEs above 50 half-PPR VORP in a league where 9–11 rivals need a starter. With **unlimited trades and only a 3-vote veto**, that's a genuine leverage asset. Draft the second TE to *trade* him, never to start him in your flex.

---

## 4. The VBD arithmetic, done properly

**Setting the baselines.** Your league starts QB1/RB2/WR2/TE1/FLEX1. Assuming the flex skews ~60% RB / ~35% WR / ~5% TE (correct for half-PPR):

| Position | 12-team demand | Baseline | 10-team demand | Baseline |
|---|---|---|---|---|
| TE | 12 + ~0.6 | **TE13 = 7.1 PPG** | 10 + ~0.5 | **TE11 = 7.6 PPG** |
| WR | 24 + ~4 | **WR30 = 9.4 PPG** | 20 + ~3.5 | **WR25 = 10.2 PPG** |
| RB | 24 + ~7 | **RB31 = 8.6 PPG** | 20 + ~6 | **RB26 = 9.4 PPG** |

**Who you actually give up at picks 21–30 — verified 2026 ADP:** Rashee Rice **22.5**, George Pickens **22.7**, A.J. Brown **23.4**, Nico Collins **26.2**, Jeremiyah Love **26.4** (rookie RB), Breece Hall **31.5**, Javonte Williams **34.9** (DAL), Josh Jacobs **35.9**, Malik Nabers **34.4**. Josh Allen goes at **20** — but with **4-pt pass TDs and −2 INTs** your league is deeply QB-suppressed, so Allen is not a real competitor for that pick.

**The head-to-head [my calc]:**

| Player | Half-PPR PPG | **VBD 12-tm** | **VBD 10-tm** |
|---|---|---|---|
| **Trey McBride** | 12.76 | **+5.64** | **+5.20** |
| **Brock Bowers** | 12.32 | **+5.20** | **+4.76** |
| A.J. Brown | 13.26 | +3.85 | +3.06 |
| George Pickens | 13.12 | +3.71 | +2.92 |
| Rashee Rice | 12.38 | +2.97 | +2.18 |
| Nico Collins | 12.32 | +2.91 | +2.12 |
| Colston Loveland | 10.06 | +2.94 | +2.50 |
| Jeremiyah Love | 11.00 | +2.44 | +1.60 |
| Tyler Warren | 9.41 | +2.29 | +1.85 |
| Breece Hall | 10.70 | +2.14 | +1.30 |
| TE6 band (LaPorta/Kraft/Pitts) | 8.76 | **+1.64** | **+1.20** |

**Answer to the task's X-vs-Y question: X ≈ 5.6 PPG over TE replacement; Y ≈ 3.9 PPG for the best WR alternative at identical ADP. Net edge to the elite TE: +1.79 PPG in a 12-team league, +2.14 in a 10-team league.** Over 17 weeks that is **~30–36 points**, or roughly **one extra win.**

That is a real edge. It is also **far smaller than TE-heavy advocates claim** — and it is entirely contingent on three things.

**Stress test 1 — McBride regresses.** Consensus expects TD regression (11 TDs on 126 catches is an 8.7% rate) plus Marvin Harrison Jr.'s target competition. At 100/1,050/6 he scores **11.2 PPG → VBD +4.1**, and **A.J. Brown (+3.85) is a coin flip.** The entire edge lives inside the projection.

**Stress test 2 — injury.** Bowers missed 5 games in 2025. LaPorta played 9. A 13-game elite season = (12.76 × 13 + 7.1 × 4) ÷ 17 = **11.4 PPG → VBD +4.3**, a **24% haircut**, and you have exactly **1 IR spot.**

**Stress test 3 — the baseline you choose is the whole argument.** Swap the starter-based baseline for a "best available free agent" baseline and everything inverts [my calc]: McBride +6.0, A.J. Brown **+6.7**, Jeremiyah Love **+6.3** — the TE *loses.* This is precisely the assumption gap that generates the published disagreement. The starter-based baseline is the correct one for lineup decisions (it measures what you'd actually be forced to start), but the FA baseline is what "streaming works" implicitly assumes. **Reality sits between them, and the honest edge is +1.0 to +1.8 PPG, not +5.**

**The counter-evidence you must weigh:** FantasyPros' VORP analysis reports **McBride and Bowers rank 36 and 46 spots higher in ADP than in VORP** — the largest positional mispricing on the 2026 board by that metric — and concludes **"a compelling case for simply punting the TE position entirely."** They note that among top-12 TEs, **only Dallas Goedert** is not overvalued by the metric.

---

## 5. Roster-slot savings with 4 bench spots — real, but worth ~0.4 PPG, not 2

**The roster budget.** 13 spots − K − D/ST = **11 skill players.** Seven of those are starters (QB, RB, RB, WR, WR, TE, FLEX), leaving **4 bench spots.**

- **Elite-TE build:** TE1 elite. Bench = RB3, RB4, WR3, WR4. **Zero bench TEs.**
- **Punt-TE build:** mediocre TE1 + a TE2 hedge. Bench = TE2, RB3, RB4, WR3. **25% of your bench on a position with one start.**

**Naive valuation:** the 4th bench spot converts into a startable lineup piece maybe 5 of 17 weeks, adding ~3 PPG when it does → **≈ 0.9 PPG.**

**But your transaction rules gut most of that.** You have **no acquisition limit, a 1-day waiver period, and no FAAB budget to run dry.** That is about the cheapest streaming environment a league can have. You can carry exactly one TE with a punt build and simply add a body on his bye. Honest capture of the slot savings: **~0.4–0.5 PPG.**

**Then the rule that gives it back — and this is the sharpest league-specific finding in this whole analysis:**

> **Your waiver order RESETS WEEKLY BY INVERSE STANDINGS.**

With FAAB, a first-place team can simply outbid for the week's hot TE. **With weekly-resetting inverse-standings order, a winning team has near-permanent last priority — every single week, all season.** The streaming plan therefore **degrades exactly in proportion to how well your team is doing.** You build a contender, and the mechanism you depend on to fill TE is the one you're structurally last in line for. Almost nobody prices this in.

That pushes the honest slot-and-certainty value to **~0.7–1.0 PPG for a team that's actually winning** — and it is *additive* to the +1.79 VBD edge.

**One more claim on the same rule:** your D/ST scoring has an unusual **yards-allowed ladder running +5 to −7**, on top of the points-allowed ladder. That's a **~12-point weekly swing** from matchup selection alone — a genuinely high-leverage streaming slot. Every waiver claim you spend on TE is one you did not spend on D/ST, where the payoff is larger. Locking TE redirects your (already disadvantaged) waiver priority to where it earns most.

**Do not double-count the "start/sit headache" argument.** Removing a weekly decision is a real quality-of-life and decision-error benefit, but it is **not points.** It is already reflected in the VBD gap.

---

## 6. What 2026 analysts actually recommend

Four distinct published camps, all verified from live 2026 articles:

**Camp 1 — Pay up.** NBC Sports/Rotoworld's 2026 TE tiers: the top of the position "can create a drastically wide gap toward replacement level, with some years the top scoring tight end having a bigger advantage over the TE12 than the WR1 has over the WR24." McBride and Bowers are "worth a late Round Two pick." ESPN's Matt Bowen puts both in a standalone superstar tier expected to deliver **15+ points a week**.

**Camp 2 — Punt entirely.** FantasyPros' VORP breakdown: **"All of these numbers make a compelling case for simply punting the TE position entirely… there are enough Hunter Henry/Dalton Schultz/Brenton Strange types available that you will never be completely doomed at the position. And most other options at the position won't score enough to leave your bargain streamer in the dust."** Also: "spending a second- or third-round pick on a tight end carries too much opportunity cost, as the next 10 tight ends after Bowers and McBride are packed so tightly in our projections."

**Camp 3 — Barbell; the middle rounds are a trap.** This is the **modal 2026 position.** Multiple sources: **"Pay up for the elite tier or wait until round 13–15 and stream — the middle rounds at tight end are a trap."** CBS's **Dave Richard** is explicit: he **would not take Warren, LaPorta, Kraft, Fannin, or Pitts in Round 4**; they're fine in Rounds 5–7 only if you don't like anyone else. His summary line: **"This is a position you can solve with a reliable starter in the back half of your Fantasy draft, and you shouldn't force yourself to take one early on unless you genuinely believe in them posting huge numbers."** He caps second-tier expectations at **"safer bets to average over 11 PPR points"** — which in your half-PPR scoring is roughly **8.5–9 PPG.**

**Camp 4 — Be price-sensitive; read the room.** FantasyPros' *"How to Draft Tight Ends (2026)"*: **do not commit to a TE strategy before the draft.** "If the top tight ends fly off the board early, you should probably wait, because the thirst for elite tight ends is letting top players at other positions slide further than they normally would." Conversely, "if you're in a draft full of avowed TE punters, you might be able to grab an elite tight end below his average draft position." Their goal statement: **"simply getting one of the tight ends you like at a price you like."**

**Synthesis:** The 2026 consensus is **barbell + price-sensitivity**. Essentially nobody recommends the middle. Essentially nobody recommends two TEs outside TE-premium. And the strongest *quantitative* published work (VORP) leans **punt.**

---

## 7. Specific targets by approach, with ADP

### Tier A — Elite pay-up (ADP 20–28)
- **Brock Bowers**, LV — ADP **20** (Underdog) / **21–22** (market) / **27.6** (CBS). Fully healthy, no brace, best offense of his career.
- **Trey McBride**, ARI — ADP **24.5** (Underdog) / **27** (Bleacher Nation) / **27.2** (CBS). Coming off the TE reception record.

> In an ESPN room, expect them at **25–30**, not 20. That is the gap you can exploit.

### Tier B — Near-elite, the best risk-adjusted buy (ADP 41–59)
- **Colston Loveland**, CHI — ADP **41–46.7 (TE3)**. **The single best value on the board by my read:** he is the third and last TE above 50 half-PPR VORP points, he costs half of Bowers, and his Weeks 9–18 rookie pace (47/597/6 in 10 games) extrapolates near the elite tier. Multiple 2026 sources call him "arguably the biggest breakout candidate."
- **Tyler Warren**, IND — ADP **55.9–59 (TE4)**. Contingent on Daniel Jones' Achilles recovery.

### Tier C — The trap band. **Avoid at cost.** (ADP 70–80)
- **Sam LaPorta**, DET — **70.4** · **Kyle Pitts** — **71.1** *(2026 team UNVERIFIED)* · **Tucker Kraft**, GB — **76.3** · **Harold Fannin Jr.**, CLE *(exact ADP UNVERIFIED)*
- These project ~8.8 PPG = **+1.64 VBD**. You pay a Round 6–7 pick for **1.5 PPG over a Round 10 TE.** This is the worst-priced band on the board.
- **Exception: Dallas Goedert** — the **only** top-12 TE that FantasyPros' VORP flags as *not* overvalued; consensus projections are well above market. Led all TEs with **11 TDs in 2025 from a TE16 ADP.** *(2026 team and exact ADP UNVERIFIED — check on the clock.)*

### Tier D — Late-round starters, the punt-build core (~TE9–14, Rounds 9–12)
- **Jake Ferguson**, DAL — **TE12 ADP, ~Round 10.** Was **fantasy TE5 in 2025** with Dak healthy. **The best-flagged value in my entire research pass.** This is your target if you skip the elite tier.
- **Dalton Schultz**, HOU — meaningfully boosted by **Jayden Higgins' torn ACL**; Heath Cummings: "if you do settle for a low-end TE1, Schultz should be your pick."
- **Brenton Strange**, JAX · **Hunter Henry**, NE (tied 2nd among TEs with 7 TDs in 2025) · **Juwan Johnson** (2025 TE12 in PPR PPG) · **Mark Andrews** *(2026 team UNVERIFIED)*
- **Travis Kelce**, KC — flagged as a value at this stage of his career; role still secure.
- **Dalton Kincaid** — post-hype; 8.4 half-PPR PPG in 2025; 4th in yards/route among TEs with 400+ routes since 2023. *(Team UNVERIFIED — presumed BUF.)*

### Tier E — Punt / stream (TE18+, last 2–3 rounds or waivers)
- **Greg Dulcich** — called **"THE late-round tight end to draft in 2026."** Among 59 qualifying TEs: **5th in target-per-route-run (24%), 2nd in yards/route (2.64), 2nd in YAC/rec (7.69), 6th in fantasy points per route run (0.50).** *(2026 team UNVERIFIED.)*
- **Isaiah Likely**, NYG — moved to the Giants; **Jaxson Dart targets TEs heavily.** Explicitly flagged for a role increase.
- **Chigoziem Okonkwo** — **TE21 PPR / TE24 standard ADP.** Was TE4 in Week 17 and TE6 in Week 16 last season.
- **Gunnar Helm**, TEN — **TE30 ADP.** Top-third among TEs in targets-per-route-run, catch rate, and team target share.

---

## 8. Draft-slot decision table — the actual answer

Snake math. **12-team:** R1 = N, R2 = 25−N, R3 = 24+N. **10-team:** R1 = N, R2 = 21−N, R3 = 20+N.

### 12-team

| Your slot | R2 pick | R3 pick | Elite TE (ADP 21–28)? | **Do this** |
|---|---|---|---|---|
| **1–3** | 22–24 | 25–27 | **Live at R2, sometimes R3** | **Best window.** Elite RB/WR at 1.x, then take McBride/Bowers at R2 if there. |
| **4–6** | 19–21 | 28–30 | Live at R2 (~1–3 picks early) | **Take it.** Small reach, well inside noise. |
| **7–9** | 16–18 | 31–33 | R2 is a **4–8 pick reach**; R3 too late | **Don't reach.** RB/WR at R2. Target **Loveland at R3 (31–33)** — 8–14 picks under ADP 41–47. |
| **10–12** | 13–15 | 34–36 | R2 is an **8–11 pick reach** | **Skip the elite tier entirely.** Loveland at R3 (34–36) is right at value, or punt to Ferguson ~Round 10. |

### 10-team

| Your slot | R2 pick | R3 pick | **Do this** |
|---|---|---|---|
| **1–3** | 18–20 | 21–23 | Elite TE **live at both**. Take it **only if you got an elite RB at 1.x.** |
| **4–6** | 15–17 | 24–26 | R2 is a 4–7 pick reach, R3 likely too late. **Marginal — prefer Loveland at R3/R4.** |
| **7–10** | 11–14 | 27–30 | **Punt.** Ferguson/Schultz/Strange late, stream aggressively. |

**Counter-intuitive result [my calc]:** the elite-TE VBD edge is *larger* in a **10-team** league (**+2.14 PPG**) than a 12-team (**+1.79**), because the WR/RB baselines rise steeply from WR30→WR25 and RB31→RB26 while the TE baseline barely moves (TE13→TE11 is a flat stretch of an already-flat curve). **But** in a 10-team league TE13–16 sit on waivers all year, so a punt build actually works — the theoretical edge is bigger while the practical edge is smaller. **Net: 12-team favors taking the elite TE; 10-team favors punting.**

**Playoff structure — a wash, don't over-weight it.** **2-week playoff matchups reduce variance**, which rewards the consistent floor an elite TE provides, and the **seeding tiebreaker of total points for** rewards raw season-long VBD maximization. But **only 4 of 10–12 teams qualify** — a top-33–40% cut, which rewards *ceiling* over floor and mildly favors concentrating capital in RB/WR. These roughly offset.

---

## 9. Best case FOR, best case AGAINST — condensed

**FOR (six points):**
1. At ADP 21–28, McBride/Bowers is **the single highest-VBD pick on the board** in your format: **+5.64 PPG** vs **+3.85** for A.J. Brown at the same cost. Edge **+1.79 PPG ≈ 30 points ≈ one win.**
2. **Half-PPR only costs the edge 29%** (+2.53 → +1.79). It does not erase it, because the TE baseline is uniquely terrible in a way no WR baseline is.
3. **Only three TEs clear 50 half-PPR VORP points** (published). That is genuine scarcity across 10–12 mandatory TE slots.
4. **Weekly-reset inverse-standings waivers structurally punish a winning team's streaming plan.** Build a contender and you pick last every week, forever. Worth **~0.7–1.0 PPG** of certainty value to a good team — additive to the VBD edge.
5. **4-pt pass TDs** kill QB value at that ADP; **Josh Allen at 20 is not a real competitor** for the pick.
6. **2-week playoff matchups** and a **total-points seeding tiebreaker** both reward consistent, VBD-maximizing rosters.

**AGAINST (seven points):**
1. **McBride and Bowers are 36 and 46 ADP spots more expensive than their VORP rank justifies** — the largest mispricing on the 2026 board by that metric.
2. **TE4 to TE14 is under 30 half-PPR points — under 1.8 PPG.** Miss the top two and you lose almost nothing by landing any of ~10 guys.
3. **Half-PPR strips 54 points off McBride** and cuts the elite edge **29%.**
4. **6-pt TDs create real late-round paths to top-6.** **Goedert led all TEs with 11 TDs from a TE16 ADP and finished TE6. Ferguson finished TE5 and now costs a Round 10 pick.** Your format rewards exactly the TD-dependent profile you can get for free.
5. **Round 2 is unusually rich at WR in 2026** — Lamb 14.7, Jefferson 15.7, London 17.3, Rice 22.5, Pickens 22.7, A.J. Brown 23.4, Collins 26.2 — and one 2026 source calls it "amazing for receivers." Real cost to pass.
6. **Unlimited acquisitions + 1-day waivers = the cheapest streaming environment possible.** With 4 bench spots you're churning anyway.
7. **Injury risk with 1 IR spot.** Bowers missed 5 games in 2025; LaPorta played 9. A 13-game season cuts the edge **24%.**
