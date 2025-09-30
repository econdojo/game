---
marp: true
math: mathjax
theme: default
size: 4:3
paginate: true
backgroundColor: '#f4f6fa'
backgroundImage: url('https://marp.app/assets/hero-background.svg')
header: 'Lecture 3: Advanced Strategic Form Games'
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

# Lecture 3: Advanced Strategic Form Games

**Instructor:** Fei Tan

<img src="images/github.png" width="30" height="30" class="logo"> @econdojo &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/youtube.png" width="30" height="30" class="logo"> @BusinessSchool101 &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/slu.png" width="30" height="30" class="logo"> Saint Louis University

**Date:** September 18, 2025

---

## The Road Ahead

1. [Probability Distributions](#probability-distributions)
2. [Mixed Strategy Nash Equilibrium](#generalized-battle-of-sexes)
3. [Comparative Statics](#comparative-statics)
4. [Rock-Paper-Scissors Game](#rock-paper-scissors-game)
5. [Indifference Principle](#indifference-principle)
6. [Generalized Rock-Paper-Scissors](#generalized-rock-paper-scissors)
7. [Mixed Strategies as Population Parameters](#mixed-strategies-as-population-parameters)

---

## Probability Distributions

A **probability distribution** is a set of events and the probability each event occurs

**Examples**:
- Coin flip: P(Heads) = 1/2, P(Tails) = 1/2
- Die roll: P(1) = P(2) = P(3) = P(4) = P(5) = P(6) = 1/6  
- Roulette: P(Red) = 18/38, P(Black) = 18/38, P(Green) = 2/38

**Connection to game theory**: Mixed strategies are probability distributions over pure strategies. Why This Matters?

- We'll work with complex probabilities like $\frac{x}{x + y + z}$
- Need to verify whether expressions form valid probability distributions
- Foundation for solving multi-strategy games

---

## Golden Rules of Probability Distributions

**Rule 1**: All events occur with probability ≥ 0
**Rule 2**: The sum of all probabilities equals 1

**Four key implications**:

1. **No probability > 1**: If some probability exceeded 1, others would need to be negative to sum to 1
2. **Complete specification**: Cannot leave gaps (e.g., "world ends tomorrow with probability 1/100")
3. **Solving for unknowns**: If probabilities sum to 1, unknown probability = 1 - sum of known probabilities
4. **Pure strategies are special cases**: P(chosen strategy) = 1, P(all others) = 0

---

### Example: Generalized Battle of Sexes

Payoff matrix with variables constraints: A > B > C and a > b > c

| | Left | Right |
|---|---|---|
| **Up** | B, a | C, c |
| **Down** | C, c | A, b |

**Mixed strategy equilibrium:**
- Player 1 plays Up with probability $\frac{b-c}{a+b-2c}$
- Player 1 plays Down with probability $\frac{a-c}{a+b-2c}$
- Player 2 plays Left with probability $\frac{A-C}{A+B-2C}$
- Player 2 plays Right with probability $\frac{B-C}{A+B-2C}$

**Key insight:** Each player's mixing probability depends on the opponent's payoffs!

---

## Example: Generalized Prisoner's Dilemma

Payoff matrix with variable constraints: T > R > P > S and t > r > p > s

| | Left (Cooperate) | Right (Defect) |
|---|---|---|
| **Up (Cooperate)** | R, r | S, t |
| **Down (Defect)** | T, s | P, p |

**Variable meanings:**
- **T/t** = Temptation (defect when opponent cooperates)
- **R/r** = Reward (mutual cooperation)  
- **P/p** = Punishment (mutual defection)
- **S/s** = Sucker (cooperate when opponent defects)

**Result:** Unique pure strategy Nash equilibrium at (Down, Right) = (Defect, Defect)

---

### Why No Mixed Strategy Equilibrium?

**Strict dominance analysis:**
- Down strictly dominates Up for Player 1 (T > R and P > S)
- Right strictly dominates Left for Player 2 (t > r and p > s)

**Mixed strategy algorithm:**
Setting Player 2 indifferent → $\sigma_{up}(r + p - s - t) = p - s$

1. **Case 1:** $r + p - s - t = 0$ → $0 = p - s$ → Contradiction since $p > s$
2. **Case 2:** $r + p - s - t < 0$ → $\sigma_{up} < 0$ → Invalid probability  
3. **Case 3:** $r + p - s - t > 0$ → $\sigma_{up} > 1$ → Invalid probability

**Key insight:** Strict dominance eliminates all mixed strategy possibilities

---

## Section 3.5 TBA

---

## Comparative Statics

Study of how changes in game parameters affect equilibrium outcomes

**Four-step process:**
1. Solve for the game's equilibria
2. Calculate the element of interest (probabilities, payoffs, outcomes)
3. Take the derivative with respect to the parameter
4. Analyze how parameter changes affect the element

**Key insight**: Game theory often produces counterintuitive results!

---

## Example: Soccer Penalty Kicks

Kicker has perfect accuracy right, accuracy $x$ (where $0 < x < 1$) aiming left

| | Goalie: Left | Goalie: Right |
|---|---|---|
| **Kicker: Left** | 0, 0 | x, -x |
| **Kicker: Right** | 1, -1 | 0, 0 |

**Mixed Strategy Nash Equilibrium:**
- Goalie dives left with probability $\frac{x}{1+x}$
- Kicker aims left with probability $\frac{1}{1+x}$

**Comparative static:** $\frac{d}{dx}\left(\frac{1}{1+x}\right) = -\frac{1}{(1+x)^2} < 0$ → As kicker's left accuracy improves, he kicks left **less frequently**!

**Strategic interaction:** Goalie anticipates kicker's improved left accuracy and guards left more → kicker exploits the now less-defended right side → improved accuracy paradoxically shifts play toward the strong side

---

## Example: Volunteer's Dilemma

Two neighbors hear woman being attacked, must decide whether to call police. Woman's life worth 1, death worth 0; calling costs $c$ where $0 < c < 1$

| | Call | Ignore |
|---|---|---|
| **Call** | 1-c, 1-c | 1-c, 1 |
| **Ignore** | 1, 1-c | 0, 0 |

**Mixed Strategy Nash Equilibrium:** Each player calls with probability $1-c$

**Comparative static:** Probability no one calls = $c^2$ → $\frac{d}{dc}(c^2) = 2c > 0$

**Bystander effect:** More potential helpers → less help! Each assumes someone else will act, creating coordination failure (e.g. public goods provision) → need clear assignment of responsibility

---

## Example: Hawk-Dove Game

Two states decide whether to be aggressive (Hawk) or peaceful (Dove); $v$ is the prize value and $c$ is the cost of fighting.

| | Hawk | Dove |
|---|---|---|
| **Hawk** | $\frac{v}{2}-c, \frac{v}{2}-c$ | $v, 0$ |
| **Dove** | $0, v$ | $\frac{v}{2}, \frac{v}{2}$ |

**Equilibrium depends on parameters:**
- If $\frac{v}{2} > c$: Both play Hawk (war certain)
- If $\frac{v}{2} < c$: Pure strategy (Hawk, Dove) and (Dove, Hawk); Mixed strategy with $P(\text{Hawk}) = \frac{v}{2c}$

**Comparative static**: Probability of war = $\frac{v^2}{4c^2}$ → $\frac{d}{dc}\left(\frac{v^2}{4c^2}\right) = -\frac{v^2}{2c^3} < 0$

**Paradox of peace**: Higher war costs → lower probability of war!

---

## Rock-Paper-Scissors Game

<table class="payoff-matrix">
<tr>
<th></th>
<th>Rock</th>
<th>Paper</th>
<th>Scissors</th>
</tr>
<tr>
<th>Rock</th>
<td>0, 0</td>
<td>-1, 1</td>
<td>1, -1</td>
</tr>
<tr>
<th>Paper</th>
<td>1, -1</td>
<td>0, 0</td>
<td>-1, 1</td>
</tr>
<tr>
<th>Scissors</th>
<td>-1, 1</td>
<td>1, -1</td>
<td>0, 0</td>
</tr>
</table>

**Observations**:
- Cyclical dominance: No pure strategy Nash equilibria
- Any two-strategy support is exploitable: Omitted third strategy beats both members of the support
- Exploitation gives the opponent a guaranteed positive payoff and forces the mixer to a negative expected payoff—impossible in symmetric zero-sum equilibrium
- Conclusion: Both players must mix over all three strategies with probability $\tfrac{1}{3}$ for each strategy

---

## Generalized Rock-Paper-Scissors Game

<table class="payoff-matrix">
<tr>
<th></th>
<th>Rock</th>
<th>Paper</th>
<th>Scissors</th>
</tr>
<tr>
<th>Rock</th>
<td>0, 0</td>
<td>-x, x</td>
<td>y, -y</td>
</tr>
<tr>
<th>Paper</th>
<td>x, -x</td>
<td>0, 0</td>
<td>-z, z</td>
</tr>
<tr>
<th>Scissors</th>
<td>-y, y</td>
<td>z, -z</td>
<td>0, 0</td>
</tr>
</table>

**Player 1's expected utilities** (Player 2 uses $\sigma_{\text{rock}}+\sigma_{\text{paper}}+\sigma_{\text{scissors}}=1$):

- $EU_{\text{Rock}} = -x\sigma_{\text{paper}} + y\sigma_{\text{scissors}}$
- $EU_{\text{Paper}} = x\sigma_{\text{rock}} - z\sigma_{\text{scissors}}$
- $EU_{\text{Scissors}} = -y\sigma_{\text{rock}} + z\sigma_{\text{paper}}$

**Mixed Strategy Equilibrium**:
- Play Rock with probability $\frac{z}{x + y + z}$  (from $EU_{\text{Paper}} = EU_{\text{Scissors}}$)
- Play Paper with probability $\frac{y}{x + y + z}$  (from $EU_{\text{Rock}} = EU_{\text{Scissors}}$)
- Play Scissors with probability $\frac{x}{x + y + z}$  (from $EU_{\text{Rock}} = EU_{\text{Paper}}$)

---

## Counterintuitive Results

The probability of playing each strategy depends on the **other strategies' effectiveness**, e.g.

- Probability of Scissors = $\frac{x}{x + y + z}$ where $x$ is Paper's advantage over Rock
- As Paper gets better at beating Rock ($x$ increases), players use Scissors **more often** because opponents anticipate the increased Paper usage
- Numeric check (x=2, y=1, z=1): equilibrium weights = $\{\tfrac{1}{4},\tfrac{1}{4},\tfrac{1}{2}\}$ — Paper's doubled effectiveness corresponds to doubling Scissors' weight.

**Real-world application**: Character selection in fighting video games

---

## Mixed Strategies as Population Parameters

**Alternative interpretation**: Mixed strategies represent **population distributions** rather than individual randomization

**Video game example**:
- Players don't randomize between characters in each match
- Instead, they specialize in one character (pure strategy)
- The population contains different types of players

**Population game**:
- Individual players choose pure strategies (e.g., always Rock)
- Random matchmaking pairs players from large population
- Mixed strategy equilibrium tells us population distribution needed for individual indifference

---

## Population Equilibrium Analysis

**Setup**: Large population where:
- Fraction $\frac{z}{x + y + z}$ specialize in Rock
- Fraction $\frac{y}{x + y + z}$ specialize in Paper  
- Fraction $\frac{x}{x + y + z}$ specialize in Scissors

**Individual optimality**: A Rock specialist's expected payoff when randomly matched:

$EU_{\text{Rock}} = 0 \cdot \frac{z}{x + y + z} + (-x) \cdot \frac{y}{x + y + z} + y \cdot \frac{x}{x + y + z} = 0$

**Key insight**: All specialists earn the same expected payoff (zero), so no individual wants to switch specializations

**Result**: Everyone plays pure strategies, yet the population achieves mixed strategy equilibrium proportions

---

## Applications and Implications

**Real-world examples**:
1. **Online gaming**: Character selection in multiplayer games
2. **Business strategy**: Product positioning in competitive markets
3. **Evolution**: Species adaptation and survival strategies
4. **Financial markets**: Trading strategy distributions

**Why this matters**:
- Explains diversity in competitive environments
- No central coordination needed - emerges from individual optimization
- Stable population distributions even with pure strategy players
- Provides foundation for evolutionary game theory

**Key takeaway**: Mixed strategy equilibria can represent **aggregate behavior** of purely strategic individuals

---

## Computational Example

**Given**: $x = 3$, $y = 2$, $z = 1$ in generalized Rock-Paper-Scissors

**Step 1**: Calculate total $x + y + z = 6$

**Step 2**: Find equilibrium probabilities
- $\sigma_{\text{rock}} = \frac{z}{x + y + z} = \frac{1}{6}$
- $\sigma_{\text{paper}} = \frac{y}{x + y + z} = \frac{2}{6} = \frac{1}{3}$
- $\sigma_{\text{scissors}} = \frac{x}{x + y + z} = \frac{3}{6} = \frac{1}{2}$

**Verification**: Each player's expected payoff equals zero
- $EU_{\text{Rock}} = -3 \cdot \frac{1}{3} + 2 \cdot \frac{1}{2} = -1 + 1 = 0$ ✓

**Interpretation**: When Scissors devastates Paper ($z=3$), half the population should specialize in Scissors

---

## Strategy-Proofness and Robustness

**Important properties** of mixed strategy equilibria in symmetric zero-sum games:

1. **Individual rationality**: No player can improve by unilateral deviation
2. **Population stability**: No subset of players can coordinate profitable changes  
3. **Robustness to information**: Equilibrium maintained even with limited knowledge of opponent strategies
4. **Scale invariance**: Results hold regardless of population size

**Contrast with other games**: 
- Coordination games: Multiple equilibria, focal points matter
- Prisoner's dilemma: Unique equilibrium, but Pareto inefficient
- Battle of the sexes: Coordination problems, communication valuable

**Unique feature**: Symmetric zero-sum games have **conflict-free** mixed equilibria

---

## Summary and Takeaways

**Key insights from Chapter 3**:

1. **Zero-sum symmetry principle**: Players earn zero expected payoff in equilibrium
2. **Indifference principle**: Mixed strategies make opponents indifferent among pure strategies  
3. **Counterintuitive effects**: Strategy probabilities depend on **other** strategies' payoffs
4. **Population interpretation**: Mixed strategies as distributions of specialized players
5. **Computational methods**: System of indifference equations plus probability constraints

**Next steps**: 
- Games with infinite strategy spaces (continuous choices)
- Incomplete information and Bayesian games
- Evolutionary stability and dynamics

**Practice**: Apply these methods to analyze competitive scenarios in your field of interest

---

## Takeaway Points

1. **In symmetric, zero-sum games, each player's payoff in equilibrium must equal 0.**

2. **Mixed strategies can be thought of as population parameters instead of single players randomizing over choices.**

3. **The indifference principle: In mixed strategy equilibria, players must be indifferent among all strategies in their support.**

4. **Counterintuitive result: The probability of playing a strategy often depends more on other strategies' payoffs than its own direct payoffs.**