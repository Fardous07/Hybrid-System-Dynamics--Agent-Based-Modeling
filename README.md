# 🏘️ Hybrid SD-ABM Model for Housing-Related Health Disparities

This project implements a **hybrid System Dynamics (SD)** and **Agent-Based Modeling (ABM)** framework to explore how housing conditions, socioeconomic disparities, and climate change interact to influence population health outcomes. Built in Python, the model supports scenario analysis and policy evaluation.

---

## 📌 Overview

The model simulates the interplay between:

- Housing quality degradation and improvement
- Environmental and climate-related changes
- Health outcomes influenced by air quality and healthcare access
- Socioeconomic behaviors and policy responses

---

## ⚙️ Model Components

### 1. System Dynamics (SD) Module

Captures macro-level trends:
- **Housing Quality**: Degrades over time; improved via investments
- **Air Quality**: Degrades with poor housing and climate change
- **Disease Prevalence**: Increases with poor air and limited healthcare
- **Climate Change**: Gradually worsens environmental conditions

**Key Equations:**
- `Climate Impact = Climate Change Rate × (1 - Housing Quality)`
- Poor housing & climate → lower air quality
- Poor air & access → higher disease prevalence

---

### 2. Agent-Based Modeling (ABM) Module

Simulates individual households and decision-making:

**Household Attributes:**
- Income level
- Education level

**Behaviors:**
- Invest 1–2% of income when health risk is high
- Adapt to conditions: higher income/education → more investment

**Other Agent Types:**
- **Policy Actors**: Intervene when average health drops below 0.3

---

## 🔁 Model Integration

- **SD → ABM**: Macro variables (e.g., disease, air quality) influence agent decisions
- **ABM → SD**: Aggregated actions (e.g., housing investment) update macro states

---

## 🧩 Key Features

- **Parameter realism**:
  - Housing deterioration: 0.5%/time step
  - Climate change: 1–5% annually
  - Healthcare access baseline: 50%

- **Policy Interventions**:
  - Triggered when avg. health < 0.3
  - Improve healthcare access under budget constraints

---

## 🛠 Implementation Details

- **Language**: Python 3.x  
- **Dependencies**:
  - [`Mesa`](https://mesa.readthedocs.io/) – Agent-Based Modeling
  - `NumPy`, `Pandas` – Data handling
  - `Matplotlib` – Visualization

- **Architecture**: Object-oriented with separate classes for SD, ABM, and integration

---

## 📊 Model Parameters

| Parameter                   | Description                    | Default | Range      |
|----------------------------|--------------------------------|---------|------------|
| `climate_change_rate`      | Annual climate deterioration   | `0.02`  | `0.01–0.05` |
| `healthcare_access`        | Baseline healthcare coverage   | `0.5`   | `0–1`       |
| `housing_deterioration_rate` | Annual housing quality decline | `0.005` | `0–0.01`    |
| `housing_improvement_factor` | Investment effectiveness       | `0.05`  | `0–0.1`     |

---

## 📈 Output Metrics

### System-Level Metrics
- **Average Population Health**: Tracks the overall health status of the population.
- **Housing Quality Index**: Measures the quality of housing conditions.
- **Air Quality Index**: Assesses the air quality affecting the population.
- **Disease Prevalence**: Monitors the prevalence of diseases influenced by environmental factors.

### Agent-Level Metrics
- **Individual Health Status**: Represents the health status of each household agent.
- **Housing Investment Levels**: Records the cumulative investments made by households in housing improvements.
- **Income and Education Distributions**: Analyzes the distribution of income and education levels among households.

## 🧠 Applications
- **Evaluate Policy Interventions for Health Equity**: Test and analyze the impact of different health policies.
- **Test Housing Improvement Programs**: Assess the effectiveness of initiatives aimed at improving housing conditions.
- **Assess Climate Change Adaptation Strategies**: Evaluate strategies to mitigate the health impacts of climate change.
- **Identify Vulnerable Populations**: Determine which groups are most at risk based on socioeconomic factors.

## 🔮 Future Extensions
- **Spatial Modeling**: Incorporate geographic distribution of households to better understand regional dynamics.
- **Climate Modeling**: Integrate region-specific climate projections to enhance model accuracy.
- **Economic Dynamics**: Model changes in income over time to reflect economic realities.
- **Validation**: Calibrate the model using real-world health and housing data to ensure its reliability and effectiveness.
