# HydroRoute
Lightweight, data-integrated rain navigation matrix featuring a 15-minute transactional decay filter engine to mitigate crowdsourced data spam.
# ⛈️ HydroRoute: Advanced Rain Navigation Matrix
### Data-Integrated Crowdsourced Hazard Core with 15-Min Temporal Expiration Engine

**Live Application URL:** http://15.252.243.168:8501  
**Target Region:** Delhi-NCR (Ghaziabad Core — Vasundhara, Indirapuram, Anand Vihar)  
**Track:** Heat and Water (Water stagnation, monsoon flooding, and pothole route navigation)

---

## 💡 Core Architecture Strategy
HydroRoute shifts navigation infrastructure from passive mapping to active, automated community safety. During intense monsoons, traditional mapping tools completely overlook immediate local hazards like deep submerged potholes or knee-deep flash flooding. 

### ⏱️ The 15-Minute Self-Cleaning Anti-Spam Engine
The primary flaw of typical crowdsourced tools is data integrity—stale listings, false inputs, or malicious spam rendering maps useless. 
**HydroRoute solves this via a strict temporal decay layout:**
* Every user report is ingested as a distinct transactional `datetime` object.
* The processing engine constantly checks timestamps against live server telemetry.
* If a reported road block is not actively re-verified by incoming traffic within **15 minutes**, the status instantly transitions to `Expired` and is automatically purged from the client canvas.

---

## 🛠️ The Technical Stack
* **Web UI Processing:** Written completely in Python utilizing the Streamlit framework for clean, lightweight, frontend asset rendering.
* **Cloud Hosting Environment:** Deployed natively on an optimized **AWS EC2 (Elastic Compute Cloud) Linux instance** using Amazon Linux 2023.
* **Firewall Layer:** Restructured via custom inbound AWS Security Groups mapping traffic strictly across Custom TCP Port 8501.
* **Future Production Scale Roadmap:** Built intentionally to map directly into serverless architectures: `User Event` ➡️ `Amazon API Gateway` ➡️ `AWS Lambda Validation` ➡️ `Amazon DynamoDB` (utilizing native database Time-to-Live TTL parameters to mirror the 15-minute auto-deletion constraint).
