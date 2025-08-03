# Problem Statement
Floods in India affect over 75 million people annually, causing major disruptions to life, agriculture, and infrastructure. Existing systems are disjointed, post-event, and not interpretable by field workers or local agencies.
# Our Solution
We propose a real-time, explainable flood monitoring system, combining:
- Rainfall Triggers using CHIRPS
- Satellite Detection via Sentinel-1 SAR & Sentinel-2 NDWI
- Historical Validation using India Flood Inventory (IFI)
- Human-Readable Alerts using Flan-T5 LLM

This is more than flood mapping. It’s a decision-support system for local governments and emergency response teams.
Technical Components
Literature Review & Gap
Component	Dataset/Technique
Flood Mapping	Sentinel-1 SAR, Sentinel-2 NDWI
Historical Validation	India Flood Inventory (IFI)
Rainfall Trigger	CHIRPS dataset
Communication	LLM-based Alerts (Flan-T5)
Gap Identified: No system in India combines all the above in a single, real-time, interpretable platform.
# System Architecture
Key Modules:
1. Rainfall Trigger: Uses CHIRPS to activate pipeline during heavy rainfall.
2. Satellite Fusion: Combines Sentinel-1 SAR (cloud-proof) & Sentinel-2 NDWI for accurate flood detection.
3. Historical Validation: Matches detections with IFI data (1967–2023) & estimates affected populations using WorldPop.
4. LLM Alerts: Auto-generates district-wise alerts like: "Patna is 42% flooded; 15,200 people at risk."
5. Dashboard: Interactive flood maps, rainfall visualizations, and alert reports.
# Dataset Summary
- CHIRPS: Global Rainfall Data
- Sentinel-1 & Sentinel-2: SAR + Optical Imagery
- IFI (India Flood Inventory): Historical Flood Records
- WorldPop: Population Exposure Estimation
# Evaluation Metrics
Metric	Module	Purpose
IoU	Satellite Mask	Accuracy of flood map vs. IFI
Precision/Recall	Detection	Flood vs non-flood performance
BLEU/ROUGE	LLM Output	Fluency & accuracy of alerts
Time-to-Alert	Pipeline	Responsiveness during real events
# Deliverables
- Flood Mapping Pipeline (Google Earth Engine + Python)
- Rainfall-Triggered Detection (CHIRPS-based)
- IFI Validation and Exposure Estimation
- LLM-Based Alert Generation (Flan-T5 / GPT)
- Dashboard Interface (map, alerts, export options)
- Full Codebase + Documentation
# Future Scope
- Integrate WhatsApp/Twitter/Email alert dissemination
- Add live sensor feeds (e.g., river gauges, weather stations)
- Deploy in a disaster response testbed with a real-time API
# References
•	India Flood Inventory (Saharia et al., 2021):
https://doi.org/10.1007/s11069-021-04698-6

•	District-Level Flood Index (Baishya et al., 2024):
https://arxiv.org/abs/2405.01602

•	Sen2FloodNet Paper (MDPI, 2022):
https://www.mdpi.com/2072-4292/14/2/428

•	CHIRPS Dataset - UCSB:
https://www.chc.ucsb.edu/data/chirps

•	Flan-T5 - Google Research (2022):
https://arxiv.org/abs/2210.11416
