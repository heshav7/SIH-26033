# Smart India Hackathon Workshop
# Date:23/11/2026
## Reference Number:26016672
## Name:R.M.Heshav

## Problem Title
SIH 26033: Multiple intermediaries reduce farmers' earnings and increase consumer prices. Organization: Ministry of Consumer Affairs, Food & Public Distribution Theme: Agriculture, FoodTech & Rural Development

## Problem Creater's Organization
Ministry of Consumer Affairs, Food & Public Distribution

## Theme
Agriculture, FoodTech & Rural Development

## Problem Description
Expected Solution: Create a digital marketplace that:

• Connects farmers/FPOs directly with consumers and bulk buyers.
• Provides logistics support.
• Uses AI for demand forecasting and route optimization.

Benefits:

• Better prices for farmers.
• Lower prices for consumers.
• Reduced supply chain inefficiencies.

## Proposed Solution
Remove These Lines
1. Detailed explanation of the proposed solution
2. How it addresses the problem
3. Innovation and uniqueness of the solution

## Technical Approach
•	Frontend: React Native (farmer and buyer apps, offline-first), React web portal and policy dashboard.
•	Backend: Python (FastAPI) microservices, PostgreSQL + PostGIS, Redis, REST APIs.
•	Price Chain Tracker: rules engine for cost components (transport, handling, fees, taxes), with data ingestion pipelines for mandi and retail prices.
•	Fair-Price AI: gradient-boosted models (XGBoost/LightGBM) for price bands; Prophet/LSTM for price and demand forecasting; SHAP for explanations.
•	Markup Detector: anomaly detection (isolation forest) and price-spread analysis by crop, route and district.
•	Routing: Google OR-Tools (vehicle routing with capacity and time windows), OpenStreetMap/Google Maps APIs.
•	Data sources: Agmarknet/e-NAM, IMD weather, crop calendars, platform order history.
•	Dashboards: React charts or Apache Superset/Grafana for the heat-map.
•	Payments and comms: UPI/escrow, SMS/WhatsApp/IVR, speech-to-text for regional languages.
•	Infra: Cloud (AWS/GCP/Azure), Docker, CI/CD, role-based access, encryption.
2. Methodology and process
Flow:
1.	Collect mandi, retail, transport and weather data into the Price Chain Tracker
2.	Fair-Price AI generates a fair-price band for each crop and location
3.	Farmer/FPO sees the minimum fair price and publishes produce
4.	Buyer sees the maximum fair price and orders directly
5.	Route optimizer pools pickups and plans delivery; payment is held in escrow
6.	Delivery is confirmed, farmer is paid within 24–48 hours, and the itemised bill is generated
7.	Order data flows back into the Markup Detector and retrains the models

<img width="900" height="856" alt="image" src="https://github.com/user-attachments/assets/6430c0b7-fc6d-4617-81f9-8ca67c2a5dda" />
Implementation phases:
•	Phase 1 (prototype): price data ingestion, rule-based itemised breakdown, simple fair-price band, price comparison screen, one-district demo.
•	Phase 2: ML fair-price model with explanations, direct ordering with escrow, route optimization, FPO dashboards.
•	Phase 3: markup heat-map for policymakers, demand forecasting, multi-district scale-up, ONDC integration.
For the PPT, add: (a) the flow chart above, (b) a system architecture diagram, (c) screenshots of the price-breakdown screen, the farmer fair-price screen and the markup dashboard

## Feasibility and Viability
1. Feasibility analysis
•	Technical: the price breakdown is arithmetic plus standard ML on public price data, so a working prototype is realistic within the hackathon.
•	Data: Agmarknet/e-NAM and weather data are public; transport and handling rates can start from standard rates and improve with real orders.
•	Operational: FPOs and existing transporters supply aggregation and delivery; the engine is the software layer on top.
•	Economic: a small platform fee plus logistics fee, funded by pooled transport savings and lower wastage. Numbers to be validated in a pilot.
•	Policy fit: supports the ministry's price-monitoring work and complements e-NAM and ONDC.
2. Challenges and risks
•	Incomplete or disputed cost data for transport and handling.
•	Fair-price models can be wrong where data is thin or prices swing quickly.
•	Retail price data is hard to collect consistently.
•	Farmers or buyers may bypass the platform after the first match.
•	Low digital literacy and weak connectivity in villages.
•	Resistance from existing traders.
3. Strategies to overcome
•	Start with standard rates and partner-verified costs, then refine with real orders.
•	Show the fair price as a band with a confidence indicator and the factors behind it; keep FPO review in the loop; start with a few high-volume crops.
•	Combine crowdsourced retail prices, partner stores and official data.
•	Keep users on the platform with escrow, fast payment, ratings and a sales history that helps with credit.
•	Voice UI, IVR/SMS fallback, offline mode, FPO/CSC-assisted onboarding.
•	Invite traders to act as logistics or aggregation partners instead of excluding them.

## Impact and Benefits
1. Potential impact on target audience•	Farmers/FPOs: know a fair price before selling, keep a larger share, get paid faster.
•	Consumers: see why they pay what they pay and can buy at lower, fairer prices.
•	Bulk buyers: predictable pricing and supply.
•	Government: real-time evidence of where price gaps arise, to target policy.
2. Benefits
•	Economic: higher farmer income, lower consumer prices, less value lost to hidden margins.
•	Social: trust and fairness in agri-trade; empowers FPOs and small farmers; digital inclusion.
•	Environmental: less wastage and fewer wasted transport trips through pooled, optimized routes.
•	Governance: data-driven monitoring of price spreads across crops and districts

## Research and References
•	e-NAM (National Agriculture Market): https://enam.gov.in
•	Agmarknet (mandi price data): https://agmarknet.gov.in
•	ONDC (Open Network for Digital Commerce): https://ondc.org
•	Ministry of Consumer Affairs, Food & Public Distribution (price monitoring): https://consumeraffairs.nic.in
•	Google OR-Tools, vehicle routing: https://developers.google.com/optimization/routing
•	Prophet forecasting library: https://facebook.github.io/prophet/
•	SHAP (explainable ML): https://shap.readthedocs.io
•	NABARD / SFAC material on FPOs: https://www.nabard.org and https://sfacindia.com
•	Add: any studies on farmer price share and price spreads that you cite, with link and year.
Note: statistics (e.g., farmer's share of consumer price) are intentionally left out; add verified figures with sources before submission.
