## 0. Method + data-integrity note

All figures below come from live searches run **Aug 22, 2026**. WebFetch was egress-blocked on FantasyPros, FFToday, DraftSharks, NFL.com, Rotoballer, Sharp Football, PFF, Yahoo, and FantasyFootballCalculator, so ADP was reconstructed from search-surfaced content on those same pages. **ADP figures come from different platforms and different dates in August 2026 and legitimately conflict** — I flag conflicts rather than smoothing them. Team assignments are marked **UNVERIFIED** where 2026 rosters were not explicitly confirmed in a source.

---

## 1. How 0.5 PPR actually shifts RB vs WR value — and the surprise

The mechanical difference vs full PPR is exactly `Δ = 0.5 × receptions`. Everyone loses points; what matters is *who loses more*.

Using a **verified 2025 stat line** — Christian McCaffrey: 1,202 rush yds, 10 rush TD, **102 rec**, 924 rec yds, 7 rec TD, 416.6 PPR pts (DIRECTV Insider):

| Archetype | Rec (est.) | Pts lost vs full PPR | Per game (17) |
|---|---|---|---|
| Elite receiving RB (McCaffrey, verified 102 rec) | 102 | **−51.0** | −3.00 |
| Elite pass-catching RB (Gibbs/Achane/Cook tier) | ~70 | −35.0 | −2.06 |
| Elite WR (Chase/Nacua/JSN tier) | ~95 | −47.5 | −2.79 |
| **Rushing-first RB (Henry / Walker / Montgomery)** | ~30 | **−15.0** | **−0.88** |
| WR2/WR3 (McConkey/McLaurin/Waddle tier) | ~70 | −35.0 | −2.06 |

Reception baselines other than McCaffrey's are **estimates (UNVERIFIED)**; the McCaffrey row is real.

**Net relative shift, full PPR → half PPR:**
- Rushing-first RB vs elite WR: **+32.5 pts (≈ +1.9 pts/gm) to the RB**
- Receiving RB (McCaffrey) vs elite WR: **−3.5 pts — the RB actually loses ground**
- Gibbs/Achane/Cook vs elite WR: **+12.5 pts (≈ +0.7/gm)** — marginal

### The non-obvious finding

**Half-PPR does not boost the RBs at the top of the 2026 board.** Gibbs, Bijan, McCaffrey, Achane, and Cook are all high-reception backs — the format helps them barely or not at all. The ~2 pts/game half-PPR premium lands almost entirely on **low-catch, TD-dependent backs who sit at RB10–RB25**: Derrick Henry (ADP 15.7), Kenneth Walker III (22.9), David Montgomery (HOU), Rhamondre Stevenson (NE).

Consequence: **the "RB dead zone" is genuinely less dead in this league than in the PPR-based literature the dead-zone research is built on.** Published 2026 dead-zone warnings (Sharp Football, RotoWire, Yahoo, Fantasy Life) are calibrated to PPR ADP. In half-PPR you should move Henry/Walker/Montgomery-types up roughly **half a round to a full round** relative to their consensus ADP.

Also note the 6-pt rush TD is **not** a boost here — 6 pts for rush and rec TD is the ESPN default. The real RB-favorable levers are (a) 0.5 PPR, and (b) rushing yards and receiving yards both at 0.1/yd, i.e. **no receiving-yardage premium**.

---

## 2. RB scarcity in 2026: how many real bell cows, and where's the cliff

### Supply-side facts (verified)
- **Only 11 running backs started all 17 games in 2025** (Fantasy Index, Feb 2026).
- In 2025, **no back averaged 20 carries/game; only 4 backs had 300 carries; only 10 had 300 touches** (Dave Richard / Seahawks.com 2026 RB analysis).
- NFL RBs have roughly a **27% chance of playing a full season**; RB injuries average longer duration than any other position (Undroppables / NBC Sports injury research).

**So the true bell-cow count in 2026 is ~10–12.** A 12-team league needs 24 mandatory RB starters. The bell-cow supply covers **less than half of the mandatory RB slots.**

### Market-side facts (verified)
- **10–13 of the first 20–22 picks are running backs** (CBS RB ADP Review counts 10 of the first 20; PFF's 10-team guide says "roughly 12 or 13 of the first 22"; Adam Levitan/ETR: "roughly 12 of the first 20").
- **RB24 is going at pick ~55 in PPR — the highest RB24 ADP since 2020** (Sharp Football Analysis, 2026 RB ADP historical trends).

### 2026 RB tiers (synthesized from Footballguys Aug tiers + verified ADPs)

**TIER 1 — True elite bell cow (RB1-overall upside).** *This is the tier that makes RB-heavy work.*
| Player | Team | ADP | Note |
|---|---|---|---|
| Jahmyr Gibbs | DET ✓ | **1.1–2.0** | Footballguys RB1. David Montgomery gone from Detroit. Levitan: "a tier of his own" — softest schedule, 2nd-highest implied team total. |
| Bijan Robinson | ATL ✓ | **2.0–2.1** | Footballguys RB2. Tyler Allgeier gone (to ARI). |

**TIER 2 — High-end RB1 with a real flaw.**
| Player | Team | ADP | Flag |
|---|---|---|---|
| Christian McCaffrey | SF ✓ | **3–6 (conflict: DIRECTV 5.8; NFL.com cites "2.03")** | **LIVE RISK:** missed August 2026 practice with "tightness," echoing the 2024 calf that cost him most of that season. SF backfield behind him is also injured (Jordan James, Kaelon Black, Isaac Guerendo). |
| Jonathan Taylor | IND ✓ | ~7 | Was overall RB1 through 10 weeks of 2025 (27.2 PPR ppg) before Daniel Jones' injury. |
| De'Von Achane | MIA ✓ | 8–11.4 | Miami's roster overhaul = environment risk. PFF's prime early-2nd target. |
| James Cook III | BUF ✓ | 10–11.9 | Coming off a rushing title; three-down role on an elite offense. |
| Ashton Jeanty | LV ✓ | 12.7 | New coach committed to feeding him. |
| Chase Brown | CIN ✓ | 14.3 | Elite once Burrow returned in 2025. FantasyPros' Robust-RB R2 target. |
| Saquon Barkley | UNVERIFIED | ~14 overall / RB8 half-PPR | |
| Derrick Henry | BAL ✓ | 15.7 | **Biggest half-PPR riser** — low catch volume is cheap in full-PPR ADP. FantasyPros' other Robust-RB R2 target. |
| Josh Jacobs | GB ✓ | ~20 | |
| Kenneth Walker III | SEA ✓ | 22.9 | Flagged as best Round-2 value by CBS; Fantasy Life makes him an RB strategy pillar. **Second-biggest half-PPR riser.** |

**TIER 3 — RB2 with upside or a question mark.**
Jeremiyah Love (ARI ✓, ADP 19–26.4 — No. 3 overall pick in the 2026 NFL Draft, but Tyler Allgeier and James Conner are on the depth chart; Yahoo has run *two* separate "ADP trap / not worth the reach" pieces on him) · Kyren Williams (LAR, RB17) · Omarion Hampton (LAC ✓) · Breece Hall (NYJ ✓, 31.5) · Bucky Irving (TB ✓, **54.8** — Field Yates has him RB22; offseason shoulder surgery, 2025 efficiency collapse, now competing with Kenneth Gainwell and Sean Tucker; NBC's tier piece calls him a rebound candidate on 20.4 touches/gm)

### **WHERE THE CLIFF FALLS**

**The 2026 RB cliff is a two-stage drop:**
1. **After ~pick 24 (≈ RB11–12)** — end of Tier 2, the last backs with genuine every-week RB1 workloads.
2. **The hard cliff after ~pick 32 (≈ RB15–16)**, which opens the **Rounds 4–7 dead zone**: D'Andre Swift, David Montgomery (HOU ✓), Rhamondre Stevenson (NE ✓), Tony Pollard, Rico Dowdle (PIT ✓), Chuba Hubbard (CAR, UNVERIFIED — RotoWire explicitly red-flags him in the 6th), Javonte Williams (flagged), Jonathon Brooks (CAR ✓).

**Hit-rate evidence for the cliff:**
- **36.5% of RB1–RB12 picks have matched or beaten their positional ADP since 2010** (Sharp Football).
- **In 2025, only 3 of 12 RB13–RB24 picks (James Cook, D'Andre Swift, RJ Harvey) matched or beat ADP — 25%, described as "well below the base rate."**
- Of dead-zone backs that *did* hit since 2010, **61% were on rookie contracts and 47.5% were in Years 1–3.** That is your filter.

---

## 3. Robust-RB vs Hero-RB — what 2026 published strategy actually says

**Robust-RB** — *FantasyPros, "Robust-RB Draft Strategy (2026)" (June 2026)*
> Invest early and aggressively in RB "regardless of the scoring system"; ideally **three RBs within your first four or five picks**. Round 1: take a **safe-floor** back even at the cost of upside — **draft Bijan or Gibbs over McCaffrey** from an early pick. Round 2: **Chase Brown and Derrick Henry** are the explicit targets; weigh Achane or Jeanty if either slides.

Fantasy Alarm published a parallel 2026 Robust-RB blueprint.

**Hero-RB** — *FantasyPros (Aug 2026) + PFF (2026)*
> One elite back in Round 1 — **Gibbs is the named top hero-RB target** (21+ PPG in each of the last two seasons) — then hammer WR and **spend up at the onesies**. PFF pairs **Gibbs + Brock Bowers** as the early-round core. TE in Round 3 (Bowers/McBride), QB in **Rounds 4–6**. PFF's stated advantage: *"it allows you to prioritize tight end and quarterback early, eliminating the need to spend additional draft capital on backups at either position."*
> FantasyPros names **a healthy Jonathon Brooks as the ideal RB2 for a hero build.**

**PFF 10-team guide (2026):** *"A clear tier break emerges after the top group of running backs, making it important to secure two early... A 10-team league has room for three set-and-forget wide receivers, which you should build in Rounds 3 through 6, starting with A.J. Brown."*

**Establish The Run — Adam Levitan, "My Strategy For 2026 Fantasy Drafts":**
> *"The big theme of this year's landscape is **running back thirst**."* Levitan advocates a **"barbell approach at RB — spending a lot of draft capital on RBs early, then spraying at ambiguous situations and one-injury-away guys late,"** which he calls **"an extremely profitable strategy in home leagues."*

**Consensus read:** the 2026 industry is meaningfully RB-forward. But note that **not one of these builds spends picks 1-2-3 all on RB.** Even "Robust-RB" is 2 RBs in the first two rounds plus a third by round 4-5. Levitan's barbell is explicitly *early + late*, deliberately skipping the middle.

---

## 4. THE SHALLOW-BENCH ANGLE (the decisive question)

### First, the actual roster math for this league

13 spots. Locked: QB1, TE1, K1, D/ST1 = 4. That leaves **9 spots for RB+WR**, of which 5 are starters (2 RB, 2 WR, 1 FLEX). **Net bench = 4, plus 1 IR.**

**But this league's transaction rules let you free up every one of those 4 spots for RB/WR:**
- **Never roster a K2 or D/ST2.** With 1-day waivers, unlimited acquisitions, and position max 3, you stream both.
- The D/ST **yards-allowed scale is brutally punitive** (350–399 = −1, 400–449 = **−3**, 450–499 = **−5**, 500–549 = **−6**, 550+ = **−7**). A "set-and-forget" D/ST is actively dangerous here — a single 480-yard game can cost you −5 before you count anything positive. **Stream D/ST on matchup, every week.** (FantasyPros names the **Houston Texans** the best 2026 fantasy defense — but the yardage scale still argues for streaming.)
- **Never roster a QB2 or TE2** — stream the bye on the 1-day wire.

**Result: all 4 bench spots are RB/WR, and the IR spot parks one injured player at zero cost.**

---

### ARGUMENT A: Shallow bench makes RB-heavy **MORE** correct

1. **You cannot replace an elite RB from waivers; you can replace a WR.** Only ~10–12 bell cows exist. Zero appear on waivers. A WR2-equivalent appears on waivers constantly.
2. **The waiver order rule is a trap for good teams.** Waiver order **resets weekly by inverse standings**. This is not FAAB and not continuous rolling. **If you build a winning roster, you have the worst waiver claim in the league every single week.** The one genuinely league-winning RB add of 2026 — the equivalent of 2025's **Kimani Vidal (LAC)**, who finished **Weeks 6–14 as the RB17** while Omarion Hampton was out (PFF's 2025 waiver league-winners piece) — will be awarded to the *worst team in the league*, not to you. **You must draft your RB certainty because the rules structurally deny you the ability to buy it later.**
3. **The IR slot absorbs the single most likely catastrophic RB injury at no roster cost**, which is exactly the failure mode RB-heavy is criticized for.
4. **Hero-RB's own justification is a shallow-bench argument.** PFF: taking TE and QB early "eliminat[es] the need to spend additional draft capital on backups at either position." That reasoning is *strongest* when you have 4 bench spots.
5. **Two-week playoff matchups + 4-team playoffs.** With 2-week rounds, single-week variance is halved and the higher-mean roster wins more often. With only 4 of 10–12 teams qualifying, you need a top-33%/40% regular season — you need mean, not variance. RB volume is the most predictable weekly floor in fantasy.

### ARGUMENT B: Shallow bench makes RB-heavy **LESS** correct

1. **The handcuff insurance model is dead — and the industry says so explicitly.** *FantasyPros, "4 Tips for Shallow Leagues (2026)":* fill the bench **"with breakout candidates, rather than handcuffs at running back."** Lindy's short-bench guide agrees: benches are for "short-term utility rather than long-shot stashes." Robust-RB's entire risk mitigation is handcuffing, and this format forbids it.
2. **The waiver wire in THIS league is unusually RB-rich — quantified.**
   - 12-team × 13 spots = **156 players rostered.** A standard 12-team/16-spot league rosters 192. **36 more players are free here.**
   - Of the 156: ~12 QB, ~12 TE, ~12 K, ~12 D/ST ≈ 48 non-RB/WR → **~108 RB+WR rostered**, split roughly 45 RB / 63 WR.
   - **⇒ RB46 and below is permanently free in a 12-team. RB39 and below is permanently free in a 10-team (130 rostered).**
   - That means **the direct backup to nearly every bell cow in the NFL is unrostered.** Handcuffing is not just wasteful — it's *redundant*.
3. **You cannot absorb a WR injury either.** Robust-RB leaves you 4 WRs for 2 WR slots + flex. One WR injury plus one WR bye and you're starting a waiver WR — with the worst claim in the league.
4. **The RB2 hit rate is the worst in fantasy.** 25% (3/12) for RB13–RB24 in 2025; 36.5% even for RB1–RB12 since 2010. Robust-RB's third back is bought at exactly the worst price point on the board.
5. **Robust-RB pays a premium for a flex body.** Your RB3 mostly occupies the FLEX — a slot a WR fills equally well in half-PPR.

### **DECISION**

**Argument A wins on the top of the board; Argument B wins on the middle.**

The two arguments are not actually about "RB-heavy vs not" — they're about *where* you buy RB. Both point at the same build:
- **Buy the scarcity you cannot replace (Tier 1–2 RB, picks 1–24).** Argument A is correct here: the weekly-resetting inverse-standings waiver order plus a 10–12-deep bell-cow supply means elite RB is genuinely un-buyable later.
- **Do NOT buy the scarcity you can replace (RB3/RB4/handcuffs, rounds 4–7 and 10+).** Argument B is correct here: RB46+ is permanently free, so a bench handcuff is a wasted spot.

**The 4-man bench therefore argues against ROBUST-RB specifically (which needs handcuff insurance and starves WR) and FOR HERO/ANCHOR-RB** — which front-loads the un-buyable resource, spends the mid-rounds on the onesies (removing the need for backup QB/TE), and refills RB from the deep free pool.

---

## 5. Waiver angle: can you actually replace an injured RB in 2026?

**Yes — but not the one you want, and not if you're winning.**

| Factor | Effect |
|---|---|
| 1-day waiver period | **Strongly favorable.** Fast turnaround; you're never more than a day from a replacement. |
| No acquisition limit | **Strongly favorable.** Claim 3–4 RBs a week; shotgun the ambiguous backfields. |
| ~156 (12-tm) / ~130 (10-tm) rostered | **Strongly favorable.** RB46+ / RB39+ always free. |
| **Waiver order resets weekly by inverse standings** | **STRONGLY UNFAVORABLE for a contender.** You will be picking 10th–12th every week you're winning. You will lose every contested claim for the one RB who inherits a bell-cow role. |
| After waivers clear (1 day), it's FCFS free agency | Partially offsetting — speed on Friday injury news and Sunday inactives is a real edge, and it's the only RB-acquisition edge a winning team retains. |

**Historical base rate:** I could not find a rigorous published study quantifying "% of league-winning RBs that came from waivers," so **treat any specific percentage as UNVERIFIED.** What is verifiable: PFF's 2025 waiver league-winners piece identifies **Kimani Vidal (LAC)** as a Weeks 6–14 **RB17** off waivers; 2025's in-season waiver RB churn also produced Trey Benson, Emanuel Wilson, and Raheim Sanders as usable pieces. The honest read is roughly **1–3 genuinely startable RBs per season emerge from waivers**, they surface unpredictably, and **under inverse-standings weekly reset, the good teams do not get them.**

**Practical conclusion:** you can reliably replace an injured RB with an **RB30–RB45-quality body**. You cannot reliably replace an RB with an **RB1–RB15-quality body**. Plan accordingly: the RBs you must own on draft day are the ones in that top-15 band.

---

## 6. How many RBs does this league actually start — RB or WR scarcer?

This is the most important calculation in the whole analysis, because **this lineup starts only 2 WR**, which is unusual (most leagues start 3).

### Weekly starter demand

**12-team:**
- Mandatory RB: 2 × 12 = **24** · Mandatory WR: 2 × 12 = **24** · TE: 12 · FLEX: 12
- Modeled flex split in half-PPR / 2WR-2RB: ~45% RB, ~50% WR, ~5% TE *(modeling assumption — UNVERIFIED)*
- **RB started weekly ≈ 24 + 5.4 = ~29** (range 28–32)
- **WR started weekly ≈ 24 + 6.0 = ~30** (range 29–32)

**10-team:** **RB ≈ 20 + 4.5 = ~24.5** · **WR ≈ 20 + 5.0 = ~25**

### **This league starts essentially EQUAL numbers of RBs and WRs (~29–30 each in 12-team; ~25 each in 10-team).**

That is the whole ballgame. A normal 3-WR league starts ~36–42 WRs against ~28–30 RBs. This one starts them 1:1.

### Demand ÷ supply

| | Weekly demand (12-tm) | NFL supply of viable starters | **Ratio** |
|---|---|---|---|
| **RB** | ~29 | ~32 lead backs (only **11** started all 17 games in 2025; only **10** had 300 touches) | **≈ 0.91** |
| **WR** | ~30 | ~60–75 WRs with a startable target share *(estimate)* | **≈ 0.44** |

**⇒ RB is roughly 2× scarcer than WR in this specific lineup.** Nearly every NFL starting RB is a fantasy starter here; fewer than half of viable WRs are needed.

**Corroborating market evidence:** RB24 goes at pick ~55; WR20 (Ladd McConkey) goes at 42.0, with McLaurin 51.4, Waddle 53.2, Burden 56.9, D.J. Moore 63.5 — so **WR24 lands roughly picks 55–63** *(inferred, UNVERIFIED as an exact figure)*. The market prices the 24th man at each position almost identically — but 10–13 of the first 20–22 picks are RBs, meaning the market's scarcity premium is concentrated entirely at the **top** of RB, not the replacement line. That is exactly right, and it is the analytical core of the verdict: **buy RB scarcity in rounds 1–2, never in rounds 4–7.**

---

## 7. Exact target boards

*All ADP figures are August 2026 consensus from the sources listed; they vary by platform.*

### ROBUST-RB BUILD (only from picks 1–2 or 11–12 in a 12-team)

The snake turn is what makes this work. From **1.01** your picks are **1, 24, 25, 48, 49** — back-to-back. From **1.12** they're **12, 13, 36, 37** — back-to-back.

| Round | Target | ADP |
|---|---|---|
| 1 | **Jahmyr Gibbs** (DET) or **Bijan Robinson** (ATL) | 1.1 / 2.1 |
| 2 | **De'Von Achane** (MIA) 8–11.4 · **James Cook III** (BUF) 10–11.9 · **Ashton Jeanty** (LV) 12.7 · **Chase Brown** (CIN) 14.3 · **Derrick Henry** (BAL) 15.7 ← *FantasyPros' named Robust-RB R2 picks are Brown and Henry* | 8–16 |
| 3 | **Josh Jacobs** (GB) ~20 · **Kenneth Walker III** (SEA) 22.9 ← *best half-PPR value on this board* | 20–23 |
| 4 | **Best WR available:** A.J. Brown 23.4 · Nico Collins 26.2 · or the R3 WR tier (Egbuka, DeVonta Smith, Zay Flowers, Tee Higgins) | 23–36 |
| 5–6 | **WR2:** Ladd McConkey 42.0 · Terry McLaurin 51.4 · Jaylen Waddle 53.2 · Luther Burden III 56.9 · D.J. Moore 63.5 | 42–64 |
| 6–7 | **QB:** Lamar Jackson 45 (bounceback at a discount) or Jayden Daniels 62 · **TE:** post-Bowers/McBride tier | 45–62 |
| 8–11 | WR3/flex upside; **do not draft handcuffs** | — |
| 12–13 | K and D/ST **last two picks** — you're streaming both anyway | — |

**Roster shape:** 5 RB / 4 WR / QB / TE / K / DST. Fragile at WR. **Requires the turn.**

### HERO-RB BUILD (the default — correct from picks 3–10)

| Round | Target | ADP |
|---|---|---|
| 1 | **Gibbs / Bijan** if they reach you. Otherwise the hero comes in R2 and R1 is **Ja'Marr Chase** (CIN) ~3.0 · **Puka Nacua** (LAR) ~2.5 (PFF: "top-ranked fantasy WR entering the season" — conflicts with Chase-as-WR1 elsewhere) · **Jaxon Smith-Njigba** (SEA) 5.6 | 1–6 |
| 1–2 | **Skip McCaffrey at ADP** unless the August "tightness" fully resolves — it echoes the 2024 calf that wiped out his season, and SF's backup RBs (Jordan James, Kaelon Black, Isaac Guerendo) are *also* hurt, so there's no cheap contingency | 3–6 |
| 2 | If R1 was a WR, your **hero** is Jeanty 12.7 / Chase Brown 14.3 / Henry 15.7 / Walker 22.9. If R1 was Gibbs/Bijan, take **CeeDee Lamb 14.7 · Justin Jefferson 15.7 · Drake London 17.3** | 12–23 |
| 3 | **Trey McBride 27.2 or Brock Bowers 27.6** — PFF's hero-RB build explicitly pairs Gibbs + Bowers. Or **Rashee Rice 22.5 / George Pickens 22.7 / A.J. Brown 23.4 / Nico Collins 26.2** | 22–28 |
| 4–6 | WR depth + **QB: Lamar Jackson 45** (the value; Josh Allen at 26 is too expensive for this build). WR: McConkey 42.0, McLaurin 51.4, Waddle 53.2 | 42–57 |
| 6–9 | **RB2 with the Sharp filter — rookie contract + pass-catching:** Jeremiyah Love (ARI, 19–26.4, No. 3 overall pick) · Breece Hall (NYJ, 31.5) · **Bucky Irving (TB, 54.8 — the single best price on the board given Field Yates has him RB22)** · Rico Dowdle (PIT) · David Montgomery (HOU) · Rhamondre Stevenson (NE) | 26–60 |
| 10–13 | **Levitan's "spray":** Tank Bigsby · Blake Corum · Tyrone Tracy · Tyjae Spears · Keaton Mitchell (LAC) · Ray Davis (BUF, Cook's handcuff and "a must-start if Cook were injured") · Jonathon Brooks (CAR) · Kenneth Gainwell / Sean Tucker (TB). Then **K and D/ST with your final two picks.** | 100+ |

**Roster shape:** 3–4 RB / 5–6 WR / elite TE / value QB / K / DST. Survives byes and injuries. No backup QB or TE needed.

---

## 8. The one 2026-specific edge nobody else in your league will price

**Half-PPR systematically underprices low-catch RBs relative to the PPR-consensus ADP everyone is drafting off.** Per §1, a ~30-reception back gains **+32.5 pts (≈ +1.9/gm)** over a ~95-reception WR relative to full PPR.

**Move up ~half a round to a full round in this league:**
- **Derrick Henry** (BAL, ADP 15.7) — the biggest beneficiary on the board
- **Kenneth Walker III** (SEA, 22.9)
- **David Montgomery** (HOU) — Fantasy Life: "a path to his largest workload in years"
- **Rhamondre Stevenson** (NE) — was RB21 in PPG as the Pats' lead back last year

**Move DOWN slightly:** McCaffrey (102 rec in 2025 — he loses the most of anyone in the format) and, marginally, pure receiving backs.

---

## 9. Draft-slot verdict (order randomized 1 hour out — have all three plans ready)

### 12-TEAM

| Slot | Build | Why |
|---|---|---|
| **1–2** | **ROBUST-RB** ✅ | Gibbs/Bijan + back-to-back 24/25 lets you take two of Achane/Cook/Jeanty/Brown/Henry. Genuinely correct here. |
| **3–5** | **HERO-RB in reverse** — take Chase / Nacua / JSN in R1 | Gibbs and Bijan are gone; the R1 RB left is McCaffrey (August tightness) or Taylor. Don't force it. Your hero comes at 2.x from Jeanty/Brown/Henry. |
| **6–9** | **HERO-RB** ✅ (classic slot) | You get exactly one of Taylor/Achane/Cook/Jeanty *or* a top-6 WR. Take the RB if the board hands you one, then hammer WR + Bowers/McBride + Lamar. |
| **10–12** | **ROBUST-RB** ✅ (second-best) | The 12/13 or 11/14 double-tap banks two Tier-2 RBs before the pick-55 RB24 cliff. |

### 10-TEAM
**Never go Robust-RB.** RB24 at pick 55 is round 6 of a 10-team — you can land a startable RB2 in rounds 5–6 without paying premium capital. WR replacement level is WR25, which is a genuinely good player. **Hero-RB from every slot**, with Robust-RB tolerable only from 1–2 or 9–10 if two Tier-2 backs fall to the turn. PFF's own 10-team guide says build "three set-and-forget wide receivers in Rounds 3 through 6."

### Hard rules for today
1. **Never draft 3 RBs in the first 3 rounds from picks 3–9.** That is the one genuinely losing version of RB-heavy.
2. **No handcuff before round 11.** With 4 bench spots and RB46+ permanently free, handcuffing is redundant.
3. **K and D/ST with your last two picks, and stream both all season.** The −7/−6/−5 yards-allowed penalties make a set-and-forget D/ST an active liability.
4. **No QB2, no TE2.** 1-day waivers + unlimited adds cover the byes.
5. **Get your RB1 by pick ~24 and your RB2 by pick ~55**, because RB24 goes at 55 and there is no RB starter after it.
6. **Draft as if you will lose every contested waiver claim**, because inverse-standings weekly reset means a winning team does.
