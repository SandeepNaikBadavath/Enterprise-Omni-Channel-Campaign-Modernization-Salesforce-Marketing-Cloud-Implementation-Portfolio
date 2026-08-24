# Functional Requirements Document (FRD)

## 1. System Architecture & Information Flow
```
[ Snowflake Data Cloud ] 
        │ (Nightly Delta ETL via Secure SFTP)
        ▼
[ SFMC Automation Studio ] ──> [ SFMC Data Extensions (HIPAA Masked) ]
        │
        ├──> [ Journey Builder ] ──> Email Studio / MobileConnect (SMS)
        │           │
        │           └──> API Trigger ──> [ AcuCall IVR Engine ]
        │
        └──> API / Flat-File Sync ──> [ NICE CXone Contact Center ]
```

## 2. Functional Requirements Breakdown

### FR-01: Automated Audience Ingestion
* **FR-01.1:** SFMC Automation Studio shall execute an import activity daily at 02:00 AM UTC to consume encrypted `.csv.gpg` files from Snowflake SFTP.
* **FR-01.2:** Data schema validation must execute automatically. If schema validation fails (missing mandatory fields: `Member_ID`, `Consent_Flag`), the file must be quarantined, and a Jira alert triggered via webhook.

### FR-02: Multi-Channel Orchestration & Prioritization
* **FR-02.1:** Channel prioritization engine will evaluate member preference:
  * Tier 1: Email (Primary engagement)
  * Tier 2: SMS (Triggered if email unopened after 48 hours)
  * Tier 3: Automated IVR call (Triggered if high-risk appointment booking remains unconfirmed after 5 days)
* **FR-02.2:** TCPA suppression rules must dynamically inspect `Time_Zone` before any SMS or IVR dispatch.

### FR-03: NICE CXone Contact Center Handoff
* **FR-03.1:** If a member replies with keyword `CALL` or abandons an IVR flow, SFMC must push a real-time task record to NICE CXone dialer queue with priority code `CAMPAIGN_WARM_LEAD`.
