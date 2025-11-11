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

**Date:** November 10, 2025

---

## The Road Ahead

1. [Introduction to PBE](#introduction-finding-our-place)
2. [Screening Games](#screening-games)
3. [Adverse Selection](#adverse-selection)
4. [Signaling Games](#signaling-games)
5. [Three Types of Equilibria](#three-types-of-equilibria)
6. [Off-the-Path Beliefs](#off-the-path-beliefs)
7. [Applications](#applications)

---

## Introduction: Finding Our Place

**Our journey so far**:

<table>
<tr><th>Game Timing</th><th>Information</th><th>Solution Concept</th></tr>
<tr><td>Simultaneous</td><td>Complete</td><td>Nash Equilibrium</td></tr>
<tr><td>Sequential</td><td>Complete</td><td>Subgame Perfect Equilibrium</td></tr>
<tr><td>Simultaneous</td><td>Incomplete</td><td>Bayesian Nash Equilibrium</td></tr>
<tr><td><b>Sequential</b></td><td><b>Incomplete</b></td><td><b>Perfect Bayesian Equilibrium</b></td></tr>
</table>

**PBE** combines the core ideas of SPE (handling sequential moves) and BNE (handling private information)

---

## The Definition: What is PBE?

A **Perfect Bayesian Equilibrium** is a set of strategies and beliefs such that:
1. Strategies are **sequentially rational** given players' beliefs
2. Players update beliefs via **Bayes' rule** wherever possible

**Critical insight**: A PBE specifies BOTH strategies AND beliefs. Forgetting one part means the entire solution is incorrect

---

## The Three Pillars of PBE

**Pillar 1: Strategies AND Beliefs** (A New Partnership)
- The solution must specify what players do (strategies) AND what they think (beliefs)
- This is an inseparable pair—leave out one, your answer is wrong

**Pillar 2: Sequential Rationality** (Making Threats Believable)
- Players must actually want to follow through on their stated plans at every decision point
- A threat's credibility depends on what you believe about your opponent's type

**Pillar 3: Updating Beliefs with Bayes' Rule** (Learning as You Go)
- Players start with prior beliefs and update them as they observe actions
- Bayes' Rule provides the logical method for updating beliefs on the equilibrium path

---

## The Big Caveat: "Wherever Possible"

**Challenge**: What happens when a player observes an action that should never happen according to the equilibrium strategies?

- These situations are known as being **"off the equilibrium path"**
- Bayes' Rule cannot be applied (probability = 0 → divide by zero error)
- Defining beliefs in these unexpected scenarios is a key challenge in solving PBE

**Key insight**: Off-the-path beliefs matter because the threat of what might happen off the path justifies players' actions on the path

---

## PBE Summary Table

<table>
<tr><th>Component</th><th>Its Job in the Game</th></tr>
<tr><td>Strategies</td><td>Action plans for each player at every possible point in the game</td></tr>
<tr><td>Beliefs</td><td>Probabilistic assessment of opponent's type, updated throughout</td></tr>
<tr><td>Sequential Rationality</td><td>Ensures strategies are logical and threats are credible</td></tr>
<tr><td>Bayes' Rule</td><td>Logical method for updating beliefs on the equilibrium path</td></tr>
</table>

---

## Screening Games

**Definition**: A game of incomplete information where the **uninformed player moves first**

**Key characteristics**:
- Uninformed player cannot signal information (they don't have any)
- Uninformed player's action can "screen" or "test" the informed player
- Informed player responds differently based on their type

**Result**: The uninformed player's action separates (filters) different types by eliciting different responses

---

## Screening Game Example: Escalation

**Setup**:
- Nature chooses Player 2's type: Weak (probability $p$) or Strong (probability $1-p$)
- Player 1 (uninformed) chooses: Escalate or Quit
- Player 2 (informed, knows own type) chooses: Fight or Concede

**Payoffs** (if Player 1 quits): $(0, 1)$ regardless of type

**Payoffs** (if Player 1 escalates):
- Player 2 is Weak: Concede $(1, 0)$ or Fight $(0.7, -0.1)$
- Player 2 is Strong: Concede $(1, 0)$ or Fight $(-0.2, 0.8)$

---

## Solving Screening Games: Step-by-Step

**Step 1: Solve for the informed player (Player 2)**
- Weak type: Concede (0 > -0.1)
- Strong type: Fight (0.8 > 0)

**Step 2: Solve for the uninformed player (Player 1)**
- Expected payoff from Quit: 0
- Expected payoff from Escalate: $p \times 1 + (1-p) \times (-0.2) = 1.2p - 0.2$

**Step 3: Compare payoffs**
- Player 1 escalates if: $1.2p - 0.2 > 0$ → $p > \frac{1}{6}$
- Player 1 quits if: $p < \frac{1}{6}$

---

## The Complete PBE Solution

**If $p > \frac{1}{6}$** (Player 1 is optimistic):
- Player 1: Escalate
- Player 2: Concede if Weak, Fight if Strong
- Belief: Player 2 is Weak with probability $p$

**If $p < \frac{1}{6}$** (Player 1 is pessimistic):
- Player 1: Quit
- Player 2: Concede if Weak, Fight if Strong (off-path)
- Belief: Player 2 is Weak with probability $p$

**Remark**: Player 2's strategy is a complete plan of action, even for actions that don't occur in equilibrium

---

## Adverse Selection

**Core question**: "If a person accepts your transaction at some price, does the very fact that they accepted it mean you no longer want to go through with it?"

**Definition**: A market problem arising when one person has important private information that the other lacks

**Key consequence**: Information imbalance can lead to market failure where mutually beneficial trades don't happen

---

## Adverse Selection: Insurance Example

<table>
<tr><th>Metric</th><th>Healthy Customer</th><th>Unhealthy Customer</th></tr>
<tr><td>Probability</td><td>60%</td><td>40%</td></tr>
<tr><td>Cost to Insure</td><td>$400</td><td>$800</td></tr>
<tr><td>Willingness to Pay</td><td>Up to $750</td><td>Up to $1,250</td></tr>
</table>

**Insurer's dilemma**:
- Low price ($500): Expected profit = $60 - $120 = -$60
- High price ($1,000): Expected profit = $0 + $80 = $80

**Equilibrium outcome**: Only high price offered → Only unhealthy buy → Market failure for healthy customers

---

## Real-World Adverse Selection

**The "Market for Lemons"** (Used Cars):
- Seller knows car's true quality; buyer doesn't
- Buyer offers "average quality" price
- Only sellers with below-average cars (lemons) accept
- George Akerlof won Nobel Prize for this insight

**Housing Market**:
- Seller knows about hidden defects; buyer doesn't
- Low offers more likely accepted by sellers with costly hidden problems

---

## Solutions to Adverse Selection

**Reputation**: Long-term incentives create trust
- Car dealership vs. random Craigslist seller
- Repeat business depends on honest dealing

**Third-Party Verification**: Independent experts level the playing field
- Home inspectors, mechanics

**Government Regulation**: Lemon laws re-allocate risk
- Buyer can return defective purchases

**Government Intervention**: Universal healthcare
- Pools everyone together, avoiding selection problems

---

## Signaling Games

**Definition**: A game where the **informed player moves first**

**Key difference from screening**: The informed player's action can "signal" information about their private type

**Critical insight**: The first mover must think carefully about what their action communicates to the uninformed player

**Result**: Leads to fascinating outcomes—pooling, separating, and semi-separating equilibria

---

## Three Types of Equilibria

<table>
<tr><th>Equilibrium Type</th><th>What Players Do</th><th>What Is Learned</th></tr>
<tr><td>Separating</td><td>Different types choose different actions</td><td>Everything—action perfectly reveals type</td></tr>
<tr><td>Pooling</td><td>All types choose the same action</td><td>Nothing—action provides no new information</td></tr>
<tr><td>Semi-Separating</td><td>One type picks one action, other type mixes</td><td>Something—partial information revealed</td></tr>
</table>

---

## Separating Equilibrium: Actions Speak Louder

**Example**: Job market with High/Low type applicant
- High type → College
- Low type → High School

**Key insight**: Perfect information revelation
- Employer sees "College" → 100% certain applicant is High type
- Employer sees "High School" → 100% certain applicant is Low type

**Signal is crystal clear**: Informed player's action completely reveals their private information

---

## Pooling Equilibrium: Hiding in the Crowd

**Example**: Job market where both types get high school diploma
- High type → High School
- Low type → High School

**Key insight**: No new information
- Employer sees "High School" → learns nothing
- Belief remains at prior: 50/50

**Signal is uninformative**: Action provides no way to distinguish types

**Challenge**: Must define off-the-path beliefs (what if someone goes to college?)

---

## Semi-Separating: Strategic Bluffing

**Example**: Job market with mixed strategies
- High type → always College (pure strategy)
- Low type → sometimes College (30%), sometimes High School (70%) (mixed strategy)

**Key insight**: Partial information
- "High School" signal → 100% certain it's Low type (perfectly revealing)
- "College" signal → ambiguous, could be High type or bluffing Low type
- Employer must use Bayes' rule to update beliefs

**Most strategically rich**: Involves true bluffing behavior

---

## War Game: Testing Separating Equilibrium

**Setup**: State 1 knows if it's Strong (60%) or Weak (40%)
- State 1 chooses: Reveal (small cost) or Hide
- State 2 wants to Fight Weak but Quit against Strong

**Test 1**: Strong Reveals, Weak Hides
- State 2's belief: Hide → 100% Weak → Fight
- Strong's deviation check: Reveal (0.99) vs. Hide (0.5) ✓
- Weak's deviation check: Hide (-1) vs. Reveal (-1.01) ✓
- **Result**: This IS a stable equilibrium

---

## War Game: Failed Separating Equilibrium

**Test 2**: Strong Hides, Weak Reveals
- State 2's belief: Hide → 100% Strong → Quit
- Weak's deviation check: Reveal (-1.01) vs. Hide & Bluff (1) ✗
- **Fatal flaw**: Weak type has massive incentive to bluff

**Key lesson**: Signals must be credible. No type should have a profitable deviation to lie or mimic another type

---

## Pooling Equilibrium: War Game

**Strategy**: Both Strong and Weak Hide

**Analysis**:
- State 2's belief: Hide → No new info → remains 60% Strong, 40% Weak
- State 2's best response: Expected payoff = $0.6 \times (-1) + 0.4 \times 0.5 = -0.4$
- Since -0.4 < 0, State 2 Quits

**Deviation checks**:
- Strong: Hide (1) vs. Reveal (0.99) ✓
- Weak: Hide (1) vs. Reveal (-1.01) ✓

**Result**: This IS a stable pooling equilibrium

---

## Off-the-Path Beliefs

**The problem**: When a player makes a zero-probability move that "should never happen" according to equilibrium strategies
- Bayes' Rule breaks down (divide by zero)
- Must define beliefs for these unexpected scenarios

**Why it matters**: The threat of what might happen off the path justifies players' actions on the path

**Solution approach**: Test all possible beliefs ($p$ from 0 to 1) to see if any can sustain the equilibrium

---

## Testing with Off-Path Beliefs

**Example**: Both types Reveal (alleged equilibrium)
- On-path: Player 2 knows types after Reveal
- Off-path: What if Player 1 Hides?
- Let $p$ = Player 2's belief that Hider is Strong

**Player 2's optimal action**:
- Expected utility of Fight: $0.5 - 1.5p$
- Fight if $p < \frac{1}{3}$, Quit if $p > \frac{1}{3}$

**Deviation checks show**: Weak type always wants to deviate regardless of $p$
- **Result**: This alleged equilibrium FAILS

---

## The Beer-Quiche Game: Setup

**Players and Types**:
- Player 1: Real Man (60%) prefers Beer, or Wimp (40%) prefers Quiche
- Both types want to avoid a fight
- Player 2: Coward who wants to fight only a Wimp

**Sequence**:
1. Player 1 chooses: Beer or Quiche
2. Player 2 observes meal, chooses: Fight or Quit

**Best possible outcomes**:
- Real Man: Beer + Player 2 Quits (3 points)
- Wimp: Quiche + Player 2 Quits (3 points)
- Player 2: Fight a Wimp (1 point)

---

## Beer-Quiche: Pooling on Beer

**Strategy**: Both Real Man and Wimp drink Beer

**Player 2's on-path response**:
- Sees Beer → Belief remains 60% Real Man, 40% Wimp
- Expected payoff from Fight: $(0.6)(-1) + (0.4)(1) = -0.2$
- Since -0.2 < 0, Player 2 Quits

**Deviation check**: Would Wimp deviate to Quiche?
- Current payoff: 2 (Beer + no fight)
- Deviation payoff: 3 if Player 2 Quits, or 1 if Player 2 Fights
- To prevent deviation, Player 2 must Fight after seeing Quiche

---

## Beer-Quiche: Off-Path Beliefs

**Two solution classes**:

**Class 1**: Fighting is strictly better ($P < \frac{1}{2}$)
- Player 2 believes quiche-eater is Real Man with probability $P < \frac{1}{2}$
- Player 2 strictly prefers to Fight

**Class 2**: Indifference case ($P = \frac{1}{2}$)
- Player 2 is exactly indifferent between Fight and Quit
- Player 2 must Fight with probability $\sigma \geq \frac{1}{2}$ to deter Wimp's deviation
- Wimp must be kept indifferent: $2 \geq \sigma(1) + (1-\sigma)(3)$ → $\sigma \geq \frac{1}{2}$

---

## Semi-Separating: Terrorist Game Setup

**Players**: Terrorist group (Player 1) vs. Target (Player 2)
- Nature chooses group type: Robust (40%) or Vulnerable (60%)
- Robust type: Attack is dominant strategy (always profitable)
- Vulnerable type: What to do?

**Payoffs**:
- No attack: $(0, 0)$
- Attack + Ignore: $(1, -1)$
- Vulnerable attacks + Resist: $(-2, 2)$
- Robust attacks + Resist: $(3, -3)$

**Question**: Can the Vulnerable type sometimes bluff?

---

## Semi-Separating: The Indifference Method

**Key principle**: For a player to mix strategies, they must be indifferent between their choices

**Step 1**: Make Vulnerable group indifferent
- Let $R$ = Probability Target resists
- Vulnerable's expected payoff from Attack: $(-2)R + (1)(1-R) = 0$
- Solving: $1 - 3R = 0$ → $R = \frac{1}{3}$

**Step 2**: Make Target indifferent
- Let $P$ = Target's belief attacker is Robust
- Target's expected payoff from Resist: $(-3)P + (2)(1-P) = -1$
- Solving: $2 - 5P = -1$ → $P = \frac{3}{5}$

---

## Semi-Separating: Finding Bluff Frequency

**Step 3**: Use Bayes' rule to find bluffing frequency
- Need $P(Robust|Attack) = \frac{3}{5}$
- Let $\sigma_b$ = Probability Vulnerable attacks

Using Bayes' rule: $\frac{3}{5} = \frac{0.4 \times 1}{0.4 \times 1 + 0.6 \times \sigma_b}$

Solving: $\sigma_b = \frac{4}{9}$

**Complete equilibrium**:
- Robust: Always attacks
- Vulnerable: Attacks with probability $\frac{4}{9}$
- Target: Resists with probability $\frac{1}{3}$ after observing attack

---

## Single Raise Poker

**Setup**: Player 1 dealt Ace (50%) or Queen (50%); Player 2 has King
- Player 1: Bet or Fold
- Player 2 (if P1 bets): Call or Fold

**Key insight**: Ace has dominant strategy (always Bet)
- Folding: -1
- Betting: +1 (if P2 folds) or +2 (if P2 calls)

**Question**: What should Queen do? Always bet? Never bet? Sometimes bet?

---

## Single Raise Poker: Testing Pooling

**Strategy**: Both Ace and Queen always Bet

**Player 2's response**:
- Sees Bet → No new info → 50% Ace, 50% Queen
- Expected payoff from Call: $(0.5)(−2) + (0.5)(2) = 0$
- Since 0 > -1, Player 2 Calls

**Queen's dilemma**:
- Betting (with P2 calling): -2
- Folding: -1
- **Result**: Pooling fails—Queen wants to deviate to Fold

---

## Single Raise Poker: Testing Separating

**Strategy**: Ace Bets, Queen always Folds

**Player 2's belief**: Bet → 100% Ace

**Player 2's response**: Fold (payoff -1 vs. -2 from calling)

**Queen's temptation**:
- Sticking with Fold: -1
- Deviating to Bet (P2 will fold): +1
- **Result**: Separating fails—Queen wants to bluff

**Conclusion**: Must have semi-separating equilibrium

---

## Single Raise Poker: Semi-Separating Solution

**Making Queen indifferent**:
- Let $\sigma_c$ = Probability P2 calls
- Queen's expected payoff from Bet: $\sigma_c(-2) + (1-\sigma_c)(1) = -1$
- Solving: $1 - 3\sigma_c = -1$ → $\sigma_c = \frac{2}{3}$

**Making Player 2 indifferent**:
- Let $p$ = Belief attacker is Queen given Bet
- P2's expected payoff from Call: $p(2) + (1-p)(-2) = -1$
- Solving: $4p - 2 = -1$ → $p = \frac{1}{4}$

**Finding bluff frequency**: Using Bayes' rule with $p = \frac{1}{4}$ → Queen bets with probability $\frac{1}{3}$

---

## Chain Store Paradox: Setup

**Complete information version**:
- Chain Store faces competitor in Town 1, then Rival in Town 2
- Weak store payoffs: 0 (Price War), 1 (Acquiesce), 3 (Rival quits)
- Backward induction → Always acquiesce

**The "paradox"**: Logic says always be passive, but real firms fight price wars to build reputation

**Resolution**: The paradox arises from assuming complete information. Real world has uncertainty!

---

## Chain Store: Incomplete Information

**Two types of chain stores**:
- Weak (90%): Price war payoff = 0
- Strong (10%): Price war payoff = 2.5

**Game structure**:
- Strong type: Always fights (dominant strategy)
- Weak type: What to do?

**Rival's belief**: Initially 90% chance store is Weak

**Key insight**: Uncertainty transforms price war into a credible signal, allowing strategic bluffing

---

## Chain Store: Semi-Separating Equilibrium

**Testing pure strategies**:
- Separating (Weak acquiesces): Fails—Weak wants to bluff (payoff 3 > 2)
- Pooling (Weak always fights): Fails—Rival still enters, Weak gets payoff 1 < 2

**Solution**: Weak store bluffs sometimes
- Weak fights with probability $\frac{1}{9}$ to keep Rival indifferent
- Rival challenges with probability $\frac{1}{2}$ to keep Weak indifferent

**Bottom line**: Bluffing is rational! It prevents the weak store from being perfectly predictable and exploitable

---

## Key Takeaways

**Perfect Bayesian Equilibrium**: Essential tool for sequential games with incomplete information
- Must specify BOTH strategies AND beliefs
- Sequential rationality ensures credible threats given beliefs
- Bayes' rule updates beliefs wherever possible

**Screening vs. Signaling**: Who moves first matters
- Screening: Uninformed moves first → action tests/filters types
- Signaling: Informed moves first → action reveals information

**Three equilibrium types**: Separating, Pooling, Semi-Separating
- Semi-separating involves strategic bluffing and mixed strategies
- Indifference conditions are key to solving mixed strategy equilibria

---

## Applications Summary

**Adverse Selection**: Information asymmetry causes market failures
- Insurance, used cars, housing
- Solutions: reputation, verification, regulation

**Beer-Quiche Game**: Off-path beliefs enforce pooling equilibria
- Multiple equilibrium classes depending on beliefs

**Poker & Chain Store**: Semi-separating equilibria in action
- Bluffing emerges naturally from rational play
- Prevents predictability and exploitation

**Common thread**: Uncertainty about types creates strategic complexity and rich behavior
