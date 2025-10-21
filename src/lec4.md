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

1. [Infinite Strategy Spaces](#infinite-strategy-spaces)
2. [Hotelling's Game](#hotellings-game)
3. [Cournot Duopolistic Competition](#cournot-duopolistic-competition)
4. [Second Price Auctions](#second-price-auctions)

---

## Infinite Strategy Spaces

So far all games had **finite** number of pure strategies represented by matrices or game trees, but many strategic situations involve **infinite** strategy choices:
- Firms choosing production levels (any real number ≥ 0)
- Politicians choosing policy positions (continuum of possibilities)
- Auction bidders choosing bid amounts (any positive value)
- Pricing decisions (continuous price range)

**New challenge**: Matrices and trees become impractical with infinite strategies. How to find equilibria without drawing payoff matrices?

---

## Games Without Payoff Matrices

**Game definition** remains the same:
- Set of players
- Strategy spaces (now possibly infinite)
- Order of moves
- Payoff functions

**Solution method** for infinite games:
1. Consider a single pure strategy from one player
2. Find the other player's best responses to that strategy
3. Check whether the original strategy is a best response to any of those best responses
4. If yes → equilibrium found; if no → try next strategy
5. Repeat for all strategies

**Advantage**: No need to draw massive (impossible) matrices!

---

## Example: Simple Infinite Game

Players 1 and 2 simultaneously select whole numbers between 1 and 100. Each player's payoff = product of the two numbers

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

**Nash's theorem**: Every **finite** game has at least one Nash equilibrium. **Infinite** games may have no equilibrium!

**Counter-example**: Players select any number > 0, payoff = product of numbers

- Suppose Player 1 chooses any value x > 0
- Player 2's best response: choose something slightly larger than x
- But then Player 1 wants to choose something even larger
- Result: No equilibrium exists (infinite regress)

---

## Hotelling's Game

**Harold Hotelling's 1929 model**: Two ice cream vendors on a beach

- Beach stretches from position 0 to position 1
- Customers evenly distributed along the beach
- Two vendors sell identical ice cream for $2 per cone
- Customers buy from nearest vendor (travel cost consideration)
- Vendors simultaneously choose locations

**Strategy space**: Each vendor chooses position x ∈ [0, 1]

**Key constraint**: Each vendor must serve exactly half the customers in equilibrium: EU₁ ≥ 1/2, EU₂ ≥ 1/2, and EU₁ + EU₂ = 1

---

## Equilibrium Analysis

Why vendors can't be equidistant from center (1/2):
- Suppose vendors at positions 1/4 and 3/4
- Vendor at 1/4 could move to 1/2: keeps left customers + steals some right customers
- This gives more than half the business → profitable deviation

Why both vendors must choose the same location:
- If both choose same position ≠ 1/2 (say both at 1/4)
- One vendor could deviate to position 1/2 → get all customers on far side plus some customers near original position
- Again a profitable deviation

**Unique equilibrium**: Both vendors locate at position 1/2 (center)
- Any deviation from center gives less than half the business
- No profitable deviations exist

---

## Median Voter Theorem

**Hotelling's game in politics**: Presidential candidates as "vendors," voters as "customers":
- Two candidates choose policy positions on left-right spectrum
- Voters distributed along this spectrum with single-peaked preferences
- Each voter supports candidate closest to their ideal position
- Candidates want to maximize vote share

**Key insight**: Both candidates will converge to the **median voter's position**

---

## Cournot Duopolistic Competition

**Antoine Augustin Cournot's model**: Firms compete over **quantities** produced

- Two firms simultaneously choose production quantities: q₁, q₂ ≥ 0
- Market price determined by demand: P = 900 - (q₁ + q₂)
- Firm 1's production cost: $12 per unit
- Firm 2's production cost: $24 per unit
- Each firm maximizes profit

**Strategy space**: Each firm chooses q ∈ [0, ∞)

---

## Equilibrium Analysis

**Solution algorithm**:
1. Profit functions: EU₁ = 888q₁ - q₁² - q₁q₂, EU₂ = 876q₂ - q₁q₂ - q₂²
2. Best responses (partial derivatives): q₁ = 444 - q₂/2, q₂ = 438 - q₁/2  
3. Solve system: Substitute to get q₂ = 438 - (444 - q₂/2)/2 = 216 + q₂/4

**Equilibrium outcome**:
- Firm 1: 300 units, Firm 2: 288 units, Market price: $312
- Lower-cost firm (Firm 1) produces more and gains larger market share

---

## Second Price Auctions

$n$ bidders compete for a single item
- Each bidder $i$ has private valuation $v_i$ for the item
- Sealed bid auction: highest bidder wins, pays **second-highest bid**
- Strategy space: Each bidder chooses bid $b_i \in [0, \infty)$

**Payoff function**: 
$$\text{Payoff}_i = \begin{cases} 
v_i - \text{(second highest bid)} & \text{if bidder } i \text{ wins} \\
0 & \text{if bidder } i \text{ loses}
\end{cases}$$

**Example**: Albert bids $10, Barbara bids $13, Charlie bids $0.13, Fei bids $30; Fei wins but pays $13

**Question**: What is the optimal bidding strategy?

---

## Equilibrium Analysis

**Theorem**: Bidding your true valuation ($b_i = v_i$) is a **dominant strategy**

**Proof**: Consider any honest bidder $i$ with $b_i=v_i$

Case 1 - Your bid wins: 
- You pay the second-highest bid
- Increase bid? Still win and pay same amount
- Decrease bid? Either still win and pay same amount or lose and get nothing

Case 2 - Your bid loses: 
- Increase bid? Either still lose or win but pay more than valuation
- Decrease bid? Still lose and receive nothing

**Conclusion**: No profitable deviation → Truth-telling is optimal regardless of others' strategies