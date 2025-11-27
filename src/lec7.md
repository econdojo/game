---
marp: true
math: mathjax
theme: default
size: 4:3
paginate: true
backgroundColor: '#f4f6fa'
backgroundImage: url('https://marp.app/assets/hero-background.svg')
header: 'Lecture 7: Bayesian Nash Equilibrium'
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

# Lecture 7: Bayesian Nash Equilibrium

**Instructor:** Fei Tan

<img src="images/github.png" width="30" height="30" class="logo"> @econdojo &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/youtube.png" width="30" height="30" class="logo"> @BusinessSchool101 &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/slu.png" width="30" height="30" class="logo"> Saint Louis University

**Date:** November 6, 2025

---

## The Road Ahead

1. [Incomplete Information](#why-information-matters)
2. [Bayesian Nash Equilibrium](#bayesian-nash-equilibrium-bne)
3. [Solving for BNE](#solving-for-bne)
4. [Dominance](#dominance-concepts)
5. [Purification](#continuous-types)
6. [Bayes' Rule](#bayes-rule)

---

## Why Information Matters

In strategic interactions, what you know—and what you don't know—is everything

**Three types of information structures**:
- Perfect and complete information: Know all past actions and all payoffs (e.g., sequential games with known payoffs)
- Imperfect information: Uncertainty about past actions, but all payoffs are known (e.g., simultaneous moves)
- Incomplete information: Know past actions, but uncertainty about payoffs, preferences, or "types"

**Why it matters**? Different information structures require completely different solution concepts

---

## Imperfect Information

A player does not know the previous actions of other players

**Example**: Prisoner's Dilemma
- Both prisoners choose simultaneously
- Player 2 doesn't observe Player 1's choice, vice versa (imperfect information)
- But both know all possible payoffs (complete information)

<table>
<tr><th></th><th>Cooperate</th><th>Defect</th></tr>
<tr><th>Cooperate</th><td>3, 3</td><td>1, 4</td></tr>
<tr><th>Defect</th><td>4, 1</td><td>2, 2</td></tr>
</table>

---

## Incomplete Information

Uncertainty about another player's payoffs, preferences, or "type"

**Examples**:

| Scenario | Hidden Characteristics |
|----------|---------------------|
| Soccer Penalty Kick | Striker's accuracy to left vs. right |
| Volunteer's Dilemma | Cost of calling for help (busy vs. leisurely) |
| Battle of the Sexes | Intensity of preference for ballet |

**Key point**: You don't know what things are worth to your opponent

---

## Elements of A Game

Complete information: Players, actions, payoffs

Incomplete information: Two additional elements

- **Player types**: Different variations of a player with private information about payoffs or capabilities
    - Each player knows their own type but opponents do not
    - Example: Striker knows if they're more accurate kicking left or right

- **Player beliefs**: Probabilities assigned to opponent types
    - Common prior assumption: All players know each other's beliefs at all levels
    - Example: Goalie believes 50% chance striker is left-accurate

---

## Bayesian Nash Equilibrium (BNE)

A set of strategies—one for each type of player—such that no type has incentive to deviate, given beliefs about types and what other types are doing:

- Focus on types: Check for deviations by each type, not just each player
- Contingency plan: One strategy for each possible type
- Beliefs drive rationality: Player's optimal choice pivots on beliefs

**BNE**: Solution concept for simultaneous-move games with incomplete information

---

## One-Sided Incomplete Information

Player 1 has two types with probabilities $p$ and $1-p$; Player 2 is uncertain which type they face

Type A Player 1:

<table>
<tr><th>Type A (prob = p)</th><th>Left</th><th>Right</th></tr>
<tr><th>Up</th><td>3, 4</td><td>1, 0</td></tr>
<tr><th>Down</th><td>4, 3</td><td>2, 0</td></tr>
</table>

Type B Player 1:

<table>
<tr><th>Type B (prob = 1-p)</th><th>Left</th><th>Right</th></tr>
<tr><th>Up</th><td>6, 2</td><td>0, 4</td></tr>
<tr><th>Down</th><td>5, 1</td><td>-1, 4</td></tr>
</table>

---

## Finding Player 1's Strategy

Type A analysis: Compare Up vs. Down
- If Player 2 plays Left: Down (4) > Up (3)
- If Player 2 plays Right: Down (2) > Up (1)
- Down strictly dominates Up for Type A

Type B analysis: Compare Up vs. Down
- If Player 2 plays Left: Up (6) > Down (5)
- If Player 2 plays Right: Up (0) > Down (-1)
- Up strictly dominates Down for Type B

Player 1's equilibrium strategy: Type A plays Down; Type B plays Up

---

## Finding Player 2's Strategy

Cannot use simple dominance because optimal action depends on Player 1's type

Expected utility:
- Left: $3p + 2(1-p) = p + 2$
- Right: $0p + 4(1-p) = 4 - 4p$

Player 2's best response:
- Play Left if $p + 2 > 4 - 4p$ → $p > \frac{2}{5}$
- Play Right if $p < \frac{2}{5}$
- Indifferent if $p = \frac{2}{5}$

**Note**: From Player 2's perspective, Player 1 appears to be "mixing" even though each type plays a pure strategy

---

## Solving for BNE

**Challenge**: When games have multiple matrices (one per opponent type), how do we find the BNE?

**Solution**: The uninformed player needs a complete contingency plan specifying what to do for each possible type they might be:

1. Create compound strategies for the uncertain player
2. Calculate expected payoffs weighted by type probabilities
3. Solve for Nash equilibria in the combined payoff matrix → Bayesian Nash equilibria of the original game

---

## Example: PD/SH Mixed Game

**Player 1**: Has one type (Stag Hunt preferences)
**Player 2**: Two possible types
- Prisoner's Dilemma type (probability 0.2)
- Stag Hunt type (probability 0.8)

<table>
<tr><th>P2: PD Type (0.2)</th><th>Left</th><th>Right</th></tr>
<tr><th>Up</th><td>3, 3</td><td>0, 4</td></tr>
<tr><th>Down</th><td>2, 1</td><td>1, 2</td></tr>
</table>

<table>
<tr><th>P2: SH Type (0.8)</th><th>Left</th><th>Right</th></tr>
<tr><th>Up</th><td>3, 3</td><td>0, 2</td></tr>
<tr><th>Down</th><td>2, 0</td><td>1, 1</td></tr>
</table>

---

## Combined Payoff Matrix

**Player 2's compound strategies**: (Action if PD, Action if SH)
- (Left, Left): PD type plays Left and SH type plays Left
- (Left, Right): PD type plays Left and SH type plays Right
- (Right, Left): PD type plays Right and SH type plays Left
- (Right, Right): PD type plays Right and SH type plays Right

**Expected payoffs**: Weight outcomes by type probabilities

<table>
<tr><th></th><th>(L, L)</th><th>(L, R)</th><th>(R, L)</th><th>(R, R)</th></tr>
<tr><th>Up</th><td>3, 3</td><td>0.6, 2.2</td><td>2.4, 3.2</td><td>0, 2.4</td></tr>
<tr><th>Down</th><td>2, 0.2</td><td>1.2, 1</td><td>1.8, 0.4</td><td>1, 1.2</td></tr>
</table>

---

## Eliminating Dominated Strategies

PD type has dominant strategy to play Right (4 > 3, 2 > 1)

**Eliminate (Left, Left)**: Dominated by (Right, Left)
- Compare Player 2's payoffs: 3.2 > 3 and 0.4 > 0.2
- Confirms PD type prefers Right when SH type plays Left

**Eliminate (Left, Right)**: Dominated by (Right, Right)
- Compare Player 2's payoffs: 2.4 > 2.2 and 1.2 > 1
- Confirms PD type prefers Right when SH type plays Right

Simplified 2×2 game:

<table>
<tr><th></th><th>(R, L)</th><th>(R, R)</th></tr>
<tr><th>Up</th><td>2.4, 3.2</td><td>0, 2.4</td></tr>
<tr><th>Down</th><td>1.8, 0.4</td><td>1, 1.2</td></tr>
</table>

---

## Finding Nash Equilibria

**Pure strategy equilibria**:
1. (Up, Right-Left): Player 1 plays Up; P2's PD type plays Right, SH type plays Left
2. (Down, Right-Right): Player 1 plays Down; P2 plays Right regardless of type

**Mixed strategy equilibrium**: 
- Player 1 mixes between Up (1/2) and Down (1/2)
- P2's PD type plays pure strategy Right (still dominant)
- P2's SH type mixes between Left (5/8) and Right (3/8)

**Interpretation**: What looks like Player 2 "mixing" might actually be different types playing different pure strategies

---

## Information Paradox

Is more information always better? Intuitively, **YES**!
- In decision theory (one actor), this is true
- Can always ignore unhelpful information

But in game theory, **NO**!
- Extra information creates credible commitment problem
- You cannot credibly commit to ignore it
- Other players know you have it and adjust behavior

**Lesson**: In games, information value depends on strategic context

---

## Coin Flip Game: Less Information

Two players, simultaneous moves
- Player 1: Play or Quit
- Player 2: Heads, Tails, or Pass
- Neither knows coin flip result yet

| P1 Action | P2 Action | Payoff (P1, P2) |
|-----------|-----------|-----------------|
| Quit | Any | (1, 1) |
| Play | Pass | (2, 2) |
| Play | H or T | (+3, -3) or (-3, +3), EV = (0, 0) |

**Equilibrium**: P1 plays, P2 passes → (2, 2)

---

## Coin Flip Game: More Information

Player 2 now sees coin flip before choosing

P2's new incentive:
- If P1 plays, P2 can guarantee herself 3 by calling correctly
- P2 will never Pass (getting 2) when she can get 3

P1's rational response:
- Knows P2 will use her information to win 3
- Means P1 gets -3 if he plays
- Better to Quit and get 1

**Result**: Only equilibrium is Quit with payoff (1, 1) → P2 is worse off with more information

---

## Dominance Concepts

Two mindsets for evaluating strategies:

| Mindset | Timing | Focus |
|---------|--------|-------|
| **Ex Ante** | Before knowing your type | Overall player's grand strategy |
| **Interim** | After knowing your type | Specific type's optimal action |

Poker analogy:
- Ex Ante: Planning what to do with Aces vs. Sevens before cards are dealt
- Interim: Choosing best move after seeing you have Aces

---

## Interim Dominance

A strategy for a type is interim dominated if an alternative strategy for that type provides higher payoff, regardless of other players' strategies

**Example**: Player 2 as PD type
- If Player 1 plays Up: Right (4) > Left (3)
- If Player 1 plays Down: Right (2) > Left (1)
- Left is interim dominated for PD type

**Question**: "Given that I'm this type, is there a move that's always better for me?"

---

## Ex Ante Dominance

A strategy for a player is ex ante dominated if an alternative strategy for that player provides higher payoff, regardless of other players' strategies

**Example**: Player 2's complete strategies
- Any plan where "PD type plays Left" is flawed
- Better plan: Switch PD type to Right, keep everything else same
- Eliminate (Left, Left) and (Left, Right)

**Question**: "Is there an overall plan that's always better for me, considering all types I could be?"

---

## Relation Between Dominance Types

If a strategy is interim dominated for a type, then any complete strategy including that action is ex ante dominated for the player

- Interim dominance: "Playing Left is always bad for PD type"
- Ex ante implication: "Any plan that says 'if I'm PD type, play Left' must be suboptimal"

A strategy can be ex ante dominated without any individual type's action being interim dominated
- This can occur when probability of one type is overwhelming
- PD/SH mixed game: PD type 90%, SH type only 10%

**Application**: Use interim dominance to identify and eliminate ex ante dominated strategies in the combined payoff matrix

---

## Example: Poker Without Antes

**Simple poker game**:
- Two players, each has own deck (2 through Ace)
- Each draws one card privately (their "type")
- Simultaneously choose: Bet $1 or Fold
- High card wins; ties split pot
- No initial pot (no ante)

**The scale problem**:
- 13 possible cards = 13 types per player
- Each type has 2 actions (Bet/Fold)
- Total strategies: $2^{13} = 8,192$ per player
- Payoff matrix would be 8,192 × 8,192 = 67 million cells!

---

## Why Antes Matter?

**Start with the Ace**: Betting is weakly dominant
- Folding guarantees $0
- Betting: Best case +$1, worst case $0 (tie)

**The Two**: Folding strictly dominates betting
- If opponent has Ace (which bets), you lose $1
- Best case for betting is $0 (tie)

**The cascade begins**: Two folds → Three has no one to beat → Folds → Four folds → ... → King folds → **BNE**:
- Only unbeatable hand (Ace) has incentive to bet
- Game collapses to "wait for perfect hand"

**Solution**: Create pot, make folding costly, force interaction across all hand strengths

---

## Continuous Types

**Challenge**: When types aren't discrete, we face an infinite strategy space and cannot use finite payoff matrices

**Solution**: Cutpoint equilibrium $C^*$ → All types below $C^*$ take one action, all above take opposite

**Example: Volunteer's Dilemma**
- Two people, benefit = 1 for both, private cost $c \in [0,1]$
- $F(C^*)$ = probability other's cost is below $C^*$ (cumulative distribution function)
- If $c < C^*$: Volunteer; If $c > C^*$: Don't volunteer
- Every type plays pure strategy

---

## Finding the Cutpoint

**Indifference condition**: At $c = C^*$, player is indifferent between actions
- Payoff from volunteering: $1 - C^*$
- Payoff from not volunteering: $F(C^*) \times 1 + (1 - F(C^*)) \times 0$

**Equilibrium condition**:
$$1 - C^* = F(C^*)$$

where a unique cutpoint $C^*$ exists because $1 - C^*$ is strictly decreasing and $F(C^*)$ is increasing in $C^*$

**Insight**: Observed "mixing" is actually pure strategies
- Each type plays deterministically based on their cost
- Randomness comes from uncertainty about types

---

## Interpreting Mixed Strategies

1. Players actually mix
   - Deliberate randomization to avoid exploitation
   - Poker, sports, competitive games

2. Population frequencies
   - Different players use different pure strategies
   - Games with random matching

3. Purification
   - Players have tiny private information differences
   - Each type plays pure strategy based on private info

---

## Purification Theorem

Mixed strategies are pure strategies in disguise
- Add tiny private information (infinitesimal "nudge")
- Each type plays pure strategy based on their nudge
- As nudge → 0, game approaches original
- Probabilities match mixed strategy exactly

**Example**: Original game with complete information

|            | Left     | Right    |
|------------|----------|----------|
| **Up**     | 0, 0     | 0, -1    |
| **Down**   | -1, 0    | 3, 5     |

Mixed strategy equilibrium: P1 plays Up with 5/6, P2 plays Left with 3/4

---

## Adding Private Information

Perturbed game with types/shocks $\theta_1, \theta_2 \sim U[-1,1]$ and small $\varepsilon > 0$

|            | Left              | Right             |
|------------|-------------------|-------------------|
| **Up**     | $\varepsilon\theta_1, \varepsilon\theta_2$ | $\varepsilon\theta_1, -1$ |
| **Down**   | $-1, \varepsilon\theta_2$ | $3, 5$            |

**Pure strategy cutpoint equilibria**:
- P1 plays Up if type $\theta_1$ high enough (above cutpoint $\theta_1^*$)
  → Probability P1 plays Up $=p = P(\theta_1 > \theta_1^*)$
- P2 plays Left if type $\theta_2$ high enough (above cutpoint $\theta_2^*$)
  → Probability P2 plays Left $=q = P(\theta_2 > \theta_2^*)$
- Note each player still uses pure strategy based on own type

---

## Finding the Cutpoints

P1's indifference condition (when $\theta_1 = \theta_1^*$) → $\theta_1^* = \frac{3 - 4q}{\varepsilon}$
- Payoff from Up: $q \cdot \varepsilon \theta_1^* + (1-q) \cdot \varepsilon \theta_1^*$
- Payoff from Down: $q \cdot (-1) + (1-q) \cdot 3$

P2's indifference condition (when $\theta_2 = \theta_2^*$) → $\theta_2^* = \frac{5 - 6p}{\varepsilon}$
- Payoff from Left: $p \cdot \varepsilon \theta_2^* + (1-p) \cdot \varepsilon \theta_2^*$
- Payoff from Right: $p \cdot (-1) + (1-p) \cdot 5$

Probabilities depend on cutpoints
- $p = P(\theta_1 > \frac{3-4q}{\varepsilon})=\frac{1 - \frac{3-4q}{\varepsilon}}{2}$
- $q = P(\theta_2 > \frac{5-6p}{\varepsilon})=\frac{1 - \frac{5-6p}{\varepsilon}}{2}$

**Upshot**: As $\varepsilon \to 0$, $(p, q) = (5/6, 3/4)$ exactly matches mixed strategy equilibrium! Apparent randomness stems from uncertainty about private info

---

## Bayes' Rule

Update beliefs based on new information
- Start with prior belief
- Observe signal/evidence
- Calculate posterior belief

**Formula**: 
$$P(A|B) = \frac{P(A) \cdot P(B|A)}{P(B)}$$

**Intuition**: 
$$P(\text{State}|\text{Signal}) = \frac{P(\text{State}) \cdot P(\text{Signal}|\text{State})}{\text{Probability of observing this signal}}$$

---

## Example: Cancer Test

60% chance cancer, 40% clean. 90% positive if cancer, 10% negative if cancer; 100% negative if clean. **Question**: What's cancer probability given negative test?

**Probability Tree**:

```
                    ┌─ Positive (0.90) → 0.60 × 0.90 = 0.54
        Cancer ─────┤
       (0.60)       └─ Negative (0.10) → 0.60 × 0.10 = 0.06
Start ──┤
        Clean ──────┬─ Positive (0.00) → 0.40 × 0.00 = 0.00
       (0.40)       └─ Negative (1.00) → 0.40 × 1.00 = 0.40
```

**Updated belief**: $P(\text{Cancer}|\text{Negative}) = \frac{0.06}{0.06 + 0.40} \approx 13\%$

---

## Winner's Curse

Common value auction
- Item has single true value (same for everyone), but unknown
- Example: Oil deposits, sports free agent
- Contrast with independent value auction (autographed book)

**Paradox**: In auctions with uncertainty, winning is bad news
- Winner is person who most overestimated the value
- Lab experiments show people overbid and fall victim to curse; Professional bidders understand curse and bid conservatively

**Key lesson**: Must bid conditional on what winning tells you

---

## Example: Oil Field Auction

Two companies bid for drilling rights:
- True value: $0 (prob 1/4), $25M (prob 1/2), or $50M (prob 1/4)
- Second-price sealed-bid auction
- Each gets private signal: "Low" or "High"

Signal structure:
| True Value | Bidder 1 Signal | Bidder 2 Signal |
|------------|----------------|----------------|
| $0 | Low | Low |
| $25M | Low | High |
| $25M | High | Low |
| $50M | High | High |

**Question**: How much should you bid based on your signal?

---

## Naive Strategy

Observe low signal:
- $P(\$0|Low) = \frac{P(Low|\$0) \cdot P(\$0)}{P(Low)} = 0.5$
- $P(\$25M|Low) = \frac{P(Low|\$25M) \cdot P(\$25M)}{P(Low)} = 0.5$
- Expected value: $0.5 \times \$0 + 0.5 \times \$25M = \$12.5M$

Observe high signal:
- $P(\$25M|High) = \frac{P(High|\$25M) \cdot P(\$25M)}{P(High)} = 0.5$
- $P(\$50M|High) = \frac{P(High|\$50M) \cdot P(\$50M)}{P(High)} = 0.5$
- Expected value: $0.5 \times \$25M + 0.5 \times \$50M = \$37.5M$

**Naive strategy**: Bid your expected value (Low → $12.5M, High → $37.5M). Why this fails? For example, low bidder gets expected payoff of -$3.125M (verify)! Better to bid $0

---

## Rational Strategy

Bayesian Nash equilibrium (verify):
- Low signal → Bid $0 (expected payoff $0)
- High signal → Bid $50M (expected payoff $12.5M)

What happens when the number of bidders increases?
- Standard first-price auctions: more bidders → higher bids due to competition
- Common value auctions: If you win against 999 other bidders, your estimate was higher than all 999 others → Overwhelmingly likely you overestimated → "Curse" becomes stronger with more competition
