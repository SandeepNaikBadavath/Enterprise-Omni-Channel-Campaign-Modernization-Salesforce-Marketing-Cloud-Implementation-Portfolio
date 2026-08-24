# Business Requirements Document (BRD)
**Project:** Omni-Channel Campaign Platform Modernization  
**Author:** Lead Business Analyst  
**Status:** Approved / Signed-Off  

## 1. Executive Summary & Problem Statement
The organization previously operated on decentralized, batch-dependent legacy marketing systems. Outbound voice, SMS, and email marketing operated in silos without real-time contact center visibility, leading to high opt-out rates, duplicated outreach, and manual list extracts vulnerable to data security risks.

## 2. Business Objectives & Success Metrics
* **Reduce Campaign Turnaround Time:** Cut campaign launch cycle from 10 days to under 24 hours.
* **Omni-Channel Synchronization:** Eliminate cross-channel message collisions across SFMC, NICE CXone, and IVR.
* **Compliance:** 100% adherence to TCPA quiet hours (8:00 AM – 9:00 PM recipient local time) and HIPAA consent rules.
* **Conversion Rate:** Increase preventive-care appointment bookings by 22% within 2 quarters.

## 3. Stakeholder Matrix & RACI
* **Executive Sponsor:** VP of Marketing & Customer Experience (Accountable)
* **Lead Business Analyst:** Requirement Elicitation, FRD/BRD, Data Mapping & UAT Lead (Responsible)
* **SFMC Technical Architect / Developers:** Platform Configuration & Integration (Responsible)
* **Contact Center Operations (NICE CXone Team):** Skill mapping & dialer queues (Consulted)
* **Information Security & Compliance:** HIPAA/TCPA audit sign-off (Consulted / Informed)

## 4. In-Scope vs. Out-of-Scope
| In-Scope | Out-of-Scope |
|---|---|
| Migration of 4.2M member profiles to SFMC Data Extensions | Redesign of core member billing portal |
| Automated nightly delta sync via Snowflake & Automation Studio | Custom mobile app push notification build |
| Journey Builder workflows (Email, SMS, IVR trigger) | Direct carrier billing integration |
| NICE CXone contact routing based on real-time campaign engagement | Legacy billing database decommissioning |
