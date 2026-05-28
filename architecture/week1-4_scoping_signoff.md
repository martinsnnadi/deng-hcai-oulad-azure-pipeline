# Internship Milestone: Weeks 1–4 Scoping & Design Sign-off
**Project Title:** Data Engineering for Human-centred AI Research  
**Intern:** Martins Ifeanyi Nnadi  
**Academic Supervisor:** Professor Solomon Sunday Oyelere  
**Framework Horizon:** 24-Week Structured Research & Development Timeline

---

## 1. Personal Development Goals Note (One-Page Summary)

My technical, ethical, and research objectives for this 24-week academic supervision internship are structured around my existing multi-cloud skillset—bridging my Microsoft Fabric Data Engineer Associate (DP-600) certification, AWS/Snowflake bootcamp tracks, and Human-Centred AI (HCAI) engineering:

*   **Goal 1: Advanced Medallion Architecture Implementation (Technical)**
    *   *Objective:* Design and provision fully segregated Bronze, Silver, and Gold lakehouse environments within the Azure Fabric workspace to isolate raw, unvetted education datasets from downstream machine learning consumers.
*   **Goal 2: Complex Data Profiling & Time-Series Wrangling (Analytical)**
    *   *Objective:* Programmatically transform, clean, and resolve anomalies within the Open University Learning Analytics Dataset (OULAD). I will write PySpark window functions to compress 10.6 million asynchronous clickstream log entries into uniform, weekly analytical feature layers.
*   **Goal 3: Cryptographic Privacy & Security Engineering (Security)**
    *   *Objective:* Enforce data-at-rest anonymisation by developing a deterministic, salted SHA-256 tokenisation pipeline over primary student keys (`id_student`), hiding secret environment salts to eliminate individual re-identification vulnerabilities.
*   **Goal 4: Algorithmic Equity Auditing & Data Governance (Ethical)**
    *   *Objective:* Master the operational integration of the `Fairlearn` toolkit. I will hardcode automated pipeline validation blocks checking historical Demographic Parity Differences across protected student cohorts (such as disability and age groups).
*   **Goal 5: Multi-Cloud Integration & Code-to-Data Alignment (Professional)**
    *   *Objective:* Establish 1:1 version control alignment by injecting GitHub commit hashes directly into Delta Lake transaction logs (`_delta_log`), maintaining a reproducible, auditable open-science workflow while cross-referencing cloud design patterns learned via AWS/Snowflake.

---

## 2. Working Environment & Access Ledger

### 2.1 Confirmed Environment Status
*   **Version Control Workspace:** Active public GitHub cloud repository (`hcai-oulad-azure-pipeline`) fully initialized with explicit directory routing (`architecture/`, `notebooks/`, `config/`).
*   **Cloud Processing Workspace:** Microsoft Azure Fabric corporate workspace `OULAD_DENG_HCAI_Analytics` established.
*   **Storage Framework:** Complete 3-tier Medallion architecture successfully provisioned as decoupled infrastructure points:
    1. `OULAD_DENG_Bronze_Raw` (Immutable append-only landing zone for education CSV tables).
    2. `OULAD_DENG_Silver_Audited` (Anonymised, joined, and fairness-vetted Delta tables).
    3. `OULAD_DENG_Gold_Curated` (Aggregated, semantic student feature matrices optimized for unbiased Power BI reporting and AI consumption).

### 2.2 Active Access Issues & Blockers Ledger
*   *Issue 1 (Fabric Capacity Migration):* Direct PySpark notebook compute allocation is running on a temporary cloud trial tier. We must schedule a migration roadmap to a stable research capacity before the 60-day trial window expires to maintain runtime integrity.
*   *Issue 2 (Cross-Organisational Access Blocker):* Microsoft Azure Fabric tenant policies currently block external domain invitations. Because Professor Oyelere is an external collaborator, the platform prevents adding his institutional account directly to the workspace Access Control List (ACL) as a Viewer. 

---

## 3. Supervision Agenda Question (For Professor Oyelere)

To ensure our cloud storage schemas are correctly configured before we begin active data ingestion in Week 5, I have narrowed our design focus down to one foundational question regarding student privacy:

1. **Clickstream Privacy Granularity**: The raw OULAD data tracks highly specific, daily student click interactions. To protect student identities and prevent vulnerabilities related to individual behaviour tracking, do you prefer that our pipeline aggregate these logs into uniform weekly totals during processing, or should we ingest the raw daily intervals exactly as they are?


