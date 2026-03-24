# IsingMarketDynamics
Agent-based simulation of financial markets using the Ising model to study herding behavior, volatility clustering, and crash sensitivity near criticality.
# Ising Model for Financial Market Dynamics

## Overview
Financial markets exhibit complex collective behavior that cannot be explained by purely random models. Empirical data shows **volatility clustering**, **fat tails**, and **sudden crashes**—all suggesting strong interaction between agents.

This project models financial markets using a **2D Ising model**, where:
- Each spin represents a trader (buy/sell)
- Local interactions model **herding behavior**
- Temperature controls randomness vs. coordination
- External fields simulate **market shocks (news/events)**

The goal is to test whether **critical phenomena** in statistical physics can explain **market instability and crash dynamics**.

---

## Key Questions
- Do markets exhibit **maximum instability near critical temperature**?
- Can small external shocks trigger **large-scale coordination (crashes)**?
- Does herding behavior explain **volatility clustering**?

---

## Model

### Trader Representation
- Spin \( s{i,j} \in \{-1, +1\} \)
  - +1 → Buy
  - -1 → Sell

### Hamiltonian
- \( J = 1 \): herding strength  
- \( h \): external field (market shock)

---

## Simulation Details

| Parameter | Value |
|----------|------|
| Grid Size | 20 × 20 (400 traders) |
| Critical Temp \(T_c\) | 2.269 |
| Replicates | 5 |
| Equilibration | 50 steps |
| Production Run | 200 steps |

- Dynamics: **Metropolis algorithm**
- Boundary: periodic

---

## Financial Interpretation

| Physics Quantity | Financial Meaning |
|----------------|------------------|
| Magnetization \(M(t)\) | Market sentiment |
| Returns \(r(t)\) | Price change |
| Volatility \(σ_r\) | Market instability |
| Susceptibility \(χ\) | Systemic risk |

---

## Results

### 1. Phase Transition Validation
- Magnetization drops sharply near \(T_c\)
- Energy increases smoothly
- Confirms correct implementation

---

### 2. Market Dynamics at Criticality
- Returns show **spikes and clustering**
- Large fluctuations emerge without external forcing
- Mimics real financial time series behavior

---

### 3. Volatility Behavior
- Volatility increases with temperature
- No sharp peak at \(T_c\) due to:
  - Finite system size
  - Limited simulation length

---

### 4. External Shock Sensitivity (Key Result)

**Most important finding:**

> Near-critical markets are highly sensitive to small shocks.

- At \(T = T_c\):
  - Small field \(h = 0.5\) → full market coordination
- Away from \(T_c\):
  - Larger shocks required for same effect

This mirrors real-world crashes where:
- Small triggers → massive coordinated reactions

---

## Example Outputs

- Spin configurations across temperatures
- Magnetization time series
- Return (volatility) series
- Susceptibility vs temperature
- External field response grids

---

## Installation

```bash
git clone https://github.com/yourusername/ising-market-dynamics.git
cd ising-market-dynamics
pip install numpy matplotlib scipy
