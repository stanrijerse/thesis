# Spiking Predictive Control of a Spring-Mass-Damper Notebooks

This folder contains the simulation notebooks supporting the thesis *"Influence
of Noise in Predictive Spiking Control Networks."* They build up the predictive
spiking controller (after Agliati et al., 2025) in stages, from the bare plant
to the full noisy closed-loop model, then benchmark it against an LQR baseline
and a Kalman-filtered variant.


## Notebooks, in reading order

| # | Notebook | Purpose |
|---|----------|---------|
| 1 | `OU_process.ipynb` | Standalone Ornstein-Uhlenbeck process demo (reference noise model). |
| 2 | `Spring-mass-dampener_without_control.ipynb` | Open-loop plant, no input, no noise. |
| 3 | `Spring-mass-dampener_with_noise.ipynb` | Open-loop plant with process noise only, no control. |
| 4 | `Spring-mass-dampener_with_spikes.ipynb` | Hand-placed open-loop spikes, illustrating the effect of B. |
| 5 | `Spring-mass-dampener_with_control.ipynb` | Deterministic closed-loop spiking controller, no noise. |
| 6 | `Spring-mass-dampener_with_control_and_noise.ipynb` | Adds σ_m/σ_v/σ_p. |
| 7 | `Spring-mass-dampener_with_control_and_noise_voltageIntegration.ipynb` | Full model: drive is a leaky-integrated voltage with spike reset. Includes an interactive slider explorer. |
| 8 | `Spring-mass-dampener_pointSimulation.ipynb` | Monte-Carlo rollout from a fixed branch point.|
| 9 | `Spring-mass-dampener_LQR_non-spikes.ipynb` | Continuous LQR baseline under the same noise model. |
| 10 | `Spring-mass-dampener_Kalman_Filter.ipynb` | Full model with a Kalman filter estimating state before it drives the controller. |

Notebook 1 is the earliest exploratory work, 2 to 4 are open-loop groundwork on
the plant itself, 5 to 8 build the spiking controller, 9 and 10 are baselines and
comparison.

## Dependencies

```
numpy, scipy, matplotlib, filterpy, ipywidgets
```
