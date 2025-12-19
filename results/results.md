# Results Summary

This document reports the evaluation results of the **Human-in-the-Loop Reinforcement Learning (HITL-RL)** system for clinical decision support.

The agent is trained using PPO with:
- a **true dynamical environment** (actions affect future state),
- **preference-based reward learning** (Bradley–Terry model),
- and a **Lagrangian constraint** to regulate intervention frequency.

---

## Evaluation Protocol

- **Deterministic**: policy uses argmax action (greedy clinician).
- **Stochastic**: actions sampled from policy distribution (realistic uncertainty).
- Metrics are averaged over held-out patient episodes.

---

## Validation Set

### Deterministic Policy
- **Mean Return**: 11.04 ± 24.47  
- **Mean Episode Length**: 16.5  
- **In-Range Ratio**: 49.61%  
- **Intervention Rate**: 64.37%

### Stochastic Policy
- **Mean Return**: 6.60 ± 25.25  
- **Mean Episode Length**: 12.0  
- **In-Range Ratio**: 33.14%  
- **Intervention Rate**: 78.85%

---

## Test Set

### Deterministic Policy
- **Mean Return**: 7.98 ± 16.57  
- **Mean Episode Length**: 12.9  
- **In-Range Ratio**: 40.93%  
- **Intervention Rate**: 68.39%

### Stochastic Policy
- **Mean Return**: 14.01 ± 18.55  
- **Mean Episode Length**: 19.5  
- **In-Range Ratio**: 59.69%  
- **Intervention Rate**: 54.18%

---

## Key Observations

- The agent avoids degenerate behaviors (0% or 100% intervention).
- Human preferences shape a **clinically conservative policy**.
- Stochastic evaluation often yields better stability under noise.
- The intervention-rate constraint meaningfully affects behavior.

---

## Conclusion

This project demonstrates that **human-in-the-loop reinforcement learning**
can produce stable, interpretable policies for clinical decision support,
balancing safety (in-range control) and action cost (interventions).

The framework is modular and extensible to other clinical signals or expert definitions.
