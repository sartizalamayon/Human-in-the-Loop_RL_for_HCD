# Human-in-the-Loop Reinforcement Learning for Clinical Decision Support

This project implements a **human-in-the-loop reinforcement learning (HITL-RL)** framework for clinical decision support, where an agent learns **when to intervene** to keep a physiological signal within a clinically defined normal range.

The system combines:
- a **dynamical environment** (actions affect future state),
- **preference-based reward learning** from expert (rule-based) feedback,
- and **constrained PPO** using a Lagrangian penalty to regulate intervention frequency.

Human expertise is incorporated through **pairwise trajectory preferences**, enabling the agent to learn clinically meaningful behavior beyond handcrafted rewards.

## Results (Summary)

| Split | Policy | In-Range Ratio | Intervention Rate |
|------|--------|---------------|-------------------|
| Validation | Deterministic | 49.6% | 64.4% |
| Test | Deterministic | 40.9% | 68.4% |
| Validation | Stochastic | 33.1% | 78.9% |
| Test | Stochastic | 59.7% | 54.2% |

The learned policy avoids degenerate behavior (0% or 100% intervention) and demonstrates stable, interpretable decision-making under uncertainty.

## Repository Structure
notebooks/ # main experiment and analysis
models/ # trained models (SB3 / Torch / ONNX)
results/ # evaluation summaries (MD / PDF)
images/ # figures and visualizations


## Key Contributions
- Human feedback via **preference learning (Bradley–Terry)**
- **Constrained RL** to control intervention rate
- Clinically interpretable evaluation metrics

This project demonstrates how **human knowledge and reinforcement learning** can be combined for safe, data-driven clinical decision support.

---


