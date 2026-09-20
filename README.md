# MiMo RL Live Study: Empirical Verification of Decoupled Grader Architecture & Operational Incidents

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Field Study MVP](https://img.shields.io/badge/Study%20Scope-2%20Calibrated%20Events-blue.svg)](#bounded-scope)
[![Epistemic Model](https://img.shields.io/badge/Epistemic%20Model-Decoupled%203--Axis-brightgreen.svg)](#three-tier-authority-architecture)

This repository provides an empirical, verifiable field study analyzing distributed reinforcement learning (RL) training operations, focusing on the **Xiaomi MiMo-V2.6 large-scale agentic RL system**.

It examines architectural decoupling, verification failure domains, and temporal observability integrity across two audited events during the September 2026 live run.

---

## Bounded Scope

This repository is strictly bounded to **two physical events** audited under the BillGaoHub empirical governance framework:

1. **Event A (`OBS-MIMO-002`)**: The architectural formulation of **Grader Compute** as an independent scaling axis.
2. **Event B (`OBS-MIMO-005`)**: A production **Grader Deployment Network Partition and Cluster Run Restart** incident.

> [!NOTE]
> This study does **not** claim to reconstruct the entire MiMo-V2.6 training run or internal datacenter topology. Claims are restricted strictly to verifiable empirical observations and explicit public statements.

---

## Three-Tier Authority Architecture

To prevent epistemic conflation and maintain rigorous traceability, authority is structured into three non-overlapping tiers:

```mermaid
flowchart TD
    subgraph Source_Tier ["1. Source Factual Authority"]
        S1["Xiaomi MiMo Live Dashboard & Production APIs<br/>(https://mimo.xiaomi.com/rl/)"]
        S2["Primary Operational Notice n-15ac72 & Status Streams"]
    end

    subgraph Record_Tier ["2. Curated Field-Study Record Authority"]
        R1["billgaohub/mimo-rl-live-study<br/>(This Repository)"]
        R2["Curated Event Records, Audited Timestamps & Corrections"]
    end

    subgraph Model_Tier ["3. Derived Model Authority"]
        M1["billgaohub/agent-world-state"]
        M2["Generalized World-State Schemas, Axioms & Cross-Study Rules"]
    end

    Source_Tier -->|"Empirically Audited By"| Record_Tier
    Record_Tier -->|"Provides Grounded Inputs To"| Model_Tier
```

1. **Source Factual Authority**: The primary production system, live API endpoints (`/api/notices`, `/api/status`), and official statements.
2. **Curated Field-Study Record Authority (`billgaohub/mimo-rl-live-study`)**: This repository, establishing timestamp calibration, secondary corroboration audits, and structured incident ledgers.
3. **Derived Model Authority (`billgaohub/agent-world-state`)**: The downstream repository modeling state transitions, verification domains, and decay dynamics across multi-agent environments.

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
│   └── OBS-MIMO-005.yaml              # Event B: Grader Network Partition & Restart
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
