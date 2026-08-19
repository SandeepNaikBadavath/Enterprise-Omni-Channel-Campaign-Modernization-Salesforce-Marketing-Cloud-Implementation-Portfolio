# Enterprise Omni-Channel Campaign Modernization & SFMC Migration
**Domain:** Healthcare & Regulated Services | **Role:** Lead Salesforce Business Analyst

## Project Overview
Modernization of a fragmented legacy marketing and campaign management system into an integrated **Salesforce Marketing Cloud (SFMC)** and **Snowflake** ecosystem. The solution automates member engagement across **Email, SMS, IVR (AcuCall), and Inbound/Outbound Contact Center (NICE CXone)** while maintaining strict HIPAA and TCPA compliance.

## Key BA Deliverables in this Repository
* **[BRD](./docs/01_Business_Requirements_Document_BRD.md):** Business objectives, stakeholder matrix, scope, and compliance standards.
* **[FRD & Flows](./docs/02_Functional_Requirements_Document_FRD.md):** Journey Builder logic, contact segmentation, and communication channel rules.
* **[Process Flows](./docs/03_OmniChannel_Process_Flows.md):** End-to-end architecture and decision orchestration flows.
* **[Data Mapping Spec](./docs/04_Data_Mapping_and_Integration_Spec.csv):** Source-to-Target mapping (Snowflake Data Lake → SFMC Data Extensions).
* **[Jira Backlog](./docs/05_Jira_User_Stories_Backlog.csv):** Epics, user stories, Gherkin acceptance criteria (Given/When/Then).
* **[UAT Test Plan & RTM](./docs/06_UAT_Test_Plan_and_RTM.md):** Requirements Traceability Matrix, test scenarios, defect lifecycle, and business sign-off criteria.

## Tech Stack & Ecosystem
* **Core CRM & Marketing:** Salesforce Marketing Cloud (Email Studio, Mobile Studio, Journey Builder, Automation Studio), Salesforce Health Cloud / CRM
* **Data & Analytics:** Snowflake Data Cloud, SFTP (Automated ETL)
* **Telephony & Contact Center:** NICE CXone, AcuCall IVR
* **Agile & Delivery Tools:** Jira, Confluence, Lucidchart
