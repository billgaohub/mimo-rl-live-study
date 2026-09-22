# MiMo RL Live Study: Empirical Verification of Decoupled Grader Architecture & Operational Incidents

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Field Study Scope](https://img.shields.io/badge/Study%20Scope-4%20Audited%20Events-blue.svg)](#bounded-scope)
[![Epistemic Model](https://img.shields.io/badge/Epistemic%20Model-Decoupled%203--Axis-brightgreen.svg)](#three-tier-authority-architecture--ingestion-pipeline)
[![Lifecycle Status](https://img.shields.io/badge/Lifecycle-STUDY__COMPLETE-brightgreen.svg)](#field-study-lifecycle--promotion-protocol)

This repository provides an empirical, verifiable field study analyzing distributed reinforcement learning (RL) training operations, focusing on the **Xiaomi MiMo-V2.6 large-scale agentic RL system**.

It examines architectural decoupling, verification failure domains, temporal observability integrity, and lifecycle completion across four audited events during the September 2026 live run and official model release.

---

## Bounded Scope

This repository is strictly bounded to **four physical events** audited under the BillGaoHub empirical governance framework:

1. **Event A (`OBS-MIMO-002`)**: The architectural formulation of **Grader Compute** as an independent scaling axis.
2. **Event B (`OBS-MIMO-005`)**: A production **Grader Deployment Network Partition and Cluster Run Restart** incident.
3. **Event C (`OBS-MIMO-006`)**: Dual Run Lifecycle Completion (`mimo-v2.6-pro` & `flash` mode `ended`), $3.47M Total Compute, and AutomationBench Inversion.
4. **Event D (`OBS-MIMO-007`)**: Ungated **Open-Weights Release** (`MiMo-V2.6-Pro-RL` & `Flash-RL` on Hugging Face under MIT license) and **Technical Report Unveiling** (YORLO, Groupwise Agentic Grading, MOPD2).

> [!NOTE]
> This study does **not** claim to reconstruct the entire internal datacenter topology. Claims are restricted strictly to verifiable empirical observations and explicit public production APIs.

---

## Three-Tier Authority Architecture & Ingestion Pipeline

To prevent epistemic conflation and maintain rigorous traceability, authority and data ingestion are structured into three non-overlapping tiers:

```mermaid
flowchart TD
    S["Xiaomi MiMo Live Dashboard / Production APIs<br/>(https://mimo.xiaomi.com/rl/)"]
    -->|"Continuous Scheduled Observations"| L["Upstream Live Observation Ledger<br/>(mimo_v2.6_rl_live_observation_ledger.md)<br/>[LIVE / CONTINUOUS]"]
    
    L -->|"New Operational Events / State Changes / Hypotheses"| G{"Material World Change<br/>Promotion Gate"}
    
    G -- "NO / Routine Metrics (step/reward drift)" --> L_ONLY["Retain in Ledger Only<br/>(0 Public Repo Pollution)"]
    G -- "YES (Verifiable & Research-Worthy)" --> R["Curated Public Field-Study Records<br/>(billgaohub/mimo-rl-live-study)<br/>[ACTIVE_FIELD_STUDY]"]
    
    R -->|"Cross-Case Generalized Structures"| M["Specification & Validation Models<br/>(billgaohub/agent-world-state)<br/>[EXPERIMENTAL / DERIVED]"]
```

| Layer | Component | Epistemic Role | Operational Lifecycle |
|---|---|---|---|
| **1. Source Authority** | Xiaomi MiMo Production APIs | Origin factual reality (live status, notices, rollouts) | `PRIMARY_ORIGIN` |
| **2. Continuous Observation** | `mimo_v2.6_rl_live_observation_ledger.md` | Continuous tracking, raw snapshots, timing metrics, anomaly signals, candidate hypotheses | `FINAL_STATE_CAPTURED` |
| **3. Public Research Projection** | `billgaohub/mimo-rl-live-study` (This Repo) | Verified, desensitized, citable field-study records (`OBS-MIMO-00X`) of material events | `STUDY_COMPLETE` |
| **4. Derived Specification** | `billgaohub/agent-world-state` | Generalized cross-study schemas, temporal integrity rules, and state decay dynamics | `EXPERIMENTAL / DERIVED` |

---

## Field Study Lifecycle & Promotion Protocol

### 1. The Ledger → Public Study Promotion Gate
`scheduled ledger update != public repo update`. Routine telemetry steps (e.g. step $321 \rightarrow 326$, reward $0.710 \rightarrow 0.712$, normal linear GPU compute burn) remain strictly in the local observation ledger to prevent noise pollution.

A world change is promoted to this public repository as an audited observation (`OBS-MIMO-00X`) only when all three criteria are met:
1. **Materiality**: It represents a significant operational state change:
   - Training run restarts, cluster crashes, or recovery checkpoints
   - Decoupled Grader or GPU training cluster network partitions/outages
   - Online dataset additions, removals, or policy rollbacks
   - Official operator notices providing architectural explanations
   - Discovery of primary first-party links for currently `SECONDARY_CORROBORATED` claims
   - Direct contradiction of an existing claim by new empirical evidence
   - Observation of new temporal/clock divergence phenomena
   - Formal conclusion of the live training run
   - Release of open-weights and formal technical report / whitepaper
2. **Verifiability**: It is backed by reproducible physical API payloads or corroborating multi-source traces.
3. **Research Value**: It provides enduring insight into distributed multi-agent RL architecture, verification failure domains, or telemetry observability.

### 2. Lifecycle & Completion Criteria
- **Observation Ledger Status**: `FINAL_STATE_CAPTURED` (Live training runs completed at step 30, ledger archived).
- **Public Field Study Status**: `STUDY_COMPLETE` (Bounded 4 audited events, open weights verified, post-run synthesis complete).
- **Coverage Status**: `FULL_LIFECYCLE_CAPTURED` (All 30 steps across Pro and Flash recorded, model deliverables verified).
- **Study Completion Gate**:
  $$\text{LIVE\_RUN\_ENDED} + \text{FINAL\_STATE\_CAPTURED} + \text{MATERIAL\_EVENTS\_ADJUDICATED} + \text{POST\_RUN\_SYNTHESIS\_COMPLETE}$$
  With the live runs formally concluded, final state captured, all material operational events adjudicated, and open-weights synthesis completed, this repository has achieved its terminal status:
  $$\text{ACTIVE\_FIELD\_STUDY} \longrightarrow \text{RUN\_COMPLETED\_PENDING\_SYNTHESIS} \longrightarrow \mathbf{STUDY\_COMPLETE}$$

---

## Core Epistemic Adjudications

### 1. Event A: Grader Compute Scaling Axis (`OBS-MIMO-002`)
- **Status**: `SECONDARY_CORROBORATED` (Downgraded from prior uncalibrated claims).
- **Adjudication**: While 5 independent tech media outlets reported statements by Xiaomi MiMo Technical Lead Luo Fuli defining Grader Compute as the 3rd scaling axis (alongside Compute and Environments/Harnesses), no immutable primary permalink (direct personal post or formal whitepaper) was pinned in sandbox. In adherence to strict epistemic standards, this claim is maintained as secondary corroboration, not primary verified.

### 2. Event B: Decoupled Grader Failure & Restart (`OBS-MIMO-005`)
- **Status**: `PHYSICAL_API_VERIFIED` (Observed single instance only).
- **Adjudication**: Direct retrieval from production endpoint `https://mimo.xiaomi.com/rl/api/notices` (Notice ID `n-15ac72`) confirmed a network connectivity issue between the Pro training cluster and the grader deployment, triggering an operational run restart. Subsequent status streams confirmed Pro step 15 recovery at 08:09:48 PDT.
- **Bound**: `observed instance != universal architecture rule`. This incident confirms that verification infrastructure *can* be deployed as an independent service and distinct failure domain, but does not mandate universal architectural dictates for all RL platforms.

### 3. Temporal Integrity: Observer / Dashboard Divergence
- **Discrepancy**: A delta of **11 hours, 39 minutes, 54 seconds** was identified between the top-level UI status bar header (17:00:05 PDT) and the underlying notice publication epoch (`1789647611.047444` $\rightarrow$ 05:20:11 PDT).
- **Epistemic Principle**: This is classified as **observer/dashboard timestamp divergence**, enforcing the separation:
  $$\text{source\_event\_timestamp} \neq \text{dashboard\_clock\_timestamp} \neq \text{collector\_timestamp}$$
  The UI header represented the dashboard snapshot time, whereas the underlying event occurred 11h 40m prior, preceding and explaining the physical restarts at 02:29 PDT and 04:21 PDT.

### 4. Event C: Dual Run Lifecycle Completion & Benchmark Inversion (`OBS-MIMO-006`)
- **Status**: `PHYSICAL_API_VERIFIED` (Production endpoint confirmation).
- **Adjudication**: Direct retrieval from `https://mimo.xiaomi.com/rl/api/status` confirmed both `mimo-v2.6-pro` and `mimo-v2.6-flash` runs terminated with mode `ended`, completing all 30 steps.
  - **Pro**: 5 days 07h 29m (127h 29m), $2.62M, 75.0B tokens, 14 cluster restarts, DeepSWE 72.57% (+6.89 pt lead).
  - **Flash**: 3 days 11h 05m (83h 05m), $854k, 81.4B tokens, 5 cluster restarts, DeepSWE 65.68%.
  - **AutomationBench Inversion**: Flash achieved 52.70% vs Pro 51.30% (+1.40 pt), confirming that lightweight, resilient agent architectures can invert heavy reasoning models on long-horizon workflow automation.
  - **Combined Resource Burn**: $3,474,715.54 USD, 156.402B tokens, 1,505,280 samples, 10,420,763 sandboxes, 19 restarts.

### 5. Event D: Ungated Open-Weights Release & Methodological Unveiling (`OBS-MIMO-007`)
- **Status**: `PHYSICAL_API_VERIFIED` (Hugging Face repository & technical portal verification).
- **Adjudication**: On 2026-09-21 15:39 UTC, Xiaomi officially published ungated weights for both models on Hugging Face under MIT license:
  - **Pro**: `XiaomiMiMo/MiMo-V2.6-Pro-RL` (524B/1.02T architecture, 1M context, Native Omnimodal). Official benchmark confirmed DeepSWE 71.9% and Artificial Analysis Intelligence Index v4.3 score of 46.32 (Rank #1 open-source model).
  - **Flash**: `XiaomiMiMo/MiMo-V2.6-Flash-RL` (159B/309B architecture, 65 shards, SGLang / vLLM production recipes, DeepSWE 67.9%).
  - **Post-Training Paradigm Disclosure**: The technical report unveiled three core mechanisms: **YORLO** (unified single large-scale RL run across coding, general agent, vision, and cyber, disproving domain-cascaded RL); **Groupwise Agentic Grading** (cohort-relative rank scalar rewards replacing binary pass/fail); and **MOPD2** (lossless on-policy prefix distillation from Pro teacher rollouts into Flash).

---

## Repository Structure

```text
mimo-rl-live-study/
├── README.md                           # Master field study specification
├── SOURCE_CONTRACT.md                  # Epistemic axes, negative gates & sources
├── LICENSE                             # Dual MIT / CC BY 4.0 License
├── evidence-map.yaml                   # Abstract payload locators & cryptographic hashes
├── events/
│   ├── OBS-MIMO-002.yaml              # Event A: Grader Compute Scaling Axis
│   ├── OBS-MIMO-005.yaml              # Event B: Grader Network Partition & Restart
│   ├── OBS-MIMO-006.yaml              # Event C: Dual Run Completion & Final Benchmarks
│   └── OBS-MIMO-007.yaml              # Event D: Open-Weights Release & Technical Report
├── temporal/
│   └── timestamp-integrity.md         # Detailed 3-timestamp divergence audit
├── claims/
│   └── claims.yaml                    # Propositional claims & verification states
├── corrections/
│   └── corrections.yaml               # 5 formal epistemic and methodological corrections
└── analysis/
    └── derived-analysis.md            # Bounded architectural implications
```

---

## Verification & Integrity

All structured YAML files in this repository conform to deterministically validated schemas. Payloads referenced in `evidence-map.yaml` are pinned via SHA-256 digests. Raw API dumps containing potentially ephemeral session data are excluded in accordance with privacy and repository cleanliness standards.

---

## License

- **Code & Tooling**: [MIT License](LICENSE#1-code--software-scripts-mit-license)
- **Documentation & Structured Records**: [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE#2-research-documentation-curated-datasets--structured-yaml-records-cc-by-40)
- **Third-Party Rights**: All referenced trademarks and third-party quotes belong to their respective rights holders.
