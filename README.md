# 🏘️ Hybrid SD-ABM Model for Housing-Related Health Disparities

## Overview
This project implements a hybrid System Dynamics (SD) and Agent-Based Modeling (ABM) framework to explore how housing conditions, socioeconomic disparities, and climate change interact to influence population health outcomes. Built in Python, the model supports scenario analysis and policy evaluation.

## 📌 Model Scope
The model simulates the interplay between:
- Housing quality degradation and improvement
- Environmental and climate-related changes
- Health outcomes influenced by air quality and healthcare access
- Socioeconomic behaviors and policy responses

## ⚙️ Model Components

### 1. Enhanced System Dynamics (SD) Module
Captures macro-level trends:
- **Housing Quality**: Degrades over time but can improve through investments.
- **Air Quality**: Affected by housing conditions and climate change.
- **Disease Prevalence**: Increases with poor air quality and limited healthcare access.
- **Climate Change**: Gradually worsens environmental conditions.

**Key Equations**:
- Climate Impact = Climate Change Rate × (1 - Housing Quality)
- Poor housing and climate → lower air quality
- Poor air quality and access → higher disease prevalence

### 2. Enhanced Agent-Based Modeling (ABM) Module
Simulates individual households and decision-making:
- **Household Attributes**:
  - Income level
  - Education level
  - Location type (urban or rural)

- **Behaviors**:
  - Invest 1–2% of income when health risk is high.
  - Adapt to conditions: higher income/education → more investment.

### 3. Policy Actor
- **Intervention Logic**: Implements health, housing, or environmental policies when average health drops below a certain threshold.

## 🔁 Model Integration
- **SD → ABM**: Macro variables (e.g., disease prevalence, air quality) influence agent decisions.
- **ABM → SD**: Aggregated actions (e.g., housing investment) update macro states.

## 🧩 Key Features
- **Parameter Realism**:
  - Housing deterioration: 0.5% per time step.
  - Climate change: 1–5% annually.
  - Healthcare access baseline: 50%.

- **Policy Interventions**:
  - Triggered when average health falls below 0.3.
  - Improve healthcare access under budget constraints.

## 🛠 Implementation Details
- **Language**: Python 3.x

### Dependencies:
- **Mesa**: Agent-Based Modeling framework
- **NumPy**: For numerical calculations
- **Pandas**: For data handling
- **Matplotlib** and **Seaborn**: For visualization
- **SciPy**: For statistical functions

### Architecture:
- Object-oriented design with separate classes for SD, ABM, and policy actors.

## 📊 Model Parameters

| Parameter                        | Description                                    | Default | Range         |
|----------------------------------|------------------------------------------------|---------|---------------|
| climate_change_rate              | Annual climate deterioration                    | 0.015   | 0.01–0.05     |
| healthcare_access                | Baseline healthcare coverage                    | 0.45    | 0–1           |
| base_housing_deterioration      | Annual housing quality decline                  | 0.008   | 0–0.01        |
| housing_improvement_factor       | Effectiveness of investments                     | 0.08    | 0–0.1         |

## 📈 Output Metrics

### System-Level Metrics
- **Average Population Health**: Tracks the overall health status of the population.
- **Housing Quality Index**: Measures the quality of housing conditions.
- **Air Quality Index**: Assesses the air quality affecting the population.
- **Disease Prevalence**: Monitors the prevalence of diseases influenced by environmental factors.
- **Healthcare Access**: Reflects the percentage of the population with access to healthcare services.

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

## 📊 Visualization
The model includes visualization functions to display results, such as:
- Average health status over time.
- Disease prevalence and housing quality metrics.
- Agent-level distributions of health and income.
