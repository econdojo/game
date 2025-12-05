---
marp: true
math: mathjax
theme: default
size: 4:3
paginate: true
backgroundColor: '#f4f6fa'
backgroundImage: url('https://marp.app/assets/hero-background.svg')
header: 'Lecture 8: Perfect Bayesian Equilibrium'
footer: 'Fei Tan | Together We Advance.'
style: |
  .logo {
    vertical-align: -0.2em;
  }
  section {
    color: #222;
    font-size: 24px;
    padding: 50px;
  }
  h1 {
    color: #003DA5;
    font-size: 38px;
    margin-bottom: 18px;
  }
  h2 {
    color: #003DA5;
    font-size: 30px;
    margin-bottom: 15px;
  }
  h3, h4, h5, h6 {
    color: #003DA5;
  }
  .slide-footer {
    color: #888;
  }
  .highlight {
    background-color: #ffeb3b;
    padding: 2px 4px;
    border-radius: 3px;
  }
  .identity-box {
    background-color: #f0f0f0;
    border-radius: 10px;
    padding: 12px;
    margin: 12px 0;
    text-align: center;
    border: 2px solid #ddd;
    font-size: 20px;
  }
  table {
    margin: 15px auto;
    border-collapse: collapse;
    font-size: 19px;
  }
  table th, table td {
    border: 2px solid #003DA5;
    padding: 8px 12px;
    text-align: center;
  }
  table th {
    background-color: #003DA5;
    color: white;
  }
  ul, ol {
    margin: 10px 0;
    padding-left: 25px;
  }
  li {
    margin: 6px 0;
    line-height: 1.5;
  }
  p {
    margin: 10px 0;
    line-height: 1.5;
  }
---

# Lecture 8: Perfect Bayesian Equilibrium

**Instructor:** Fei Tan

<img src="images/github.png" width="30" height="30" class="logo"> @econdojo &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/youtube.png" width="30" height="30" class="logo"> @BusinessSchool101 &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/slu.png" width="30" height="30" class="logo"> Saint Louis University

**Date:** November 11, 2025

---

## The Road Ahead

1. [Perfect Bayesian Equilibrium](#perfect-bayesian-equilibrium-pbe)
2. [Screening Games](#screening-games)
3. [Adverse Selection](#adverse-selection)
4. [Signaling Games](#signaling-games)
5. [Separating Equilibrium](#separating-equilibrium)
6. [Pooling Equilibrium](#pooling-equilibrium)
7. [Semi-Separating Equilibrium](#semi-separating-equilibrium)

---

## Perfect Bayesian Equilibrium (PBE)

Finding our place in the game theory toolkit:

| Game Timing | Information | Solution Concept |
|-------------|-------------|------------------|
| Simultaneous | Complete | Nash Equilibrium |
| Sequential | Complete | Subgame Perfect Equilibrium |
| Simultaneous | Incomplete | Bayesian Nash Equilibrium |
| **Sequential** | **Incomplete** | **Perfect Bayesian Equilibrium** |

**Key insight**: PBE combines sequential rationality (from SPE) with beliefs about types (from BNE)

---

## Definition of PBE

A Perfect Bayesian Equilibrium is a set of strategies and beliefs such that:
1. Strategies are sequentially rational given beliefs
2. Players update beliefs via Bayes' rule wherever possible

**Critical point**: A PBE solution requires BOTH strategies AND beliefs
- Leaving out one means your answer is wrong
- Common mistake: forgetting beliefs (like forgetting off-path strategies in SPE)

**Why beliefs matter**: In incomplete information, credibility of threats depends on what you believe about opponent types

---

## Three Pillars of PBE

**Pillar 1: Strategies AND Beliefs**
- Solution must specify what players do (strategies) and what they think (beliefs)
- These are inseparable partners

**Pillar 2: Sequential Rationality**
- Strategy must be best choice at every point, given current beliefs
- Credibility filtered through beliefs: "Maybe I fight a weak type but not a strong type"

**Pillar 3: Updating with Bayes' Rule**
- Initial prior belief → Observe action → Updated posterior belief
- Example: If only strong types bully, seeing bully makes you certain opponent is strong
- Caveat: Only works "wherever possible" (when observed action has positive probability)

---

## Off the Equilibrium Path

**The problem**: What if a player does something that should never happen?
- Proposed equilibrium assigns zero probability to this action
- Bayes' Rule breaks down (division by zero)
- Called "off the equilibrium path"

**Example**: In separating equilibrium where strong type Reveals and weak type Hides
- If we see Hide → Bayes' Rule tells us type is weak (on path)
- If we see unexpected action → Must specify belief without Bayes' Rule (off path)

**Importance**: Off-path beliefs justify on-path actions
- The threat of what would happen off path prevents players from deviating

---

## Screening vs. Signaling Games

Two main categories of PBE applications:

| Type | Who Moves First | Complexity | Signal Information |
|------|----------------|------------|-------------------|
| **Screening** | Uninformed player | Simpler | First move cannot signal private info |
| **Signaling** | Informed player | More complex | First move can signal type |

**Signaling game outcomes**:
- Separating equilibrium: Different types choose different actions
- Pooling equilibrium: All types choose same action
- Semi-separating equilibrium: One type mixes, creating strategic bluffing

---

## Screening Games

**Definition**: Incomplete information game where the uninformed player moves first

**Example game structure**:
1. Nature chooses Player 2's type: Weak (prob $p$) or Strong (prob $1-p$)
2. Player 1 (uninformed) chooses: Escalate or Quit
3. Player 2 (informed) observes choice, then decides: Fight or Concede

**Key feature**: Dashed line in game tree shows Player 1's information set (uncertainty about type)

---

## Solving a Screening Game

**Step 1**: Solve for informed player (Player 2)
- Weak type: Concede (0) > Fight (-0.1) → Always concede
- Strong type: Fight (0.8) > Concede (0) → Always fight

**Step 2**: Solve for uninformed player (Player 1)
- Payoff from Quit: 0 (certain)
- Expected payoff from Escalate: $p \times 1 + (1-p) \times (-0.2) = 1.2p - 0.2$
- Escalate if $1.2p - 0.2 > 0$ → $p > \frac{1}{6}$

**Equilibrium**:
- If $p > \frac{1}{6}$: P1 escalates; P2 concedes if weak, fights if strong
- If $p < \frac{1}{6}$: P1 quits; (P2's strategy still specified but not used)

---

## Why "Screening"?

Escalating serves as a test or "screen":
- Separates different types by eliciting different behaviors
- Weak type concedes, strong type fights
- Uninformed player can use this action to "filter" opponent types

**Strategic choice**: Whether to screen (escalate) or not (quit)

**Contrast with signaling**: In screening, first mover has no private information to reveal

---

## Adverse Selection

"If a person accepts your transaction at some price, does the very fact that they accepted it mean that you no longer want to go through with it?"

**Definition**: Market failure when one party has crucial private information
- Information asymmetry leads to dysfunctional outcomes
- Prevents mutually beneficial trades

**Key examples**:
- Insurance: Healthy vs. unhealthy customers
- Used cars: "Market for lemons"
- Real estate: Hidden defects

---

## Insurance Game Example

**Setup**:
- Insurer wants profit, Customer wants protection
- Private information: Customer knows if healthy or unhealthy

| Metric | Healthy (60%) | Unhealthy (40%) |
|--------|--------------|-----------------|
| Cost to Insure | $400 | $800 |
| Willingness to Pay | $750 | $1,250 |

**Insurer's calculation**:
- High price ($1,000): Only unhealthy accept → $0.6(0) + 0.4(200) = 80$
- Low price ($500): Both accept → $0.6(100) + 0.4(-300) = -60$

**Result**: Insurer offers only high price → Healthy customers left uninsured

---

## Market Failure in Action

**Why this is a problem**: Mutually beneficial trade is missed
- If insurer knew customer was healthy: Offer $500, customer accepts, both better off
- Insurer makes $100 profit, customer gets valued insurance

**Information asymmetry prevents this**:
- Cannot safely offer low price (risk of unhealthy customers)
- High price drives away profitable healthy customers
- Market failure: Inefficient outcome

**Same principle applies to**:
- Used cars: Low offers accepted mainly by "lemons"
- Houses: Low offers accepted by sellers hiding defects

---

## Solutions to Adverse Selection

**Four main approaches**:

1. **Reputation**: Long-term incentives create trust
   - Dealership vs. Craigslist seller

2. **Third-party verification**: Independent experts level information
   - Home inspectors, mechanics

3. **Government regulation**: Re-allocate risk
   - Lemon laws give buyers right to return defective cars

4. **Government intervention**: Pool all types
   - Universal healthcare eliminates selection problem

**Common thread**: All solutions close the information gap

---

## Signaling Games

**Definition**: Informed player moves first, action can signal their type
- Opposite of screening games
- First mover's action potentially reveals private information

**Example**: Job market
- Applicant (Player 1) knows own capability: High or Low type
- Employer (Player 2) has 50/50 prior belief
- Applicant chooses: College or High School
- Employer observes choice, then decides: Hire or Pass

**Three possible equilibrium types**: Separating, Pooling, Semi-separating

---

## Separating Equilibrium

**Definition**: Different types choose different actions to distinguish themselves

**Job market example**:
- High type always goes to college
- Low type always gets high school diploma

**Employer's inference**:
- See College → 100% certain applicant is High type
- See High School → 100% certain applicant is Low type

**Key insight**: Signal completely reveals private information
- Uncertainty eliminated
- Action speaks louder than words

---

## Pooling Equilibrium

**Definition**: All types choose same action, hiding their identity

**Job market example**:
- High type gets high school diploma
- Low type also gets high school diploma

**Employer's inference**:
- See High School → Learn nothing new
- Belief remains at prior: 50/50

**Key insight**: Signal reveals no information
- All types "pool" together
- Beliefs don't change

**Complication**: Must still define off-path beliefs (what if someone goes to college?)

---

## Semi-Separating Equilibrium

**Definition**: One type uses pure strategy, other type mixes
- Most strategically interesting case
- Involves "true bluffing behavior"

**Job market example**:
- High type always goes to college (pure strategy)
- Low type sometimes goes to college (30%), sometimes high school (70%) (mixed)

**Employer's inference**:
- See High School → 100% certain Low type (perfectly revealing)
- See College → Ambiguous; use Bayes' rule to update belief

**Key insight**: Partial information revealed, requires belief updating

---

## Summary: Three Equilibrium Types

| Type | What Players Do | What Uninformed Learns |
|------|----------------|----------------------|
| **Separating** | Different types → Different actions | Everything (perfect revelation) |
| **Pooling** | All types → Same action | Nothing (beliefs unchanged) |
| **Semi-Separating** | One type pure, other mixes | Something (partial revelation) |

Understanding these patterns is key to analyzing signaling games

---

## War Game: Finding Separating Equilibrium

**Setup**:
- State 1: Strong (60%) or Weak (40%)
- State 1 knows own type, State 2 doesn't
- State 1 chooses: Reveal (costly demonstration) or Hide
- State 2 wants to Fight Weak, Quit against Strong

**Testing separating strategy**: Strong Reveals, Weak Hides

**Step 1**: State 2 sees Hide → Believes Weak with 100% → Fights

**Step 2**: Check for profitable deviations
- Strong: Reveal (0.99) > Hide (0.5) ✓
- Weak: Hide (-1) > Reveal (-1.01) ✓

**Result**: This IS a stable separating equilibrium

---

## Failed Separating Equilibrium

**Testing opposite strategy**: Strong Hides, Weak Reveals

**Step 1**: State 2 sees Hide → Believes Strong with 100% → Quits

**Step 2**: Check for profitable deviations
- Strong: Hide (1) > Reveal (0.99) ✓
- Weak: **Deviate!** Hide (1) >> Reveal (-1.01)

**Fatal flaw**: Weak type has huge incentive to bluff
- Can pretend to be strong and get much better payoff
- Signal not credible

**Result**: This is NOT a stable equilibrium

---

## Pooling Equilibrium Example

**Testing strategy**: Both Strong and Weak Hide

**Step 1**: State 2 sees Hide → Learns nothing → Beliefs remain 60% Strong, 40% Weak

**Step 2**: State 2's expected utility
- Fight: $0.6(-1) + 0.4(0.5) = -0.4$
- Quit: $0$
- Best response: Quit (since $0 > -0.4$)

**Step 3**: Check for profitable deviations
- Strong: Hide (1) > Reveal (0.99) ✓
- Weak: Hide (1) > Reveal (-1.01) ✓

**Result**: This IS a stable pooling equilibrium

---

## Off-the-Path Beliefs

**The challenge**: When unexpected action occurs with zero probability
- Bayes' Rule cannot be applied
- Must specify belief without logical constraint

**Testing "Both Reveal" equilibrium**:
- If both types supposed to Reveal, seeing Hide is unexpected
- Let $p$ = belief that hider is Strong
- P2 fights if $0.5 - 1.5p > 0$ → $p < \frac{1}{3}$

**Checking deviations**:
- Strong: For $p \leq \frac{1}{3}$, deviation profitable only if P2 quits
- Weak: **Always has profitable deviation** (Hide always better than Reveal)

**Result**: This equilibrium fails regardless of off-path belief

---

## Beer-Quiche Game

**Setup**:
- P1 type: Real Man (60%, prefers beer) or Wimp (40%, prefers quiche)
- P1 chooses meal: Beer or Quiche
- P2 (coward) observes, decides: Fight or Quit
- P2 wants to fight only Wimps

**Payoffs**:
- P1: 2 points for avoiding fight + 1 point for preferred meal
- P2: +1 for fighting Wimp, -1 for fighting Real Man, 0 for quitting

**Question**: Is there a pooling equilibrium where both types drink beer?

---

## Solving Beer-Quiche Pooling

**Step 1**: Both types drink beer

**Step 2**: P2 sees beer → Beliefs unchanged (60% Real, 40% Wimp)
- Expected payoff for Fight: $0.6(-1) + 0.4(1) = -0.2$
- Payoff for Quit: $0$
- Best response: Quit

**Step 3**: Check deviations
- Real Man: Beer gives 3 (maximum) → No deviation
- Wimp: Beer gives 2; Quiche could give 3 if P2 quits, or 1 if P2 fights

**Key**: To prevent Wimp's deviation, P2 must Fight if sees Quiche (off-path belief)

---

## Beer-Quiche Solutions

**Solution Class 1**: $P(\text{Real Man}|\text{Quiche}) = p < \frac{1}{2}$
- P2 strictly prefers to Fight quiche-eater
- P1 strategy: Both drink beer
- P2 strategy: Quit if beer, Fight if quiche (with belief $p < 1/2$)

**Solution Class 2**: $P(\text{Real Man}|\text{Quiche}) = \frac{1}{2}$ exactly
- P2 indifferent between Fight and Quit
- P2 must fight with probability $\sigma \geq \frac{1}{2}$ to deter Wimp
- This keeps Wimp's expected payoff from deviating at most 2

**Key lesson**: Off-path beliefs hold equilibrium together
- Threat of fighting quiche-eater prevents deviation

---

## Semi-Separating Equilibrium

**When it arises**: Pure strategies (always attack or never attack) both fail

**Example: Terrorist game**
- Robust type (40%): Always attacks
- Vulnerable type (60%): Mixes between attack and not attack
- Target: Doesn't know type, must respond to attack

**Key concept**: Strategic indifference
- For player to mix, must be indifferent between choices
- Opponent's mixing probability must make player exactly indifferent

---

## Solving Semi-Separating: Indifference Conditions

**Making Vulnerable type indifferent** (to mix between attack/not):
- Payoff from not attacking: 0
- Expected payoff from attacking: $-2R + 1(1-R) = 1 - 3R$
- Set equal: $1 - 3R = 0$ → $R = \frac{1}{3}$
- Target must resist with probability $\frac{1}{3}$

**Making Target indifferent** (to mix between resist/ignore):
- Let $P$ = posterior belief attacker is Robust
- Expected payoff from resisting: $-3P + 2(1-P) = 2 - 5P$
- Payoff from ignoring: -1
- Set equal: $2 - 5P = -1$ → $P = \frac{3}{5}$

---

## Connecting Bluff to Belief

**Using Bayes' Rule** to find Vulnerable type's bluffing frequency:

$$P(\text{Robust}|\text{Attack}) = \frac{P(\text{Attack}|\text{Robust}) \cdot P(\text{Robust})}{P(\text{Attack})}$$

$$\frac{3}{5} = \frac{1 \times 0.4}{0.4 + \sigma_v \times 0.6}$$

Solving: $\sigma_v = \frac{4}{9}$

**Equilibrium**:
- Robust: Always attacks
- Vulnerable: Attacks with probability $\frac{4}{9}$
- Target: Resists with probability $\frac{1}{3}$ (given attack)
- Belief: $P(\text{Robust}|\text{Attack}) = \frac{3}{5}$

---

## Single Raise Poker

**Setup**:
- P1 dealt: Ace (50%) or Queen (50%)
- P2 has: King
- P1 chooses: Bet or Fold
- If P1 bets, P2 chooses: Call or Fold

**Payoffs** (P1 perspective):
- Fold: -1
- Bet → P2 folds: +1
- Bet → P2 calls: Ace wins +2, Queen loses -2

**Key insight**: Ace always bets (dominant strategy)

---

## Testing Pure Strategies in Poker

**Pooling (both bet)**: Fails
- P2's expected payoff for calling: $0.5(2) + 0.5(-2) = 0 > -1$
- P2 always calls
- Queen gets -2 from betting vs. -1 from folding → Deviates

**Separating (Queen folds)**: Fails
- P2 knows bet = Ace → P2 always folds
- Queen could bluff and win +1 vs. -1 from folding → Deviates

**Conclusion**: Must be semi-separating equilibrium

---

## Solving Poker Semi-Separating

**Making Queen indifferent** (to mix):
- Payoff from folding: -1
- Expected from betting: $-2\sigma_c + 1(1-\sigma_c) = 1 - 3\sigma_c$
- Set equal: $1 - 3\sigma_c = -1$ → $\sigma_c = \frac{2}{3}$

**Making P2 indifferent** (to mix):
- Let $p$ = belief facing Queen after seeing bet
- Expected from calling: $2p - 2(1-p) = 4p - 2$
- Payoff from folding: -1
- Set equal: $4p - 2 = -1$ → $p = \frac{1}{4}$

**Finding bluff frequency** (using Bayes' Rule): $\sigma_b = \frac{1}{3}$

---

## Poker Equilibrium

**Complete equilibrium strategy**:
- Ace: Always bets (100%)
- Queen: Bets $\frac{1}{3}$ of time (bluffs), folds $\frac{2}{3}$ of time
- P2 (after seeing bet): Calls $\frac{2}{3}$ of time, folds $\frac{1}{3}$ of time
- Belief: $P(\text{Queen}|\text{Bet}) = \frac{1}{4}$

**Strategic lessons**:
- Strong hand: Always aggressive
- Weak hand: Bluff sometimes to remain unpredictable
- Opponent: Mix responses to prevent exploitation

**Key insight**: "Rich bluffing strategies" emerge naturally from rational play

---

## Chain Store Paradox

**Original setup** (complete information):
- Chain store is weak (price war unprofitable)
- Faces potential competitor in Town 2
- Logic: Backward induction → Always acquiesce
- "Paradox": Real firms use aggressive price wars to deter entry

**Why not really a paradox**: Simplified model doesn't capture real-world uncertainty

**Resolution**: Introduce incomplete information
- Rival uncertain if chain store is weak or strong
- Strong store: Price war profitable
- Creates possibility for strategic bluffing

---

## Chain Store with Incomplete Information

**Setup**:
- Prior belief: 90% weak, 10% strong
- Strong store: Always fights (dominant strategy)
- Question: What does weak store do?

**Testing pure strategies**:
- Separating (weak acquiesces): Fails—bluffing is profitable
- Pooling (weak fights): Fails—being challenged makes acquiescing better

**Solution**: Semi-separating equilibrium
- Weak store bluffs with probability $\frac{1}{9}$
- Rival challenges with probability $\frac{1}{2}$
- Creates strategic uncertainty

---

## Lessons from Chain Store

**Key insights**:
1. Weak store cannot always acquiesce → Bluffing becomes too attractive
2. Weak store cannot always bluff → Skeptical rival would always challenge
3. Only stable solution: Occasional bluffing, occasional challenging

**Resolving the "paradox"**:
- Incomplete information makes "irrational" price war rational
- Bluffing prevents perfect predictability
- Maintains strategic uncertainty
- Prevents exploitation

**Bottom line**: What seemed paradoxical under certainty becomes logical under uncertainty

---

## Summary: Key Takeaways

**Perfect Bayesian Equilibrium**:
- Combines sequential rationality with beliefs about types
- Requires specifying both strategies AND beliefs
- Updates via Bayes' rule wherever possible

**Three equilibrium types**:
1. Separating: Actions reveal types completely
2. Pooling: Actions hide types completely  
3. Semi-separating: Actions partially reveal through mixing

**Applications**:
- Screening: Uninformed moves first (escalation as test)
- Signaling: Informed moves first (education, military displays)
- Markets: Adverse selection and information asymmetry

---

## Final Thoughts

**Strategic bluffing is rational**:
- Not random or irrational behavior
- Carefully calculated to maintain uncertainty
- Frequency determined by indifference conditions

**Information is powerful**:
- Can reveal types (separating)
- Can hide types (pooling)
- Can partially reveal (semi-separating)

**Real-world relevance**:
- Poker and sports (mixing strategies)
- Business competition (chain store)
- Labor markets (education signaling)
- Insurance and used cars (adverse selection)

**Next**: Applications and extensions of PBE
