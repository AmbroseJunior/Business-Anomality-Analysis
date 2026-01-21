Anomaly Detection in Financial Order-to-Cash Processes

Process Mining & Machine Learning

📌 Project Overview

This project focuses on detecting anomalous customer orders within a financial order-to-cash (O2C) process using process mining and machine learning techniques.

Each invoice represents a customer order (case), and each transaction line represents an event in the process. The goal is to identify irregular, risky, or unusual process executions that are not visible through traditional reporting.

The analysis combines event-level process understanding with case-level behavioral modeling to provide explainable, data-driven anomaly detection.

🎯 Business Problem

Organizations handling large volumes of financial transactions often face challenges such as:

Undetected financial irregularities

Unusual customer order behavior

Manual, rule-based fraud detection that does not scale

Limited visibility into how and why anomalies occur

The dataset does not contain labeled anomalies, making supervised classification impractical. Therefore, an unsupervised, process-aware approach is required.

🧠 Methodology
1️⃣ Event Log Construction

Raw transactional data was transformed into an event log

Each Invoice = Case

Each transaction line = Event

Events ordered by timestamp to reflect the true execution flow

2️⃣ Feature Engineering (Process-Aware)

Case-level features were engineered to capture behavioral characteristics:

Case duration (start → end time)

Number of events per case

Total order value

Total quantity

Number of unique products

Composite process risk score

These features combine time, structure, and financial impact.

3️⃣ Process Mining

Using process mining principles:

Event ordering and case boundaries were validated

Execution patterns and variants were explored

Process behavior was analyzed beyond flat transactional summaries

4️⃣ Machine Learning (Unsupervised)

Because no labels were available:

Isolation Forest was used to detect anomalous cases

K-Means clustering was applied to group orders by behavioral similarity

A percentile-based threshold (95th percentile) was used for interpretability

5️⃣ Visualization & Interpretation

Multiple visual techniques were used:

Risk-ranking line charts

Scatter plots (time vs value)

Heatmaps for process behavior density

Cluster profile comparisons

These ensured that anomalies were explainable, not just flagged.

📊 Key Results & Insights

Approximately 5% of customer orders were identified as anomalous

Extreme financial values (very high or negative order values) were the strongest anomaly drivers

Processing time alone was not sufficient to explain anomalies

Anomalous cases clustered into distinct behavioral groups, enabling prioritization

The approach significantly improved interpretability compared to raw transaction analysis

💼 Business Value

Early identification of financial and operational risks

Supports audit, fraud detection, and compliance

Reduces dependency on manual rules

Enables targeted investigation of high-risk orders

Scalable and adaptable to other transactional processes

🛠️ Tools & Technologies

Python (Pandas, NumPy)

Process Mining: pm4py

Machine Learning: Scikit-learn (Isolation Forest, K-Means)

Visualization: Matplotlib, Seaborn

Environment: Google Colab

📌 Conclusion

This project demonstrates how combining process mining with unsupervised machine learning enables explainable, scalable anomaly detection in real-world financial processes. The methodology is applicable across domains such as finance, logistics, CRM systems, and enterprise operations.
