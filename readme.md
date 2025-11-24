# Financial Data Drift Attribution Framework

A conceptual framework designed to improve data quality, observability, and explainability in legacy or vendor-controlled financial systems—without requiring schema changes or intrusive integration.

This project introduces structured methods to detect, cluster, classify, and attribute field‑level drifts across instruments, portfolios, and reference data domains to meaningful business, market, and technical causes.

---

## 🎯 Purpose
Financial data changes constantly—ratings migrate, coupons reset, sanctions are introduced, and benchmarks rebalance. Some changes are legitimate and expected, others indicate upstream feed issues, partial loads, missing attributes, or vendor errors.

This framework aims to:
- Reduce operational and compliance risk
- Improve transparency into data evolution
- Detect suspicious or unexplained changes early
- Attribute systemic changes to real-world events
- Support trade booking and guideline enforcement accuracy

---

## ✅ Core Problems Addressed
- Silent data drift affecting rule evaluation
- Missing or stale attributes from market data vendors
- Difficulty tracing origin of changes across feeds
- Vendor database limitations preventing schema extensions
- No historical context to differentiate expected vs abnormal changes

---

## 🔍 Key Capabilities
### 1. **Field-Level Drift Detection**
- Detect attribute changes across snapshots
- Log old vs new values with timestamps
- Support instruments, holdings, benchmarks, ESG, MSCI, BBG and more

### 2. **Drift Clustering & Correlation**
- Group related drifts by:
  - issuer, sector, index, currency, region
  - time window
  - affected attribute type
- Identify broad vs isolated changes

### 3. **Event Attribution Engine**
Classify drift clusters based on:
- Corporate actions
- Systemic rating migrations
- Sanctions updates
- Federal rate decisions
- Benchmark rebalancing calendars
- ESG methodology shifts
- Upstream vendor outages or partial feeds

### 4. **Feed Observability & Reliability Signals**
- Track vendor feed schedules, record counts, SLA adherence
- Detect missing, late, or incomplete loads
- Correlate technical issues with unexpected data drift

### 5. **Peer- & Issuer-Based Validation**
New instrument appears with no historical baseline?
- Compare against issuer siblings, sector medians, tenor buckets
- Surface missing or abnormal values

### 6. **Explainability & Auditability**
Every drift should answer:
**What changed? When? Why? From which source? Is it expected?**

---

## 📂 Recommended Data Model Concepts (External Storage)
Since operational DB changes are restricted, store externally:
- Drift events
- Snapshot history
- Event registry
- Feed metadata
- Peer reference profiles
- Attribution results and confidence

Storage may be:
- Cloud object store
- Document database
- Relational side system
- Data lake or warehouse

---

## 🧠 Attribution Logic – Industry Patterns
Inspired by capital markets data management standards:
- Temporal alignment with public or vendor events
- Scope overlap (issuer, country, sector, benchmark)
- Attribute impact signature matching
- Population baselines and volatility expectations
- Hierarchical entity reasoning
- Feed health correlation

Used in:
- Index rebalancing workflows
- Market data distribution platforms
- Surveillance systems
- Security master/reference data hubs

---

## 📊 Dashboarding & Insights
A practitioner-facing UI should:
- Summarize drift volumes by domain, attribute, severity
- Break down by attributed cause (event, feed issue, unknown)
- Highlight systemic vs isolated drifts
- Provide drill‑downs per instrument or event
- Visualize historical attribute timelines

Example dashboard sections:
- "Top unexplained drifts today"
- "Instruments missing critical attributes"
- "Sector‑wide rating changes – event linked?"
- "Feed health vs drift correlation"

---

## 🚦 Adoption Strategy
### Phase 1 – Observer Mode
- Parallel process
- Non‑blocking
- Drift detection + attribution + reporting

### Phase 2 – Data Quality Gatekeeping
- Integrate pre‑load validation
- Optionally block or quarantine bad data

---

## 🏛 Governance & Standards Alignment
Recommended alignment:
- EDM Council DCAM
- BCBS 239 (risk data aggregation)
- ISO 8000 (data quality semantics)
- Internal model risk and audit frameworks

---

## 💡 Ideal Use Cases
- Trade booking guardrails
- Compliance rule evaluation
- Client guideline monitoring
- Reference data onboarding
- Position & holdings integrity review
- Vendor feed reliability monitoring

---

## 🔧 Non‑Goals
This framework does **not**:
- Modify vendor application tables
- Replace upstream feeds
- Automatically correct data
- Guess missing values without human confirmation

---

## 🚀 Why This Matters
Bad reference data leads to:
- Incorrect compliance violations
- Missed regulatory reporting
- Wrong NAVs or exposure calculations
- Operational incidents and client escalations

A structured, transparent, and attributable drift monitoring framework prevents that.

