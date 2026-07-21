# Round Two — Verdict Flips on the Revised Memo

Files: new memo `/Users/sanketk/Downloads/everpure-case-research/sanket-draft/STRATEGY-MEMO-sanket-draft-v2.md` (2,284 words, no exhibits present), old memo `STRATEGY-MEMO-sanket-draft.md`, round-one report `GAP-ANALYSIS-red-team.md` in the same directory.

## Scorecard

| Persona | Old verdict | New verdict | Flipped? |
|---|---|---|---|
| Product Director, Everpure Data Intelligence | Fund only a carve-out experiment | Fund Stage 0, gate Stage 1 on org charter | Partial |
| Distinguished Engineer, Everpure | Would build a different, smaller system | Commit to Stage 0; gate Stages 1-2 on three designs | Partial |
| CISO, global bank | Cheap feed pilot only, no security budget | Sign shadow pilot; can't defend production spend | Partial |
| CDO, global insurer | Veto at architecture review | Approve shadow pilot; standing hold on advisory mode | Partial |
| Director of Product, runtime platform | Refuse — memo funds my competitor | Take to term sheet; Stage 1 needs economics/indemnity | Partial |
| AI Platform Lead, retailer | Shadow feed only, never hot path | Sponsor Stage 0 + paid Stage 1 | Partial |
| Case-compliance examiner | Passable on form, weak on substance | More coherent, fails the brief as submitted | No |

The pattern is uniform and striking: all six stakeholder personas moved from "no / not as written" to "yes to Stage 0, conditional on named artifacts for Stage 1." Nobody flipped fully, and everyone's remaining conditions are concrete and finite — a charter, a term sheet, a freshness mechanism, a latency number, a precedence rule. The strategy argument is essentially won. The one regression is the examiner: the revision fixed substance by deleting the evidence, exhibits, citations, and one mandatory case answer, so the document now fails the case brief on form. The remaining work is mostly writing, not rethinking.

## What the revision fixed (confirmed by the people who raised it)

- **Decision-authority contradiction.** "Everpure would not own the final policy decision," held consistently through Recommendation, GTM, and boundaries. Confirmed by all six personas and the examiner; the DE, CISO, CDO, and runtime partner each called it their core structural objection, resolved.
- **Warranty demoted to a later option.** Year one collects underwriting data; PMF must not depend on coverage. Confirmed by the Product Director (removes the Cyber Resilience collision and the Engine-2 contradiction), CISO, runtime partner, DE (removes snapshot-attack peril), and examiner.
- **Universal fail-closed removed.** Per-policy configurable stale/missing behavior (restrict/escalate/deny/last-known). Confirmed by the DE, CISO, CDO, AI Platform Lead, and runtime partner as a structural fix, not wordsmithing.
- **Staged investment plan (6-8 → 12-15 → 20-25, evidence-gated, shadow-first).** Confirmed by the Product Director ("exactly my option (a)"), DE ("exactly the option I proposed"), AI Platform Lead, and examiner.
- **Shadow mode as the memo's own entry point**, including as an ICP filter. Confirmed by the CISO, CDO, and AI Platform Lead.
- **Honest sizing:** $150M Y3 base, $500M explicitly a bull case, four revenue categories with a no-double-counting rule. Confirmed by the Product Director, CISO, runtime partner, and examiner.
- **Month-12 acquisition option deleted.** Confirmed by the runtime partner (their biggest reason to refuse), Product Director, and examiner.
- **Validation protocol upgraded:** adjudicated ground truth, severity-weighted false allows, ≤2pp false-deny ceiling, ≥15% unique-signal threshold, escalation-class labels. Confirmed by the Product Director, DE, CDO, AI Platform Lead, and examiner.
- **Narrower beachhead does real engineering work:** destructive actions on Everpure-managed data name their target resource, largely dissolving the action-to-resource problem for class 1 and leaning on attributes where Everpure is the system of record. Confirmed by the DE, CDO, and AI Platform Lead (the DE notes the memo never claims this credit — worth stating as design rationale).
- **Overclaims and sloppiness gone:** the unverifiable Meta incident, misused 97% stat, wrong CyberArk price, EU AI Act compliance overclaim, "no decision plane anywhere" competitive claim, typos, and broken numbering. Confirmed by the CISO, CDO, and examiner.

## What is still open

Ranked by severity.

1. **Case-brief compliance (examiner: fails as submitted).** Zero citations/dated sources, both load-bearing exhibits unwritten (and two exhibits would violate the one-exhibit allowance anyway), sizing math not shown, build/partner/acquire (question 5) no longer explicitly answered, no question weighting, BLUF missing prize/why-now/why-Everpure. Next move: execute the punch list below before anything else — this is drafting work, not strategy work.

2. **The Cyber Resilience org seam.** Product Director's dealbreaker, now customer-visible per the CISO: v2 names the CISO as economic buyer in writing while the sibling Cyber Resilience team owns that buyer and the recoverability story reads as resilience budget. Deferring the warranty removed the worst collision but sharpened the charter question. Next move: a one-page org proposal co-signed above both GMs (joint venture vs charter transfer, warranty-SKU ownership, revenue booking) before Stage 1 opens paid pilots into security budgets. Not a memo edit — an internal artifact the memo should reference.

3. **The experiment still can't prove Everpure-beats-incumbents.** The §6 baseline (identity, role, action type, basic sensitivity) is context-blind; "unique material signal" is undefined against the customer's deployed Purview/DSPM/Unity/Cyera stack — and in the beachhead class, recovery-point context is unique by construction. Held by the CISO, AI Platform Lead, and examiner. Next move: define "unique" relative to the customer's deployed context sources, measured at a customer running that stack, with customer-run divergence reports and per-decision provenance.

4. **Freshness has a gate but no mechanism.** The <5% stale gate has no named source; the graph is scan-fed batch. Held by the DE (central remaining objection) and AI Platform Lead. Next move: one paragraph — three tiers (array-native telemetry for class-1 operational attributes, CDC for database-resident classification, scan cadence for the rest), per-attribute context_age, per-class TTLs. The DE calls this known and cheap to write.

5. **Latency and the integration artifact went vague instead of getting fixed.** No numbers anywhere, "production representative latency" is a gate that cannot fail, and SDK-vs-sidecar-vs-gateway-plugin plus binding ownership is still unnamed. Held by the AI Platform Lead, DE, runtime partner, and CISO. Next move: state "Stage 0-1 recommendations are advisory and asynchronous; inline enforcement latency is a Stage 2 design gate with a partner-negotiated per-decision p95 and per-workflow overhead budget," and name the reference integration artifact.

6. **No partner economics or accountability structure.** "Could include" is a list of genres, not a deal; ceding decision authority also ceded all liability for materially wrong context, and the warranty deferral removed the only skin-in-the-game gesture. Held by the runtime partner (term-sheet blocker), CDO, and CISO. Next move: a design-partner term sheet with named rev-share before Stage 0 partner work, plus the accountability matrix (context wrong / policy wrong / enforcement wrong, remedy per cell) with capped context-error indemnity.

7. **Catalog-of-record reconciliation.** No precedence rule when Everpure's inferred ownership/criticality/regulatory attributes disagree with steward rulings in Collibra/Unity, no provenance flags, no production steward-correction workflow, and "last-known context" is an unauthorized-allow generator without reclassification guardrails. The CDO's standing architecture hold. Next move: named Collibra/Unity integration commitment with steward-overrides-inference precedence and inferred/curated provenance flags, gated before any non-shadow mode.

8. **The field motion Year 1 depends on is unfunded, and the Y3 ramp is the new $500M.** Three paying customers from security budget needs specialist sellers the memo doesn't fund; ~350 customers by Y3 with 9-12 month procurement cycles has no sales-capacity math. Held by the Product Director; the CISO adds that customer onboarding alone is 9-12 months. Next move: 3-4 named funded overlay sellers, and Exhibit B must show the capacity math.

9. **Signing/PKI named everywhere, designed nowhere.** Trust roots, key custody, rotation, revocation, post-termination offline verification. Held by the DE, runtime partner, CDO, and CISO. Next move: make it an explicit Stage 0 design deliverable — it cannot be retrofitted after a partner integrates.

10. **Operating model and security-review pack deferred past where the money is.** Stage 1 is paid but SLOs, on-call, incident ownership, kill switch, SOC 2 scope, DORA pack, and the five-nines serving hire all arrive later or never. Held by the DE, Product Director, CISO, and AI Platform Lead. Next move: written Stage 2 entry criterion plus an explicit condition that Stage 1 recommendations remain advisory; pre-integration SLOs before any embed.

11. **Kill discipline diluted.** v1's four falsification tests each had a named fallback; v2 keeps one composite test. Held by the DE, AI Platform Lead, Product Director, and CISO. Next move: restore as one paragraph — each stage gate gets a number or named artifact and a predefined consequence, and state that gates are condition-based, not calendar-based.

12. **Smaller open items:** where Stage 0's 6-8 engineers come from (Product Director — trades against Guardium OEM commitments); the governance office still routed around in GTM with no CDO sign-off gate (CDO); the regulatory posture of the evidence record — export format, escrow, Article 12 crosswalk (CDO, CISO); new §2 attributes (blast-radius/recoverability simulation) unscoped for Stage 0 (DE); class 2 presented as "expansion" when it is architecturally a second build (DE); Section 6 imposes unfunded adjudication labor on partners and customers (runtime partner).

## What the revision lost

**Lost and must restore:**
- **The entire evidence base and why-now.** Every statistic, incident, regulatory date, and funding signal was deleted rather than re-cited. The Product Director can't take the ask to a GM, the CISO has nothing for a budget request, and the examiner calls it a direct brief violation. The round-one instruction was fact-check, not delete.
- **Named competitors.** v1 named ~17 vendors; v2 names zero. A panel will probe names in Q&A and the presenter has nothing.
- **Latency reasoning.** The fabricated sub-20ms number deserved to die, but it told partners what architecture was intended. Replace with honest staged statements (advisory-async now, negotiated budget at Stage 2), not silence — three personas flagged that an undefined target is worse than an aggressive one.
- **The four falsification tests with named fallbacks.** The red team explicitly credited these; the DE and AI Platform Lead relied on them.
- **The explicit build/partner/acquire answer** (mandatory case question 5) — deleting the acquisition signal was right; deleting the answer was not.
- **The sizing math and the exhibit it lived in** — plus a one-sentence bridge explaining what changed in the model from $500M to $150M, or the ambition drop reads as a hedge.
- **The BLUF's prize, why-now, and why-Everpure** — and with them the 15-minute presentation spine.

**Lost deliberately and fine:**
- The month-12 acquisition option (the runtime partner asked for exactly this).
- The warranty-led pitch and Engine 2's +35% renewal uplift (source of the strategy-vs-revenue contradiction).
- "Decision authority" as product framing.
- The specific bad facts — Meta incident, 97% stat, CyberArk price, EU AI Act discharge claim. The category must come back with verified sources; these instances should not.

## Case-compliance punch list

- [ ] Restore dated, numbered citations for every load-bearing market claim; re-add a declared source list ("public information only, cited and dated" is a hard requirement — zero citations fails the brief alone).
- [ ] Write the exhibit — and consolidate: the brief allows exactly ONE one-page exhibit, so Exhibit A (competitive landscape, referenced at line 117) and Exhibit B (sizing assumptions, line 264) must become a single page or one must fold into the memo body.
- [ ] Reconcile or delete the stale `v3/EXHIBIT-sizing-v3.md`, which was built for the old $500M base case and contradicts v2.
- [ ] Show the sizing math in-memo: customer counts × ACV × attach → $150M, with assumptions stated.
- [ ] Re-answer build/partner/acquire explicitly (build: §2 boundaries; partner: §4; acquire: a stated position, even if "no acquisition in the plan period").
- [ ] Add the 3-4 line justified weighting of the 8 case questions.
- [ ] Rewrite the BLUF: prize, why-now, and why-Everpure in the first paragraph; lead with the product thesis instead of burying it at the end of the Recommendation.
- [ ] Name key competitors in §3 (category altitude plus representative vendors).
- [ ] Add the $500M→$150M bridge sentence and cut the pervasive conditional voice ("we should," "could provide") where the memo means "we will."
- [ ] State that stage gates are condition-based with a defined clock start, and pull the context-consumption kill test fully inside Stage 0 so falsification lands within two quarters.
- [ ] Quantify the coverage fraction: what share of intercepted agent actions at a real joint customer touch Everpure-managed data.
- [ ] Add the incumbent-context experiment arm (or the "unique vs deployed stack" definition) to §6.
- [ ] Add the declared word count.
- [ ] Rebuild the presentation spine: quotable opening claim, dated urgency, named landscape, prize before section 7.

## Bottom line

Yes — build final deliverables from v2. Every stakeholder who refused v1 now funds Stage 0, the architecture and org objections that were fatal are structurally fixed, and the remaining stakeholder asks are finite artifacts rather than rethinks; v1 had the opposite profile (compliant form, broken substance) and is not worth returning to. But v2 cannot be submitted as-is because it fails the brief on form. Order of work: (1) execute the compliance punch list — citations, the single consolidated exhibit with sizing math, build/partner/acquire, weighting, BLUF, named competitors; (2) restore the evidence base and why-now with verified sources; (3) add the four cheap in-memo paragraphs the personas dictated almost verbatim — freshness mechanism, advisory-vs-inline latency posture, restored falsification-with-fallback structure, unique-signal-vs-incumbent-stack definition; (4) draft the two off-memo artifacts Stage 1 actually gates on — the Cyber Resilience charter one-pager and the design-partner term sheet with economics and the accountability matrix. Items 1-3 are a day or two of writing; item 4 is the only genuinely hard remaining work.