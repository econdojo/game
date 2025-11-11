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
2. [Bayesian Nash Equilibrium](#bayesian-nash-equilibrium)
3. [Solving for BNE: Matrix Method](#solving-for-bne)
4. [Ex Ante vs. Interim Dominance](#dominance-concepts)

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

## Solving for BNE: The Matrix Method

**Challenge**: When games have multiple matrices (one per opponent type), how do we find the BNE?

**Solution**: Transform the game into a single, unified matrix

**Key insight**: The uninformed player needs a complete contingency plan specifying what to do for each possible type they might be

**Method**: 
1. Create compound strategies for the uncertain player
2. Calculate expected payoffs weighted by type probabilities
3. Solve for Nash equilibria in the combined matrix
4. These Nash equilibria are the Bayesian Nash equilibria of the original game

---

## Example Setup: PD/SH Mixed Game

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

## Building the Combined Matrix

**Player 2's compound strategies**: (Action if PD, Action if SH)
- (Left, Left): PD type plays Left AND SH type plays Left
- (Left, Right): PD type plays Left AND SH type plays Right
- (Right, Left): PD type plays Right AND SH type plays Left
- (Right, Right): PD type plays Right AND SH type plays Right

**Calculating expected payoffs**: Weight outcomes by type probabilities

**Example**: Up, (Left, Right)
- Player 1: $(0.2)(3) + (0.8)(0) = 0.6$
- Player 2: $(0.2)(3) + (0.8)(2) = 2.2$

---

## The Combined Matrix

<table>
<tr><th></th><th>(L, L)</th><th>(L, R)</th><th>(R, L)</th><th>(R, R)</th></tr>
<tr><th>Up</th><td>3, 3</td><td>0.6, 2.2</td><td>2.4, 3.2</td><td>0, 2.4</td></tr>
<tr><th>Down</th><td>2, 0.2</td><td>1.2, 1</td><td>1.8, 0.4</td><td>1, 1.2</td></tr>
</table>

**Critical step**: Ensure arithmetic is correct! Wrong calculations → Wrong equilibria

**Next step**: Eliminate dominated strategies and find Nash equilibria

---

## Eliminating Dominated Strategies

**Key insight**: PD type has dominant strategy to play Right (4 > 3, 2 > 1)

**Eliminate (Left, Left)**: Dominated by (Right, Left)
- Compare Player 2's payoffs: 3.2 > 3 and 0.4 > 0.2
- Confirms PD type prefers Right when SH type plays Left

**Eliminate (Left, Right)**: Dominated by (Right, Right)
- Compare Player 2's payoffs: 2.4 > 2.2 and 1.2 > 1
- Confirms PD type prefers Right when SH type plays Right

**Simplified 2×2 game**:

<table>
<tr><th></th><th>(R, L)</th><th>(R, R)</th></tr>
<tr><th>Up</th><td>2.4, 3.2</td><td>0, 2.4</td></tr>
<tr><th>Down</th><td>1.8, 0.4</td><td>1, 1.2</td></tr>
</table>

---

## Finding the Equilibria

**Pure strategy equilibria** (mutual best responses):
1. **(Up, Right-Left)**: Player 1 plays Up; P2's PD type plays Right, SH type plays Left
2. **(Down, Right-Right)**: Player 1 plays Down; P2 plays Right regardless of type

**Mixed strategy equilibrium**: 
- Player 1 mixes between Up and Down
- P2's PD type plays pure strategy Right (still dominant)
- P2's SH type mixes between Left and Right

**Interpretation**: What looks like Player 2 "mixing" might actually be different types playing different pure strategies

---

## Dominance Concepts

**Two mindsets for evaluating strategies**:

| Mindset | Timing | Focus |
|---------|--------|-------|
| **Ex Ante** | Before knowing your type | Overall player's grand strategy |
| **Interim** | After knowing your type | Specific type's optimal action |

**Poker analogy**:
- **Ex Ante**: Planning what to do with Aces vs. Sevens before cards are dealt
- **Interim**: Choosing best move after seeing you have Aces

---

## Interim Dominance

**Definition**: A strategy for a type is interim dominated if an alternative strategy for that type provides higher payoff, regardless of other players' strategies

**Focus**: Single type after knowing their identity

**Example**: Player 2 as PD type
- If Player 1 plays Up: Right (4) > Left (3)
- If Player 1 plays Down: Right (2) > Left (1)
- **Conclusion**: Left is interim dominated for PD type

**Key question**: "Given that I'm this type, is there a move that's always better for me?"

---

## Ex Ante Dominance

**Definition**: A strategy for a player is ex ante dominated if an alternative strategy for that player provides higher payoff, regardless of other players' strategies

**Focus**: Player before knowing their type

**Example**: Player 2's complete strategies
- Any plan where "PD type plays Left" is flawed
- Better plan: Switch PD type to Right, keep everything else same
- Eliminates: (Left, Left) and (Left, Right)

**Key question**: "Is there an overall plan that's always better for me, considering all types I could be?"

---

## The Relationship Between Dominance Types

**Key result**: If a strategy is interim dominated for a type, then any complete strategy including that action is ex ante dominated for the player

**Logic**: 
- Interim dominance: "Playing Left is always bad for PD type"
- Ex ante implication: "Any plan that says 'if I'm PD type, play Left' must be suboptimal"

**Practical application**: Use interim dominance to identify and eliminate ex ante dominated strategies in the combined matrix

---

## Summary: Key Takeaways

**Incomplete vs. Imperfect Information**:
- Imperfect: Don't know opponent's past action
- Incomplete: Don't know opponent's payoffs/preferences

**Bayesian Nash Equilibrium**:
- Solution concept for incomplete information games
- Assigns one strategy to each type of player
- Uses beliefs to calculate expected payoffs

**Solving for BNE**:
- Matrix method: Combine multiple games into one
- Create compound strategies for uncertain player
- Find Nash equilibria in combined matrix

**Dominance**: Interim (type-specific) vs. Ex Ante (player-level)
