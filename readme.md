# Financial Data Drift Attribution Framework

A conceptual framework designed to improve data quality, observability, and explainability in legacy or vendor-controlled financial systems—without requiring schema changes or intrusive integration.

This project introduces structured methods to detect, cluster, classify, and attribute field-level drifts across instruments, portfolios, and reference data domains to meaningful business, market, and technical causes.

---

## 🎯 Purpose

Financial data changes constantly—ratings migrate, coupons reset, sanctions are introduced, and benchmarks rebalance. Some changes are legitimate and expected, others indicate upstream feed issues, partial loads, missing attributes, or vendor errors.

This framework aims to:

* Reduce operational and compliance risk
* Improve transparency into data evolution
* Detect suspicious or unexplained changes early
* Attribute systemic changes to real-world events
* Support trade booking and guideline enforcement accuracy

---

## ✅ Core Problems Addressed

* Silent data drift affecting rule evaluation
* Missing or stale attributes from market data vendors
* Difficulty tracing origin of changes across feeds
* Vendor database limitations preventing schema extensions
* No historical context to differentiate expected vs abnormal changes

---

## 🔍 Key Capabilities

### 1. **Field-Level Drift Detection**

* Detect attribute changes across snapshots
* Log old vs new values with timestamps
* Support instruments, holdings, benchmarks, ESG, MSCI, BBG and more

### 2. **Drift Clustering & Correlation**

* Group related drifts by:

  * issuer, sector, index, currency, region
  * time window
  * affected attribute type
* Identify broad vs isolated changes

### 3. **Event Attribution Engine**

Classify drift clusters based on:

* Corporate actions
* Systemic rating migrations
* Sanctions updates
* Federal rate decisions
* Benchmark rebalancing calendars
* ESG methodology shifts
* Upstream vendor outages or partial feeds

### 4. **Feed Observability & Reliability Signals**

* Track vendor feed schedules, record counts, SLA adherence
* Detect missing, late, or incomplete loads
* Correlate technical issues with unexpected data drift

### 5. **Peer- & Issuer-Based Validation**

New instrument appears with no historical baseline?

* Compare against issuer siblings, sector medians, tenor buckets
* Surface missing or abnormal values

### 6. **Explainability & Auditability**

Every drift should answer:
**What changed? When? Why? From which source? Is it expect
