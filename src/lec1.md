---
marp: true
math: mathjax
theme: default
paginate: true
backgroundColor: '#f4f6fa'
backgroundImage: url('https://marp.app/assets/hero-background.svg')
header: 'Lecture 1: Basic Strategic Form Games'
footer: 'Fei Tan | Made on Earth by humans.'
style: |
  .logo {
    vertical-align: -0.2em;
  }
  section {
    color: #222;
  }
  h1, h2, h3, h4, h5, h6 {
    color: #003DA5;
  }
  .slide-footer {
    color: #888;
  }
  .payoff-matrix {
    margin: 20px auto;
    border-collapse: collapse;
  }
  .payoff-matrix th, .payoff-matrix td {
    border: 2px solid #003DA5;
    padding: 10px 15px;
    text-align: center;
  }
  .payoff-matrix th {
    background-color: #003DA5;
    color: white;
  }
  .highlight {
    background-color: #ffeb3b;
    padding: 2px 4px;
    border-radius: 3px;
  }
---

# Lecture 1: Basic Strategic Form Games

**Instructor:** Fei Tan

<img src="images/github.png" width="30" height="30" class="logo"> @econdojo &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/youtube.png" width="30" height="30" class="logo"> @BusinessSchool101 &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/slu.png" width="30" height="30" class="logo"> Saint Louis University

**Date:** July 19, 2025

---

## The Road Ahead

1. [What is Game Theory?](#what-is-game-theory)
2. [Dominant Strategies](#dominant-strategies)
3. [Pure Strategy Nash Equilibrium](#pure-strategy-nash-equilibrium)
4. [Best Response](#best-response)
5. [Mixed Strategy Nash Equilibrium](#mixed-strategy-nash-equilibrium)

---

## What is Game Theory?

**Game Theory** is the study of **strategic interdependence** - situations where your actions affect both your welfare and others' welfare, and vice versa. Key elements include:
- **Players**: Decision makers (individuals, firms, countries)
- **Strategies**: Available choices for each player
- **Payoffs**: Outcomes that result from the combination of all players' choices
- **Information**: What each player knows about the game

### Why Study Game Theory?
- Understanding competition and cooperation in business and markets
- Analyzing political and economic policies and their outcomes
- Making better strategic decisions in interactive situations

---

## Example: Prisoner's Dilemma

Two thieves are arrested for trespassing. Police suspect they planned to rob a store but lack evidence. Each prisoner is offered a deal:

- **If you confess and your partner doesn't**: You go free, partner gets 12 months
- **If both confess**: You each get 8 months  
- **If neither confesses**: You each get 1 month (trespassing only)
- **If your partner confesses and you don't**: You get 12 months, partner goes free

---

## Payoff Matrix

<table class="payoff-matrix">
<tr>
<th></th>
<th>Player 2: Quiet</th>
<th>Player 2: Confess</th>
</tr>
<tr>
<th>Player 1: Quiet</th>
<td>-1, -1</td>
<td>-12, 0</td>
</tr>
<tr>
<th>Player 1: Confess</th>
<td>0, -12</td>
<td>-8, -8</td>
</tr>
</table>

**Note**: Payoffs represent negative months in jail (higher numbers are better)

### Reading the Matrix
- Player 1 chooses rows, Player 2 chooses columns
- First number in each cell = Player 1's payoff
- Second number in each cell = Player 2's payoff

---

## Solving the Prisoner's Dilemma

### Player 1's Analysis
**If Player 2 stays quiet:**
- Quiet: -1 months
- Confess: 0 months ✓ (Better!)

**If Player 2 confesses:**
- Quiet: -12 months  
- Confess: -8 months ✓ (Better!)

**Conclusion**: Player 1 should **always confess** regardless of what Player 2 does!

### Player 2's Analysis (by symmetry)

---

## Dominant Strategies

A **dominant strategy** is a strategy that gives a player the highest payoff regardless of what other players do. There are two types of dominance:

- **Strictly Dominant**: Always gives strictly higher payoffs
- **Weakly Dominant**: Always gives higher or equal payoffs (at least as good)

### The Prisoner's Dilemma
- "Confess" is a **strictly dominant strategy** for both players, leading to the **dominant strategy equilibrium**: (Confess, Confess) or (-8, -8)
- Both staying quiet would give (-1, -1) - better for everyone!
- But (-1, -1) is **not stable** - each player has incentive to deviate

---

## Iterated Elimination of Strictly Dominated Strategies

<table class="payoff-matrix">
<tr>
<th></th>
<th>Left</th>
<th>Center</th>
<th>Right</th>
</tr>
<tr>
<th>Up</th>
<td>13, 3</td>
<td>1, 4</td>
<td>7, 3</td>
</tr>
<tr>
<th>Middle</th>
<td>4, 1</td>
<td>3, 3</td>
<td>6, 2</td>
</tr>
<tr>
<th>Down</th>
<td>-1, 9</td>
<td>2, 8</td>
<td>8, -1</td>
</tr>
</table>

**Step 1**: Center dominates Right for Player 2 → eliminate Right  
**Step 2**: Middle dominates Down for Player 1 → eliminate Down  
**Step 3**: Center dominates Left for Player 2 → eliminate Left  
**Result**: (Middle, Center) with payoffs (3, 3) (order does not matter!)
**Caution**: Does this work for weakly dominated strategies?

---

## Pure Strategy Nash Equilibrium

A **Pure Strategy Nash Equilibrium** is a set of strategies where each player's strategy is a best response to the other players' strategies.

**Key Property**: No player wants to unilaterally change their strategy.

### The Prisoner's Dilemma
(Confess, Confess) is the **unique pure strategy Nash equilibrium**
- If Player 2 confesses, Player 1's best response is confess
- If Player 1 confesses, Player 2's best response is confess

---

## Example: Stag Hunt Game

<table class="payoff-matrix">
<tr>
<th></th>
<th>Player 2: Stag</th>
<th>Player 2: Hare</th>
</tr>
<tr>
<th>Player 1: Stag</th>
<td>3, 3</td>
<td>0, 2</td>
</tr>
<tr>
<th>Player 1: Hare</th>
<td>2, 0</td>
<td>1, 1</td>
</tr>
</table>

### Multiple Equilibria
- **(Stag, Stag)**: High payoff but risky - requires coordination
- **(Hare, Hare)**: Lower payoff but safe
- Coordination and trust matter for achieving better outcomes

---

## Example: Stoplight Game

<table class="payoff-matrix">
<tr>
<th></th>
<th>Player 2: Go</th>
<th>Player 2: Stop</th>
</tr>
<tr>
<th>Player 1: Go</th>
<td>-5, -5</td>
<td>1, 0</td>
</tr>
<tr>
<th>Player 1: Stop</th>
<td>0, 1</td>
<td>-1, -1</td>
</tr>
</table>

### Multiple Equilibria
- **Real-world solution**: Traffic lights coordinate behavior by telling players which equilibrium, (Go, Stop) or (Stop, Go), to play
- **Self-enforcing**: No police needed - players naturally want to follow the signal because it makes their strategy optimal

---

## Best Response

A **best response** is the optimal strategy for a player given what all other players are doing

### Method for Finding Nash Equilibria
1. For each possible combination of strategies by all other players, mark each player's best response in the payoff matrix
2. Nash equilibria occur where **all players** are simultaneously playing best responses

### Why This Works
- **Nash Equilibrium Property**: No player wants to unilaterally deviate, and best responses ensure no player can improve by changing strategies
- **Mutual Best Response**: When all players are simultaneously best responding, the outcome is stable and self-reinforcing

---

## Example: 4×4 Safety in Numbers

Two generals each have 3 units. They can send 0, 1, 2, or 3 units to battle. The side with more troops wins (+1), fewer troops loses (-1), equal troops draw (0), no battle means (0,0)

<table class="payoff-matrix">
<tr>
<th></th>
<th>0 units</th>
<th>1 unit</th>
<th>2 units</th>
<th>3 units</th>
</tr>
<tr>
<th>0 units</th>
<td>0*, 0*</td>
<td>0, 0</td>
<td>0, 0</td>
<td>0*, 0*</td>
</tr>
<tr>
<th>1 unit</th>
<td>0*, 0</td>
<td>0, 0</td>
<td>-1, 1*</td>
<td>-1, 1*</td>
</tr>
<tr>
<th>2 units</th>
<td>0*, 0</td>
<td>1*, -1</td>
<td>0, 0</td>
<td>-1, 1*</td>
</tr>
<tr>
<th>3 units</th>
<td>0*, 0*</td>
<td>1*, -1</td>
<td>1*, -1</td>
<td>0*, 0*</td>
</tr>
</table>

**Note:** Nash equilibria are marked with * for both players

---

## Mixed Strategy Nash Equilibrium

A **mixed strategy** is a probability distribution over a player's pure strategies. Consider matching pennies:
<table class="payoff-matrix">
<tr>
<th></th>
<th>Player 2: Heads</th>
<th>Player 2: Tails</th>
</tr>
<tr>
<th>Player 1: Heads</th>
<td>1, -1</td>
<td>-1, 1</td>
</tr>
<tr>
<th>Player 1: Tails</th>
<td>-1, 1</td>
<td>1, -1</td>
</tr>
</table>

### Mixed Strategy Solution
- Each player randomizes: 50% Heads, 50% Tails
- This makes the opponent indifferent between their strategies
- Mixed strategy equilibrium exists when pure strategy equilibrium doesn't

---

## Example: Zero-Sum Game
<table class="payoff-matrix">
<tr>
<th></th>
<th>Player 2: Left</th>
<th>Player 2: Right</th>
</tr>
<tr>
<th>Player 1: Up</th>
<td>3, -3</td>
<td>-2, 2</td>
</tr>
<tr>
<th>Player 1: Down</th>
<td>-1, 1</td>
<td>0, 0</td>
</tr>
</table>

**Step 1**: Let Player 1 play Up with probability $p$, Down with probability $1-p$

**Step 2**: Player 2's expected payoffs:
- Left: $p(-3) + (1-p)(1)$, &nbsp;&nbsp;&nbsp; Right: $p(2) + (1-p)(0)$

**Step 3**: Player 2 must be indifferent between Left and Right &rarr; $p = \frac{1}{6}$

**Note**: By symmetry, Player 2 plays Left with probability $\frac{1}{3}$, Right with probability $\frac{2}{3}$

---

## Example: Battle of the Sexes

A couple wants to go on a date. She prefers the ballet, he prefers the fight. Both prefer being together to being alone

<table class="payoff-matrix">
<tr>
<th></th>
<th>She: Ballet</th>
<th>She: Fight</th>
</tr>
<tr>
<th>He: Ballet</th>
<td>1, 2</td>
<td>0, 0</td>
</tr>
<tr>
<th>He: Fight</th>
<td>0, 0</td>
<td>2, 1</td>
</tr>
</table>

### All Nash Equilibria
- **Pure strategy**: (Ballet, Ballet) and (Fight, Fight)
- **Inefficiency of mixed strategy**: He plays Ballet $\frac{1}{3}$, Fight $\frac{2}{3}$; She plays Ballet $\frac{2}{3}$, Fight $\frac{1}{3}$. Both earn only $\frac{2}{3}$ and fail to coordinate $\frac{5}{9}$ of the time
