---
marp: true
math: mathjax
theme: default
size: 4:3
paginate: true
backgroundColor: '#f4f6fa'
backgroundImage: url('https://marp.app/assets/hero-background.svg')
header: 'Lecture 5: Expected Utility Theory'
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

# Lecture 5: Expected Utility Theory

**Instructor:** Fei Tan

<img src="images/github.png" width="30" height="30" class="logo"> @econdojo &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/youtube.png" width="30" height="30" class="logo"> @BusinessSchool101 &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/slu.png" width="30" height="30" class="logo"> Saint Louis University

**Date:** October 28, 2025

---

## The Road Ahead

1. [From Preferences to Utilities](#why-numbers-matter-in-game-theory)
2. [Axioms of Rational Choice](#axioms-of-rational-choice)
3. [Utility Transformations](#utility-transformations)

---

## Why Numbers Matter in Game Theory

**Challenge**: Describing preferences with words is messy and hard to analyze. Consider four possible outcomes:
- Outcome 3: "I love this"
- Outcome 1: "I like this" 
- Outcome 4: "meh"
- Outcome 2: "This is worse than death"

Problems with descriptive language:
- Becomes an "absolute mess to memorize"
- Impossible to manage with many or infinite outcomes
- Cannot perform mathematical analysis

**Solution**: Use numerical utilities to represent preferences cleanly and compactly

---

## From Preferences to Utilities

**Utilities** are a numerical system to represent rank-ordered preferences → Larger numbers = better outcomes, smaller numbers = worse outcomes

<table>
<tr>
<th>Preference Description</th>
<th>Assigned Utility</th>
</tr>
<tr>
<td>I love outcome 3</td>
<td>0</td>
</tr>
<tr>
<td>I like outcome 1</td>
<td>-1</td>
</tr>
<tr>
<td>Outcome 4 is meh</td>
<td>-8</td>
</tr>
<tr>
<td>Outcome 2 is worse than death</td>
<td>-10</td>
</tr>
</table>

**Insight**: Numbers instantly capture rank ordering: 0 > -1 > -8 > -10

---

## Preferences Come First

No one thinks in numbers. We don't care about utilities themselves, we care about what they represent

**The one-way street**: Preferences map to utilities, not the other way around

1. You have preferences over outcomes (this comes first)
2. We assign utility numbers to represent those preferences
3. Higher utility numbers don't cause preferences - preferences cause higher utility numbers

**Example**: In modeling international conflict, we first understand what outcomes leaders prefer, then construct utilities to represent those preferences

---

## Axioms of Rational Choice

To predict behavior in strategic situations, we need rules governing preferences. Expected utility theory rests on **four key axioms**:

1. **Completeness**: For any two outcomes, you can state a preference
2. **Transitivity**: Preferences are logically consistent 
3. **Independence**: Common components in lotteries don't affect choice
4. **Continuity**: No sudden jumps in preferences

These axioms form the logical bedrock of game theory by ensuring preferences can be represented with utility numbers that allow mathematical analysis.

---

## Completeness Axiom

For any two outcomes X and Y, you must be able to state your preference

**Three possibilities**:
1. Prefer X to Y
2. Prefer Y to X  
3. Be indifferent between X and Y

**Example:** $1 million, $0, and painful death. Typical preference ordering:
- $1 million > $0
- $0 > Painful death  
- $1 million > Painful death

**Key point**: Completeness is about having **any** preference, not a "sensible" one

---

## Transitivity Axiom

If X is preferred to Y and Y is preferred to Z, then X must be preferred to Z → Mathematical analogy: If A > B and B > C, then A > C

**Example**: Million dollars vs. $0 vs. dying
1. Prefer $1M to $0 (X > Y)
2. Prefer $0 to dying (Y > Z)
3. Must prefer $1M to dying (X > Z)

Transitivity works with indifference too:
- If indifferent between $1M and $0, and between $0 and dying
- Then must be indifferent between $1M and dying
- Transitivity: If A = B and B = C, then A = C

**Key point**: Transitivity eliminates illogical preference cycles

---

## Rationality

**Everyday rationality**: Making sensible, logical choices

**Game theory rationality**: Having preferences that are complete and transitive

<table>
<tr>
<th>Everyday Rationality</th>
<th>Game Theory Rationality</th>
</tr>
<tr>
<td>Judges content of preferences</td>
<td>Only cares about structure</td>
</tr>
<tr>
<td>Subjective assessment of wisdom</td>
<td>Mechanical check of consistency</td>
</tr>
<tr>
<td>"Is this choice sensible?"</td>
<td>"Can you compare outcomes consistently?"</td>
</tr>
</table>

**Insight**: A preference for dying over $1 million can be **rational** (if complete and transitive) even if not **sensible**

---

## Dealing with Uncertainty: Lotteries

**Lottery**: A probability distribution over outcomes. Why it matters:
- Mixed strategies create uncertainty for opponents
- Many real-world situations involve risk
- Need to compare certain outcomes with uncertain ones

**Example**:
- Option A: Get $0 for certain
- Option B: 50% chance of $1M, 50% chance of death

**Key question**: How do we compare these options rationally? → Expected utility theory provides the framework for consistent choice under uncertainty

---

## Independence Axiom

When comparing lotteries, identical components should not affect your choice → If you prefer X to Y, then you should prefer:
- [X with probability p, Z with probability (1-p)] to
- [Y with probability p, Z with probability (1-p)]

**Example**:
- Lottery 1: 50% chance $1M, 50% chance death
- Lottery 2: 50% chance $0, 50% chance death

**Analysis**: The 50% chance of death is common to both → ignore it and focus on the difference: Do you prefer $1M or $0? If you prefer $1M, then choose Lottery 1

**Key point**: Independence enables consistent decision-making under uncertainty

---

## Allais Paradox

**Choice 1**: A vs. B
- **A**: 11% chance of $1M, 89% chance of $0
- **B**: 10% chance of $5M, 90% chance of $0

**Choice 2**: C vs. D  
- **C**: 100% chance of $1M
- **D**: 10% chance of $5M, 89% chance of $1M, 1% chance of $0

**Paradox**: Many people choose B and C, violating independence
- Both choices reduce to the same core decision
- Prefer certain $1M when certainty available (C over D)
- Prefer risky $5M gamble when risk unavoidable (B over A)

**Psychological insight**: "Certainty effect" - people overweight guaranteed outcomes

---

## Continuity Axiom

For any three ranked outcomes (best, middle, worst), there exists a probability that makes you indifferent between the middle outcome for certain and a lottery on the best and worst

**Example**: 
- Best: $1 million
- Middle: $0  
- Worst: Painful death

What probability p makes you indifferent between:
- Getting $0 for certain
- p chance of $1M, (1-p) chance of death

**Key point**: As long as such a probability exists (even if p = 0.9999999), your preferences satisfy continuity → continuity rules out lexicographic preferences with infinite jumps

---

## Utility Transformations

Utility numbers are representations, not absolute values. Consider **positive affine transformation**: $u' = au + b$ where $a > 0$

**Example**: Original Stag Hunt game

<table>
<tr>
<th></th>
<th>Player 2: Stag</th>
<th>Player 2: Hare</th>
</tr>
<tr>
<th>Player 1: Stag</th>
<td>3, 3</td>
<td>1, 2</td>
</tr>
<tr>
<th>Player 1: Hare</th>
<td>2, 1</td>
<td>0, 0</td>
</tr>
</table>

Transformed game (multiply Player 1's payoffs by 2):

<table>
<tr>
<th></th>
<th>Player 2: Stag</th>
<th>Player 2: Hare</th>
</tr>
<tr>
<th>Player 1: Stag</th>
<td>6, 3</td>
<td>2, 2</td>
</tr>
<tr>
<th>Player 1: Hare</th>
<td>4, 1</td>
<td>0, 0</td>
</tr>
</table>

**Key point**: Identical equilibria because preference ordering preserved

---

## Rules for Valid Transformations

**Three fundamental rules**:

1. Use positive affine transformations only: $u' = au + b$ with $a > 0$
   - Never use $a ≤ 0$ (reverses or eliminates preferences)
   - Avoid squaring, cubing, or other nonlinear transformations

2. Apply consistently within player: Same $a$ and $b$ for all payoffs of one player

3. Players can be transformed independently: 
   - Player 1: $a = 2, b = 0$
   - Player 2: $a = 1, b = -1$ 
   - Or leave one player unchanged

**Bottom line**: Preserve preference ordering, maintain strategic equivalence

---

## Pareto Efficiency

An outcome is Pareto efficient if there is no other outcome that makes at least one player better off without making any other player worse off

**Example**: Battle of the Sexes

<table>
<tr>
<th></th>
<th>Player 2: Ballet</th>
<th>Player 2: Fight</th>
</tr>
<tr>
<th>Player 1: Ballet</th>
<td>1, 2</td>
<td>0, 0</td>
</tr>
<tr>
<th>Player 1: Fight</th>
<td>0, 0</td>
<td>100, 1</td>
</tr>
</table>

Player 1's payoffs ÷ 100:
<table>
<tr>
<th></th>
<th>Player 2: Ballet</th>
<th>Player 2: Fight</th>
</tr>
<tr>
<th>Player 1: Ballet</th>
<td>0.01, 2</td>
<td>0, 0</td>
</tr>
<tr>
<th>Player 1: Fight</th>
<td>0, 0</td>
<td>1, 1</td>
</tr>
</table>

**Key point**: Sum of interpersonal utilities gives opposite conclusions, yet both are the same game!

---

## Pareto Efficiency in Stag Hunt

<table>
<tr>
<th></th>
<th>Player 2: Stag</th>
<th>Player 2: Hare</th>
</tr>
<tr>
<th>Player 1: Stag</th>
<td>3, 3</td>
<td>0, 1</td>
</tr>
<tr>
<th>Player 1: Hare</th>
<td>1, 0</td>
<td>1, 1</td>
</tr>
</table>

- **Pareto efficient**: (Stag, Stag) only
- **Pareto inefficient**: All other outcomes
- From (Hare, Hare), both players can improve by moving to (Stag, Stag)

---

## Pareto Efficiency in Prisoner's Dilemma

<table>
<tr>
<th></th>
<th>Player 2: Cooperate</th>
<th>Player 2: Defect</th>
</tr>
<tr>
<th>Player 1: Cooperate</th>
<td>3, 3</td>
<td>1, 4</td>
</tr>
<tr>
<th>Player 1: Defect</th>
<td>4, 1</td>
<td>2, 2</td>
</tr>
</table>

The unique equilibrium (Defect, Defect) is the only inefficient outcome!

Pareto efficient outcomes:
- (Cooperate, Cooperate) - both can improve from equilibrium
- (Cooperate, Defect) and (Defect, Cooperate) - can't help one without hurting the other

**Key lesson**: Equilibrium doesn't guarantee efficiency

---

## Risk Preferences

Choose between:
- Lottery 1: 50% chance of $1,000,000, 50% chance of $0
- Lottery 2: Guaranteed payment of $X

Expected value of Lottery 1: (0.5 × $1,000,000) + (0.5 × $0) = $500,000

**Question**: For what value of $X are you indifferent? Your answer reveals your risk preference:
- **Risk-averse**: $X < $500,000 (prefer certainty)
- **Risk-neutral**: $X = $500,000
- **Risk-acceptant**: $X > $500,000 (prefer the gamble)

---

## Utility Functions

**Mathematical representation**: $U(x) = x^a$

**Risk-neutral** ($a = 1$): $U(x) = x$ 
- Linear relationship between money and utility
- Each dollar provides same additional happiness

**Risk-averse** ($0 < a < 1$): $U(x) = x^{0.5}$ (square root)
- Diminishing marginal utility
- Each additional dollar provides less happiness

**Risk-acceptant** ($a > 1$): $U(x) = x^2$
- Increasing marginal utility  
- Each additional dollar provides more happiness
