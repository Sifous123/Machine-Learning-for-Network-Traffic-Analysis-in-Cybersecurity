# Machine-Learning-for-Network-Traffic-Analysis-in-Cybersecurity
An end-to-end Machine Learning pipeline designed for Security Operations Centers. This project analyzes network traffic flows to detect modern cyber threats (DDoS, Botnets, Web Attacks) while focusing on Operational Robustness, Alert Fatigue reduction, and Explainable AI (XAI).


## Key Features
*   **OS-Agnostic Data Pipeline:** Utilizes `pathlib` for seamless cross-platform dataset loading.
*   **Feature Engineering:** Extracts top 15 network behaviors using Random Forest Gini Impurity.
*   **Time-Aware Detection:** Implements rolling time-windows (50-flow aggregations) to successfully track DDoS/Botnet attack rhythms.
*   **Explainable AI (SHAP):** Unboxes the Random Forest model using Game Theory (SHAP TreeExplainer) to provide local explanations for SOC analysts.
*   **Red Teaming / Adversarial ML:** Evaluates model fragility against Evasion Attacks (Timing noise & Packet padding).

## Prerequisites
*   Python 3.11+

## Dataset Setup
Due to size constraints, the dataset is not hosted in this repository. 

1. Download the **CIC-IDS2017 Intrusion Detection Evaluation Dataset** from the official Canadian Institute for Cybersecurity website.
   https://www.unb.ca/cic/datasets/ids-2017.html 
2. Create a directory named `TrafficLabelling` in the root folder of this project.
3. Place all extracted CSV files inside the `TrafficLabelling` folder. The `pathlib` configuration will automatically locate and process them.

## Results & Explainability
The Random Forest model achieved a **Weighted F1-Score of 99.71%**. To build analyst trust, SHAP values are integrated to explain specific alerts, mapping variables like *Packet Length Variance* to malicious intent.
