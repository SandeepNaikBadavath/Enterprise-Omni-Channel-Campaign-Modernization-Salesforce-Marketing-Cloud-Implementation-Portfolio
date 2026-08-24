# UAT Test Plan & Requirements Traceability Matrix (RTM)

## 1. Requirements Traceability Matrix (RTM)
| Requirement ID | Jira Key | Test Scenario Description | Expected Outcome | Status |
|---|---|---|---|---|
| FR-01.1 | OMNI-101 | Validate delta record import from Snowflake SFTP | 50,000 records loaded; invalid records rejected to error log | Passed |
| FR-02.1 | OMNI-102 | Test Email-to-SMS fallback sequence | Unopened emails receive SMS exactly at T+48h mark | Passed |
| FR-02.2 | OMNI-104 | Validate TCPA suppression during quiet hours | Dispatches between 9:01 PM - 7:59 AM local time are queued | Passed |
| FR-03.1 | OMNI-105 | Member SMS reply 'AGENT' routing to NICE CXone | Interaction record appears in CXone agent queue within 30s | Passed |

## 2. Defect Severity & Triage Matrix
* **Severity 1 (Blocker):** Data leakage, HIPAA breach risk, or failure of TCPA suppression engine.
* **Severity 2 (Critical):** Integration failure between SFMC and NICE CXone; journey halts completely.
* **Severity 3 (Major):** Data field truncation in non-mandatory personalisation strings.
* **Severity 4 (Minor):** Cosmetic template formatting issue on email clients (e.g., Outlook desktop padding).

## 3. Business Sign-off Protocol
UAT exit criteria require 100% test execution of critical path test cases, 0 open Severity 1/2 defects, and written sign-off from Marketing Operations, Compliance, and Contact Center leadership.
