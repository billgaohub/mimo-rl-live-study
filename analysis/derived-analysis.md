# Derived Architectural Analysis & Bounded Empirical Rules

**Study**: Xiaomi MiMo-V2.6 Distributed RL Field Study  
**Framework**: BillGaoHub Empirical Architecture Research  

---

## 1. Methodological Boundary

> [!IMPORTANT]
> **Axiom: Observed Instance $\neq$ Universal Architecture Rule**  
> Empirical findings derived from a single production incident or platform deployment represent bounded observations, not mandatory universal architecture rules. They illustrate real failure modes and tradeoffs, but must not be overgeneralized into dogmatic dictates.

---

## 2. Derived Rules

### Rule `D-RULE-MIMO-001`: Verification Infrastructure as a Distinct Service and Failure Domain

- **Grounding Evidence**:
  - `OBS-MIMO-005` (Notice `n-15ac72` & physical Pro run restarts)
  - `OBS-MIMO-002` (Grader Compute tri-axial scaling formulation)
- **Status**: `EMPIRICAL_CASE_OBSERVATION`
- **Formal Statement**:
  > MiMo demonstrates that verification infrastructure can be deployed as a distinct service/failure domain; such decoupling introduces independent network and recovery risks. When the verification service (Grader deployment) experiences network partition or timeout, it can disrupt policy training rollouts and trigger cluster run restarts.

- **Bounded Engineering Implications**:
  1. **Decoupled Verification Benefits**: Separating evaluation/grading from policy rollout GPU nodes allows heterogeneous resource allocation (e.g. CPU vs GPU pools, specialized sandbox isolation) and independent horizontal scaling.
  2. **Failure Domain Tradeoffs**: Decoupling introduces network partition vulnerabilities. Distributed RL orchestrators should implement circuit breakers, asynchronous grading buffers, and resilient retry thresholds before aborting active training runs.

---

### Rule `D-RULE-MIMO-002`: Temporal Ambiguity of Global UI Clock in Monitoring Dashboards

- **Grounding Evidence**:
  - `OBS-MIMO-005` (11h 40m timestamp divergence audit)
  - `temporal/timestamp-integrity.md`
- **Status**: `SPECIFIC_DASHBOARD_AUDIT_PHENOMENON`
- **Formal Statement**:
  > This MiMo dashboard demonstrated that a global UI clock can be temporally ambiguous when used as an event timestamp. In this instance, the top-level status bar header clock reflected snapshot acquisition time (17:00:05 PDT), while the underlying incident notice had been emitted at 05:20:11 PDT (11h 40m earlier).

- **Bounded Engineering Implications**:
  1. **Underlying Payload Grounding**: Observers, automated scrapers, and evaluators must extract item-level creation timestamps (`created_at`, Unix epoch) from underlying JSON API payloads rather than surface DOM clock headers.
  2. **Telemetry Schema Enforcement**: State tracking systems must explicitly separate `source_event_timestamp`, `dashboard_clock_timestamp`, and `collector_timestamp` to preserve causal ordering in forensic postmortems.

---

### Rule `D-RULE-MIMO-003`: Capability Divergence & Workflow Automation Inversion

- **Grounding Evidence**:
  - `OBS-MIMO-006` (Full 30-step completion across dual runs, final benchmark evaluations)
  - `claims/claims.yaml` (`CLM-MIMO-003`)
- **Status**: `EMPIRICAL_CASE_OBSERVATION`
- **Formal Statement**:
  > Large-scale agentic RL produces divergent capability profiles between heavy and lightweight models. Heavier MoE models (`pro`, $2.62M consumed, 14 cluster restarts) achieve superior gains on complex software engineering code reasoning (DeepSWE 72.57% vs 65.68%, +6.89 pt). Conversely, lighter models (`flash`, $854k consumed, 5 cluster restarts) exhibit faster, more resilient policy iteration, achieving an empirical inversion on multi-step agent workflow automation (AutomationBench 52.70% vs 51.30%, +1.40 pt).

- **Bounded Engineering Implications**:
  1. **Task-Specific Post-Training Selection**: Scale does not monotonically dominate across all agent domains. For complex code reasoning, compute scaling yields high rewards; for tool orchestration and long-horizon workflow automation, lightweight architectures can achieve higher convergence throughput under equivalent or lower verification overhead.
  2. **Recovery Latency as an ROI Multiplier**: High model complexity increases infrastructure fragility (GPU OOM, routing imbalance). The effective throughput of agent RL must account for recovery latency and rerun penalties, not raw token throughput alone.

