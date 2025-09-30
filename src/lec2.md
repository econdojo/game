---
marp: true
math: mathjax
theme: default
size: 4:3
paginate: true
backgroundColor: '#f4f6fa'
backgroundImage: url('https://marp.app/assets/hero-background.svg')
header: 'Lecture 2: Extensive Form Games'
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

# Lecture 2: Extensive Form Games

**Instructor:** Fei Tan

<img src="images/github.png" width="30" height="30" class="logo"> @econdojo &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/youtube.png" width="30" height="30" class="logo"> @BusinessSchool101 &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/slu.png" width="30" height="30" class="logo"> Saint Louis University

**Date:** September 4, 2025

---

## The Road Ahead

1. [From Simultaneous to Sequential Games](#from-simultaneous-to-sequential-games)
2. [Subgame Perfect Equilibrium](#subgame-perfect-equilibrium)
3. [Backward Induction](#backward-induction)
4. [Commitment Problems](#commitment-problems)
5. [Forward Induction](#forward-induction)

---

## From Simultaneous to Sequential Games

**Simultaneous Move Games**: players move at the same time or cannot observe each other's moves
- Prisoner's dilemma: prisoners in separate interrogation rooms
- Football: offense and defense call plays simultaneously
- Meeting coordination: couple choosing locations without communication

**Sequential Games**: strategic interactions that flow over time in specific steps
- Military invasion followed by response decision
- Police officer requesting search permission, then deciding thoroughness
- Chess: white moves, black responds, cycle repeats
- Firm entry followed by incumbent's competitive response

---

## Introducing Selten's Game

Firm 1 considers entering Firm 2's monopoly market. If Firm 1 enters, Firm 2 must decide whether to accommodate entry or wage a price war.

**Payoff Structure**:
- **Price war**: both firms earn 0 (profits eliminated)
- **Accommodation**: Firm 1 earns 3, Firm 2 earns 1
- **No entry**: Firm 1 earns 2 (saves investment), Firm 2 earns 2 (maintains monopoly)

<table class="payoff-matrix">
<tr>
<th></th>
<th>Firm 2: Accommodate</th>
<th>Firm 2: War</th>
</tr>
<tr>
<th>Firm 1: Enter</th>
<td>3, 1</td>
<td>0, 0</td>
</tr>
<tr>
<th>Firm 1: Stay Out</th>
<td>2, 2</td>
<td>2, 2</td>
</tr>
</table>

---

## Extensive Form Games

**Game Tree Representation** of the firm entry game:

```
                Firm 1
               /      \
           Enter      Stay Out
             /           \
         Firm 2          (2, 2)
        /      \
  Accommodate  War  
     /          \
  (3, 1)      (0, 0)
```

**Key Elements**:
- **Decision nodes**: where players make choices
- **Terminal nodes**: end points with payoffs
- **Branches**: represent available strategies
- **Sequential structure**: order of play is explicit

---

## Multiple Nash Equilibria in Strategic Form

Recall Selten's game has multiple Nash equilibria:

1. **Pure strategy equilibria**:
   - (Enter, Accommodate): (3, 1)
   - (Stay Out, War): (2, 2)

2. **Mixed strategy equilibria**:
   - Firm 1 plays Stay Out with probability 1
   - Firm 2 plays War with probability $\geq\frac{1}{3}$

Multiple equilibria make prediction difficult. Which one will actually occur? **Sequential structure** helps us resolve this ambiguity!

---

## Analyzing Sequential Play

If Firm 1 enters, Firm 2 faces this decision:

```
         Firm 2
        /      \
  Accommodate  War  
     /          \
   (3, 1)     (0, 0)
```

**Firm 2's analysis**: 1 > 0, so Firm 2 prefers Accommodate over War

**Firm 1's analysis** (knowing Firm 2 will accommodate):
- Enter → Firm 2 accommodates → payoff = 3
- Stay Out → payoff = 2
- Since 3 > 2, Firm 1 should enter

**Unique sequential solution**: (Enter, Accommodate) with payoffs (3, 1)

---

## Subgame Perfect Equilibrium

A **Subgame Perfect Equilibrium (SPE)** is a strategy profile where each player's strategy constitutes a Nash equilibrium in every subgame.

**Key insight**: SPE ensures that threats are **credible**
- Firm 2's threat to wage war is NOT credible
- Once Firm 1 enters, Firm 2 has no incentive to follow through
- Firm 1 recognizes this and enters anyway

**Refinement**: SPE eliminates Nash equilibria that rely on non-credible threats
- All SPE are Nash equilibria
- Not all Nash equilibria are SPE
- SPE is the gold standard for extensive form games

---

## Games with Simultaneous Moves in Extensive Form

Some extensive form games include simultaneous moves, e.g. matching pennies

```
           Player 1
          /        \
      Heads        Tails
        /            \
   Player 2  - - -  Player 2    <- information set
   /      \         /      \
 Heads   Tails    Heads   Tails
  /        \       /        \
 (1,-1)  (-1,1)  (-1,1)   (1,-1)
```

**Information set**: dashed line shows Player 2 cannot observe Player 1's choice

**Solution method**: convert to matrix form and solve as simultaneous game

---

## Constructing Games with Simultaneous Moves

Critical rules for information sets:

1. **Identical strategy sets**: same available actions at all nodes in the information set

2. **Irrelevance of player order**: whoever plays first, the resulting payoff matrix must be the same

**Example of violation**:
```
If Player 1 chooses Heads → Player 2 chooses {A, B}
If Player 1 chooses Tails → Player 2 chooses {C, D}
```

**Problem**: Player 2 can infer Player 1's move from available actions, violating simultaneity

---

## Backward Induction

**Method**: solve extensive form games by working backwards from the end:

1. Start at the final decision nodes and determine optimal actions
2. Work backwards using optimal future play to determine current optimal actions
3. Continue until reaching the initial node

Backward induction always finds the subgame perfect equilibrium

**Note**: complete strategy must specify actions at ALL decision nodes, even those not reached in equilibrium

---

## Example: Escalation Game

Two countries are on the brink of war:

```
Player 1: Accept ──── (0, 0)
    │
    └── Threaten ── Player 2: Concede ──── (1, -2)
                         │
                         └── Escalate ── Player 1: War ──── (-1, -1)
                                              │
                                              └── Back Down ──── (-2, 1)
```

**Step 1**: Player 1 chooses between War (-1) and Back Down (-2). Since -1 > -2, choose War.

**Step 2**: Player 2 chooses between Concede (-2) and Escalate (leading to War: -1). Since -1 > -2, choose Escalate.

**Step 3**: Player 1 chooses between Accept (0) and Threaten (leading to Escalate→War: -1). Since 0 > -1, choose Accept.

**SPE**: ⟨(Accept, War), Escalate⟩ with outcome (0, 0)

---

## Example: Ultimatum Game

Player 1 has a good worth 2 and must bargain with Player 2 over division
- **Split**: Offer equal division (1, 1)  
- **Take**: Attempt to take everything (2, 0)
- Player 2 can **Accept** or **Reject** any proposal
- Rejection leads to (0, 0) for both

```
Player 1: Split ── Player 2: Accept ──── (1, 1)
    │                   │
    │                   └── Reject ──── (0, 0)
    │
    └── Take ── Player 2: Accept ──── (2, 0)
                     │
                     └── Reject ──── (0, 0)
```

---

## Multiple SPE in Ultimatum Game

After **Split**: Player 2 prefers Accept (payoff 1) over Reject (payoff 0)

After **Take**: Player 2 is indifferent between Accept (payoff 0) and Reject (payoff 0)

Multiple equilibria arise from Player 2's indifference:

1. **Player 2 always Accepts**: Player 1 takes (payoff 2 > 1), so SPE is ⟨Take, (Accept, Accept)⟩
2. **Player 2 always Rejects**: Player 1 splits (payoff 1 > 0), so SPE is ⟨Split, (Accept, Reject)⟩  
3. **Player 2 mixes**: Any probability p of accepting after "Take"
   - If p > 1/2: Player 1 takes
   - If p < 1/2: Player 1 splits
   - If p = 1/2: Player 1 indifferent, can mix with any probability q

---

## Example: Weighted Matching Pennies

```
                    Player 1
                   /        \
                Stay        Go
                /            \
           (-1/3, 4)      Player 2
                         /        \
                      Left        Right
                      /              \
                Player 1 - - - - - Player 1
                /      \            /    \
               Up     Down        Up     Down
              /         \         /        \
           (3,-3)     (-1,1)   (-2,2)    (0,0)
```

**Why backward induction fails?** It requires every decision node to have unique history, but Player 1's last decision (Up/Down) violates this requirement.

**Valid subgame**: Only the simultaneous portion after "Go" forms a proper subgame since Player 2's choice has unique history.

---

## Multiple SPE in Weighted Matching Pennies

**Solution method**: 
1. Solve the simultaneous subgame first: Player 1 plays Up with prob 1/6; Player 2 plays Left with prob 1/3
2. Replace subgame with expected payoffs (-1/3, 1/3)
3. Player 1 compares Stay(-1/3) vs Go(-1/3) → Indifferent!

**Multiple SPE**: Player 1 can mix with any probability between Stay and Go

**Key insight**: Simultaneous moves within extensive form games can create multiple SPE even when all payoffs are unique

---

## Making Threats Credible

Two armies fight over an island. Each has a bridge for access:

- Island is valuable but not worth fighting for
- Each army prefers to concede rather than fight
- First army occupies island, second decides whether to invade

```
       Army 1: Burn Bridge?
        /              \
     Burn            Don't Burn
      /                  \
   Army 2               Army 2
    /    \              /      \
Invade  Concede      Invade   Concede
  /        \          /          \
(-1,-1)   (1,0)    Army 1      (1,0)
                  /      \
               Fight   Retreat
                /          \
             (-1,-1)     (0,1)
```

---

## Bridge Burning Analysis

**Backward Induction**:

**Step 1** - If bridge not burned and Army 2 invades: Army 1 chooses Fight (-1) vs Retreat (0) → Choose Retreat

**Step 2** - Army 2's decision if bridge not burned: Concede (0) vs Invade (1, since Army 1 retreats) → Choose Invade

**Step 3** - Army 2's decision if bridge burned: Concede (0) vs Invade (-1, since Army 1 must fight) → Choose Concede

**Step 4** - Army 1's initial decision: Burn (1) vs Not Burn (0) → Choose Burn

**SPE**: ⟨(Burn, Retreat), (Concede, Invade)⟩

**Tying Hands**: Deliberately limiting your future options to make a threat or commitment **credible**!

---

## Commitment Problems

Situations where the inability to commit to future actions leads to suboptimal outcomes. Consider a graduate student pulled over in Texas. Officer requests vehicle search but cannot credibly commit to "quick" search.

```
                    Student
                   /        \
              Allow Search   Request K-9
                 /              \
             Officer           (2, 1)
            /        \
       Quick       Extensive
        /              \
     (3, 2)          (1, 3)
```

**SPE**: ⟨Request K-9, Extensive⟩ - Both prefer quick search (3,2) but can't achieve it

**Key insight**: Words without credible commitment mechanisms are worthless

---

## Example: Civil War

Dictator faces rebel revolution. Must choose: Fight (20% win, 80% lose) or Surrender immediately. If rebels win, they choose Forgive vs Execute dictator.

```
                Dictator
               /        \
            Fight     Surrender
             /            \
         Nature          Rebels
        /      \        /      \
     Win      Lose   Forgive  Execute
    (7,-10)    |      (-5,8)  (-10,10)
            Rebels
           /      \
       Forgive   Execute
       (-8,5)   (-13,7)
```

**Expected payoffs** when Dictator Fights: Dictator gets (.2)(7) + (.8)(-13) = -9, Rebels get (.2)(-10) + (.8)(7) = 3.6

**SPE**: ⟨Fight, (Execute, Excute)⟩ - Rebels cannot credibly commit to spare dictator if he surrenders, so civil wars rarely end in negotiated settlements

---

## Example: Centipede Game

Two players alternate adding $2 to a growing pot or taking $2 plus splitting the pot. Player 1 starts, and the game can continue for up to 100 rounds.

```
        Continue       Continue       Continue       Continue                Continue
    1 ———————————— 2 ———————————— 1 ———————————— 2 ———————————— ... ———— 2 ———————————— 1
    |              |              |              |                       |              |
   End            End            End            End                     End            End
    |              |              |              |                       |              |
  (2,0)          (1,3)          (4,2)          (3,5)                  (99,101)      (100,100)
```

**Backward Induction**: Player 2 takes in final round ($101 > $100) → Player 1 takes in round 99 → ... → Both take immediately with (2,0)

**SPE**: Both players take at every opportunity → SPE gives worst possible outcome!

**Paradox**: Laboratory evidence shows players cooperate for many rounds, explained by irrationality, altruism, or strategic "feigning irrationality"

---

## Forward Induction

Forward induction uses the assumption that all **past** play was rational to make inferences about opponents' private information or strategies

```
                    Player 1 ——————— (2.5, 2.5)
                  /         \
               Stag         Hare
                /             \      
           Player 2 - - - - Player 2  (information set)
           /      \         /      \
        Stag     Hare    Stag     Hare
          |        |       |        |
        (3,3)    (0,2)   (2,0)    (1,1)
```

Forward induction selects **unique** equilibrium ⟨Stag, Stag⟩:

1. Hare is strictly dominated by Pub (2.5 > 2) → Player 1 never chooses Hare
2. Player 2 infers Player 1 chose Stag → Player 2 chooses Stag (payoff 3 > 2)
3. Player 1 anticipates this → chooses Stag over Pub (payoff 3 > 2.5)
