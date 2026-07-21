# Strategy Memo: Enterprise Context for AI Agent Decisions

## Recommendation

Everpure has a distinct opportunity to make AI runtime authorization more data-aware, explainable, and defensible by building the enterprise data context infrastructure that enforcement platforms do not consistently maintain themselves.

As enterprise AI moves from supervised copilots to systems that execute work autonomously, the control point shifts from model quality to the context informing each action. Enterprises must not only authenticate the actor but also determine its appropriate scope of authority over the data involved.

Everpure is well positioned to become this enterprise context layer through the combination of Enterprise Data Cloud [12] and Everpure Data Intelligence [9]. The incremental bet is to operationalize Data Intelligence at the moment of action, turning its context graph from a discovery and governance asset into a low-latency recommendation and evidence service for external enforcement platforms.

Everpure would provide context and recommendations, while existing identity, authorization, and runtime platforms retain final policy and enforcement authority.

The product would deliver current, comprehensive data context to agent runtimes, identity and authorization systems, and security platforms as policy-ready attributes, explainable recommendations, and signed evidence records. This would enable more informed and defensible decisions based on factors such as data sensitivity, ownership, lineage, approved destinations, business criticality, freshness, and recoverability. We begin with high-blast-radius changes to Everpure-managed data, then expand into sensitive-data movement after validating the first use case.

This gives us a differentiated role in the emerging agent governance stack — approximately $150 million of year three core product ARR in the base case — without requiring us to become an identity provider, authorization engine, agent runtime, or general purpose AI security platform.

## 1. Market Need

Enterprise AI is moving from generating content to executing work. As agents gain permission to modify systems, move data, invoke tools, and complete business processes, each action becomes a runtime risk decision. Investment, acquisition activity, and new product categories validate the urgency of agent security, but the specific market for third-party runtime data context remains unproven: roughly $392M of venture funding closed around a single security conference, and Palo Alto's acquisition of CyberArk — announced at roughly $25B in July 2025 and closed in February 2026 at $21.1B — put securing AI agent identity at the center of its stated rationale [2]. Gartner published its Market Guide for Guardian Agents in February 2026 and predicts that 25% of enterprise breaches will trace to agent abuse by 2028 [1]. McKinsey's 2026 AI trust survey found that cybersecurity was one of the two most widely cited AI risks, rated highly relevant by 72 percent of respondents (alongside 74 percent for inaccuracy). More importantly for this strategy, nearly two-thirds named security and risk concerns as the top barrier to fully scaling agentic AI [11], and 40% of organizations delayed Copilot rollouts by three months or more over data oversharing [3]. The EU AI Act's high-risk obligations — including lifetime event logging — were set to apply from August 2, 2026 and now become enforceable December 2, 2027, following the Digital Omnibus postponement adopted in June 2026 [6].

Several platform categories already address parts of the runtime decision:

* Identity providers establish who, or what agent, is acting and under whose authority (Okta Cross App Access, Microsoft Entra Agent ID, CyberArk) [7].
* Authorization engines evaluate customer defined policies (AWS AgentCore Policy on Cedar, OPA) [7].
* Agent security products intercept actions and monitor behavior (Zenity, Noma, WitnessAI). Rubrik's Agent Rewind adds application layer rollback [8].
* Data governance and DSPM products discover and classify enterprise data (Cyera, BigID, Varonis, Microsoft Purview).
* Data platforms enforce controls within the environments they govern (Databricks Unity Catalog, Snowflake Horizon).

The gap is that runtime systems often lack complete, current, and operationally useful information about the data affected by an action. IBM's breach research points at exactly this: 97% of AI related breaches hit organizations with no AI specific data access controls [4]. A request to delete a dataset cannot be evaluated safely using identity and action type alone. The decision may also depend on whether the data supports a critical business process, has downstream dependencies, contains regulated information, has a recent recovery point, or belongs to an organization outside the agent's delegated scope.

That information exists today, but it is fragmented across catalogs, security products, infrastructure systems, and application metadata, and it is rarely delivered in a form runtime systems can consume consistently. Our opportunity is to operationalize this context. We should not attempt to replace the platforms that enforce policy.

## 2. Product and Beachhead

### Initial action class: high blast radius changes

The first product addresses destructive or high impact actions involving Everpure managed data: bulk deletion, overwrite, or encryption; snapshot, retention, replication, or recovery point modification; destructive dataset, volume, schema, or object store operations; and changes exceeding a customer defined blast radius threshold.

This is our strongest beachhead because we can combine enterprise context with storage level operational information and direct knowledge of the recovery path. For a proposed action the service provides classification and regulatory status, business owner and organizational relationships, upstream and downstream lineage, business criticality and affected workloads, estimated size and blast radius, available recovery points and their freshness, expected recoverability and restoration requirements, and recommended constraints or escalation conditions. The enforcement platform combines these signals with identity, delegation, and customer policy to make the final decision.

### Expansion action class: sensitive data movement

After proving the first use case, we expand into actions that copy, export, or transmit governed data to unapproved SaaS applications or external agents, public or unapproved model endpoints, lower trust accounts, regions, tenants, or environments, and unmanaged stores or collaboration platforms. The recommendation would weigh classification, ownership, purpose, destination approval, regulatory restrictions, lineage, and customer defined policy. Varonis finds 99% of organizations have sensitive data exposed to AI tools [5], but our recovery advantage is weaker here, so this action class follows validation of the first rather than launching alongside it.

### Product boundaries

The initial product will not attempt to provide:

* Agent identity or lifecycle management.
* Generic prompt injection detection or general behavioral anomaly detection.
* A proprietary agent gateway or runtime.
* A universal policy language.
* Controls for actions that do not materially involve governed enterprise data.

Other vendors have stronger architectural positions and more established buyers in these areas.

## 3. Right to Win

We should not claim that other platforms lack data context, lineage, classification, or runtime controls; each category above is strongest in its own layer, and data platforms provide the deepest context within their own ecosystems. Our potential differentiation is the combination of:

1. Context spanning heterogeneous enterprise environments — including mainframe and legacy estates where no single cloud or data platform has complete visibility, and where the Data Intelligence engine (acquired with 1touch.io, OEM'd by IBM since November 2021 as IBM Security Discover and Classify, now IBM Guardium Discover and Classify; classification accuracy above 98% independently verified) already operates in place [9].
2. Storage level operational and recovery information that application layer platforms do not typically have.
3. A context graph linking data to owners, applications, dependencies, and policies.
4. Policy ready delivery through runtime integrations.
5. Cryptographically verifiable records showing what context and recommendation Everpure produced at decision time.

Everpure's role is that of a neutral data context provider complementing these systems, not replacing them. The advantage must be proven, not asserted, through measurable capabilities: breadth and depth of supported sources, classification quality, lineage completeness, context freshness, the percentage of relevant actions where Everpure provides a unique material signal, and recoverability information unavailable to application layer platforms such as recovery point freshness on the underlying storage. The competitive landscape and category level differentiation are summarized in the Exhibit, Panel A.

## 4. Customer and Go to Market

**Ideal customer profile.** A large regulated or data intensive enterprise — financial services, healthcare, telecom, public sector first — that uses Everpure for business critical data or recovery, is deploying agents with write, modification, or export capabilities, has a runtime, gateway, API layer, or authorization service capable of intercepting actions, has centralized AI platform, data security, or cyber resilience ownership, faces material operational or regulatory consequences from incorrect agent actions, and is willing to begin with shadow mode evaluation. Our installed base (14,500+ customers, 64% of the Fortune 500 [10]) gives access and trust, but accounts qualify on agent maturity and risk, not on whether they own Everpure infrastructure.

**Buyer and stakeholders.** The economic buyer is the CISO or VP of Data Security, with the Head of AI Platform as co-sponsor. Technical champions: Director of AI Platform Security, Data Security Architect, Enterprise Authorization Architect, or Director of Data Governance or Cyber Resilience.

**Distribution.** Use installed base relationships to recruit design partners and simplify procurement, with the product packaged and priced separately. Agent runtimes, MCP gateways, authorization platforms, and security products are both integration partners and distribution channels: runtimes get to support regulated, high risk workflows; authorization platforms gain richer policy inputs without building data discovery; security platforms gain business impact and recovery context; Everpure gains the interception points we do not control. Partners retain the enforcement point, the end user experience, and the final policy decision. Commercial models can include embedded licensing, OEM arrangements, marketplace distribution, co-sell, or usage based context access.

## 5. One Year Plan and Investment Gates

We stage the investment rather than committing a 25 engineer team up front.

**Stage 0 — validate the hypothesis (months 0–3).** Team: 6–8 engineers, one PM, shared security, design, and data science support. Build a shadow mode prototype exposing a limited set of policy ready attributes, producing recommendations with reason codes and signed evidence records, integrated with one runtime or gateway, evaluated on at least five customer workflows. **Gate to expand:** two qualified customer design partners; one committed runtime or authorization partner; at least five adjudicated high risk workflows; evidence that Everpure context materially changes or qualifies decisions; a credible path through customer security review.

**Stage 1 — paid pilot (months 4–6).** Team: 12–15 engineers. Add locally distributed context projections, explicit freshness and missing context semantics, production observability and tenant isolation, active recommendations for the first action class, and initial packaging and pricing. **Gate to expand:** at least one paid pilot; at least 90 percent context coverage for selected workflows; decision quality targets met; production representative latency; customer and partner architecture approval.

**Stage 2 — production platform (months 7–12).** Team: expand to 20–25 engineers only after the prior gates are met. Deliver production service level objectives, a second runtime or authorization integration, repeatable deployment and field enablement, portable signed evidence, and initial support for sensitive data movement.

Year one success requires at least three paying production customers, two production enforcement integrations, independent security or AI platform budget, and measurable improvement in decision quality.

## 6. Decision Quality Validation

The central strategic assumption is that rich enterprise data context materially improves runtime decisions.

Each design partner creates a corpus of representative agent actions — historical, synthetic, and adversarial — spanning legitimate actions, high risk but valid actions, erroneous actions, malicious actions, and stale or incomplete context cases. Each action is reviewed by at least two relevant stakeholders (e.g. data owner, security representative, AI platform owner), with disagreements escalated to a third reviewer; actions without clear ground truth are classified as escalation cases rather than forced into allow or deny labels.

The same corpus is evaluated under a baseline policy (identity, role, action type, basic sensitivity) and a context enriched policy adding ownership, lineage, destination, freshness, criticality, and recoverability. Initial thresholds for success, to be finalized before testing with design partners:

* At least a 30 percent reduction in severity weighted false allows.
* No more than a two percentage point increase in false denies.
* At least 90 percent context coverage for the selected workflows.
* A unique material Everpure signal in at least 15 percent of high risk actions.
* Fewer than 5 percent stale or unresolved context cases.
* Reason codes judged sufficient for investigation and review.

If we do not meet these thresholds, we narrow the strategy to context feeds, governance evidence, and storage native controls rather than continue investing in runtime recommendations.

## 7. Economics and Market Potential

We measure the business in four separate categories, with no double counting: **direct context service ARR** (separately contracted product revenue), **partner or OEM ARR** (net recurring revenue through platform partners), **storage and Data Intelligence pull through** (influenced bookings, reported separately), and **retained ARR** (renewals where the capability materially influenced retention). Only direct and partner revenue count as core product ARR.

The market model is bottom up and tied to adoption milestones. Illustrative base case: three to five customers in year one; forty to seventy-five direct and partner customers in year two; approximately 250 direct and 100 partner sourced customers in year three, for **approximately $150 million of year three core product ARR**. Approximately $500 million of year three ARR is a bull case requiring materially higher penetration, ACV, and partner distribution — it is not the expected outcome. Detailed assumptions are in the Exhibit, Panel B.

## 8. Risks and Strategic Options

The largest risk is that enforcement platforms will not consume third party context beyond basic classification labels. We test this before scaling the organization. Other material risks: platform vendors building sufficient context internally; data context becoming a commodity feed; insufficient context freshness or coverage; customers refusing a new component in the runtime path; partner economics failing to support distribution; difficulty establishing ground truth for decision quality; and long enterprise security and procurement cycles.

The architecture minimizes runtime dependency through signed, locally distributed context projections. Customers configure behavior when context is missing or stale — restrict, escalate, deny, or use last known context. Fail closed behavior should not be universal.

A recovery backed warranty remains a later strategic option. During the first year we collect the operating, attribution, recovery, and loss data required to determine whether narrowly defined integrity and availability failures can be economically underwritten. The initial product must succeed on better decisions, explainability, evidence, and recovery intelligence — not on warranty coverage.

## Conclusion

Everpure should not attempt to become the universal control plane for enterprise agents. Our strongest opportunity is narrower and more defensible: the enterprise data context and recommendation layer that helps existing platforms make safer decisions about high risk data actions. We begin with destructive actions on Everpure managed data, where our context and recovery advantage is clearest, and expand into sensitive data movement only after customers and partners consume the context, decision quality measurably improves, and independent budget exists. This approach keeps us neutral, limits direct competition, stages investment behind evidence, and creates a credible path from a differentiated infrastructure capability to a standalone enterprise software business.

### Sources

[1] Gartner, first Market Guide for Guardian Agents, Feb 25, 2026; Gartner press release, Feb 17, 2026 (25% of enterprise breaches traced to agent abuse by 2028). [2] RSAC 2026 funding roundup, ~$392M in two weeks (Software Strategies/Calcalist); SentinelOne–Prompt Security ~$250M (Aug 2025); Cisco–Astrix ~$400M (2026); Palo Alto Networks–CyberArk announced Jul 30, 2025 at ~$25B equity value (joint press release), closed Feb 11, 2026 at $21.1B total purchase consideration (PANW 10-Q, quarter ended Apr 30, 2026). [3] Gartner survey of 132 IT leaders, via Computerworld, Nov 2024 (40% delayed Copilot deployments ≥3 months over oversharing). [4] IBM Cost of a Data Breach Report 2025 (97% of AI related breaches at organizations lacking AI specific data access controls). [5] Varonis State of Data Security Report 2025 (99% of organizations with sensitive data exposed to AI tools; 90% with sensitive files reachable through Copilot). [6] EU AI Act (Reg. (EU) 2024/1689), Arts. 12/14; Annex III high risk obligations originally applicable Aug 2, 2026, postponed to Dec 2, 2027 by the Digital Omnibus on AI, adopted June 2026 (European Parliament vote Jun 16, 2026; Council adoption Jun 29, 2026). [7] Okta Cross App Access (GA target Aug 2026); Microsoft Entra Agent ID (2026); AWS AgentCore Policy on Cedar, GA Mar 2026 (vendor documentation). [8] Rubrik Agent Rewind, Aug 2025 (press release). [9] Everpure Data Intelligence GA, June 17, 2026 (company release; Blocks & Files; StorageReview); 1touch.io acquisition closed May 11, 2026; classification accuracy above 98%, Tolly verified; IBM–1touch.io OEM announced Nov 2, 2021 (sold as IBM Security Discover and Classify; renamed IBM Guardium Discover and Classify, Oct 2024). [10] Everpure FY2026 results: 14,500+ customers, 64% of Fortune 500. [11] McKinsey & Company, "State of AI trust in 2026: Shifting to the agentic era," March 2026 (AI Trust Maturity Survey, ~500 organizations, fielded Dec 2025–Jan 2026: inaccuracy 74% and cybersecurity 72% the two most cited AI risks; nearly two-thirds cite security and risk as the top barrier to fully scaling agentic AI). [12] "Pure Storage Introduces the Enterprise Data Cloud," company press release, Pure//Accelerate, June 18, 2025.
