# SEIQR-model
This repository contains a Python implementation of the SEIQR model with Monte Carlo simulations to analyze the spread of a hypothetical Mpox outbreak under different intervention scenarios. The model incorporates parameters for disease natural history, isolation strategies, and outbreak discovery timing.

## Introduction

This project uses a modified SEIQR (Susceptible-Exposed-Infected-Quarantined-Recovered) model to simulate the dynamics of a Mpox outbreak. Key features include:

- Monte Carlo simulations to account for parameter uncertainty
- Multiple intervention scenarios based on outbreak discovery timing
- Visualization of daily new cases and cumulative infections
- Statistical analysis of results with 95% confidence intervals
- Outputs in both graphical and Excel formats

## Data

The simulation relies on:

1. **Natural history parameters** (e.g., 潜伏期，传染期，隔离率) derived from literature

2. Model inputs   :

   - Population size (N=300,000,000)
   - Initial conditions (I0=1, E0=0, R0=0, Q0=0)
   - Intervention timing (discovery_days = [24, 29, 34, 39 days])

3. Output data  :

   - Daily new cases (mean ± 95% CI)
   - Cumulative cases before/after intervention (with CI)
   - Excel file containing raw simulation results

## Code

### Requirements

- Python 3.7

- Required libraries:

- ```python
  pip install numpy matplotlib scipy pandas
  ```

  ### Key Components

  1. **SEIQR Model**:

     - Differential equations defining disease progression
     - Time-dependent isolation rate after outbreak discovery
     - Monte Carlo sampling for parameter uncertainty

  2. **Simulation Parameters**:

     ```python
     N = 300000000  # Population size
     R0_range = (1.78, 2.69)  # Basic reproduction number range
     time_steps = 80  # Simulation duration (days)
     ```

     1. **Output Generation**:
        - Line charts with confidence intervals
        - Excel file with simulation results per scenario
        - Bar chart overlay for actual case data (example included)

     ## Run

     ### Instructions

     1. **Adjust Parameters**:

        - Modify `discovery_days` in the code to test different intervention timings
        - Update isolation rates (`isolation_rate`, `enhanced_isolation_rate`)
        - Adjust simulation parameters (e.g., `num_simulations`, `R0_range`)

     2. **Execute**:

        ```python
        python mpox_simulation.py
        ```

        3.**Outputs**:

        - Interactive matplotlib chart showing daily cases and intervention impacts
        - Excel file (`simulation_results2.xlsx`) with raw data and CI calculations

        ### Notes

        - The code uses hard-coded paths for Excel output. Update `excel_path` in the code to your desired location.
        - The visualization includes example actual case data (bars) that can be replaced with real-world data.

        For parameter references and model assumptions, consult relevant epidemiology literature on Mpox transmission dynamics.

