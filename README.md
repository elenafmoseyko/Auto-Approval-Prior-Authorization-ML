🐾 Healthy Pets Auto-Approval Machine Learning Model
Overview
This project aims to reduce the operational burden and delays associated with manual review of prior authorization requests in the pet insurance domain. Healthy Pets receives thousands of such requests from veterinarians, some of which are currently processed through rule-based systems, while others require manual intervention. This machine learning model provides a data-driven approach to predict which requests can be confidently auto-approved.

📌 Objective
Develop and deploy a classification model to:

Predict if a prior authorization (PA) request should be auto-approved.

Complement existing rule-based logic.

Reduce manual workload while maintaining clinical safety and appropriateness.

📊 Data Exploration & Insights
Key insights from exploratory analysis:

72.5% of PA requests were approved.

Approval likelihood increases for routine procedures (e.g., check-ups).

Time since last claim/auth, provider history, and pet service history significantly influence approval chances.

Cold cases (long gaps in prior history) are less likely to be approved.

🧠 Modeling Approach
Three classification models were evaluated:

Logistic Regression

Random Forest

XGBoost

After tuning and performance evaluation, Random Forest was selected due to:

Strong F1 score (0.873)

High interpretability via feature importance

Feature Engineering Highlights:
Prior approvals and claims history

Provider and service-specific patterns

Time-based features (e.g., time since last claim)

📈 Evaluation
The model outputs probabilities which allow threshold tuning:

Threshold	Precision	Recall	F1 Score	Auto-Approval Rate
0.47 (Balanced)	88%	86%	0.87	~74%
0.90 (Conservative)	98%	42%	0.58	~29%

✅ Recommendations
Initial Deployment: Use threshold = 0.90 for conservative rollout.

Monitoring: Track performance metrics (precision, recall, approval rate) continuously.

Human Oversight: Manually review all non-auto-approved requests.

Pilot First: Begin with select providers/services before scaling.

Retraining: Incorporate feedback loops and periodic model updates.
