# Splunk-Log-analysis
Windows security events log analysis in Splunk with dashboards and correlation rules for privileged activity

# Splunk Log Analysis — Windows Security Events

## Overview
This project applies Splunk to analyse **8,000+ Windows Security logs**, focusing on high-value events tied to privilege escalation and account misuse. The goal was to improve SOC visibility by creating searches and dashboards that highlight risky activities and support faster triage.

## Key Event IDs
- **4672** — Special Logon (privileged accounts)
- **4688** — Process Creation
- **4799** — Security Group Management

## Approach
1. Ingested Windows event logs into Splunk 9.3.2.
2. Built dashboards visualising:
   - Total events by ID
   - Frequency of audit failures vs. successes
   - Spikes in special logons and process creation :contentReference[oaicite:0]{index=0}.
3. Tuned SPL searches to reduce false positives while catching abnormal privilege activity.

## Results
- Identified spikes in privileged logons (4672) and group membership queries (4799).  
- Created correlation searches combining 4672 + 4688 to flag **processes spawned shortly after special logons** — a strong indicator of compromise.  
- Dashboards improved analyst visibility into account misuse and suspicious process chains.

## Repository Structure
- `dashboards/` — XML + screenshots of Splunk dashboards
- `queries/` — saved SPL searches and correlation rules
- `docs/` — methodology and lessons learned

## How to Reproduce
1. Collect Windows logs (EVTX export or Splunk Universal Forwarder).
2. Import SPL queries from `queries/` into Splunk.
3. Upload dashboard XMLs to Splunk Web.

## Next Steps
- Add enrichment with Active Directory metadata (user roles, OU).
- Convert SPL queries into **Sigma rules** for broader SOC use.

---
