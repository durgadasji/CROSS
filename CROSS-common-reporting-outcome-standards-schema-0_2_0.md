---
title: CROSS - Common Reporting Outcome Standards Schema
version: 0.2.4
date: 2026-05-15
license: CC0
status: Working draft. Supersedes version 0.1.0. Incorporates comparative research across thirteen grant programs spanning web3, open source, and institutional funding contexts.
related_documents:
  - standards/standards-3_0-adverse-signal-engagement-0_7_11.md
  - standards/standards-3_0-information-asymmetry-0_1_25.md
  - standards/standards-3_0-precision-first-2_1_7.md
  - standards/standards-3_0-regenerative-obligation-0_1_7.md
  - standards/standards-3_0-coordination-scaling-0_1_0.md
companion_documents:
  - standards/CROSS-runbooks-0_1_0.md
  - standards/CROSS-common-reporting-outcome-standards-schema-guidance-0_2_0.md
  - standards/CROSS-common-reporting-outcome-standards-schema-templates-0_2_0.md
  - standards/CROSS-common-reporting-outcome-standards-schema-rubric-0_2_0.md
  - standards/CROSS-common-reporting-outcome-standards-schema-worked-examples-0_2_0.md
implementation_documents:
  - standards/CROSS-grant-configurator-0_2_0.md
  - standards/CROSS-grantee-dashboard-0_2_0.md
  - standards/CROSS-reviewers-dashboard-0_1_0.md
  - standards/claude-skills/claude-skill-CROSS-0_2_0.md
---

# CROSS: Common Reporting Outcome Standards Schema

Version 0.2.4 | 2026-05-15 | CC0

---

## Purpose

CROSS specifies what funded interventions are obligated to demonstrate. It provides grants ecosystems with a portable obligation schema that accommodates multiple obligation modes, calibrates evidentiary pressure to program context, and generates structured reporting data that is comparable across funders, rounds, and grantees.

Version 0.2.0 extends version 0.1.0 in three structural ways. First, CROSS now recognizes three distinct obligation modes: build obligation, change obligation, and retroactive obligation. The Theory of Build is a failure mode only within a change-obligation round; it is a correct and complete specification within a build-obligation round. Second, CROSS introduces a gate architecture with four named gate types whose evidence requirements are configured by the funder and published before any round opens. Third, CROSS introduces a program-level continuation gate that governs progression across rounds and stages, enabling staged program designs of the kind used by major public goods funders.

CROSS is not a process standard. It does not specify how rounds are structured, how funds are distributed, or how funding decisions are made. CROSS specifies the content of obligation: what applicants must demonstrate, what funders must evaluate, what grantees must report, and how evidentiary pressure is structured across the funding lifecycle.

Funder obligation maturation is trackable through CROSS. A funder operating within a conformant program records their gate configuration for each round. Funders who maintain a versioned round record can track gate configurations across rounds, making funder maturation visible to the field over time.

---

## Scope

CROSS applies to any grants program that makes funding decisions based on expected or demonstrated contribution. It is designed for adoption by public goods funders in the web3 ecosystem (Octant, Gitcoin, Stellar Development Foundation, and similar programs) and is portable to grant-making contexts outside web3. Any organization that funds interventions and expects grantees to be obligated to demonstrate results can adopt CROSS independently of any other standard or protocol.

Runbooks providing pre-built configurations for common program types are companion documents to this standard. A funder adopting CROSS may select a runbook as a starting configuration or build a custom configuration from the gate architecture specification in Part IV.

CROSS imposes obligations on concurrent funding attribution as well as on applicants and reviewers. Where concurrent funding is disclosed under Part VI, scope attribution and outcome credit obligations are specified in Part VI-A.

CROSS imposes obligations on funders as well as on applicants, grantees, and reviewers. Funder obligations and redress mechanisms are specified in Part XI.

---

## Part I: Independence and Suite References

CROSS is an independent standard. It is not a document of any specific grants program or protocol. Any grants ecosystem may adopt CROSS in whole or in part without adopting any other standard it references.

CROSS incorporates requirements from the following Coordination Structural Integrity Suite standards by reference. Adopters of CROSS inherit the requirements of these standards in the contexts specified below. They do not need to implement the full Suite to use CROSS.

The Adverse-Signal Engagement Principle Core Standard applies to adverse signal disclosure. Applicants must surface signals that contradict their self-presentation: prior grant rejections from similar programs, contradictory technical findings, negative due diligence results from other funders. Reviewers must not suppress adverse signals surfaced during evaluation.

The Information Asymmetry Classification Standard applies to concurrent funding disclosure. Undisclosed concurrent funding is an omission asymmetry under the Information Asymmetry Classification Standard. The disclosure requirement in Part VI of this standard instantiates the omission class in the grant application context.

The Precision-First Design Standard applies to indicator sourcing and the double-negation invariant. Documentation requirements must not be so light that obligation is absent, and must not be so heavy that legitimate small-team applicants are excluded. The proportionality requirements in Part IV are a Precision-First Design Standard corollary.

The Coordination Scaling Standard governs which evidence tier applies based on the scale and public impact claims of the application. Small technical teams with clear diagnoses do not require the same obligation machinery as large institutional applications. The Coordination Scaling Standard provides the calibration.

The Regenerative Obligation Standard and CROSS are structurally paired. The Regenerative Obligation Standard handles direction: how internal extraction and return mechanics operate within a funding mechanism. CROSS handles destination: what funded interventions must produce. A funding mechanism can satisfy the Regenerative Obligation Standard and fail CROSS, or satisfy CROSS and fail the Regenerative Obligation Standard. These are independent evaluations.

CROSS was developed using Frame Language as a conceptual tool. Frame Language is not a formal dependency of this standard. Adopters of CROSS are not required to use, cite, or license Frame Language.

---

## Part II: Independent Obligation Dimensions

CROSS specifies multiple obligation dimensions. Each dimension has its own triggering logic and its own tier structure. Dimensions do not scale together. A small grant does not automatically receive relaxed standards on all dimensions. A large grant does not automatically receive heavier requirements on all dimensions. Each dimension is assessed independently based on its own trigger.

The following dimensions are specified in this standard. Additional dimensions may be activated by funder configuration through the Grant Configurator.

**Outcome documentation rigor.** Triggered by: funding amount and the scale of the public impact claim. The Coordination Scaling Standard provides the calibration. Small-team applications with specific diagnoses and modest claims require less formal documentation than large institutional applications with broad population impact claims.

**Institutional capacity.** Triggered by: the scope of the proposed work relative to the applying organization's demonstrated track record. A team proposing a \$150,000 multi-year infrastructure project with no prior grant history faces a higher institutional capacity bar than a team with ten years of verified outputs proposing a \$20,000 continuation. Capacity assessment is not a disqualifier; it calibrates the disbursement conditions tier.

**Conflict of interest.** Triggered by: the nature of relationships between decision-makers and applicants, and between applicants and committee members. Three tiers apply: categorical bar (no waiver), qualified waiver, and disclosure-encouraged. Specified in full in Part VII.

**Concurrent funding disclosure.** Triggered by: whether the applicant has active grants, investments, or revenue sources related to the scope of the application in the prior 24 months. Required field for all applications, across all obligation modes. Non-disclosure is a disqualifier; disclosed concurrent funding is not.

**Adverse signal disclosure.** Triggered by: whether any adverse signals exist relating to the application. Applicants must disclose prior rejections from similar programs, contradictory technical findings, and negative due diligence results from other funders. Reviewers must not suppress adverse signals found during evaluation.

**Open source and intellectual property.** Triggered by: whether the funded work produces code, data, research, or other artifacts, and what the public goods claim rests on. For work claiming a public goods benefit through open access to its outputs, those outputs must be demonstrably open at the time of reporting, not only at the time of application.

Where the funded work produces research outputs, models, datasets, or novel technical artifacts for which intellectual property rights are material, the applicant must submit an IP ownership declaration specifying: who holds rights in the outputs, under what terms those rights are held, and what the public's rights of access and use are. The declaration must be specific enough to answer whether a third party could use, fork, or build upon the outputs without seeking permission from any rights holder. An applicant who holds exclusive rights over outputs claimed as public goods must reconcile those rights with the public goods claim in the additionality declaration (Part VI-A). For programs funding decentralized science, AI model development, or research producing novel patentable outputs, the Grant Configurator activates the IP ownership declaration as an explicit gate criterion rather than a supplementary disclosure.

**Beneficiary engagement and beneficiary validation.** Triggered by: whether the application claims to address a problem experienced by a defined population. In change-obligation rounds, the claimed FROM state must be validated by parties outside the applicant's control. In build-obligation rounds, the claimed need for the deliverable must be validated by at least one party outside the applicant's organization who would use or benefit from it.

**Privacy and data sensitivity.** Triggered by: whether the beneficiary population faces elevated risk from standard outcome measurement. For interventions where standard measurement would compromise the safety of the beneficiary population, privacy-preserving measurement methodologies are required in lieu of standard analytics. The accommodation is not an exemption from obligation; it specifies which obligation mechanisms are appropriate to the context.

**Environmental and social impact.** Optional dimension. Activated by funder configuration when the funded work may produce significant, diverse, potentially irreversible, or unprecedented impacts on communities, ecosystems, or cultural heritage. If activated, follows the A/B/C classification structure derived from International Finance Corporation Performance Standards and Green Climate Fund Environmental and Social Policy.

**Gender equity.** Optional dimension. Activated by funder configuration when the funded work affects populations where gender-disaggregated outcomes are material to the public goods claim.

**Procurement integrity.** Optional dimension. Activated by funder configuration when the funded work involves sub-contracting, sub-granting, or re-granting to third parties exceeding 20% of the total award.

---

## Part III: Obligation Modes

Every CROSS-conformant round operates in one of three obligation modes. The mode is declared by the funder in the Grant Configurator before the round opens and published as part of the round specification. Applicants are entitled to know which mode applies before they submit.

The mode determines what the entry specification gate asks, what the completion verification gate requires, and what failure modes are relevant at each gate. A finding that would disqualify an application in one mode may be correct and complete in another.

**Build obligation.** The funded work must produce a specified deliverable. The obligation object is the deliverable itself: does it exist, does it meet the stated completion criteria, and is it publicly accessible? The entry specification asks whether the applicant can name a falsifiable deliverable with independently verifiable completion criteria. The Theory of Build is not a failure mode in a build-obligation round; it is the correct and complete form of specification. An application that describes what it will build, with enough specificity that a reviewer who did not commission the work could verify whether it was completed, passes the entry specification.

Appropriate for: early-stage innovation grants, infrastructure development, tooling and library development, any program where the funder's primary goal is the existence of a public good artifact rather than a measured change in a population's condition.

**Change obligation.** The funded work must produce a measurable change in a defined population. The obligation object is the change itself: did the condition named in the FROM state improve toward the target named in the TO state, as measured by the specified indicator? The entry specification asks whether the applicant can name the FROM state as a specific measurable condition in a defined population. This was the sole gate in version 0.1.0 of this standard; in version 0.2.0 it is correctly scoped to change-obligation rounds.

The Theory of Build is a failure mode specifically in change-obligation rounds. An application that describes what it will build but cannot name the FROM state it addresses has not performed a problem diagnosis. It is not disqualified because it describes building; it is disqualified because it cannot answer the entry specification question for change-obligation: what specific measurable condition, in what defined population, does this intervention address?

Appropriate for: programs seeking measured population-level outcomes, continuation grants where prior epochs established a measurable baseline, programs aligned with institutional impact standards such as development agencies or foundations.

**Retroactive obligation.** The funded work has already produced value, and the funding rewards demonstrated past contribution. The obligation object is the prior contribution itself, assessed against the program's published criteria. The entry specification asks what evidence of prior contribution the applicant presents. No prospective commitment to future deliverables or outcomes is required, though the program may configure a forward commitment as a condition of the award.

Appropriate for: retroactive public goods funding programs, recognition grants for sustained infrastructure maintenance, programs where measuring prospective impact is less reliable than rewarding demonstrated past contribution.

**Application timing is not the diagnostic.** Across all three modes, when a team began their work is not a gate criterion. A team that built something before a grant opportunity appeared and presents it during an application window may be applying for build-obligation recognition of completed work, or may be presenting a baseline for a change-obligation continuation. The diagnostic is whether the entry specification question for the declared mode can be answered, not when the work began.

**Mixed and staged modes.** A multi-stage program may configure different obligation modes at different stages. An early stage may use build obligation; a later stage, after the deliverable exists and is in use, may require change obligation. The continuation gate between stages is the instrument that enforces the transition. The Grant Configurator supports mode assignment per stage.

---

## Part IV: Gate Architecture

Every CROSS-conformant round publishes a gate configuration before the round opens. The gate configuration specifies, for each active gate: the evidence scope requirement, the evidence strength requirement, and the infrastructure declaration confirming how the funder will operate the gate.

Gate configurations are not retrospective. A funder may not apply a higher evidence requirement than was published at round opening. A funder may not waive a published requirement without a documented rationale submitted to a named authority before the gate is reached.

**The four gate types.**

*Entry specification gate.* What an applicant must demonstrate to enter the round. Content depends on the declared obligation mode. In build-obligation rounds: a falsifiable deliverable specification, meaning a description of the artifact to be produced that includes completion criteria specific enough that an independent reviewer could verify whether they were met. In change-obligation rounds: a FROM state specification, meaning a specific measurable condition in a defined population with a named data source. In retroactive rounds: evidence of prior contribution meeting the program's published criteria. The entry specification gate is always present; what it asks depends on the mode.

*Progress verification gates.* What a grantee must demonstrate to trigger mid-funding disbursement tranches. Each tranche disbursement is contingent on verification of progress against the milestone committed at the prior stage. The minimum acceptable evidence at a progress verification gate is a publicly linkable artifact demonstrating work toward the specified deliverable or indicator. Funders may configure higher evidence requirements; they may not configure lower ones. Where no mid-funding disbursement is planned, progress verification gates are not required, and the full obligation weight rests on the completion verification gate.

*Completion verification gate.* What a grantee must demonstrate to receive final payment. This gate cannot be informal. The funder must have a named, published mechanism for determining whether completion criteria have been met. Grantee self-report alone does not satisfy the completion verification gate at any evidence strength level. The funder must review the grantee's submission against the published completion criteria and make a documented determination. For build-obligation rounds, the completion gate must additionally confirm that the specified deliverable is publicly accessible before final payment is released. Final payment may not be released without this confirmation.

*Continuation specification gate.* What a project must demonstrate to advance from one stage to the next in a multi-stage program, or to receive funding from the same funder in a subsequent round. This gate sits above the individual round and is configured at the program level, not the round level. It is the primary mechanism for escalating evidentiary pressure as a project matures. Not all programs require a continuation gate; it is activated by funder configuration. Where configured, the continuation gate must be published before any round in the program opens, so applicants understand the progression requirements before committing to the program.

**Pre-Award Indicator Confirmation**

After the entry specification gate is passed and before first disbursement, funders may configure a pre-award indicator confirmation window. During this window, the funder reviews the indicator specification submitted at entry (Part V) and issues a written confirmation, a revision request, or an escalation to structured clarification. The window must be time-bounded and must not delay first disbursement beyond the published window period.

The purpose of the pre-award confirmation window is to surface indicator specification problems before work begins, when revision is costless, rather than at the completion gate, when it becomes a dispute about whether the work satisfied obligations the funder considers binding. A grantee who receives written confirmation of their indicator specification before work begins has an explicit record of what the funder accepted as sufficient. A funder who confirms an indicator specification and subsequently claims it was insufficient at the completion gate must document the specific discrepancy and the basis on which the confirmed specification was found wanting.

Where a pre-award confirmation window is configured, the following apply:

- The funder must respond within the published window period. Silence at the window's close constitutes confirmation; no additional notification is required.
- Written confirmation or revision request is the required output. Verbal or informal communication does not satisfy this requirement.
- Grantee revisions requested during the window do not affect funding status. Revision requests issued after the window closes are governed by the mid-grant amendment procedure.
- The confirmed indicator specification governs all subsequent gate assessments unless the grant is formally amended.

Where no pre-award confirmation window is configured, the indicator specification submitted at the entry gate governs all subsequent gate assessments, and the funder may not impose requirements at the completion gate that were not visible in the published gate configuration.

**Evidence scope.** The scope of evidence accepted at any gate falls into one of four levels, in ascending order of rigor.

Output evidence: the specified deliverable exists, or a measurable artifact demonstrates progress toward it. Applicable to build-obligation gates. A shipped feature, a deployed contract, a published dataset, a recorded demonstration meeting the specified completion criteria are all output evidence.

Usage evidence: the deliverable is being used by parties outside the applicant's control, at a scale and in a manner that an independent reviewer can verify from public sources. Not all build-obligation programs require usage evidence, but continuation gates in build-obligation programs should require it to confirm that the deliverable has public uptake.

Outcome evidence: a measurable change has occurred in the specified population, documented against the baseline established at entry. Required for completion and continuation gates in change-obligation rounds.

Impact evidence: a credible causal link is established between the funded work and the measured change, through methodology sufficient to support causal inference. Not required in most public goods grant contexts, but may be configured as a continuation gate requirement for large-scale programs with institutional funders.

For on-chain contract and protocol deliverables, output evidence includes not only the existence of the deployed contract but also the existence of a verification artifact demonstrating that the contract satisfies the specified invariant set. Where the obligation object is a behavioral property rather than a discrete output, the verification artifact is part of the output evidence, not only supporting documentation.

**Outcome Verification with Counterfactual Reference**

The default completion verification gate for change-obligation rounds asks whether a measurable change occurred against the baseline established at entry. This is a completion gate: it asks whether the indicator moved in the documented direction by the documented amount. It is not a causal gate: it does not ask whether the intervention produced the change rather than confounding factors.

For programs where causal attribution is material to the funding decision, funders may configure the completion verification gate or the continuation specification gate at counterfactual reference level. A gate configured at counterfactual reference level asks: did the funded intervention produce a change in the specified condition above the level expected in the absence of the intervention?

A grantee submitting evidence at counterfactual reference level must include all of the following as required contract elements:

- **Counterfactual baseline.** A documented estimate of what the indicator value would have been during the grant period without the intervention, derived from one of: historical trend extrapolation from pre-intervention data, a matched comparison group not exposed to the intervention, or a modeled counterfactual with stated assumptions and sensitivity ranges.
- **Attribution argument.** A written account of why the observed change is attributable to the intervention rather than to confounding factors, naming the main alternative explanations and explaining why they are insufficient to account for the observed change.
- **Comparison period or group.** A defined period or population that serves as the counterfactual reference, described specifically enough that an independent reviewer can assess whether it is an appropriate comparison for the intervention context.
- **Independent attestation.** Confirmation from a party outside the grantee organization that the counterfactual method and comparison group are reasonable given the intervention context and available data.

Where a comparison group cannot be defined because the intervention affects an entire ecosystem or operates at a protocol level with universal effects, the grantee must document why a comparison group approach is not feasible and provide a modeled counterfactual with stated assumptions. Absence of a comparison group is not itself a gate failure; absence of a counterfactual estimate and attribution argument is.

Counterfactual reference requirements apply only when explicitly configured by the funder in the gate configuration and declared in the infrastructure declaration. Funders activating counterfactual reference requirements must specify the acceptable counterfactual methods before the round opens. Default gate configurations do not require counterfactual attribution. The requirement is not implied by selecting outcome evidence scope; it is an additional layer that must be activated explicitly.

**Evidence strength.** The verification mechanism at any gate falls into one of four levels, in ascending order of rigor.

Self-report with documentation: the grantee provides a narrative account with supporting links, files, or on-chain data references, reviewed by funder staff against the published criteria. Appropriate for small grants and early-stage progress verification gates.

Third-party verifiable: the evidence is independently accessible to any reviewer with internet access, from sources outside the applicant's control. On-chain data from named public contracts, public repository activity, published results with open data. Appropriate as the minimum for completion verification gates above small grant thresholds.

Independent review: a named party outside the funder-grantee relationship confirms that the submitted evidence meets the completion criteria. The reviewer may be a domain expert, a named committee member not involved in the original award decision, or another funder who has reviewed the same work. Appropriate for continuation gates and for grants above a funder-defined size threshold.

For contract-centric interventions, independent review and independent evaluation may be satisfied by a named external security auditor, formal verification provider, or equivalent qualified reviewer who attests that the submitted verification artifacts and on-chain behavior meet the published completion criteria.

Independent evaluation: a qualified evaluator with relevant domain expertise conducts a structured assessment of whether the funded work produced the claimed output, usage, or outcome, using methods proportional to the evidence scope required. Appropriate for Stage 2 and Stage 3 grants in graduated programs, and for programs where causal attribution is material to the funding decision.

**Infrastructure declaration.** Funders configuring any gate at independent review level or above must declare, before the round opens, the specific mechanism by which that verification will be conducted: who will conduct it, what their qualification is, what process they will follow, and what the timeline for completion is. Declaring a gate at a verification level the funder cannot actually operate is a conformance violation. The infrastructure declaration is part of the published round specification and may not be changed after the round opens without documented justification and notification to applicants.

**Proportionality.** Minimum gate requirements scale with funding amount and program stage. The Coordination Scaling Standard provides the calibration logic. As a baseline: grants below a funder-defined small grant threshold may configure all gates at self-report with documentation level. Grants above the threshold must configure the completion verification gate at no lower than third-party verifiable level. Continuation gates for programs at their second stage or beyond must configure the evidence scope at usage level or higher.

**Cost-effectiveness for continuation.** Where a continuation gate is configured for a change-obligation program, the entry specification for the next stage includes a cost-effectiveness consideration: does the evidence from the prior stage indicate that further investment in this intervention produces meaningful change relative to available alternatives? This is not a disqualifying criterion at first-stage entry; it is a continuation criterion. The Grant Configurator may configure cost-effectiveness as a required or advisory element of the continuation gate.

**External Standard References**

Any gate in a CROSS-conformant program may reference an external standard by URL. Where a gate references an external standard, the funder specifies: the URL at which the standard is published, a human-readable label, a version anchor (a dated access record, version number, or content hash) that identifies which edition of the standard governs, and the scope of the reference (which gate criteria the standard governs: eligibility, evidence quality, methodology, or all gates in the round).

A version anchor is required. Without a version anchor, the referenced standard may change after the gate configuration is published, making the gate undefined. At minimum, the funder must record the date on which the URL was confirmed to contain the standard being referenced. A versioned URL or content hash provides stronger anchoring.

At configuration time, the system confirms that the URL resolves to readable content and extracts a summary of the standard's key criteria for display in the Grant Configurator and the Grantee Dashboard. This confirmation is re-run at each gate if no version anchor is provided. If the URL does not resolve or the content is not substantive, the reference cannot be saved.

For standards that are themselves approved lists of items (for example, the Open Source Initiative approved license list, the Open Definition approved data license list, or the OFAC Specially Designated Nationals list), the reference may specify a list membership check: the funder identifies the list URL, specifies the field or item type to match, and the system confirms membership programmatically against the machine-readable version of the list at the anchored date. Machine-readable approved lists suitable for this use include:

- Software licenses: the SPDX License List JSON at https://github.com/spdx/license-list-data, with an OSI-approved boolean field per license identifier.
- Open content and data licenses: the Open Definition API at https://licenses.opendefinition.org/licenses/groups/all.json.
- Sanctions screening: the OFAC Specially Designated Nationals list XML at https://sanctionslist.ofac.treas.gov/Home/SdnList, updated daily.
- Digital Public Goods registry: the Digital Public Goods Alliance candidate list JSON at https://github.com/DPGAlliance/publicgoods-candidates.

Where a funder references an external standard for the eligibility gate, that standard governs the eligibility determination in addition to any criteria specified directly in the gate configuration. The external standard reference does not replace CROSS's own gate criteria; it adds to them. Reviewers must assess conformance with both.

**Gate Criterion Specification**

The bidirectional precision principle applies to gate criteria as well as to applicant indicators. CROSS Part V requires applicants to specify their outcome indicators with operational definitions, measurement form, construction methodology, and evidence classification. The same precision requirement applies to funders specifying gate criteria. A gate criterion that a reviewer cannot operationalize consistently is a funder-side conformance failure.

Every gate criterion published in a CROSS-conformant round must satisfy the following specification requirements:

- **Criterion intent.** A plain-language statement of what the criterion is measuring or verifying, distinct from the label. "Qualifies as a Digital Public Good" is a label; "the project satisfies DPG Standard Indicators 2, 4, and 5 as specified below" is a criterion intent.
- **Operational definition.** For criteria with defined options or thresholds: what each option or threshold means, with at least one example of a qualifying and a non-qualifying case. Options without definitions produce inconsistent reviewer judgments.
- **Response form.** Whether the criterion is single-select, multi-select, binary, numeric, text, or URL, and the justification for that form. A single-select response form for a criterion that naturally produces multiple valid answers externalizes the cost of ambiguity onto applicants.
- **Evidence form.** The specific artifact or data point that satisfies the criterion: a file in a public repository, a URL resolving to readable content, a named on-chain address, a signed attestation. A criterion satisfied only by reviewer judgment without a named evidence form is not operable at third-party verifiable strength or above.
- **Compliance threshold.** For criteria referencing external standards with multiple sub-indicators: which sub-indicators are required, which are advisory, and whether compliance is all-or-nothing or minimum-subset. A criterion referencing an external standard without specifying which components apply delegates interpretation to reviewers, producing inconsistent outcomes.

For external standard references activated under the External Standard References subsection above, the compliance threshold requirement applies in full: the funder must enumerate which components of the referenced standard are gate criteria, what evidence satisfies each component, and the minimum threshold for gate passage. An external standard reference without a compliance threshold specification is incomplete and must be resolved before the round opens.

The DPG Standard case illustrates the requirement: a gate criterion of "qualifies as a Digital Public Good" is incomplete without specifying which of the nine DPG Standard indicators are required, what evidence form satisfies each (for example, a LICENSE file in a public repository for Indicator 2, a public documentation URL accessible without authentication for Indicator 5), and whether all nine indicators or a specified subset must pass. An incomplete DPG criterion produces reviewer shortcuts (registry membership checked as a proxy for the nine-indicator assessment) that the funder cannot detect or audit after the fact.

---

## Part V: Indicator Specification

Applicants self-specify their outcome indicators across all obligation modes. CROSS does not pre-specify what outcomes or deliverables are valid for a given funding domain. The funder specifies eligibility criteria. The applicant specifies what their intervention produces within that domain. CROSS specifies the fields that self-specified indicators must contain and the quality standards those fields must satisfy.

Each claimed indicator requires the following fields.

**Indicator name.** A short descriptive label. The name is not the operational definition; two funders may use the same indicator name with different operational definitions.

**Rationale for indicator.** Why this indicator was selected over available alternatives. Documents the diagnostic thinking that preceded tool selection. Mandatory across all obligation modes. An applicant who cannot articulate why they chose this particular indicator, deliverable definition, or evidence form over obvious alternatives has not engaged seriously with whether their obligation instrument is valid.

**Measurement form and evidence classification.** A plain-language description of what a result looks like and in what form it will be reported. This field replaces the prior constrained list of four data types, which was calibrated only for quantitative change-obligation indicators.

The applicant names the measurement form in plain language: a count of unique addresses, a shipped library version, a published dataset with a named license, a binary yes/no against defined completion criteria, a scored assessment on a defined scale. Reviewers classify the stated form against three axes for data quality assessment purposes.

Source type: on-chain verifiable (accessible from public blockchain data with a named contract or address), off-chain verifiable (accessible from public sources outside the blockchain, such as a public code repository, a published report, or a named application programming interface), or qualitative/narrative (documented through structured narrative, interview data, or artifact review requiring a human evaluator). Each source type carries different minimum verification requirements at the data quality assessment stage.

Measurement form: quantitative (expressed as a number, proportion, rate, currency amount, or duration), ordinal (expressed as a position on a defined ordered scale), binary (expressed as met or not met against named completion criteria), or qualitative (expressed as a documented condition, verified artifact, or narrative record assessed against named criteria).

Aggregation type: cumulative (values sum correctly across reporting periods) or non-cumulative (values describe a state at a point in time; summing across periods is a construction error). Reviewers must flag a non-cumulative indicator presented with a cumulative target at the application stage, not the reporting stage.

For build-obligation indicators: the measurement form is typically binary (the deliverable either meets the completion criteria or does not) or qualitative (the deliverable is a documented artifact assessed against named criteria). The measurement form declaration specifies what done looks like with enough precision that a reviewer who did not commission the work could verify it independently.

For change-obligation indicators: the measurement form is typically quantitative or ordinal. The declaration must include the unit of measurement and the direction of desirable change.

**On-Chain Execution and Verification Instruments.** For interventions where the primary deliverable is a smart contract, protocol, or on-chain system, the obligation object may be the contract's behavior under specified conditions rather than discrete artifacts or counts. In these cases, the indicator's measurement form and evidence classification must explicitly name the execution and verification instruments that will be used to confirm completion.

An execution and verification instrument is any mechanism that provides structured evidence about contract behavior or protocol properties, including but not limited to:

- Formal verification artifacts (machine-checkable proofs and their specifications).
- Independent security audits and review reports.
- On-chain invariant monitors or watchdog contracts.
- Canonical transaction patterns or state transitions on named contracts, observable from public blockchain data.

Where the obligation object is a contract's behavior, the indicator specification must additionally contain:

- **Invariant specification.** A narrative description of the invariants or properties the contract must satisfy (for example, conservation of balances, absence of re-entrancy on named functions, bounded slippage for a specific operation). This description is the human-readable counterpart of the formal specification used in verification tools.
- **Verification method.** A statement of whether the invariant will be assessed by formal verification, independent audit, manual review of on-chain behavior, continuous monitoring, or a combination. If formal verification is used, the named tool or approach must be specified (for example, model checking, theorem proving, or a named framework).
- **Verification artifact.** The concrete artifact that constitutes completion evidence: a proof object, an audit report from a named firm, or a named contract and query that a reviewer can use to reproduce the behavioral check from public chain data.
- **Failure surface.** At least one example of behavior that would constitute a failure to meet the invariant, and how such a failure would be detected by the chosen instrument.

For build-obligation indicators in contract-centric projects, the measurement form may be binary ("the contract satisfies the specified invariant set as demonstrated by the named verification artifact") rather than a count of outputs. The operational definition and construction methodology fields must still enable an independent reviewer to reproduce the verification procedure or validate the artifact from public sources.

Indicators that rely solely on applicant-controlled test suites or private monitoring dashboards, without any independent verification instrument, fail the integrity standard. They may appear as supplementary evidence but do not satisfy the minimum verification requirement at the completion gate for contract-centric deliverables.

**Operational definition.** A narrative specification of what counts and what does not count as one unit of the claimed result. Must include: inclusion criteria (what qualifies as one instance), exclusion criteria (what the indicator explicitly does not count), unit of analysis (person, wallet address, transaction, repository, site, or other named unit), and edge case determination (at least one example of how an ambiguous instance is handled). Without an operational definition, the claimed indicator is a name, not a measurement instrument.

**Construction and aggregation methodology.** The calculation rule in sufficient detail that an independent reviewer with access to the stated data source could replicate the result. Must include the formula or counting rule, how partial data is handled, and how values from sub-units are aggregated. For build-obligation indicators, the construction methodology specifies how completion is determined: what constitutes a passing demonstration, who performs the verification, and by what process. For change-obligation indicators, this is the standard data construction methodology. Self-report of a result without a stated construction methodology does not satisfy this field.

**Cumulative or non-cumulative.** Whether the indicator is cumulative (can be summed across reporting periods; life-of-grant target is achieved by addition) or non-cumulative (measures a status at a point in time; life-of-grant target is the target status at grant end, not a sum of period targets).

**Disaggregation.** The categories by which indicator values will be reported. Disaggregation categories committed to in the application may be supplemented in subsequent reporting periods but may not be removed without committee approval and documented rationale. This constraint protects longitudinal comparability.

**Data source and collection method.** The named source and the collection method. The source must be accessible to an independent reviewer. Applicant-controlled sources without named independent corroboration do not satisfy the integrity standard. For build-obligation indicators, the data source for completion verification is the named artifact itself plus the named party who will confirm it meets the completion criteria.

**Data cost estimation.** Attestation that data collection is operationally feasible within the project budget, with the approximate cost and source of funding for collection. An indicator that cannot be collected within the project budget has not been operationalized.

**Baseline (FROM state).** For change-obligation indicators: the documented state of the condition before the intervention begins, with a named data source. Required. For build-obligation indicators: the documented current absence or inadequacy of the deliverable, with named evidence of the gap it addresses. Required where the funder has activated the beneficiary engagement dimension. For retroactive indicators: the documented state of the contribution at the time the award period begins.

**Target (TO state).** The expected state of the indicator at the end of the grant period or stage. For change-obligation indicators: expressed in the same units as the baseline. For build-obligation indicators: expressed as the completion criteria the deliverable must meet. For retroactive indicators: may describe a forward commitment the awardee makes as a condition of the award, if configured by the funder.

**Sustainability and transition plan.** Optional field, activated by funder configuration. Required for grants above a funder-defined size threshold or grants producing infrastructure, software, or services with ongoing operational requirements beyond the grant period. The sustainability and transition plan specifies:

- What happens to the funded work at the end of the grant period: who maintains it, under what conditions it remains publicly accessible, and what operational costs are required to sustain it.
- How those costs will be covered after the grant ends, naming the expected source (self-funding, successor grant, revenue, community contribution, or protocol treasury) with enough specificity that a reviewer can assess plausibility.
- Where the funded work will be handed to another organization, community, or protocol: the identity of the receiving party and the conditions of the transition.
- Where the funded work reaches a defined end state after which maintenance is not required: a specification of that end state and the conditions under which it will be declared reached.

A grant producing infrastructure with ongoing operational requirements that provides no sustainability plan has not addressed whether the public benefit it claims will persist beyond the grant period. The sustainability and transition plan is not a guarantee; it is a documented position on continuation that the funder may use in subsequent continuation gate assessments.

---

## Part VI: Concurrent Funding Disclosure

All active grants, investments, or revenue sources from the prior 24 months that are related to the scope of this application must be disclosed. Required across all obligation modes. Required fields:

- Source name (investor, foundation, decentralized autonomous organization, protocol, or other)
- Approximate amount
- Relationship to this application's scope
- Whether ongoing reporting or milestone obligations to the source exist
- Whether any investor or funder has board, coordinating, or decision-making rights over the funded work

Non-disclosure of concurrent funding is a disqualifier. Disclosure is not. An applicant with venture capital backing can receive public goods grant funding if the relationship between commercial financing and the public goods ask is clear and the public goods ask is specifically scoped to work the commercial funding does not cover.

---

## Part VI-A: Scope Attribution and Outcome Credit

CROSS distinguishes between disclosure of concurrent funding (Part VI) and attribution of results to specific funding sources. This Part specifies how scope attribution and outcome credit are handled when concurrent funding is present. It applies across all obligation modes and all gate types where outcome or usage evidence is required.

Scope attribution and outcome credit obligations are triggered when the concurrent funding disclosure requirement in Part VI is triggered. Where no concurrent funding exists, this Part does not apply.

### 1. Additionality Declaration (Budget Scope)

Where concurrent funding is disclosed at application stage, the applicant must submit an additionality declaration for this award. The additionality declaration specifies what this grant funds that concurrent sources do not.

The additionality declaration is a required field in the entry specification for any application with concurrent funding, across build, change, and retroactive obligation modes. Failure to submit an additionality declaration when concurrent funding is disclosed is a gate failure at entry.

The additionality declaration must contain:

- **Scope boundary.** A narrative specification of the work, deliverables, or costs funded by this grant that are not funded by any concurrently disclosed source. The boundary must be specific enough that a reviewer can determine whether a proposed activity lies inside or outside this grant's scope.
- **Overlap statement.** A brief statement of where overlap exists between this grant and concurrent sources, if any, and how double funding of the same input is avoided in practice.
- **Assurance of non-duplication.** An attestation that the applicant will not knowingly charge the same cost to multiple funders, and that any material changes in concurrent funding affecting this assurance will be reported at the next gate.

For build-obligation applications, the additionality declaration specifies which parts of the deliverable or which development stages this grant covers relative to other funders.

For change-obligation applications, the additionality declaration specifies which portion of the intervention pathway (activities, geography, population segment, or time period) this grant is funding relative to other funders.

For retroactive applications, the additionality declaration specifies whether the prior contribution has already received retroactive awards from other programs and what forward-facing obligations, if any, this award uniquely creates.

### 2. Outcome Credit Attribution (Reporting Stage)

Where concurrent funding is disclosed and outcome or usage evidence is required at a completion verification or continuation gate, the applicant must submit an outcome credit attribution statement alongside their results. This requirement applies to any gate configured at usage, outcome, or impact evidence scope in Part IV.

The outcome credit attribution statement must contain:

- **Attribution fractions.** A declared percentage allocation of the reported result across all funders that materially contributed to it, including this program. Percentages must sum to 100 percent across named funders and, where relevant, a residual category for un-funded or self-funded contribution.
- **Attribution rationale.** A short narrative explaining how the attribution fractions were determined. The rationale must name the main factors used (relative funding amounts, timing, specific work packages funded, or other relevant distinctions) and acknowledge material uncertainties.
- **Change tracking.** If attribution fractions change between reporting periods for the same indicator, the applicant must document the reason for the change and its implications for comparability of prior periods.

The attribution requirement is a documentation obligation, not a causal proof requirement. The failure mode is absence of a declared attribution position where concurrent funding exists, not imprecision in the fractions themselves. Reviewers assess whether an attribution statement is present and coherent with the additionality declaration and the indicator specification.

### 3. Gate-Level Consistency

Reviewers must assess consistency between:

- The concurrent funding disclosure (Part VI)
- The additionality declaration (Section 1 of this Part)
- The indicator specification (Part V)
- The outcome credit attribution statement (Section 2 of this Part)

Inconsistencies that must be flagged at the rigor tier include:

- An additionality declaration that asserts unique funding for work that, by the applicant's own description, is also fully funded by another source.
- An outcome credit attribution statement that assigns 100 percent of outcome credit to this funder where multiple concurrent funders are disclosed for the same scope and time period.
- Material changes in attribution fractions across periods without documented rationale.

These are rigor-tier failures, not automatic gate failures. Review committees may request clarification or revision before making a final determination.

### 4. Program-Level Continuation Gate Option

Programs that configure a continuation specification gate in Part IV may activate a scope attribution check as part of the continuation criteria. Where activated, the continuation gate must specify:

- Whether a public prior-claims registry or equivalent record will be consulted to determine whether the same outcomes have been previously claimed in other programs.
- How inconsistent or conflicting attribution statements across funders will be handled in continuation decisions.
- Whether a minimum standard for attribution coherence (for example, stable fractions over time for the same indicator absent documented changes in the funding mix) is required for advancement to the next stage.

Activation of the scope attribution check at continuation is optional at Stage 1 and required for programs whose Grant Configurator specifies Stage 2 or above, consistent with the cost-effectiveness and maturation logic in Part IV and the Appendix.

### 5. Relationship to Concurrent Funding Disclosure

Concurrent funding disclosure in Part VI is a public documentation requirement. The additionality declaration and outcome credit attribution requirements in this Part are obligation requirements. Disclosure alone is not sufficient for CROSS conformance where concurrent funding exists.

Non-disclosure of concurrent funding remains a disqualifying integrity failure under Part VI. Submission of a materially incomplete or incoherent additionality declaration or attribution statement is a rigor-tier failure under this Part, subject to remediation where feasible.

---

## Part VII: Conflict of Interest Framework

The conflict of interest framework applies independently from the outcome documentation rigor tier and independently from the obligation mode. A small-grant build-obligation round does not receive relaxed conflict of interest requirements. Relationship type, not funding amount or mode, determines conflict of interest tier assignment.

**Coverage.** Conflict of interest obligations run in both directions. Reviewers must disclose relationships to applicants. Applicants must disclose relationships to committee members and reviewers.

**Governing standard.** The reasonable third party standard applies: would an informed observer with knowledge of the relevant facts conclude that the person cannot maintain independence and is therefore not capable of exercising objective and impartial judgment? The checklist below illustrates the standard; it does not exhaust it. Novel relationship types not on the checklist that meet the reasonable third party standard require disclosure.

**Tier 1: Categorical bar. No waiver.**

- Direct financial interest in the applicant entity, including equity, revenue share, or token holdings above the materiality threshold (default: greater than 1% of circulating supply or greater than \$5,000 in value at time of review)
- Family relationship with any principal, director, officer, or owner of the applicant project
- Prior receipt of funding from this funder in the same program area where the reviewer's funded work is directly related to the applicant's scope
- Being named as a team member, advisor, or contributor on the applicant project's public materials, whether compensated or not

**Tier 2: Disclosure required. Qualified waiver possible.**

A qualified waiver requires: (a) a written justification submitted to a named authority other than the conflicted party, (b) approval granted before participation, not after, and (c) documentation in the review record. Waiver is not available where the relationship creates a financial interest.

- Employment with the applicant organization in the past 36 months
- Co-authorship or active project collaboration with applicant principals in the past 48 months
- Mentor or student relationship with applicant principals (no expiration)
- Governance token voting power exercised on proposals affecting the applicant project
- Decentralized autonomous organization co-membership in coordinating or committee roles within the same decentralized autonomous organization as the applicant
- Having received an honorarium, award, or gift from the applicant entity in the past 12 months
- Active job negotiations or arrangements for future employment with the applicant organization
- Organizational conflict: the reviewer's employer has a material financial relationship with the applicant

**Tier 3: Disclosure encouraged. Reasonable third party standard applies.**

- Social and community relationships (conference co-speakers, forum co-membership, shared group chats)
- Prior interactions across grant rounds in different program areas
- Informal mentorship or advisory conversations without ongoing engagement

**Web3-specific categories.**

The following relationship types require the same three-tier assessment but are not present in standard conflict of interest frameworks developed outside web3: token holdings (see Tier 1 materiality threshold), governance token voting on applicant proposals, core contributor or unpaid advisory status on applicant projects, having received investment from the same named investor backing the applicant, and decentralized autonomous organization co-governance roles.

**Process.**

Before review: each reviewer and each applicant completes a conflict of interest declaration covering all three tiers. The declaration is submitted to a named receiving function that is separate from the person making the funding decision. In programs using the CROSS Reviewers Dashboard, the conflict of interest declaration is enforced as a gate: a reviewer who has not completed their declaration for a specific application cannot open that application.

After review: each reviewer completes a post-participation certification confirming that no new conflicts arose during the review process and that the declaration remained accurate.

Non-disclosure of a Tier 1 conflict is a disqualifying violation. Non-disclosure of a Tier 2 conflict is a process violation requiring remediation. Remediation options are: retroactive recusal, review restart with a non-conflicted panel, or award cancellation, depending on the degree of influence the conflicted party had.

---

## Part VIII: Data Quality Standards

The following five standards apply to the indicator specification across all obligation modes. Reviewers apply them during gate assessment. Each standard has its own assessment question and failure mode.

**Validity.** The measurement instrument must have a documented logical chain from the evidence collected to the result level claimed. Assessment question: could an independent reviewer, given the stated source and construction methodology, confirm that the indicator measures what it claims to measure? Validity failure: the reported metric is downstream of unmeasured confounders, or the completion criteria named for a deliverable are insufficient to determine whether the work was done.

**Integrity.** Evidence collection and reporting must be separated from the actor who benefits from the results. A named independent verification mechanism is required. Assessment question: does any evidence for this claim originate from a source independent of the applicant? Integrity failure: all evidence originates from applicant-controlled systems with no independent corroboration.

**Precision.** The measurement method must be capable of detecting changes at the magnitude the project claims to produce, or confirming completion at the specificity the criteria require. Assessment question: is the measurement or verification instrument precise enough to support the claimed result? Precision failure: completion criteria so vague that any output satisfies them; or a change claim smaller than the variance of the measurement instrument.

**Reliability.** The measurement instrument and collection methodology must be consistent across reporting periods. Assessment question: if this project submitted a prior report using a different metric, methodology, or completion criteria for the same indicator, is the change documented and the comparability of prior periods determined? Reliability failure: different criteria or metrics reported in different periods without explanation.

**Timeliness.** Evidence must be current to the reporting period. Assessment question: does the collection frequency match the funder's decision cycle? Timeliness failure: annual data collection where quarterly disbursement decisions depend on current data; or a completion claim based on work from a prior period not covered by the current gate.

---

## Part IX: Implementation Architecture

CROSS is implemented through four operational tools. The standard specifies what is required. The tools make the standard usable without requiring funders, grantees, or reviewers to interpret the full specification directly.

**CROSS Grant Configurator** (CROSS-grant-configurator-0_2_0.md): the funder onboarding instrument. Generates a round-specific obligation specification from the funder's declared obligation mode, gate configuration, evidence requirements, and infrastructure declarations. Inherits all field definitions, tier logic, and conflict of interest requirements from this standard. The configurator also supports program-level configuration: the continuation gate structure and stage progression requirements are specified here, separately from individual round configuration. Runbook configurations may be selected as a starting point and customized.

The Grant Configurator records whether concurrent funding is present and, where it is, activates the additionality declaration and outcome credit attribution requirements specified in Part VI-A. These parameters are published alongside gate configurations so applicants understand both their obligations and their methods for recording attribution.

The Grant Configurator records external standard references for each gate, including the URL, version anchor, scope, and machine-readable list membership check parameters where applicable. These parameters are published alongside gate configurations so applicants and reviewers can confirm the standards in force for each gate.

The Grant Configurator also records the program's funder-side obligation configuration: internal clarification mechanism, structured appeals procedure, and whether an independent redress mechanism is operated. These parameters are published alongside gate configurations so applicants understand both their obligations and their avenues for recourse.

The Grant Configurator enforces a field clarity gate before a round can be opened for applications. For each application field, the funder must supply a criterion specification meeting the requirements of Part IV (Gate Criterion Specification): criterion intent, operational definition with examples, response form justification, evidence form, and compliance threshold for any external standard reference. Fields that do not meet the specification requirement are flagged before the round opens. The configurator provides AI-assisted review of each field specification, surfacing ambiguous terms, undefined options, inappropriate response forms, and missing examples as clarifying questions. The funder must either resolve each flagged item or explicitly override it with documented justification. An override is recorded as a conformance choice in the round configuration and is visible to applicants and reviewers as part of the published gate configuration.

**CROSS Grantee Dashboard** (CROSS-grantee-dashboard-0_2_0.md): the post-award obligation interface. Converts the round specification produced by the Grant Configurator into a live record for each funded project. Inherits the indicator schema, evidence requirements, gate configuration, disaggregation ratchet, cumulative/non-cumulative designation, and disbursement condition structure from the configurator. Tracks gate evidence submissions and produces structured attestations suitable for on-chain publication.

**CROSS Reviewers Dashboard** (CROSS-reviewers-dashboard-0_1_0.md): the stage-gated review interface. Active only during the evaluation stage of a round, as configured in the Grant Configurator. Enforces conflict of interest declarations as access gates before any application is opened. Maintains assessment isolation between reviewers until submission. Provides role-differentiated access: guest reviewers see their assigned applications; lead reviewers see all applications and submitted assessments; funder administrators see the aggregate output. Loads the appropriate rubric based on the obligation mode configured for the round. Provides AI-assisted evaluation in three layers: submitted evidence verification against the applicant's claims, independent investigation of applicant claims against third-party sources, and a draft evaluation applying the rubric to the combined findings. Human reviewer assessment is the final artifact; the AI draft and investigation findings are stored alongside it in the review record.

**CROSS skill** (claude-skills/claude-skill-CROSS-0_2_0.md): machine-readable encoding of the standard for AI-assisted implementation across all three tools. Covers three obligation modes, the four-gate architecture, open measurement form with three-axis classification, and gate evidence assessment procedures.

**Runbooks.** Pre-built, documented configuration packages for common program types. Each runbook specifies a complete gate configuration, obligation mode assignment, evidence scope and strength at each gate, infrastructure declaration requirements, and a recommended evolution path to a more mature configuration. The initial runbook library covers: discovery sprint, staged development, community allocation with build obligation, retroactive impact, graduated evidence, and institutional conformance configurations. Runbooks are companion documents to this standard.

---

## Part X: Companion Documents

The standard states criteria tersely. The companion documents operationalize them for practitioners.

**Guidance** (CROSS-common-reporting-outcome-standards-schema-guidance-0_2_0.md): what qualifies and what does not at each decision point; how to answer the entry specification for each obligation mode; common failures at the gate and at the rigor tier; how to complete each indicator field; how to apply the conflict of interest standard to novel relationship types.

**Templates** (CROSS-common-reporting-outcome-standards-schema-templates-0_2_0.md): the entry specification forms (mode-specific variants for build, change, and retroactive obligation), the indicator registration form, the conflict of interest declaration forms, the gate evidence submission form, and the privacy-sensitive accommodation request. Template complexity is tiered to the scale of the application.

**Assessment Rubric** (CROSS-common-reporting-outcome-standards-schema-rubric-0_2_0.md): how reviewers assess against the gate criteria for each obligation mode. Includes the data quality standard assessment questions and failure mode descriptions from Part VIII. The rubric is mode-specific: build-obligation, change-obligation, and retroactive obligation gates produce different assessment questions.

**Worked Examples** (CROSS-common-reporting-outcome-standards-schema-worked-examples-0_2_0.md): existing evaluations illustrating gate passage and gate failure across all three obligation modes, from the Epoch 12 public goods evaluation cycle and comparable programs. Includes canonical cases demonstrating deliverable specification failures, FROM state failures, retroactive evidence failures, concurrent funding non-disclosure, conflict of interest remediation, and well-specified versus underspecified indicators.

---

---

## Part XI: Funder Obligations and Redress

CROSS specifies what funded interventions are obligated to demonstrate and how reviewers must assess the evidence. It also imposes obligations on funders: to publish gate configurations, declare verification infrastructure, and apply gate criteria as published. This Part specifies the minimum mechanisms by which funders are held to their published obligations, and how applicants and grantees may seek redress when they believe those obligations have been violated.

This Part applies to all CROSS-conformant programs. Configurable elements are tiered by program scale.

---

#### 1. Funder Obligation Requirements

In addition to the obligations stated elsewhere in this standard, a CROSS-conformant funder must:

- Maintain a record of gate configurations, infrastructure declarations, and documented waivers for each round and stage.
- Apply gate criteria consistently with the published configuration for that round.
- Document any deviation from the published configuration or infrastructure declaration, including justification and the party under whose authority the deviation was made.

Failure to meet these obligations is a funder obligation violation. It does not automatically invalidate individual awards, but it does create an obligation to remediate where affected applicants or grantees are identified.

---

#### 2. Internal Review and Clarification

Before formal redress is sought, applicants and grantees must have access to an internal clarification mechanism. At minimum, this mechanism must provide:

- A named point of contact to whom applicants and grantees can submit questions about how gate decisions were applied in their specific case.
- A requirement that the funder provide a written response explaining how the decision was consistent with the published gate configuration, the applicable rubric, and the evidence on record.
- A time bound for response that is shorter than the round's typical cycle time, so that clarifications can inform subsequent applications.

The internal clarification mechanism is not an appeals body. It is a structured means of obtaining a record of the funder's reasoning and ensuring that gate decisions are anchored to the published configuration.

---

#### 3. Structured Appeals on Procedural Grounds

CROSS recognizes appeals on procedural grounds: claims that the funder did not follow its own published gate configuration, infrastructure declaration, or conflict of interest framework in a way that materially affected an applicant or grantee.

A CROSS-conformant program must:

- Publish an appeals procedure that specifies:
    - What decisions are appealable (for example, entry gate rejections, completion verification failures, continuation denials).
    - The grounds on which appeals may be made (procedural non-conformance, conflict of interest violations, undisclosed changes to gate configuration).
    - The time window within which an appeal must be filed after the decision is communicated.
- Designate an appeals body that is structurally separate from the original decision-making panel. In small programs, this may be a board member or external advisor who did not participate in the original decision.
- Commit to issuing a written determination on each appeal that states:
    - Whether a funder obligation violation occurred.
    - Whether the original decision stands, is modified, or is reversed.
    - What remediation, if any, will be offered.

Appeals under this Part assess whether the funder followed CROSS-conformant procedures. They do not reopen substantive scoring absent a documented procedural error.

---

#### 4. Independent Redress Mechanism (Optional)

Larger programs and multi-round ecosystems may configure an independent redress mechanism analogous to the Independent Redress Mechanism operated by institutional funders such as the Green Climate Fund and the World Bank. Where configured, the mechanism:

- Accepts complaints from applicants, grantees, or affected parties who allege that the funder has violated CROSS or its own published policies.
- Operates independently from the program's grant decision-making structure.
- May review documentation, interview parties, and issue findings and recommendations.

For CROSS conformance, the independent mechanism is optional. Where a program chooses to operate without one, the funder must state this explicitly in the Grant Configurator and publish the decision as part of the program-level specification.

---

#### 5. Linkage to Failure Record Obligation

Where a funder obligation violation has materially affected the status of a grant (for example, premature termination, unjustified completion failure, or denial of continuation funding), the case must be recorded in the funder's failure record, alongside the remediation offered. Future versions of this standard may make the failure record a conformance requirement for all CROSS-conformant programs.

## Appendix: Open Design Questions (v0.2.0)

**Single-outcome constraint.** Whether CROSS should require one primary indicator per application or permit multiple. Current position: permit multiple, require one designated primary indicator. The primary indicator is the one against which the entry specification, progress verification, and completion verification gates are primarily assessed.

**Reporting frequency.** Whether reporting frequency requirements belong in the standard or the guidance. Current position: guidance, calibrated by the Coordination Scaling Standard.

**Cost-effectiveness as a required field.** Whether cost-effectiveness assessment should be a required field at the continuation gate for all change-obligation programs or remain advisory. Current position: required for continuation in programs whose Grant Configurator specifies Stage 2 or above; advisory elsewhere.

**Round-level common indicators.** Whether funders may designate indicators common to all applications in a round, in addition to applicant-specified indicators. Current position: yes, a valid configurator option. Common indicators do not change the applicant-specification principle for all other indicators.

**Failure record obligation.** Whether CROSS-conformant funders are required to maintain a public record of terminated grants, missed milestones, and declined continuation applications. Current position: strongly indicated by the research but not yet specified as a conformance requirement. To be addressed in v0.3.0.

**Decentralized Autonomous Organization Improvement Proposal 5 relationship.** CROSS should reference Decentralized Autonomous Organization Improvement Proposal 5 as a companion coordinating instrument governing round process structure. Decentralized Autonomous Organization Improvement Proposal 5 handles how rounds are structured and funds distributed. CROSS handles what funded interventions must demonstrate. The formal relationship is to be specified in a subsequent draft.

---

## Changelog

| Version | Date | Summary |
|---|---|---|
| 0.2.4 | 2026-05-15 | Bidirectional Precision Principle: added Gate Criterion Specification subsection to Part IV requiring funders to specify gate criteria with the same operational definition, response form, evidence form, and compliance threshold precision that Part V requires of applicant indicators. Added compliance threshold requirement for external standard references: funders must enumerate which sub-indicators apply, what evidence satisfies each, and the minimum threshold for gate passage, illustrated with the DPG Standard nine-indicator case. Added field clarity gate to Grant Configurator in Part IX: AI-assisted review flags ambiguous criteria before a round opens; overrides are documented conformance choices in the published round configuration. |
| 0.2.3 | 2026-05-15 | Four structural additions. (1) Part II: extended the open source and intellectual property dimension with an IP ownership declaration requirement for research, model, and novel artifact outputs; Grant Configurator activation note added. (2) Part IV: added Pre-Award Indicator Confirmation Window subsection specifying the optional post-entry, pre-disbursement review of indicator specifications, including silence-as-confirmation rule and governing scope. (3) Part IV: added Outcome Verification with Counterfactual Reference subsection specifying the four required contract elements (counterfactual baseline, attribution argument, comparison period or group, independent attestation) for gates configured at counterfactual reference level; distinguished from default outcome evidence scope. (4) Part V: added Sustainability and Transition Plan as a funder-activated optional field specifying post-grant continuation conditions for infrastructure-producing grants. |
| 0.2.2 | 2026-05-15 | Added Part VI-A: Scope Attribution and Outcome Credit, specifying additionality declaration and outcome credit attribution requirements triggered by concurrent funding disclosure. Added cross-reference in the Scope section. Added Grant Configurator note in Part IX specifying how Part VI-A parameters are recorded and published. Added Part XI: Funder Obligations and Redress, specifying minimum mechanisms by which funders are held to their published gate configurations and how applicants may seek recourse. Added cross-references in Scope and Implementation Architecture. External Standard References: new subsection in Part IV specifying the mechanism by which any gate may reference an external standard by URL with a version anchor, including support for machine-readable approved lists. |
| 0.2.1 | 2026-05-15 | On-chain execution and verification instruments: added subsection to Part V specifying indicator requirements for smart contract and protocol deliverables, including invariant specification, verification method, verification artifact, and failure surface fields. Added two clarifying paragraphs to Part IV on verification artifacts as output evidence and on independent review for contract-centric interventions. |
| 0.2.0 | 2026-05-14 | Major structural revision. Introduced three accountability modes (build, change, retroactive). Theory of Build correctly scoped as a failure mode in change-accountability rounds only. Replaced Level 1 / Level 2 binary with four-gate architecture (entry specification, progress verification, completion verification, continuation specification). Added evidence scope and evidence strength taxonomies. Added program-level continuation gate. Replaced constrained data type list with open measurement form and evidence classification. Added Reviewers Dashboard to implementation architecture. Added runbook library concept. Added funder maturation tracking note. Resolved several v0.1.0 open questions. |
| 0.1.0 | 2026-05-14 | Initial draft. Single accountability mode (change). Binary Theory of Build gate (Level 1) and scored rigor tier (Level 2). PIRS-derived indicator schema with four-option data type field. |
