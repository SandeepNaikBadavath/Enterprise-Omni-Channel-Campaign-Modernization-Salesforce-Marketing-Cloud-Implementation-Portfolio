# Omni-Channel Process Flows & Sequence Logic

## 1. End-to-End Campaign Orchestration Flow

```text
[ Member Trigger Event (Care Gap / Screening Due) ]
                        │
                        ▼
       [ Snowflake Delta Ingestion (Nightly) ]
                        │
                        ▼
       [ SFMC Automation Studio Import & Validation ]
                        │
                        ▼
            [ Journey Builder Injection ]
                        │
                        ├───────────────────────────┐
                        │ Email Opt-In Valid        │ No Email / Suppressed
                        ▼                           ▼
            [ Send Responsive Email ]        [ Check SMS Opt-In ]
                        │                           │
          ┌─────────────┴─────────────┐             ├─────────────┐
          ▼ (Opened & Clicked)        ▼ (No Action)  ▼ (Opted-in)  ▼ (No SMS)
   [ Member Booked ]           [ Wait 48 Hours ]  [ Send SMS ] [ AcuCall IVR ]
                                      │                 │
                                      ▼                 ▼
                              [ Fallback to SMS ] [ Response: 'AGENT' ]
                                                        │
                                                        ▼
                                             [ Route to NICE CXone Queue ]
```

## 2. Decision Logic Rules
1. **Consent Priority:** Always verify explicit Opt-In flags (`Email_OptIn`, `SMS_OptIn`) before each channel step.
2. **Quiet Hours Enforcement:** If execution timestamp falls outside `08:00 - 21:00` member local time, pause journey branch until the next legal dispatch window.
3. **De-duplication & Frequency Capping:** Maximum 2 SMS messages per recipient per 7-day rolling window.
