---
marp: true
math: mathjax
theme: default
size: 4:3
paginate: true
backgroundColor: '#f4f6fa'
backgroundImage: url('https://marp.app/assets/hero-background.svg')
header: 'Lecture 6: Repeated Games'
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

# Lecture 6: Repeated Games

**Instructor:** Fei Tan

<img src="images/github.png" width="30" height="30" class="logo"> @econdojo &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/youtube.png" width="30" height="30" class="logo"> @BusinessSchool101 &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/slu.png" width="30" height="30" class="logo"> Saint Louis University

**Date:** October 30, 2025

---

## The Road Ahead

1. [The Hope and Collapse of Finite Repetition](#finite-repeated-games)
2. [Discount Factors and Infinite Games](#discount-factors)
3. [Geometric Series: Taming Infinity](#geometric-series)
4. [One-Shot Deviation Principle](#one-shot-deviation-principle)
5. [Grim Trigger Strategy](#grim-trigger-strategy)
6. [Tit-for-Tat and Credibility](#tit-for-tat)
7. [Folk Theorem: The Explosion of Equilibria](#folk-theorem)
8. [The Prediction Problem](#prediction-problem)

---

## Finite Repeated Games

**The Intuitive Hope**: If we play the Prisoner's Dilemma repeatedly, surely the shadow of the future will encourage cooperation?

**Classic Prisoner's Dilemma Payoffs**:
<table>
<tr><th></th><th>Cooperate</th><th>Defect</th></tr>
<tr><th>Cooperate</th><td>3, 3</td><td>1, 4</td></tr>
<tr><th>Defect</th><td>4, 1</td><td>2, 2</td></tr>
</table>

**The Brutal Reality**: In any **finitely repeated** game where the end is known, backward induction destroys all hope of cooperation.

**Why?** Players can build trust, signal intentions, and seek rewards/punishments—but a cold, backward-flowing logic prevents cooperation when the end is certain.

---

## The Logic of the End

**Final Round Analysis**: In the last round, all previous payoffs are locked in. Players must play the one-shot Nash Equilibrium.

**In Prisoner's Dilemma**: The unique Nash Equilibrium is **(Defect, Defect)** with payoffs (2, 2).

**The First Domino**: Certainty of final-round betrayal triggers the unraveling process.

<div class="identity-box">
"My actions in this round cannot sway what you will do in the final round. Since I cannot influence the future, my only rational choice is to maximize my payoff for today by defecting."
</div>

---

## The Domino Effect

**Second-to-Last Round**: Players know the final round outcome is (Defect, Defect).

1. **The Known Future**: Final round is predetermined as mutual defection
2. **The Empty Promise**: Cooperating now cannot influence future behavior  
3. **The Inevitable Choice**: This round becomes strategically identical to a one-shot game

**The Unstoppable Collapse**: This logic continues backward through every round:
- Stage N → Stage N-1 → Stage N-2 → ... → Stage 1

<div class="identity-box">
<strong>Finite Repetition Result</strong>: The only subgame perfect equilibrium is <em>(Defect, Defect)</em> in every single round.
</div>

---

## A Glimpse of Hope

**The Key Insight**: The entire unraveling depends on **certainty about the end**.

**Remove the certainty** → **Prevent backward induction**

**Two Ways to Eliminate the End**:
1. **Infinitely repeated games**: No final round exists
2. **Unknown termination**: Players don't know when the game ends

**The Result**: The incentive to build reputation and encourage future cooperation remains powerful because there's always a "next round" to consider.

**However**: This opens a complex world where almost anything can be justified as rational—the realm of the **Folk Theorem**.

---

## Discount Factors

**The Infinity Problem**: How do we compare infinite payoff streams?

Player 1 always defects: $4 + 4 + 4 + ... = \infty$
Player 1 always cooperates: $1 + 1 + 1 + ... = \infty$

**Paradox**: Best and worst outcomes both equal infinity!

**Solution**: The **discount factor** $\delta$ where $0 < \delta < 1$

**Two Interpretations**:
1. **Time Value**: $3 today > $3 tomorrow (can invest, consume sooner)
2. **Continuation Probability**: $\delta =$ probability the game continues to next period

---

## How Discount Factors Work

**Infinite Cooperation Payoff**: $3 + 3\delta + 3\delta^2 + 3\delta^3 + ...$

**Period-by-Period Breakdown**:
- **Period 1 (Today)**: Value = 3 (no discounting)
- **Period 2 (Tomorrow)**: Value = $3\delta$ 
- **Period 3**: Value = $3\delta^2$ (discounted twice)
- **Period t**: Value = $3\delta^{t-1}$

**Key Rule**: The exponent on $\delta$ is always one less than the period number.

**Interpretation of $\delta$ Values**:
- **High $\delta$ (close to 1)**: Patient player, future matters greatly
- **Low $\delta$ (close to 0)**: Impatient player, present dominates

---

## Geometric Series

**The Challenge**: Calculate $X + X\delta + X\delta^2 + X\delta^3 + ...$

**Step 1 - Finite Series**: $S = X + X\delta + X\delta^2 + ... + X\delta^{n-1}$

**Step 2 - The Magic Trick**:
- Original: $S = X + X\delta + X\delta^2 + ... + X\delta^{n-1}$
- Multiply by $\delta$: $\delta S = X\delta + X\delta^2 + ... + X\delta^{n-1} + X\delta^n$
- Subtract: $S - \delta S = X - X\delta^n$
- Factor: $S(1-\delta) = X(1-\delta^n)$
- Solve: $S = \frac{X(1-\delta^n)}{1-\delta}$

---

## From Finite to Infinite

**Taking the Limit**: As $n \to \infty$, what happens to $\delta^n$?

**Example with $\delta = 1/2$**:
- $(1/2)^1 = 1/2 = 0.5$
- $(1/2)^2 = 1/4 = 0.25$ 
- $(1/2)^3 = 1/8 = 0.125$
- $(1/2)^{10} = 1/1024 ≈ 0.001$
- As $n \to \infty$: $\delta^n \to 0$

<div class="identity-box">
<strong>Infinite Geometric Series Formula</strong>: $X + X\delta + X\delta^2 + ... = \frac{X}{1-\delta}$
</div>

**We've tamed infinity!** The "dot dot dot" becomes a simple, finite value.

---

## One-Shot Deviation Principle

**The Exponential Strategy Problem**: In a 16-decision game:
- 1 decision → 2 strategies
- 2 decisions → 4 strategies  
- 3 decisions → 8 strategies
- 16 decisions → 65,536 strategies!

**Traditional Approach**: To prove a strategy is optimal, check it against all 65,535 alternatives. **Impossible!**

**One-Shot Deviation Principle**: A strategy is a subgame perfect equilibrium **if and only if** no player can profitably deviate at a single stage while maintaining their strategy everywhere else.

---

## How the Principle Works

**The "Obvious" Part**: If a strategy is truly optimal, it must beat any single-change alternative.

**The "Powerful" Part**: If you can't improve by changing one decision, you can't improve by changing multiple decisions.

**Why?** Any complex, profitable multi-stage deviation must contain at least one "pivotal" stage that alone provides improvement.

**Practical Benefit**:
- **Without principle**: Check 65,535 alternatives
- **With principle**: Check only 16 one-shot deviations

**Result**: Transform an impossible task into a manageable one!

---

## Grim Trigger Strategy

**The Unforgiving Rule**: 
*"If anyone has defected at any point previously, defect forever. Otherwise, cooperate."*

**Two Simple Rules**:
1. **Start by cooperating** (offer initial trust)
2. **Permanent punishment** for any defection (no forgiveness, ever)

**Two Possible Paths**:
- **Cooperation Path**: Both cooperate → steady payoff of 3 each round
- **Punishment Path**: Someone defects → mutual defection forever (payoff 2)

**Why "Bloodthirsty"?** A single mistake triggers permanent conflict.

---

## The Trade-Off in Grim Trigger

**The Choice**: Stick to cooperation or grab a short-term gain?

**Option A - Cooperate**: Steady payoff stream of $3, 3, 3, 3, ...$

**Option B - Defect Once**:
- **Today**: Get 4 instead of 3 (temptation payoff)
- **Forever After**: Stuck with 2 in all future rounds (punishment)
- **Payoff Stream**: $4, 2, 2, 2, ...$

**When Does Cooperation Work?**
- Present value of cooperation: $\frac{3}{1-\delta}$
- Present value of defection: $4 + \frac{2\delta}{1-\delta}$
- **Cooperation condition**: $\frac{3}{1-\delta} \geq 4 + \frac{2\delta}{1-\delta}$
- **Simplifies to**: $\delta \geq \frac{1}{2}$

---

## Tit-for-Tat Strategy

**The "Nice" Alternative**: A forgiving strategy that doesn't hold grudges forever.

**Two Simple Rules**:
1. **Start by cooperating** (be nice first)
2. **Copy opponent's last move** (forgive quickly, but retaliate immediately)

**On Equilibrium Path**: 
- Round 1: Both cooperate
- Round 2: Both cooperate (copying each other)
- Forever: Mutual cooperation with payoff (3, 3)

**Off Equilibrium Path** (after one defection):
- Creates alternating pattern: Cooperate, Defect, Cooperate, Defect, ...
- **Payoff streams**: $4, 1, 4, 1, ...$ vs. steady $3, 3, 3, ...$

---

## Tit-for-Tat's Success

**Robert Axelrod's Computer Tournaments**: Tit-for-Tat consistently performed well against complex strategies submitted by experts.

**Why It Works**:
- **Simple**: Easy to understand and implement
- **Nice**: Starts with cooperation and forgives quickly  
- **Retaliatory**: Punishes defection immediately
- **Forgiving**: Returns to cooperation after one round of punishment

**The Trade-Off**: Cooperation $(3, 3, 3, ...)$ vs. Alternating $(4, 1, 4, 1, ...)$

**Condition for Cooperation**: Same as Grim Trigger in this example: $\delta \geq \frac{1}{2}$

---

## The Credibility Problem

**The Fatal Flaw**: Tit-for-Tat's threat isn't actually credible!

**After Opponent Defects, You Face**:
- **Option A (Punish)**: Defect → payoff stream $4, 1, 4, 1, ...$
- **Option B (Forgive)**: Cooperate → return to payoff stream $3, 3, 3, ...$

**The Contradiction**:
- **To cooperate initially**: Need $\delta \geq \frac{1}{2}$ (future matters enough)
- **To punish credibly**: Need $\delta \leq \frac{1}{2}$ (prefer alternating to steady 3s)

**Knife-Edge Condition**: Only works if $\delta = \frac{1}{2}$ exactly!

<div class="identity-box">
<strong>Result</strong>: Tit-for-Tat is a Nash Equilibrium but <em>not</em> a Subgame Perfect Equilibrium (except at the knife-edge).
</div>

---

## Folk Theorem

**The Big Idea**: In infinitely repeated games with patient players, almost any reasonable outcome can be sustained as an equilibrium.

**Formal Statement**: Any outcome that gives all players payoffs **strictly better** than their punishment payoff can be supported as a subgame perfect equilibrium.

**Why "Folk"?** The theorem emerged simultaneously from the "folklore" of game theory—many theorists discovered it around the same time.

**The Mechanism**: 
1. **Agreement**: Players commit to a specific strategy profile
2. **Temptation**: Players always face short-term gains from deviating  
3. **Punishment**: Any deviation triggers permanent reversion to Nash equilibrium

---

## Beyond Simple Cooperation

**Example of Complex Equilibrium**:
- Player 1: Cooperate 100% of the time
- Player 2: Cooperate 95% of the time, defect 5% of the time

**Why This Works**: 
- Both players still get expected payoffs > 2 (punishment level)
- Any deviation triggers permanent mutual defection (payoff = 2 forever)
- As long as players are patient enough, they won't risk losing the good deal

**The Explosion**: There are **infinitely many equilibria** in infinitely repeated games!

**Key Condition**: Players must be "sufficiently patient" (high enough $\delta$).

---

## The Prediction Problem

**The Challenge**: When everything is possible, nothing is predictable.

**Example**: Imagine observing this 8-period sequence:
1. Mutual Cooperation  
2. Mutual Defection
3. Mutual Defection
4. (Defect, Cooperate)
5. Mutual Cooperation
6. Mutual Cooperation  
7. (Defect, Cooperate)
8. (Cooperate, Defect)

**Seemingly Random?** The Folk Theorem shows this can be a rational equilibrium!

---

## The Chaotic Equilibrium Explained

**The Strategy**:
1. **Periods 1-8**: Follow the exact prescribed sequence
2. **Period 9 onward**: Cooperate forever
3. **Punishment**: Any deviation triggers defection forever

**Why It Works**: 
- The value of infinite future cooperation (payoff 3 forever) vastly outweighs any finite sequence of strange payoffs
- For patient players, any 8-period "cost" becomes irrelevant compared to infinite future benefits

**The Problem**: If **any** observed behavior can be explained as rational, our theory "predicts everything and therefore predicts nothing."
