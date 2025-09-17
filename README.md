# Fuzzy Expert System for Spare Parts Service Center
---

## Overview
This repository contains a **Fuzzy Expert System** that models the operation of a spare parts service center. It manages the service center and recommends the number of spare parts based on factors such as **mean delay**, **number of servers**, and **utilisation factor**. The system demonstrates handling uncertainty in expert systems using fuzzy logic. It is based on **Section 4.7** of the textbook and encodes expert knowledge for practical decision making.

## Features
- Define linguistic variables and fuzzy sets for inputs and outputs  
- Construct fuzzy rules covering all input combinations  
- Encode fuzzy sets and rules into a fuzzy expert system  
- Evaluate system with multiple test cases  
- Generate 3D visualizations to analyze input-output relationships  
- Demonstrate uncertainty handling in fuzzy expert systems  


## Linguistic Variables and Fuzzy Sets

**Inputs:**  
- Mean Delay: Very Short, Short, Medium  
- Servers: Small, Medium, Large  
- Utilisation Factor: Low, Medium, High  

**Output:**  
- Spares: Very Small, Small, Rather Small, Medium, Rather Large, Large, Very Large  

---

## Fuzzy Rules

**Examples of implemented rules:**  
- If `utilisation_factor` is Low → `spares` are Small  
- If `mean_delay` is Very Short and `servers` are Small → `spares` are Very Large  
- If `mean_delay` is Very Short and `servers` are Large → `spares` are Medium  
- If `mean_delay` is Medium and `servers` are Large → `spares` are Very Small  

(All 12 rules covering all combinations of inputs are implemented.)

---

## System Implementation Steps

1. Define linguistic variables and fuzzy sets using `skfuzzy.control.Antecedent` and `skfuzzy.control.Consequent`  
2. Construct fuzzy rules with `skfuzzy.control.Rule`  
3. Create the fuzzy control system with `skfuzzy.control.ControlSystem`  
4. Evaluate the system using `ControlSystemSimulation` by providing input values  
5. Visualize outputs with 3D surface plots using Matplotlib  
6. Test multiple input cases and analyze uncertainty using Mamdani defuzzification  

---

## Test Cases

| Case | Mean Delay | Servers | Utilisation Factor | Recommended Spares |
|------|------------|--------|------------------|------------------|
| 1    | 0.2        | 0.2    | 0.3              | 0.51             |
| 2    | 0.5        | 0.5    | 0.5              | 0.37             |
| 3    | 0.8        | 0.8    | 0.9              | 0.54             |

### Uncertainty Explanation
- Fuzzy outputs reflect overlaps in categories (e.g., "Very Small" vs "Small")  
- Defuzzification converts fuzzy outputs into actionable numerical recommendations

