> ## ⚠️ READ THIS FIRST — RESEARCH LIMITATION DISCLOSURE
>
> **I could not perform any live web research.** Two independent blockers:
> 1. **Search budget exhausted before I started.** This session had already consumed 200/200 `WebSearch` calls. My first two searches returned: *"Web search was not performed: this session has used its web search budget."*
> 2. **Network egress proxy blocks every fantasy/NFL source.** Every `WebFetch` returned `EGRESS_BLOCKED`. I attempted FantasyPros (×2), Sleeper, Underdog, PFF, EstablishTheRun, 4for4, FootballGuys, DraftSharks, RotoBaller, Reddit. The proxy log also shows a prior agent in this session was already rejected by ESPN API, NFL.com, RotoWire, Ourlads, FantasyData, FantasyNerds, DynastyLeagueFootball, and Wikipedia.
>
> **Consequence:** I have **ZERO verified 2026 ADP**. Per your explicit instruction — *"Never fabricate a player name, team, or ADP figure"* — I am **not printing a single ADP number**, because every one I could produce would be invented. That instruction outranks the "give exact ADP" instruction when the data is unobtainable.
>
> **What IS fully reliable below:** Sections 1, 3, 4, 6 and the Verdict. These are **pure math on your league settings**, which you gave me. They need no external data and are the load-bearing part of your question. My knowledge cutoff is **May 2026**, so I have the completed 2025 season, 2026 free agency, and the 2026 draft — but **nothing from June–August 2026** (camp, preseason, injuries, ADP).

---

# The One-Sentence Answer

**Your league is the anti-Zero-RB league on five independent structural axes simultaneously.** Zero-RB's native habitat is full-PPR / 3-WR / 6-7 bench spots / FAAB / 6-of-12 playoffs. Yours is half-PPR / 2-WR / **4** bench spots / **inverse-standings waivers** / **4-team playoffs**. Every single axis moves against it. **Play Anchor-RB (Hero-RB) with a WR-heavy middle instead.**

---

# 1. Does 2WR + FLEX suppress WR value? Yes — but only HALF as much as it looks

This is the question most people get wrong, and the naive answer is wrong in an important way.

### The naive read overstates the damage

| Read | 12-team WR starter demand | Change |
|---|---|---|
| **Naive (mandatory slots only)** | 36 → 24 | **−33%** |
| **Real (mandatory + FLEX equilibrium)** | 42 → 33 | **−21%** |

The FLEX cushions roughly a third of the blow. Here's why: in a 2WR league the WR pool is deep relative to demand, so the marginal WR outscores the marginal RB, so **the FLEX gets filled with a WR by most teams anyway.** You don't lose a WR slot; you lose *most* of one.

Critically — **a Zero-RB team flexes a WR by definition** (its RBs are dart throws). So a Zero-RB roster starts 3 WRs here, not 2. The "only 2 WR!" objection is weaker against Zero-RB specifically than against a balanced build.

### But RB demand falls too — and this is the subtle part

Because the FLEX absorbs WRs, **fewer RBs are started league-wide** than in a 3WR league (27 vs 30 in a 12-teamer). That *raises* the RB replacement baseline, which *shrinks* elite-RB VOR as well. Both positions get devalued.

### VOR table (12-team, half-PPR PPG)

Replacement levels: **This league** WR33 = 10.6, RB27 = 9.6 · **Standard 3WR** WR42 = 9.7, RB30 = 9.0

| Player | VOR (std 3WR) | VOR (this league) | Change |
|---|---|---|---|
| WR1 | 9.8 | 8.9 | **−9%** |
| WR3 | 7.5 | 6.6 | **−12%** |
| WR6 | 5.8 | 4.9 | **−16%** |
| WR12 | 4.3 | 3.4 | **−21%** |
| WR18 | 3.1 | 2.2 | **−29%** |
| RB1 | 12.0 | 11.4 | −5% |
| RB3 | 9.0 | 8.4 | −7% |
| RB6 | 7.0 | 6.4 | −9% |
| RB12 | 4.5 | 3.9 | −13% |

**Elite RB : elite WR VOR ratio moves from 1.20 → 1.27.** RB gains about **6% of relative value.**

### Verdict on Q1

**Yes, WR-heavy is structurally weakened — but modestly, ~6% at the elite tier, not catastrophically.** The damage compounds down the WR board (−29% at WR18), which is exactly where a WR-heavy build stacks its 4th and 5th receivers. **The 2WR setting alone is NOT enough to kill Zero-RB.** The bench constraint (§3) is what kills it.

*⚠️ The PPG-by-rank curves used are historical-average positional SHAPES, not 2026 projections for any player. The percentage deltas are robust to reasonable changes in these curves; the absolute PPG values are not.*

---

# 2. State of Zero-RB in 2026 — ⚠️ UNVERIFIED

**I cannot answer this. I could not reach a single 2026 article.** Do not act on anything in this section without checking it yourself.

What I can say, clearly labeled:

**Through my May 2026 cutoff**, the industry trend had been running *against* Zero-RB for roughly three seasons. The drivers, as of that point:
- A genuine bell-cow revival — elite dual-threat backs (Bijan Robinson, Jahmyr Gibbs, De'Von Achane, Saquon Barkley, Ashton Jeanty) delivering three-down, pass-catching workloads that produce RB scoring unavailable at any other position.
- Notably strong recent rookie-RB hit rates, which raises the *ex-ante predictability* of RB — and RB unpredictability is the entire foundation of the Zero-RB thesis.
- Prevailing framing had shifted toward "Anchor RB" / "Hero RB" / "Robust RB" as the default, with Zero-RB retained as a **best-ball, full-PPR, deep-bench** tactic rather than a general-purpose redraft strategy.

**⚠️ UNVERIFIED for 2026 specifically.** I have no visibility into the August 2026 discourse.

**Do this before 2:00 PM:** search *"Zero RB 2026"* on FantasyPros, Establish The Run, PFF, and r/fantasyfootball. Ten minutes of reading replaces this entire section.

**Important framing:** the published state of the debate is **the least important input to your decision.** Generic Zero-RB commentary is written for full-PPR, 3-WR, deep-bench leagues. Your format deviates on five axes at once, so the *format math below is far more decisive than any article's verdict.*

---

# 3. 🔪 THE KILLER OBJECTION — and it is fatal

You identified the right objection. It is worse than you framed it, because it isn't a difficulty. **It's an infeasibility proof.**

### The constraint

```
13 active roster spots
Mandatory: 1 K + 1 D/ST + 1 QB + 1 TE  =  4 spots consumed
Therefore:   WR count (w) + RB count (r)  ≤  9
```

### Canonical Zero-RB's requirements

- **r ≥ 5** — you need 5+ RB lottery tickets, because that's the whole strategy
- **w ≥ 5** — you need 4 startable WRs *plus at least one bench WR*, or a single WR injury detonates your only competitive advantage

**w + r ≥ 10 > 9. The strategy does not fit. It is arithmetically impossible.**

### Every feasible shape breaks a leg

| Shape | Total | Assessment |
|---|---|---|
| **WR5 + RB4** | 9 ✅ | This is **Anchor-RB**, not Zero-RB. Only 3 tickets — mathematically forces you to own a real RB. |
| **WR4 + RB5** | 9 ✅ | "True" Zero-RB. **Zero bench WR insurance.** One WR injury and the thesis is dead. |
| **WR6 + RB3** | 9 ✅ | 3 RBs while starting 2. One RB injury = starting a waiver pickup immediately. |
| **WR5 + RB5** | 10 ❌ | **What Zero-RB actually wants. Does not fit.** |

Want a backup QB or a second TE? Now `w + r ≤ 8` and it gets strictly worse.

### The bye-week compounder

Bye weeks span ~10 weeks. Birthday-problem math on collisions:

| Rostered | P(≥2 share a bye week) |
|---|---|
| 3 RBs | 28.0% |
| **4 RBs** | **49.6%** |
| 5 players | 69.8% |

With 4 RBs and 2 RB slots to fill, there is a **~50% chance of a week where you must start a waiver-wire RB.** Add one injury and it approaches certainty. The WR4+RB5 build fares no better — 70% chance of a WR bye collision with only 4 WRs and 3 WR-capable slots.

### The head-to-head model — the single most important number in this report

Same two rosters. Only the WR lineup slot changes. **I gave Zero-RB the benefit of hitting on an RB** (a 14.0-PPG breakout — a genuine league-winner).

*Assumptions (half-PPR PPG, illustrative shapes, NOT 2026 projections):*
*Zero-RB — WRs 17.0/15.0/13.5/12.5, RBs 14.0 (the hit)/8.0 · Anchor-RB — RBs 17.0/11.0, WRs 15.0/13.0/12.0/10.5*

| Format | Zero-RB | Anchor-RB | Result |
|---|---|---|---|
| **Standard 3WR+FLEX** (starts 4 WR) | RB 22.0 + WR 58.0 = **80.0** | RB 28.0 + WR 50.5 = **78.5** | ✅ **Zero-RB wins by 1.5** |
| **YOUR LEAGUE 2WR+FLEX** (starts 3 WR) | RB 22.0 + WR 45.5 = **67.5** | RB 28.0 + WR 40.0 = **68.0** | ❌ **Anchor-RB wins by 0.5** |

**The identical rosters flip result on one lineup setting — in the scenario where Zero-RB HITS.** In the ~40–50% of seasons where no dart lands, it isn't close.

Mechanically: Zero-RB's WR edge shrinks from +7.5 to +5.5 PPG (its 4th WR is stranded on a bench spot it can't spare), while its RB deficit stays at −6.0. The strategy's entire margin evaporates.

### 3b. But shallow benches also help Zero-RB — the strongest counter-argument

This is real and I'm giving it full weight:

| | This league | Standard 16-man | Extra free talent |
|---|---|---|---|
| 12-team | 156 rostered (132 skill) | 192 (168 skill) | **+36 players (~3 extra rounds)** |
| 10-team | 130 rostered (110 skill) | 160 (140 skill) | **+30 players (~3 extra rounds)** |

**You can't hoard — but neither can anyone else.** ~3 full rounds' worth of talent that would be locked on benches in a normal league sits on your wire all season. The tickets you couldn't stash in August are *still there in Week 6.* This genuinely reduces the cost of not hoarding.

**But it does not rescue the strategy,** because the infeasibility proof is about your *lineup*, not your access to players. A deep wire helps you find an RB2. It does nothing about the fact that your 4th elite WR has nowhere to play.

---

# 4. Does the waiver system rescue it? **No — it's the worst possible system for Zero-RB**

You framed this as a potential rescue. Rigorously: **it's an additional kill shot, and it's the least obvious one.**

### The anti-correlation problem

Zero-RB is a promise: *"I punt RB in August and repair it in-season."* Your league's waiver design **specifically prevents winning teams from repairing anything.**

```
Zero-RB is WORKING  →  you have a good record
                    →  inverse-standings order puts you 8th–12th
                    →  P(winning the week's top RB claim) ≈ 0
```

**Waiver priority is anti-correlated with the strategy's success.** In the exact scenario where Zero-RB pays off — elite WRs carrying you to 3-1 while you hunt an RB — you have the **worst claim priority in the league.** The 0-4 team gets the breakout back.

### No FAAB is the specific killer

This is the crux. **With FAAB, a winning Zero-RB team simply outbids** — drop 60% of budget on the Week 3 backfield takeover and the strategy works exactly as designed. FAAB decouples repair capability from record.

**Your league has no FAAB.** Inverse-standings priority *couples* them, inversely. You cannot buy the fix at any price. **Zero-RB's core repair mechanism is disabled.**

### Steelmanning the counter, honestly

Three things genuinely work in your favor:

1. **1-day waivers + unlimited acquisitions + no FAAB = zero-friction churn.** Your 4th bench spot becomes a *rotating carousel* — cycle it 15–20× per season at literally no cost. That's real and worth having.
2. **Post-waiver FCFS window.** Once the 1-day period clears, unclaimed players become free agents, first-come-first-served. A diligent manager gets many bites.
3. **Shallow benches keep the wire rich** (see §3b).

**But #1 and #2 capture the wrong players.** Churn wins you *tier-2 speculation.* Zero-RB doesn't need speculation — **it needs THE hit**, the one back who takes over a backfield. That player is claimed on waivers by a losing team before he ever reaches the FCFS window.

**Zero-RB needs the top claim, weekly, while winning. This system structurally denies exactly that.**

### 🚨 THE SINGLE HIGHEST-VALUE THING TO CHECK BEFORE 2:00 PM

**ESPN → League Settings → Transactions → Player Acquisition.** Determine whether **undrafted players** are (a) continuous free agents, FCFS, or (b) routed through the waiver period.

- **(a) FCFS** → Zero-RB gets **meaningfully** more viable. A fast, attentive manager can grab the emerging back on Monday morning before waivers matter at all. This partially restores the repair mechanism.
- **(b) Waivers** → the analysis above holds in full and **Zero-RB is close to unplayable.**

*ESPN commonly ships (a) as default with waivers applying to dropped players, but this is league-configurable and I cannot verify your league's setting.* **This one checkbox is worth more to your decision than anything else in this report.**

### 4b. The playoff structure — a second, independent kill shot

| Format | Playoff qualification rate |
|---|---|
| **12-team, 4 spots** | **33%** |
| **10-team, 4 spots** | **40%** |
| Standard 6-of-12 | 50% |

**Zero-RB's expected value is back-loaded.** RB breakouts land Weeks 4–12. The strategy deliberately accepts a slow start.

In a 6-of-12 league you can start 1-3 and still make the field. **In a 4-of-12 league (33%), a 1-3 start is usually terminal.** You have dramatically less margin for the exact failure mode Zero-RB is built around.

**Mildly offsetting:** 2-week playoff matchups halve variance and reward the higher-mean roster (which a *successful* Zero-RB team is by December), and the total-points seeding tiebreaker favors top-heavy WR rooms. **Net: the playoff structure is strongly anti-Zero-RB on entry, mildly pro once in.** Entry dominates — you have to get there first.

---

# 5. WR vs RB durability and volatility — ⚠️ DIRECTIONAL ONLY

**I could not verify a single 2026-specific injury rate.** These are historically stable, directionally reliable findings — treat the direction as sound and any implied precision as unverified.

### Season-long availability — advantage WR (a real Zero-RB argument)

- RB has the **highest injury incidence and shortest career length** of any skill position. Not close.
- Historically **roughly half** of preseason top-24 RBs miss meaningful time; top-24 WRs are materially lower.
- RB failures skew toward **injury**; WR failures skew toward **underperformance**. Injury is less predictable and less recoverable.

### 🔥 The shallow-bench twist — the best pro-Zero-RB argument in this report

**With 4 bench spots, you cannot handcuff your own stud RB.**

If you spend pick 1.03 on an elite back and he's lost in Week 4, your first-round pick is **dead, unhedged, and unreplaceable** — you never had room to roster his backup, and the waiver order won't give him to you either. Meanwhile a first-round WR is far likelier to play a full season.

**Shallow benches make early RB investment structurally riskier, not just Zero-RB harder.** This genuinely cuts both ways and I want to be honest that it's a strong point.

*(It does not overturn the verdict — but it does mean: prefer the **durable** elite RB profile over the highest-ceiling one, and see the mitigation in the draft plan below.)*

### Week-to-week volatility — advantage RB

- **RBs have higher weekly floors.** Carries are far more stable week-to-week than targets and air yards. Volume is game-script-protected in a way receiving is not.
- **WRs have higher ceilings and higher bust rates** — coefficient of variation runs higher at comparable ADP.

**In a 4-team-playoff league, weekly consistency is worth more than usual.** You need *wins*, not points — and a top-heavy, boom-bust WR room converts points into wins less efficiently. This compounds §4b.

### Net

**RB = higher weekly floor, lower season-long availability. WR = lower weekly floor, higher availability.** Your format punishes both sides: 4-team playoffs punish WR volatility; 4 bench spots punish RB fragility. Neither position gets a clean win — but the *lineup* math in §3 does.

---

# 6. Half-PPR vs full PPR — worth ~1.8 PPG, and it flips orderings

Computed with **your league's exact scoring** (0.5/rec, 0.1/yd, 6 for all TDs).

### The 100-catch WR

| | Full PPR | Half PPR | Loss |
|---|---|---|---|
| **WR: 100 rec / 1,200 yds / 7 TD** | **262** | **212** | **−50 pts (−2.94 PPG)** |
| **RB: 1,150 rush / 10 rush TD + 40/300/1** | **251** | **231** | **−20 pts (−1.18 PPG)** |

### The ordering flips

```
FULL PPR:   WR 262  vs  RB 251   →  WR ahead by 11
HALF PPR:   WR 212  vs  RB 231   →  RB ahead by 19
                                    ─────────────────
              30-POINT SWING (1.76 PPG) — SAME PLAYERS
```

**Reception-edge math:** a 100-catch WR's reception advantage over a 40-catch RB goes from **60 points to 30 points.** WR-heavy's single largest structural advantage is **cut exactly in half by definition.**

### Total format cost vs Zero-RB's native habitat

| Source | Cost to Zero-RB |
|---|---|
| 2WR instead of 3WR (WR edge +7.5 → +5.5) | **2.0 PPG** |
| Half-PPR instead of full PPR | **1.8 PPG** |
| **Combined** | **≈3.8 PPG** |
| **Over a 14-week regular season** | **≈53 points** |

That is roughly **one full extra win of margin** surrendered before the draft starts — and it excludes the bench infeasibility and the waiver structure, which are the actual killers.

---

# 7. Targets — ⚠️ NO ADP AVAILABLE, NAMES REQUIRE VERIFICATION

**I have no 2026 ADP and will not invent any.** Below are names I have reason to believe were relevant as of **May 2026**. **Every team assignment, role, and health status must be verified** — I have no June–August 2026 information, which covers free-agent stragglers, camp battles, preseason injuries, and depth-chart changes.

### 🚨 Do this in your first 10 minutes

Open **FantasyPros half-PPR ADP** *and* **ESPN's own live-draft ADP** side by side. ESPN's ADP diverges materially from consensus because ESPN drafters follow ESPN's ranks — **and you are drafting on ESPN.** Use ESPN ADP for timing, consensus ranks for value.

### Elite RB tier — target in Round 1 (⚠️ verify team/health)

Bijan Robinson · Jahmyr Gibbs · Saquon Barkley · Ashton Jeanty · De'Von Achane · Jonathan Taylor · Christian McCaffrey *(age)* · Josh Jacobs · Bucky Irving · Omarion Hampton · Chase Brown · Kyren Williams · James Cook · Derrick Henry *(age)* · Kenneth Walker III · TreVeyon Henderson · Quinshon Judkins

*Given §5 (no room to handcuff), prefer the **durable, three-down, pass-catching** profile over the highest-ceiling one.*

### Elite WR tier — target Rounds 2–4 (⚠️ verify team)

Ja'Marr Chase · Justin Jefferson · CeeDee Lamb · Amon-Ra St. Brown · Puka Nacua · Malik Nabers · Nico Collins · Brian Thomas Jr. · Drake London · A.J. Brown · Garrett Wilson · Jaxon Smith-Njigba · Ladd McConkey · Tee Higgins · Rome Odunze · Marvin Harrison Jr. · Tetairoa McMillan · Emeka Egbuka · Travis Hunter · Matthew Golden

### TE (⚠️ verify)

Brock Bowers · Trey McBride · George Kittle · Sam LaPorta · Tyler Warren · Colston Loveland · Tucker Kraft · T.J. Hockenson · David Njoku · Jake Ferguson

**With only 4 bench spots, do NOT roster two TEs.** Either secure a top-2 TE or take the last starting-caliber one and stream.

### QB — take late, roster exactly one

Josh Allen · Lamar Jackson · Jayden Daniels · Jalen Hurts · Patrick Mahomes · Joe Burrow · Drake Maye · Bo Nix · C.J. Stroud · Caleb Williams · Baker Mayfield · Kyler Murray · Jordan Love

**Never roster a backup QB.** One roster spot is ~7.7% of your team; QB is the easiest position to stream.

### RB dart throws — ARCHETYPES, since I can't verify ADP

I can't name the specific 2026 late-round backs. **Sort your board by these five filters instead — this is more durable than a stale name list anyway:**

1. **Direct backup to a bell cow who is age 29+ or has injury history.** Highest-value ticket type — one injury converts him to an RB1. *Your best category by far.*
2. **Rookie/2nd-year RB in a committee** where the incumbent is on a one-year deal or underperformed.
3. **Pass-catching back in a high-implied-total offense.** Half-PPR floor plus game-script immunity — he scores in losses.
4. **Any backfield the beat writers call unsettled in mid-August.** Camp reporting is the entire edge here and it's free.
5. **Goal-line specialists on good offenses.** Rush TD = 6 in your scoring, so TD equity is worth a lot.

### K and D/ST — last two picks, always

Your D/ST **yards-allowed scale is unusually wide (+5 to −7)**. A bad week can post roughly −10 before sacks and turnovers. That volatility makes D/ST **highly matchup-dependent — so stream it**, and never roster two. Combined with 1-day waivers and unlimited free acquisitions, streaming D/ST costs you nothing and is strictly correct here.

**Never draft a K before the final pick.** With `w + r ≤ 9`, one wasted roster spot is ~7.7% of your team.

---

# 🏆 VERDICT

## True Zero-RB: NO. Not viable. It is arithmetically infeasible, not merely difficult.

Five independent structural strikes:

| # | Strike | Severity |
|---|---|---|
| 1 | **`w + r ≤ 9` makes canonical Zero-RB literally impossible** | 🔴 **FATAL** |
| 2 | **No FAAB + inverse-standings waivers disables the repair mechanism, anti-correlated with success** | 🔴 **FATAL** |
| 3 | **4-of-10/12 playoffs punish the slow start Zero-RB accepts by design** | 🟠 Severe |
| 4 | **Half-PPR halves the reception edge (−1.8 PPG)** | 🟡 Moderate |
| 5 | **2WR compresses elite WR VOR ~12%, strands the 4th WR (−2.0 PPG)** | 🟡 Moderate |

Strikes 4 and 5 alone cost ~53 points a season. **Strikes 1 and 2 are the ones that end it.** And the head-to-head model shows Zero-RB losing *even when it hits.*

## ✅ PLAY THIS INSTEAD: Anchor-RB (Hero-RB) + WR-heavy middle

You keep ~80% of the WR-heavy upside you wanted while removing the infeasibility.

**Roster template — WR5 / RB4 / QB1 / TE1 / K1 / D/ST1 = 13**

```
STARTERS (9):  QB · RB1 · RB2 · WR1 · WR2 · TE · FLEX=WR3 · D/ST · K
BENCH   (4):  RB3 · RB4 · WR4 · WR5
```

Insurance at both positions. Three WRs starting every week. Fits exactly.

**Round-by-round:** R1 anchor RB (or elite WR from a late slot) → **R2–R4 hammer WR** → R5–R6 your RB2 → TE in its value window → RB darts R7–R9 → **QB late** → K and D/ST with your final two picks.

**Do not exit Round 5 without two RBs.**

## 📍 By draft slot (order randomizes at 1:00 PM — have all three branches ready)

### Picks 1–4 → 🚫 **Zero-RB is actively, unambiguously wrong**
Take the elite RB. You are being handed the scarcest asset in the format at its cheapest relative cost. Passing is a straightforward error. Then hammer WR in Rounds 2–4.

### Picks 5–8 → ⚖️ **Best player available, then correct immediately**
Take whichever of (elite RB / elite WR) represents better value. **If you take a WR at 1.05–1.08, you MUST take an RB in Round 2 or early Round 3.** Never WR-WR-WR-WR.

### Picks 9–12 → ✅ **The only slot where WR-heavy is genuinely right**
Elite RBs are gone; you're in the RB dead zone. **WR-WR at the 1–2 turn is correct here.** Then WR or TE at 3, and start on RBs Rounds 4–5. This is **"Late-Round RB," not Zero-RB** — you still own a real back by Round 5. In a 2WR half-PPR room, drafters often push RBs up, so a top-5 WR frequently survives to 1.09+. Take him.

## 📊 10-team vs 12-team

- **12-team:** Anchor-RB is **clearly** correct. Scarcity is real, the wire is thinner, mistakes compound.
- **10-team:** Zero-RB is **more survivable** (only 110 skill players rostered — the wire is stacked) but **less rewarding**: elite WR3 VOR is just 5.9 vs 6.6 in a 12-teamer, because replacement level is so high. **Structure matters less overall — lean BPA, take the value, don't force anything.** Still not optimal, just less punished.

## ✔️ Pre-draft checklist — 15 minutes, before 2:00 PM

1. 🚨 **ESPN → Settings → Transactions → Player Acquisition.** Are undrafted players FCFS free agents or routed through waivers? **This single checkbox is the highest-leverage unknown in your entire draft.**
2. **Confirm league size (10 vs 12).** Changes every tier boundary.
3. **Pull live half-PPR ADP** — FantasyPros consensus *and* ESPN's own ADP. They will disagree; you're drafting on ESPN.
4. **Injury/camp check your top 15 targets.** It's Aug 22 — preseason Week 3 has happened and there is fresh news I do not have.
5. **Pre-queue 3–4 deep at every position.** 90 seconds per pick is not enough time to think.
6. **Write all three slot branches on paper** before the order is revealed at 1:00 PM.

---

### Confidence summary

| Section | Confidence | Basis |
|---|---|---|
| §1, §3, §4, §6, Verdict | 🟢 **High** | Pure math on league settings you provided |
| §5 | 🟡 **Medium** | Historically stable findings, directional only |
| §2, §7 | 🔴 **Low / UNVERIFIED** | No live data reachable; names from May 2026 knowledge, **zero ADP** |
