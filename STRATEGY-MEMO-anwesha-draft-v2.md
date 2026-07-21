# Strategy Memo: Enterprise Context for AI Agent Decisions

## Recommendation

Everpure should build the enterprise data context and recommendation layer for high risk AI agent actions.

The product would provide agent runtimes, identity systems, authorization engines, and security platforms with current information about the data affected by an action. This would include sensitivity, ownership, lineage, approved destinations, business criticality, freshness, and recoverability. The service would return policy ready attributes, an explainable recommendation, and a signed evidence record.

Everpure would not own the final policy decision. Partner platforms would continue to apply customer specific policies and retain the final decision to allow, restrict, escalate, or deny an action.

We should begin with two action classes:

1. High blast radius changes to Everpure managed data.
2. Movement of sensitive data into unapproved environments.

This gives us a differentiated role in the emerging agent governance stack without requiring us to become an identity provider, authorization engine, agent runtime, or general purpose AI security platform.

**Product thesis:** Everpure can make runtime authorization more data aware, explainable, and defensible by providing enterprise context that enforcement platforms do not consistently maintain themselves.

## 1. Market Need

Enterprise AI is moving from generating content to executing work. As agents gain permission to modify systems, move data, invoke tools, and complete business processes, each action becomes a runtime risk decision.

Several platform categories already address important parts of that decision:

* Identity providers establish who, or what agent, is acting and under whose authority.
* Authorization engines evaluate customer defined policies.
* Agent security products intercept actions and monitor behavior.
* Data governance products discover and classify enterprise data.
* Data platforms enforce controls within the environments they directly govern.

The gap is that runtime systems often lack complete, current, and operationally useful information about the data affected by an action.

A request to delete a dataset, for example, cannot be evaluated safely using identity and action type alone. The decision may also depend on whether the data supports a critical business process, has downstream dependencies, contains regulated information, has a recent recovery point, or belongs to an organization outside the agent's delegated scope.

This information exists today, but it is fragmented across catalogs, security products, infrastructure systems, and application metadata. It is rarely normalized and distributed in a form that runtime authorization systems can consume consistently.

Our opportunity is to operationalize this context. We should not attempt to replace the platforms that enforce policy.

## 2. Product and Beachhead

### Initial action class: high blast radius changes

The first product should address destructive or high impact actions involving Everpure managed data, including:

* Bulk deletion, overwrite, or encryption.
* Snapshot, retention, replication, or recovery point modification.
* Destructive dataset, volume, schema, or object store operations.
* Large scale changes that exceed a customer defined blast radius threshold.

This is our strongest beachhead because we can combine enterprise context with storage level operational information and direct knowledge of the recovery path.

For a proposed action, the service could provide:

* Data classification and regulatory status.
* Business owner and relevant organizational relationships.
* Upstream and downstream lineage.
* Business criticality and affected workloads.
* Estimated size and blast radius.
* Available recovery points and their freshness.
* Expected recoverability and restoration requirements.
* Recommended constraints or escalation conditions.

The enforcement platform would combine these signals with identity, delegation, and customer policy to make the final decision.

### Expansion action class: sensitive data movement

After proving the first use case, we should expand into actions that copy, export, or transmit governed data to:

* Unapproved SaaS applications or external agents.
* Public or unapproved model endpoints.
* Lower trust accounts, regions, tenants, or environments.
* Unmanaged stores or collaboration platforms.

The recommendation would consider data classification, ownership, purpose, destination approval, regulatory restrictions, lineage, and customer defined policy.

This action class expands the addressable problem, but our recovery advantage is weaker. It should follow validation of the first use case rather than launch alongside it.

### Product boundaries

The initial product should not attempt to provide:

* Agent identity or lifecycle management.
* Generic prompt injection detection.
* General behavioral anomaly detection.
* A proprietary agent gateway or runtime.
* A universal policy language.
* Controls for actions that do not materially involve governed enterprise data.

Other vendors have stronger architectural positions and more established buyers in these areas.

## 3. Right to Win

We should not claim that other platforms lack data context, lineage, classification, or runtime controls. Many vendors provide portions of these capabilities.

Our potential differentiation is the combination of:

1. Context spanning heterogeneous enterprise environments.
2. Storage level operational and recovery information.
3. A context graph linking data to owners, applications, dependencies, and policies.
4. Policy ready delivery through runtime integrations.
5. Signed records showing what context was used and why a recommendation was produced.

Data platforms generally provide the deepest context within their own ecosystems. Identity platforms are strongest in principal, delegation, and access governance. Agent security vendors are strongest in runtime interception and behavioral visibility. DSPM and governance vendors are strongest in discovery, classification, and posture.

Everpure can complement these systems by serving as a neutral data context provider, particularly in heterogeneous and legacy estates where no single cloud or data platform has complete visibility.

We will need to prove this advantage through measurable product capabilities, including:

* Breadth and depth of supported data sources.
* Classification quality.
* Lineage completeness.
* Context freshness.
* Percentage of relevant actions for which Everpure provides a unique material signal.
* Recoverability information unavailable to application layer platforms.

The competitive landscape and category level differentiation are summarized in Exhibit A.

## 4. Customer and Go to Market

### Ideal customer profile

The initial customer should be a large, regulated or data intensive enterprise that:

* Uses Everpure for business critical data or recovery.
* Is deploying agents with write, modification, or export capabilities.
* Has an agent runtime, gateway, API layer, or authorization service capable of intercepting actions.
* Has centralized AI platform, data security, or cyber resilience ownership.
* Faces material operational or regulatory consequences from incorrect agent actions.
* Is willing to begin with shadow mode evaluation.

Financial services, healthcare, telecom, public sector, and other highly regulated industries are the strongest initial segments.

Our installed base gives us access and customer trust, but we should qualify accounts based on agent maturity and risk, not simply on whether they own Everpure infrastructure.

### Buyer and stakeholders

The likely economic buyer is the CISO or VP of Data Security, with the Head of AI Platform or Enterprise AI as a co-sponsor.

The technical champion is likely to be a:

* Director of AI Platform Security.
* Data Security Architect.
* Enterprise Authorization Architect.
* Director of Data Governance or Cyber Resilience.

### Distribution strategy

We should use our installed base relationships to recruit design partners and simplify procurement, while packaging the product as a separately priced offering.

Agent runtimes, MCP gateways, authorization platforms, and security products should be treated as both integration partners and distribution channels.

The partner value proposition is:

* Runtime providers can support more regulated and high risk enterprise workflows.
* Authorization platforms gain richer policy inputs without building data discovery infrastructure.
* Agent security platforms gain business impact, lineage, and recovery context.
* Everpure gains access to the interception and enforcement points we do not control.

Partners should retain the enforcement point, end user experience, and final policy decision. Commercial models could include embedded licensing, OEM arrangements, marketplace distribution, co-sell agreements, or usage based context access.

## 5. One Year Plan and Investment Gates

We should stage the investment rather than immediately committing a 25 engineer team.

### Stage 0: Validate the hypothesis, months 0 to 3

**Team:** 6 to 8 engineers, one PM, and shared security, design, and data science support.

Build a shadow mode prototype that:

* Exposes a limited set of policy ready attributes.
* Produces recommendations and reason codes.
* Creates signed evidence records.
* Integrates with one runtime or gateway.
* Evaluates at least five customer workflows.

**Gate to expand:**

* Two qualified customer design partners.
* One committed runtime or authorization partner.
* At least five adjudicated high risk workflows.
* Evidence that Everpure context materially changes or qualifies decisions.
* A credible path through customer security review.

### Stage 1: Paid pilot, months 4 to 6

**Team:** Expand to 12 to 15 engineers.

Add:

* Locally distributed context projections.
* Explicit freshness and missing context semantics.
* Production observability and tenant isolation.
* Active recommendations for the first action class.
* Initial packaging and pricing.

**Gate to expand:**

* At least one paid pilot.
* At least 90 percent context coverage for selected workflows.
* Decision quality targets met.
* Production representative latency.
* Customer and partner architecture approval.

### Stage 2: Production platform, months 7 to 12

**Team:** Expand to approximately 20 to 25 engineers only after the prior gates are met.

Deliver:

* Production service level objectives.
* A second runtime or authorization integration.
* Repeatable deployment and field enablement.
* Portable signed evidence.
* Initial support for sensitive data movement.

Year one success requires at least three paying production customers, two production enforcement integrations, independent security or AI platform budget, and measurable improvement in decision quality.

## 6. Decision Quality Validation

The central strategic assumption is that rich enterprise data context materially improves runtime decisions.

Each design partner should create a corpus of representative agent actions using historical, synthetic, and adversarial scenarios. The corpus should include legitimate actions, high risk but valid actions, erroneous actions, malicious actions, and cases involving stale or incomplete context.

Each action should be reviewed by at least two relevant stakeholders, such as the data owner, security representative, and AI platform owner. Disagreements should be escalated to a third reviewer. Actions without clear ground truth should be classified as escalation cases rather than forced into an allow or deny label.

The same action corpus should be evaluated using:

1. A baseline policy with identity, role, action type, and basic sensitivity.
2. A context enriched policy adding ownership, lineage, destination, freshness, criticality, and recoverability.

Success should require:

* At least a 30 percent reduction in severity weighted false allows.
* No more than a two percentage point increase in false denies.
* At least 90 percent context coverage for the selected workflows.
* A unique material Everpure signal in at least 15 percent of high risk actions.
* Fewer than 5 percent stale or unresolved context cases.
* Reason codes judged sufficient for investigation and review.

If we do not meet these thresholds, we should narrow the strategy to context feeds, governance evidence, and storage native controls rather than continue investing in runtime recommendations.

## 7. Economics and Market Potential

We should measure the business using four separate economic categories:

1. **Direct context service ARR:** separately contracted product revenue.
2. **Partner or OEM ARR:** net recurring revenue distributed through platform partners.
3. **Storage and Data Intelligence pull through:** influenced bookings, reported separately.
4. **Retained ARR:** renewals or expansions where the capability materially influenced retention.

Only direct and partner revenue should count as core product ARR. Storage pull through and retention impact should not be double counted.

The market model should be bottom up and connected to adoption milestones. An illustrative base case is:

* Three to five customers in year one.
* Forty to seventy-five direct and partner customers in year two.
* Approximately 250 direct customers and 100 partner sourced customers in year three.
* Approximately $150 million of year three core product ARR.

Approximately $500 million of year three ARR should be presented as a bull case that requires materially higher penetration, ACV, and partner distribution. It should not be presented as the expected outcome.

The detailed assumptions are included in Exhibit B.

## 8. Risks and Strategic Options

The largest risk is that enforcement platforms will not consume third party context beyond basic classification labels. We should test this before scaling the organization.

Other material risks include:

* Platform vendors building sufficient context internally.
* Data context becoming a commodity feed.
* Insufficient context freshness or coverage.
* Customers refusing a new component in the runtime path.
* Partner economics failing to support distribution.
* Difficulty establishing ground truth for decision quality.
* Long enterprise security and procurement cycles.

The architecture should minimize runtime dependency through signed, locally distributed context projections. Customers should be able to configure behavior when context is missing or stale, including restrict, escalate, deny, or use last known context. Fail closed behavior should not be universal.

A recovery backed warranty should remain a later strategic option. During the first year, we should collect the operating, attribution, recovery, and loss data required to determine whether narrowly defined integrity and availability failures can be economically underwritten.

The initial product must succeed based on better decisions, explainability, evidence, and recovery intelligence. It should not depend on warranty coverage to establish product market fit.

## Conclusion

Everpure should not attempt to become the universal control plane for enterprise agents.

Our strongest opportunity is narrower and more defensible. We should become the enterprise data context and recommendation layer that helps existing platforms make safer decisions about high risk data actions.

We should begin with destructive actions involving Everpure managed data, where we have the clearest context and recovery advantage. We should expand into sensitive data movement only after proving that customers and partners consume the context, decision quality improves, and independent budget exists.

This approach keeps us neutral, limits direct competition, stages investment behind evidence, and creates a credible path from a differentiated infrastructure capability to a standalone enterprise software business.
