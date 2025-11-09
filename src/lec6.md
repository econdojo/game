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

1. [Finite Repeated Games](#finite-repeated-games)
2. [Infinite Repeated Games](#a-glimpse-of-hope)
3. [Grim Trigger Strategy](#grim-trigger-strategy)
4. [Tit-for-Tat Strategy](#tit-for-tat-strategy)
5. [Folk Theorem](#folk-theorem)

---

## Finite Repeated Games

If we play the Prisoner's Dilemma repeatedly, surely the shadow of the future will encourage cooperation?

<table>
<tr><th></th><th>Cooperate</th><th>Defect</th></tr>
<tr><th>Cooperate</th><td>3, 3</td><td>1, 4</td></tr>
<tr><th>Defect</th><td>4, 1</td><td>2, 2</td></tr>
</table>

In any **finitely repeated** game where the end is known, backward induction destroys all hope of cooperation

**Why?** Players can build trust, signal intentions, and seek rewards/punishments—but a cold, backward-flowing logic prevents cooperation when the end is certain

---

## Backward Induction

**Final Round N**: All previous payoffs are locked in. Players must play the one-shot Nash Equilibrium (Defect, Defect) with payoffs (2, 2)

**Round N-1**: Players know the final round outcome is predetermined as mutual defection
- Known future: Final round will be (Defect, Defect) regardless
- Empty promise: Cooperating now cannot influence future behavior  
- Inevitable choice: This round becomes strategically identical to a one-shot game

**Unstoppable collapse**: This logic continues backward through every round:
- Stage N → Stage N-1 → Stage N-2 → ... → Stage 1
- The only subgame perfect equilibrium is (Defect, Defect) in every single round

---

## A Glimpse of Hope

The entire unraveling depends on certainty about the end. Two ways to eliminate the end → prevent backward induction:

1. **Infinitely repeated games**: No final round exists
2. **Unknown termination**: Players don't know when the game ends

**Result**: The incentive to build reputation and encourage future cooperation remains powerful because there's always a "next round" to consider

**Folk Theorem**: This opens a complex world where almost anything can be justified as rational

---

## Discount Factors

How do we compare infinite payoff streams?

- Player 1 always defects: $4 + 4 + 4 + ... = \infty$
- Player 1 always cooperates: $1 + 1 + 1 + ... = \infty$
- Paradox: Best and worst outcomes both equal infinity!

**Solution**: The discount factor $\delta$ where $0 < \delta < 1$. Two interpretations:

1. Time value: $3 today > $3 tomorrow (can invest, consume sooner)
2. Continuation probability: $\delta =$ probability the game continues to next period

**Infinite cooperation payoff**: $3 + 3\delta + 3\delta^2 + 3\delta^3 + ...$

- High $\delta$ (close to 1) = Patient player
- Low $\delta$ (close to 0) = Impatient player

---

## Geometric Series

How to calculate $X + X\delta + X\delta^2 + X\delta^3 + ...$

**Magic trick**:
- Finite series: $S = X + X\delta + X\delta^2 + ... + X\delta^{n-1}$
- Multiply by $\delta$: $\delta S = X\delta + X\delta^2 + ... + X\delta^{n-1} + X\delta^n$
- Subtract: $S - \delta S = X - X\delta^n$ → $S = \frac{X(1-\delta^n)}{1-\delta}$
- As $n \to \infty$, $\delta^n \to 0$

**Infinite series formula**: $X + X\delta + X\delta^2 + ... = \frac{X}{1-\delta}$

---

## One-Shot Deviation Principle

In a 16-decision game, there are 65,536 possible strategies! Traditional approach: check against all 65,535 alternatives

**One-shot deviation principle**: A strategy is a subgame perfect equilibrium if and only if no player can profitably deviate at a single stage while maintaining their strategy everywhere else. Why It Works?
- If a strategy is truly optimal, it must beat any single-change alternative
- If you can't improve by changing one decision, you can't improve by changing multiple decisions

**Benefit**: Without principle → Check 65,535 alternatives; With principle → Check only 16 one-shot deviations. Transform an impossible task into a manageable one!

---

## Grim Trigger Strategy

**Unforgiving rule**: If anyone has defected at any point previously, defect forever. Otherwise, cooperate. Two simple rules:
1. Start by cooperating (offer initial trust)
2. Permanent punishment for any defection (no forgiveness, ever)

**Two possible paths**: Cooperation path (steady payoff of 3) vs. Punishment path (mutual defection: 4, 2, 2, 2, ...)
- Present value of cooperation: $\frac{3}{1-\delta}$
- Present value of defection: $4 + \frac{2\delta}{1-\delta}$
- Cooperation condition: $\frac{3}{1-\delta} \geq 4 + \frac{2\delta}{1-\delta}$ → $\delta \geq \frac{1}{2}$

**Remark**: Cooperation requires sufficient patience ($\delta \geq 1/2$). If players are too impatient (low $\delta$), the immediate temptation payoff outweighs future punishment, and defection becomes rational

---

## Grim Trigger Is Self-Enforcing

Grim Trigger is not an imposed rule—it's a **voluntary strategy** that rational players choose because it's in their self-interest:

- No external enforcement needed—players follow it because deviation makes them worse off
- It's a Subgame Perfect Equilibrium with **credible** threats (when δ ≥ 1/2): Once in punishment phase, continuing to defect is optimal

**Bottom line**: Grim Trigger works precisely because rational players commit to it knowing that both cooperation and punishment are self-enforcing

---

## US Dollar As Reserve Currency

**Players**: United States and other countries holding dollar reserves

- Cooperation path: US maintains sound monetary policy; other countries hold dollar reserves → Global financial stability, low transaction costs, US seigniorage benefits (payoff: 3, 3)

- Temptation to defect: US prints money excessively, inflates away debt; other countries diversify reserves early to avoid dollar devaluation risk (payoff: 4 today)

**Grim Trigger punishment**: Permanent loss of dollar dominance → US loses seigniorage benefits, higher borrowing costs forever; global financial instability (payoff: 2, 2, 2, ...)

**Self-enforcing strategy**: No treaty needed—Both sides value long-term cooperation over short-term gains when patient ($\delta \geq 1/2$)

---

## Tit-for-Tat Strategy

A forgiving strategy that doesn't hold grudges forever. Two simple rules:
1. Start by cooperating (be nice first)
2. Copy opponent's last move (forgive quickly, but retaliate immediately)

**Trade-off**: Cooperation $(3, 3, 3, ...)$ vs. Alternating $(4, 1, 4, 1, ...)$ after defection

**Cooperation condition**: $\delta \geq \frac{1}{2}$ (same as Grim Trigger)

**Credibility problem**: Tit-for-Tat's threat isn't credible! After opponent defects:
- Punish: Defect → $(4, 1, 4, 1, ...)$ vs. Forgive: Cooperate → $(3, 3, 3, ...)$
- To cooperate initially: Need $\delta \geq 1/2$; To punish credibly: Need $\delta \leq 1/2$
- Nash equilibrium but not subgame perfect equilibrium (except at $\delta = 1/2$)

---

## Folk Theorem

In infinitely repeated games, any outcome that gives all players payoffs strictly better than their punishment payoff can be supported as a subgame perfect equilibrium. The mechanism includes:

1. Agreement: Players commit to a specific strategy profile 
2. Punishment: Any deviation triggers permanent reversion to Nash equilibrium

**Generalized Grim Trigger**:
- Player 1: Cooperate 100% of the time → Expected payoff: 2.85
- Player 2: Cooperate 95% of the time, defect 5% → Expected payoff: 3.15
- Both payoffs > 2 (punishment level), so both accept this asymmetric deal

**Infinitely many equilibria**: As long as players are patient enough (high $\delta$), they won't risk losing any arrangement that beats permanent punishment

---

## Prediction Problem

**Challenge**: When everything is possible, nothing is predictable

**Example**:
- Imagine observing this 4-period sequence: 1. Mutual Cooperation → 2. Mutual Defection → 3. Mutual Defection → 4. (Defect, Cooperate)
- Strategy: Follow the prescribed periods 1-4, then cooperate forever; Any deviation triggers permanent defection
- Seemingly random? Folk Theorem shows this can be a rational equilibrium!

**Insight**: The value of infinite future cooperation vastly outweighs any finite sequence of strange payoffs. For patient players, any 4-period "cost" becomes irrelevant compared to infinite future benefits
