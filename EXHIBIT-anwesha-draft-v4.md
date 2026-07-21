# Exhibit — Competitive Position and Year Three Market Model (one page)

## Panel A: Category landscape and Everpure's differentiation

| Category | Representative vendors | Strongest at | Missing at decision time | Everpure posture |
|---|---|---|---|---|
| Identity providers | Okta Cross App Access, Microsoft Entra Agent ID, CyberArk | Agent identity, delegation, credential governance | Data blind to the action's target (sensitivity, lineage, criticality, recoverability) | Context feed partner |
| Authorization engines | AWS AgentCore Policy (Cedar), OPA | Policy evaluation at the enforcement point | Rich, current data attributes to evaluate against | Policy ready attribute source |
| Agent security | Zenity, Noma, WitnessAI; Rubrik Agent Rewind (rollback) | Interception, behavior monitoring, application layer undo | Business impact, blast radius, storage recovery context | Business impact and recovery context provider |
| Data governance / DSPM | Cyera, BigID, Varonis, Microsoft Purview | Discovery, classification, posture | Runtime delivery — context is scan based, not served at the moment of action | Closest adjacency; we differ on runtime delivery, storage and recovery signals, mainframe reach |
| Data platforms | Databricks Unity Catalog, Snowflake Horizon | Deepest context inside their own ecosystems | Coverage beyond their estate; storage level recovery information | Complement across heterogeneous estates |

**Differentiation to prove (§3):** cross estate context including mainframe (1touch.io engine, >98% classification accuracy, Tolly verified), storage level recovery signals, policy ready runtime delivery, cryptographically verifiable evidence. Initial proof thresholds (§6, to be finalized with design partners): ≥90% context coverage, ≥15% of high risk actions with a unique material Everpure signal, <5% stale context.

## Panel B: Year three market model (bottom up, milestone gated)

**Base case build up (Year 3):**

| Segment | Customers | Avg. ARR to Everpure | ARR |
|---|---|---|---|
| Direct context service | ~250 | ~$480K (platform ~$250K + usage on governed high risk actions ~$230K) | ~$120M |
| Partner / OEM sourced | ~100 | ~$300K net (revenue share on embedded and marketplace distribution) | ~$30M |
| **Core product ARR** | **~350** | | **~$150M** |

**Trajectory:** Year 1: 3–5 paying production customers (~$1–2M exit ARR). Year 2: 40–75 direct and partner customers (~$18–30M). Year 3: ~350 (~$150M). The Year 2 → Year 3 ramp assumes both production enforcement integrations are live and the partner channel scales; it is gated on the Stage 1–2 evidence gates (§5), not on calendar time.

**Penetration checks:** ~250 direct customers ≈ 1.7% of the 14,500 customer installed base, or ~10% of an assumed ~2,500 account ideal pool — roughly the regulated, Fortune 500 scale subset of the installed base (64% of the F500 [10]) deploying write capable agents with an interception point, plus net new equivalents. Partner sourced accounts are primarily net new, outside the installed base.

**Bridge to the $500M bull case (not the expected outcome):** ~550 direct customers (≈22% of the ideal pool) × ~$640K ACV (deeper usage plus sensitive data movement attach) ≈ $350M, plus ~425 partner sourced × ~$350K net ≈ $150M. Requires ~2.2× penetration, ~1.3× ACV, and ~4× partner distribution versus base — bull, not base.

**Not counted above (§7):** storage and Data Intelligence pull through (influenced bookings) and retained ARR are reported separately; no double counting.

**What falsifies this model:** enforcement platforms not consuming context beyond classification labels, coverage or unique signal below the §6 thresholds, or failed partner economics — in which case we narrow per §8, and the direct only path caps near the ~$120M line, later.

*Illustrative planning figures, not commitments. ACVs are management estimates consistent with separately priced enterprise data security platforms at Fortune 500 scale regulated accounts; partner net ARR assumes ~55–60% revenue share on partner side pricing of ~$500–550K; customer counts are production customers, not pilots.*
