---
marp: true
math: mathjax
theme: default
size: 4:3
paginate: true
backgroundColor: '#f4f6fa'
backgroundImage: url('https://marp.app/assets/hero-background.svg')
header: 'Lecture 4: Games with Infinite Strategy Spaces'
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

# Lecture 4: Games with Infinite Strategy Spaces

**Instructor:** Fei Tan

<img src="images/github.png" width="30" height="30" class="logo"> @econdojo &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/youtube.png" width="30" height="30" class="logo"> @BusinessSchool101 &nbsp;&nbsp;&nbsp;&nbsp; <img src="images/slu.png" width="30" height="30" class="logo"> Saint Louis University

**Date:** September 25, 2025

---

## The Road Ahead

1. [Introduction to Infinite Strategy Spaces](#introduction)
2. [Games Without Payoff Matrices](#simple-infinite-games)
3. [Existence and Non-existence of Equilibria](#equilibrium-existence)
4. [Second Price Auctions](#second-price-auctions)
5. [The Median Voter Theorem](#median-voter-theorem)
6. [Applications and Extensions](#applications)

---

## Introduction to Infinite Strategy Spaces

**So far**: All games had **finite** number of pure strategies → could represent with matrices or game trees

**Reality**: Many strategic situations involve **infinite** strategy choices:
- Firms choosing production levels (any real number ≥ 0)
- Politicians choosing policy positions (continuum of possibilities)
- Auction bidders choosing bid amounts (any positive value)
- Pricing decisions (continuous price range)

**Key insight**: Matrices and trees become **impractical** or **impossible** with infinite strategies

**New challenge**: How to find equilibria without drawing payoff matrices?

---

## Games Without Payoff Matrices

**Game definition remains the same**:
- Set of players
- Strategy spaces (now possibly infinite)
- Order of moves
- Payoff functions

**New solution method** for infinite games:
1. Consider a single pure strategy from one player
2. Find the other player's best responses to that strategy
3. Check whether the original strategy is a best response to any of those best responses
4. If yes → equilibrium found; if no → try next strategy
5. Repeat for all strategies

**Advantage**: No need to draw massive (impossible) matrices!

---

## Example: Simple Infinite Game

**Setup**: Players 1 and 2 simultaneously select whole numbers between 1 and 100. Each player's payoff = product of the two numbers.

**Analysis using new method**:

**Step 1**: Suppose Player 2 chooses 1
- Player 1's payoff = x × 1 = x → best response: choose 100
- But Player 2's best response to 100 is 100 (not 1) → No equilibrium

**Step 2**: Suppose Player 2 chooses any k < 100
- Player 1's payoff = x × k → best response: choose 100
- But Player 2's best response to 100 is 100 (not k) → No equilibrium

**Step 3**: Suppose Player 2 chooses 100
- Player 1's payoff = x × 100 → best response: choose 100
- Player 2's best response to 100 is 100 ✓ → **Equilibrium: (100, 100)**

---

## Equilibrium Existence in Infinite Games

**Nash's theorem**: Every **finite** game has at least one Nash equilibrium

**Warning**: **Infinite** games may have **no equilibrium**!

**Counter-example**: Players select any number > 0, payoff = product of numbers

**Analysis**:
- Suppose Player 1 chooses any value x > 0
- Player 2's best response: choose something slightly larger than x
- But then Player 1 wants to choose something even larger
- **Result**: No equilibrium exists (infinite regress)

**Key lesson**: Existence theorems don't apply to infinite games

---

## When Do Infinite Games Have Equilibria?

**Sufficient conditions** for equilibrium existence:
1. **Bounded strategy spaces** (e.g., [0, 100] instead of all positive numbers)
2. **Continuous payoff functions**
3. **Compact strategy sets**
4. **Quasi-concave payoff functions**

**Example of bounded game**: Choose number in [1, 100]
- Upper bound prevents infinite regress
- Guarantees equilibrium exists

**Example without bounds**: Choose any positive number
- No upper limit → players keep trying to choose larger numbers
- No equilibrium possible

---

## Applications: Second Price Auctions

**Setup**: 
- n bidders compete for single item
- Each bidder has private valuation v_i for the item
- Sealed bid auction: highest bidder wins, pays **second-highest bid**

**Strategy space**: Each bidder chooses bid b_i ∈ [0, ∞)

**Payoff function**: 
- Winner: v_i - (second highest bid)  
- Losers: 0

**Key question**: What is the optimal bidding strategy?

---

## Second Price Auction Analysis

**Claim**: Bidding your true valuation (b_i = v_i) is a **dominant strategy**

**Proof idea**:
**Case 1**: Your bid wins
- You pay second-highest bid (independent of your exact bid)
- Bidding higher than v_i: same outcome, but risk paying more than value
- Bidding lower than v_i: might lose auction you could have won profitably

**Case 2**: Your bid loses  
- You pay 0 regardless of exact bid amount
- No incentive to deviate from truth-telling

**Result**: Truth-telling is optimal regardless of others' strategies → **dominant strategy equilibrium**

---

## Applications: The Median Voter Theorem

**Setup**: 
- Two candidates choose policy positions on a line (e.g., left-right spectrum)
- Voters distributed along this line with single-peaked preferences
- Each voter supports candidate closest to their ideal position
- Candidates want to maximize vote share

**Strategy space**: Choose any position x ∈ ℝ

**Key insight**: Both candidates will converge to the **median voter's position**

**Intuition**: 
- If you're away from median, opponent can move slightly toward median
- Opponent captures majority of voters between your positions
- Only stable outcome: both at median position

---

## Median Voter Theorem: Formal Analysis

**Assumptions**:
1. Voters have single-peaked preferences
2. Candidates care only about winning (not ideology)
3. Voters vote for candidate closest to their ideal point
4. Odd number of voters (to avoid ties)

**Equilibrium prediction**: Both candidates locate at median voter's ideal point

**Real-world implications**:
- Explains convergence to political center
- Why extreme candidates often lose general elections
- Strategic moderation in two-party systems

**Extensions**: Result may fail with multiple dimensions, strategic voting, or candidate ideology

---

## Summary: Key Insights

**Main takeaways from infinite strategy games**:

1. **Solution method**: Use best-response analysis instead of matrices
2. **Existence**: Infinite games may have no equilibrium (unlike finite games)
3. **Bounded sets**: Help guarantee equilibrium existence
4. **Dominant strategies**: Still powerful solution concept (second-price auctions)
5. **Convergence**: Competition can lead to clustering (median voter theorem)

**Applications beyond this lecture**:
- Cournot competition (firms choosing quantities)
- Bertrand competition (firms choosing prices)
- Public goods provision
- Arms races and conflict models

---

## Practice Problems

**Problem 1**: Two firms choose production levels x₁, x₂ ∈ [0, 10]. Profit functions: π₁ = x₁(12 - x₁ - x₂), π₂ = x₂(12 - x₁ - x₂). Find Nash equilibrium.

**Problem 2**: In a first-price auction (highest bidder wins and pays their bid), is truth-telling still optimal? Why or why not?

**Problem 3**: Consider median voter theorem with three candidates instead of two. What happens to the equilibrium prediction?

**Problem 4**: Players choose numbers in [0, 1]. Player 1's payoff = x₁ - x₁², Player 2's payoff = x₂ - 2x₁x₂. Find best responses and equilibrium.

---

## Takeaway Points

1. **Infinite strategy spaces require new solution methods beyond payoff matrices.**

2. **Nash's existence theorem doesn't apply to infinite games - equilibria may not exist.**

3. **Bounded strategy sets and continuous payoffs help ensure equilibrium existence.**

4. **Truth-telling is dominant in second-price auctions but not in first-price auctions.**

5. **The median voter theorem explains convergence to the center in two-candidate elections.**