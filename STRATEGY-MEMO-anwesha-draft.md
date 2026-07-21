# Strategy Memo — Principal PM, Enterprise AI & Analytics
*Word count: 2,269 (source list adds ~326).*


Recommendation
 Everpure should build the context-aware runtime decision engine for
enterprise AI agents and ship it as the decision authority every enforcement point calls. Concretely this presents as a signed, sub-50-millisecond service that tells any agent runtime [Arcade, Okta Cross App Access, Entra, AWS Cedar policies] exactly what the data behind an action is in terms of  sensitivity, ownership, lineage, freshness, regulatory class, served live from Data Intelligence's graph1 and what should happen - through a verdict-as-recommendation with the evidence attached, backed by a capped blast-radius warranty. We provide contractual guarantees on any agent actions that we approve  on data we physically hold. Only a company that owns both the semantic graph and the storage substrate can underwrite such a decision. 


The market has already proven the problem — $392M of venture funding around one RSAC [4], a $21B CyberArk
acquisition [5], a Gartner category [6] — so this memo spends its effort where the burden actually
sits: why Everpure is the right company to solve it. Sized honeestly: **~$500M incremental ARR by
year three** (bear ~$240M, bull ~$850M) — Exhibit A shows the math.


Market and customer
Three macro shifts define enterprise AI in 2026, and the opportunity sits where they intersect.


AI is moving from generating content to executing work - The unit of value has evolved from being a supervised copilot to an autonomous assistant. When AI executes work, every execution is a decision point that needs to be rooted in trusted and complete guardrails.


Enterprise data is the primary competitive asset for AI - As models increasingly become  commoditized shared utilities, the focus is back on the fundamental unit of value that drives it all - data. For most enterprises today, this sits fragmented across databases, SaaS, object stores, and even in mainframes for some industries. The scarce input to enterprise AI is known, understood, governed data.


Trust, not model quality, blocks adoption. ~86% of enterprise leaders cite
reliability/security as the top blocker to autonomous agents; two-thirds cite security risk as the
#1 barrier to scaling2. 40% of organizations delayed Copilot rollouts ≥3 months over oversharing
[8]. Gartner predicts 25% of enterprise breaches will trace to agent abuse by 2028 and that half of
agent deployment failures by 2030 will stem from insufficient *runtime* enforcement [6]. The EU AI
Act's high-risk obligations — automatic lifetime logging, meaningful oversight — bite August 2,
2026 [9]. Governance is becoming a runtime property.


The shifts intersect the moment an agent touches enterprise data. At that
moment the enterprise must answer four questions. (1) Who is acting, (2) Whether policy permits the action. (3) What the action scope is at runtime for the data/artifacts the agent touches and (4) What if the decision was wrong. Across the industry, players are trying to solve for these at different layers. And all these questions are at different maturity levels of being answered. Most enterprises are stuck between agent pilots and production under the weight of these questions. Everpure has a unique position to answer the final two questions from a holistic data perspective with Everpure Enterprise Data Cloud and Everpure Data Intelligence.


Competitive landscape
The competitive landscape around runtime governance is well funded and  is converging around the goal of providing trusted context for enterprise AI. But competitors are approaching it from fundamentally different starting points.
 Identity vendors such as Microsoft Entra, Okta, and CyberArk focus on **who** is acting, managing authentication, delegated permissions, and machine identities. 
Data security vendors such as Cyera, BigID, Securiti, Varonis, and Sentra focus on **what** the data is, building data inventories, classification, governance, privacy controls, and AI security posture. 
Agent security companies including Zenity, Noma, and WitnessAI focus on **what the agent is doing**, providing runtime visibility into AI agents, tool invocations, permissions, and execution behavior. 
Data platform vendors such as Snowflake (Horizon Catalog) and Databricks (Unity Catalog) are building semantic catalogs, lineage, governance, and AI context, but primarily within their respective analytics and lakehouse ecosystems. Microsoft Purview similarly provides governance and business context across the Microsoft estate. Where they fall short is that the breadth of data they have visibility over is constrained to their slice of the  enterprise  data.  




These existing initiatives and associated funding prove the problem is real. And here the burden shifts to right-to-win.
Most however have a blindspot when it comes to the most decisive input that is cross enterprise context. No decisionplane anywhere consumes lineage, ownership, business meaning, freshness, or regulatory class at decision time [12]. The failure record shows that is exactly what breaks: in  March 2026 Meta had an incident where the agent "held valid credentials and cleared every identity check" but still exposed internal data for two hours [14]; 97% of AI-related breaches involved organizations lacking AI access controls [15]. These are missing-context failures, not missing-identity failures.


Everpure's opportunity is differentiated: rather than competing as another identity provider, DSPM vendor, or agent security platform, it can become the Enterprise context infrastructure  that sits beneath them all. By combining storage-native visibility with 1touch's enterprise context graph, semantic enrichment, lineage, and governance across databases, SaaS, object stores, mainframes, cloud, and on-premises environments, Everpure can provide a vendor-neutral source of enterprise context that feeds policy engines, runtime authorization platforms, AI agents, analytics systems, and security products alike. In this model, identity platforms continue to establish *who* is acting, agent security platforms observe *how* agents behave, policy engines determine *whether* an action should be allowed, and Everpure provides the rich enterprise context that enables all of those systems to make more intelligent, explainable, and consistent decisions.


Microsoft, Snowflake, Databricks, and Salesforce all have an incentive to make their own context layer the authoritative one within their ecosystems so Everpure's success depends on proving two things: Breadth: It can see and understand enterprise data that those platform-specific context layers cannot (especially across storage, mainframes, SaaS, and heterogeneous environments). Neutrality: It isn't trying to replace identity providers, policy engines, or runtime security products. Instead, it provides a vendor-neutral context service that all of them can consume.
If Everpure can establish itself as the universal cross-enterprise source of contextual truth, then Zenity, Noma, Microsoft Purview, OpenFGA, Cedar, and others become integration partners rather than direct competitors. Specifically for something as precarious and important as autonomous AI execution,  external providers are unlikely to gain enterprise trust to take over the decision-making process. The more long lived platforms would emit proprietary signal to policy engines as opposed to owning the  verdict itself.. 


## 3. The bet
Everpure has the opportunity to extend its position in enterprise data infrastructure into a trusted decision layer for AI actions involving enterprise data. Unlike application-layer platforms that understand only the data within their own ecosystems, Everpure can combine cross-enterprise context with customer-defined policies to inform runtime decisions about whether an agent action should be allowed, denied, restricted, or escalated. This universal context infrastructure could become a durable strategic moat, supplying high-value decision signals to enterprise security and runtime platforms while those systems apply customer-specific constraints and retain final enforcement.


The Data Intelligence Enterprise Context Graph would feed a semantic and policy-evaluation layer that considers the relevant identity, delegation, data, destination, purpose, lineage, and risk parameters described in Appendix A. The service would return an explainable recommendation with reason codes and cryptographically signed evidence. Consistent with the principle of proportional governance, routine, low-sensitivity actions would be evaluated at low latency using locally replicated, fail-closed context and policy bundles, while high-risk actions, stale context, or exceptional cases would require a fresh online evaluation or human approval. Existing agent runtimes, identity systems, policy engines, and security platforms would retain the final decision and contractual veto, allowing Everpure to provide differentiated contextual reasoning without replacing the platforms that execute or block the action.


Where Everpure manages the underlying data and controls the recovery mechanism, eligible approved actions could carry a limited, insurance-backed warranty covering defined restoration costs and recovery or availability failures caused by reversible destructive actions such as bulk deletion, overwrite, encryption, recovery-point modification, or destructive dataset operations. Every evaluation would also produce a signed attestation recording the agent, action, data classification, recommendation, policy basis, context version, conditions, and supporting evidence. This would create a portable record for audits, incident investigations, insurance claims, and regulatory traceability.


The combination of proprietary enterprise context, explainable runtime recommendations, signed evidence, recoverability, and bounded risk transfer would differentiate Everpure from data-intelligence vendors that lack comparable visibility across enterprise data or direct control over the underlying recovery mechanisms.




Appendix a
the human principal, agent identity, delegated authority, tool, requested action, affected data, destination, business purpose, sensitivity, ownership, lineage, and relevant organizational relationships,


## 4. Go-to-market
GTM Principles
Keep the initial scope narrow enough to prove Everpure's differentiated advantage in observing, protecting, and recovering enterprise data before expanding into broader agent actions.
Use the installed base to prove the product, the existing field organization to gain access, specialist sellers to establish the category, and platform partners to scale distribution.
Use Everpure's existing commercial relationships and renewal processes to simplify procurement, while packaging runtime decisioning, signed evidence, advanced integrations, and eventual warranty coverage as a separately priced add-on.
Treat independent budget from security and AI-platform teams as a core validation criterion. If customers value the capability only as part of a storage renewal, it has not yet established itself as a standalone decision product.
Position agent runtimes, identity systems, policy engines, and security platforms as customers and distribution partners rather than competitors. These platforms provide the interception and enforcement points, while Everpure supplies the enterprise context, recommendations, reason codes, and evidence that make their decisions more accurate and defensible.
Phased Rollout
Focus the initial product on reversible, data-centric actions where Everpure has a structural advantage, including bulk deletion, overwrite, encryption, recovery-point modification, destructive dataset changes, and movement of governed data into unapproved locations.
Use existing account teams to identify suitable pilot customers. Begin with two or three paid design partners from Everpure's installed base, prioritizing customers that already trust Everpure with critical data and are actively deploying AI agents against that data. Specialist AI-security and data-governance resources should lead discovery, solution design, and engagement with security, data, and AI-platform stakeholders.
Integrate with one agent runtime or MCP gateway within a shared customer deployment and use the pilot to validate decision quality, latency, context freshness, explainability, enforcement behavior, recoverability, and willingness to pay.
Convert successful pilots into repeatable deployment patterns, reference architectures, customer proof points, and clearly defined product packaging.
Expand distribution through agent runtimes, identity systems, authorization engines, and security platforms once the design-partner phase demonstrates repeatable value.
Introduce a limited, insurance-backed recovery warranty after Everpure has collected sufficient operating and loss data to define coverage, eligibility requirements, exclusions, pricing, and recovery obligations.




5. Build, Partner, or Acquire
Strategic Rule
Own the differentiated context, decision, evidence, and recovery capabilities; partner for enforcement; and acquire further up the stack only after customer consumption validates the need.
Build
Build the capabilities that depend on assets Everpure uniquely controls:
The context-driven decision-serving layer
The signed evidence plane
The recovery-backed warranty for eligible actions involving Everpure-managed data
Keep the product centered on Everpure's differentiated advantages in enterprise context, data protection, recoverability, and accountable decisioning.
Partner
Partner for enforcement with agent runtimes, MCP gateways, identity platforms, authorization engines, and security products that already own the interception point and final allow-or-deny decision.
Provide these platforms with enterprise context, recommendations, reason codes, and signed evidence while allowing them to apply customer-specific constraints and retain the final veto.
Avoid building a proprietary inline runtime initially. Doing so would introduce a new buyer, require Everpure to operate within a highly available execution path, and create direct competition with specialist vendors without a clear structural advantage.
Acquire
Preserve the option to acquire an agent-runtime or enforcement company after approximately 12 months.
Pursue an acquisition only if production usage demonstrates that owning the runtime would materially improve product control, economics, or distribution.
Evaluate the acquisition against clear consumption signals, including:
Meaningful production decision volume
Independent security or AI-platform budget
Strong customer demand
Successful partner adoption
Evidence that runtime ownership would improve margins, adoption, or product performance
Allow any acquired security or runtime business to retain specialist leadership and sufficient operating autonomy to serve its distinct buyer and product category.
Do Not Build
Generic AI gateways or proxies
Prompt-injection detection and general-purpose AI guardrails
Agent identity and lifecycle management
Other capabilities where established runtime, security, or identity vendors have stronger structural advantages




6. One-Year Plan
H1: Build and validate
During the first two quarters, we will build the runtime decision-serving layer on top of the existing Data Intelligence graph and APIs. The initial system will support signed decision outputs, locally distributed fail-closed bundles, and a target p95 decision latency below 20 milliseconds for routine actions.
We will recruit two design partners: one agent runtime or MCP gateway that can intercept actions, and one authorization platform that can consume Everpure context as attributes or relationship data. These partnerships will validate the complete decision path from enterprise context through policy evaluation to final enforcement.
The central H1 experiment will measure whether Everpure's context materially improves decision quality. We will evaluate identical agent traffic using both context-enriched and context-blind policies, then compare false allows, false denies, latency, explainability, and override rates. This will establish whether the enterprise context graph produces better decisions rather than simply adding more metadata.
We will also launch the signed attestation feed during H1. Each evaluation will produce a portable record of the agent, action, recommendation, policy basis, context version, and supporting evidence. This will create immediate value for audits, incident investigations, insurance, and emerging regulatory traceability requirements without tying the launch to a single regulatory deadline.
In parallel, we will work with an insurance partner to define the eligibility requirements, exclusions, pricing model, loss data, and recovery obligations required for a future warranty.
H2: Commercialize and scale
During quarters three and four, we will make the decision engine generally available with published service-level objectives for availability, latency, context freshness, and evidence delivery.
Our initial commercial target is at least three paying production customers whose purchases come from security, AI-platform, governance, or data-protection budgets. This will validate that the capability has independent value beyond the existing storage relationship.
We will package the decision service, signed evidence, advanced integrations, and eligible recovery guarantees into a clearly defined commercial offering. Customers will be able to transact through the existing account and renewal process, while the product remains separately priced.
At month 12, we will decide whether owning an agent runtime or enforcement platform would materially improve product performance, economics, distribution, or customer adoption. We will consider an acquisition only if production usage, partner demand, decision volume, and independent customer budget support moving further up the stack.
Team and operating model
The existing 1Touch team will remain focused on discovery, classification, lineage, and the enterprise context graph. A dedicated platform team of approximately 25 engineers will build and operate the runtime decision-serving layer, supported by product, security, compliance, and product-marketing resources that understand security and AI-platform buyers.
We will treat this as a new investment rather than a reorganization of existing teams. The runtime decision service will require dedicated ownership of low-latency serving, policy integration, evidence generation, observability, reliability, and partner integrations.
Year-one success criteria
By the end of the first year, we will demonstrate that:
The decision service meets its latency and availability targets.
Enterprise context measurably reduces false allows and false denies.
Agent runtimes and authorization platforms can integrate with the service.
Security and AI-platform teams are willing to pay for the capability independently.
Signed attestations provide meaningful audit and incident-response value.
Recovery-backed use cases can be defined narrowly enough to support future warranty coverage.
Customer demand supports further investment in, or acquisition of, the runtime layer.


7. Metrics and Falsification
The central unproven assumption behind this strategy is that enterprise security and runtime platforms will use third-party context richer than a basic sensitivity label when making real-time decisions. We will test that assumption directly during the first two quarters. Each test has a predefined success threshold and a clear fallback if the threshold is not met.
1. Context consumption
Success means at least two production enforcement points use Everpure attributes beyond sensitivity labels—such as lineage, ownership, freshness, regulatory classification, or approved destinations—as inputs to an active runtime policy.
If we do not meet this threshold, we will conclude that customers value the graph primarily as an inventory and classification system. We will narrow the product to context feeds, labels, governance evidence, and storage-backed execution rather than continuing to invest in runtime decisioning.
2. Runtime architecture
Success means resolving context at partner production volumes with p95 latency below 20 milliseconds, using cached and signed local projections with no synchronous dependency on the Everpure cloud. The deployment must also pass the partner's security and reliability review.
If we cannot meet these requirements, we will conclude that partners will not place Everpure in the runtime execution path. We will move decisioning out of the hot path and focus on catalog-time, policy-authoring, and precomputed governance use cases.
3. Independent customer budget
Success means at least three production customers purchase the capability through security, AI-platform, governance, or data-protection budgets using a pricing model tied to governed assets, protected workflows, or decision consumption.
If customers will pay only through the storage renewal, we will treat the capability as a differentiated storage feature rather than a standalone decision business and package and price it accordingly.
4. Underwriting viability
Success means an insurance partner is willing to price the recovery warranty at commercially viable terms, with acceptable premiums, coverage limits, eligibility requirements, exclusions, and claims obligations.
If the warranty cannot be underwritten economically, we will remove risk transfer from the initial offering while retaining runtime recommendations, signed evidence, recovery integrations, and context feeds.
Decision-quality proof point
The design-partner experiment must also show that context-enriched policies reduce false allows while maintaining equal or lower false-deny rates than context-blind policies on equivalent agent traffic. We will measure recommendation accuracy, override rates, latency, and explainability, and publish the result internally regardless of whether it supports the original thesis.
Together, these tests determine whether Everpure is building a standalone runtime decision business, a context and governance platform, or a differentiated capability within the existing data infrastructure portfolio.




8. Risks
1. Platforms may not consume external recommendations
The highest-risk assumption is that agent runtimes, identity systems, policy engines, and security platforms will accept third-party context and recommendations in their runtime decisions. We will mitigate this by preserving their authority: Everpure will provide context, recommendations, evidence, and eligible risk coverage, while the platform applies customer-specific policies and retains the final enforcement decision.
We will test this assumption early through design-partner integrations. If platforms are unwilling to consume context beyond basic labels, we will narrow the product to governance feeds, signed evidence, and storage-backed controls rather than continuing to invest in runtime decisioning.
2. Data-security platforms may provide substitutable context
Vendors such as Cyera are already extending data-security context into AI and MCP workflows. We will differentiate through the breadth and depth of Everpure's context, including visibility into mainframes and legacy enterprise systems, entity relationships, data lineage, and the underlying data infrastructure.
We will also maintain a neutral posture toward security platforms rather than competing for their full security budget. Our strongest additional differentiator is the ability to connect recommendations to recovery and, where eligible, provide bounded warranty coverage that vendors without control of the underlying data cannot offer.
3. Context may become a commodity feed
If enterprise context is consumed only as labels or attributes, pricing may converge toward commodity data-feed economics. We will protect against this by packaging context with explainable recommendations, signed evidence, recovery integrations, and bounded risk transfer.
If customers do not value the recommendation and accountability layers, we will treat the context service as a lower-margin platform capability and adjust investment and pricing accordingly.
4. The warranty cannot cover confidentiality failures
Some of the most severe AI incidents involve disclosure or exfiltration of sensitive information, which cannot be reversed through snapshots or recovery. We will state this limitation clearly and scope initial warranty coverage to defined integrity and availability harms, such as recoverable deletion, overwrite, encryption, or recovery-point modification.
Confidentiality risks will be addressed through preventive recommendations, policy integrations, and evidence rather than financial guarantees. Clear exclusions will be essential to maintaining trust with security, legal, and insurance stakeholders.
5. Customers may not trust Everpure in the runtime path
A runtime dependency must meet a much higher reliability and security standard than a traditional catalog or management service. Customers and partners may be reluctant to place a storage vendor in the critical path of agent execution.
We will address this through locally replicated, signed, fail-closed decision bundles that avoid a synchronous dependency on the Everpure cloud for routine actions. High-risk or stale-context decisions may require fresh evaluation or human approval, but common execution will remain local. Latency, availability, context freshness, and security-review outcomes will be explicit product gates.
6. The market window may close quickly
Identity, security, cloud, and agent-platform vendors are moving rapidly to establish control over agent governance and runtime enforcement. Everpure's opportunity to define the enterprise context layer may therefore be limited.
We will front-load design-partner integrations and context-consumption tests during the first two quarters. The objective is to determine quickly whether partners value Everpure's context and whether the company can establish a differentiated position before larger platform vendors consolidate the market.
