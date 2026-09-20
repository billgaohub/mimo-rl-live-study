# Source Contract & Epistemic Protocol (SC-MIMO-FIELD-STUDY-MVP-2EVENTS)

## 1. Study Scope

This empirical study is strictly limited to **two events** from the Xiaomi MiMo-V2.6 live run:
- **Event A**: Grader Compute Scaling Axis (`OBS-MIMO-002`)
- **Event B**: Grader Deployment Network Partition & Run Restart (`OBS-MIMO-005`)

---

## 2. Decoupled Three-Axis Epistemic Framework

In place of conflated scalar levels, evidence and claims are evaluated across three orthogonal axes:

### Axis 1: Review Depth (Observer Rigor)
- **Identity Pinned**: Whether endpoint URL, system origin, or speaker identity is cryptographically or uniquely pinned.
- **Metadata Verified**: Whether headers, schema structures, payload sizes, or duration intervals are verified.
- **Content Reviewed**: Whether underlying JSON payloads, response fields, or transcripts were physically inspected by the observer.

### Axis 2: Source Authority (Inherent Epistemic Standing)
- **PRIMARY**: First-party origin system, canonical production API, or official release.
- **MIRROR**: Cryptographically verifiable or byte-accurate synchronized redistributions.
- **SECONDARY**: Third-party journalism, commentaries, or aggregated reporting.

### Axis 3: Claim State (Adjudicated Propositional Status)
- `PHYSICAL_API_VERIFIED`: Confirmed directly against primary API payload with consistent temporal sequence.
- `SECONDARY_CORROBORATED`: Multiple secondary sources corroborate the event/quote, but direct primary permalink was unpinned or unreviewed.
- `ACTION_CLAIM` / `SPOKEN_CLAIM`: Propositional claims requiring validation against real operational traces.
- `CONTRADICTED`: Empirical evidence physically disproves the assertion.
- `UNVERIFIED`: Insufficient evidence to adjudicate.

---

## 3. Negative Gates

1. **Anti-Inheritance Gate**: Prior ledger conclusions cannot be accepted without re-verification of raw evidence.
2. **Anti-Overgeneralization Gate**: Observed instances do not constitute universal architectural rules (`observed instance != universal architecture rule`).
3. **Bounded Scope Gate**: No ad-hoc expansion beyond the 2 authorized events without prior governance approval.
4. **Timestamp Integrity Gate**: UI display clock must never be conflated with the payload publication epoch.

---

## 4. Grounded Sources

### Primary Origin Source (`SRC-MIMO-LIVE-001`)
- **Name**: Xiaomi MiMo RL Live Dashboard & APIs
- **Base URL**: `https://mimo.xiaomi.com/rl/`
- **Authority**: `PRIMARY`
- **Endpoints**:
  - Notices Stream: `https://mimo.xiaomi.com/rl/api/notices`
  - Run Status: `https://mimo.xiaomi.com/rl/api/status?run=pro`
  - Runs Directory: `https://mimo.xiaomi.com/rl/api/runs`
- **Audited Payloads**:
  - `notices.json` (SHA-256: `7d245e1aac5f00c5fbd6a1475e5f5d4c1b09b54996eaae3c8d5bc910f2a75f9e`)
  - `status_pro.json` (SHA-256: `a331cf7bc8aac3f99686c0935afca205845f408e5650e132856149943ec661f4`)
  - `runs.json` (SHA-256: `06784c35fb303c2323497ee757533c2498a8338c982565fb5f1517ab5c84f25e`)

### Secondary Media Corroboration (`SRC-MIMO-PRESS-001`)
- **Topic**: Luo Fuli statement on Grader Compute as the 3rd scaling axis.
- **Authority**: `SECONDARY`
- **Discovery Status**: `MULTI_SOURCE_SEARCH_CORROBORATED` (5 independent outlets discovered)
- **Primary Source Permalink**: `NOT_PINNED_IN_SANDBOX`
- **Corroborating Outlets**:
  - QbitAI (量子位): `https://m.qbitai.com/2026/09/322960.html`
  - Sina Tech (新浪科技): `https://finance.sina.com.cn/tech/roll/2026-09-17/doc-incvswvm9191494.shtml`
  - Tencent News (腾讯科技): `https://view.inews.qq.com/k/20260917A04D0T00`
  - Ifeng Tech (凤凰网科技): `https://news.ifeng.com/c/8mZ5iV6T5eB`
  - TMTPost (钛媒体): `https://www.tmtpost.com/7279328.html`
- **Adjudication**: Pinned URLs corroborate the existence of the reported quote, but absence of a direct primary link limits claim state to `SECONDARY_CORROBORATED`.
