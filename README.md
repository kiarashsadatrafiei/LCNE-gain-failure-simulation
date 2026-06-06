# LC–NE Gain Failure Simulation

This repository contains the Python code and supplementary outputs for a formal model-behavior simulation accompanying a manuscript on locus coeruleus–norepinephrine (LC–NE) gain failure and cognitive-state instability in aging and Alzheimer’s disease.

The simulation illustrates the sign structure of the proposed cognitive-state stability model:

```text
S_cog(t) = alpha * G_LC(t) - beta * D_state(t) - gamma * V_arousal(t)
```

where:

- `S_cog(t)` is the cognitive-state stability margin.
- `G_LC(t)` is adaptive LC–NE gain.
- `D_state(t)` is neural state dispersion away from the task-relevant regime.
- `V_arousal(t)` is arousal volatility.

In this model, positive `S_cog(t)` indicates that the task-relevant cognitive regime remains stable. Values at or below zero indicate vulnerability to attentional lapse, distractor capture, state drift, failed encoding, unstable recall, or inefficient task switching.

## Simulated regimes

The code simulates four LC–NE gain-control regimes:

1. Healthy adaptive gain
2. Hypogain
3. Hypertonic noise
4. Gain mistiming

These regimes correspond to distinct proposed mechanisms of noradrenergic gain failure:

- Healthy adaptive gain: preserved, well-timed LC–NE gain stabilizes task-relevant states.
- Hypogain: weak phasic amplification fails to stabilize task-relevant states.
- Hypertonic noise: excessive or unstable tonic arousal increases state dispersion and distractor competition.
- Gain mistiming: LC–NE gain is present but delayed relative to task demand, creating transient instability.

## Analysis structure

The simulation includes:

- representative stability traces;
- cohort-level Monte Carlo simulation;
- simulated inter-individual variability;
- parameter-sensitivity analysis;
- pairwise robustness analysis of instability signatures.

The outputs include time-series figures, cohort-level metric distributions, model-component traces, sensitivity plots, and summary tables.

## Repository contents

```text
LCNE-gain-failure-simulation/
│
├── lcne_if10_simulation.py
├── requirements.txt
├── README.md
├── LICENSE
│
└── lcne_if10_outputs/
    ├── simulation_parameters.json
    │
    ├── figures/
    │   ├── FigS1_representative_stability_timeseries.png
    │   ├── FigS2_cohort_metric_distributions.png
    │   ├── FigS3_representative_model_components.png
    │   └── FigS4_sensitivity_and_rank_robustness.png
    │
    └── tables/
        ├── condition_level_summary.csv
        ├── cohort_subject_level_metrics.csv
        ├── representative_timeseries.csv
        ├── sensitivity_analysis_metrics.csv
        └── sensitivity_pairwise_rank_probabilities.csv
```

## How to run

Install dependencies:

```bash
pip install -r requirements.txt
```

or manually:

```bash
pip install numpy pandas matplotlib
```

Run the simulation:

```bash
python lcne_if10_simulation.py
```

The script generates outputs in:

```text
lcne_if10_outputs/
```

## Main outputs

The main generated figures are:

```text
lcne_if10_outputs/figures/FigS1_representative_stability_timeseries.png
lcne_if10_outputs/figures/FigS2_cohort_metric_distributions.png
lcne_if10_outputs/figures/FigS3_representative_model_components.png
lcne_if10_outputs/figures/FigS4_sensitivity_and_rank_robustness.png
```

The main generated tables are:

```text
lcne_if10_outputs/tables/condition_level_summary.csv
lcne_if10_outputs/tables/cohort_subject_level_metrics.csv
lcne_if10_outputs/tables/sensitivity_analysis_metrics.csv
lcne_if10_outputs/tables/sensitivity_pairwise_rank_probabilities.csv
```

## Interpretation

This simulation is intended as a formal model-behavior illustration. It is not patient-level empirical validation and does not estimate biological parameters from human or animal data. Its purpose is to show how distinct LC–NE gain-control regimes can generate separable instability signatures under the same stability-margin equation.

The simulation should therefore be interpreted as a supplementary formal analysis supporting the operational structure of the model, rather than as direct evidence for clinical diagnosis, prognosis, or treatment response.

## Citation and code availability

The Python code used for the supplementary model-behavior simulation, together with parameter files and generated summary outputs, is provided for transparency and reproducibility.

Repository:

```text
https://github.com/kiarashsadatrafiei/LCNE-gain-failure-simulation
```

## License

This repository is released under the MIT License.
