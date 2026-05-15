---
title: CROSS - Grant Mechanism Primitives
version: 0.1.0
date: 2026-05-15
license: CC0
status: Working draft. Documents five emergent synthesis primitives identified through cross-combination of governmental, academic, international development, and web3 grant program designs. Each primitive addresses a failure mode that no single program type resolves on its own.
companion_documents:
  - standards/CROSS-runbooks-0_1_0.md
  - standards/CROSS-common-reporting-outcome-standards-schema-0_2_0.md
---

# CROSS: Grant Mechanism Primitives

Version 0.1.0 | 2026-05-15 | CC0

---

## Purpose

This document names five grant mechanism primitives that emerge from crossing the design spaces of multiple program types. Each primitive is a self-contained design element that can be combined with others to form runbook configurations for specific program contexts. Primitives are not runbooks; they are the building blocks from which runbooks are assembled.

A primitive addresses one specific failure mode in standard grant design. Combining primitives addresses multiple failure modes simultaneously, with the constraint that some combinations produce new tensions that must be managed in the runbook configuration.

---

## Primitive 1: Pre-Registered Pull

**What it is.** A funder announces in advance that it will fund any team that achieves a specified outcome, where the outcome is fully specified before any team begins work. Teams self-select into the challenge and apply retroactively once the outcome is achieved. No application is chosen in advance.

**What it solves.** Standard grant design funds promises. Pre-registered pull funds achievement. It eliminates post-hoc rationalization of what was supposed to happen, prevents goalpost movement by either party, and opens participation to teams the funder has never encountered. The participation set is determined by who achieves the outcome, not by who the funder knew about at application time.

**CROSS integration.** A new obligation mode alongside build, change, and retroactive: pull obligation. The funder publishes the outcome specification (a fully specified CROSS indicator) before any team begins work. Any team demonstrating gate passage receives the award. The application stage is replaced by an outcome verification stage. Appropriate for program areas where the desired outcome is well-specified but the optimal implementation approach is unknown.

**Key design question.** How long does the pull window stay open? Multi-year windows work for complex infrastructure challenges. Epoch-cycle windows work for shorter-horizon public goods programs.

**Failure mode addressed.** Selection bias in standard grant design: applicants must be known to the funder at application time, excluding teams the funder has not yet discovered.

---

## Primitive 2: Conviction-Weighted Retroactive Recognition

**What it is.** Community members stake tokens to recognize past contributions. Conviction accumulates continuously over time using an exponential decay function. The longer and larger the stake, the more conviction accumulates. A project reaches recognition threshold when accumulated conviction crosses a configurable bar, triggering retroactive funding from a treasury.

**What it solves.** Retroactive public goods funding programs require judges to evaluate impact in a point-in-time vote, which creates snapshot gaming and recency bias. A project that contributed genuinely over many months needs to mobilize supporters during a fixed window to receive recognition. Conviction-weighted recognition removes the time boundary: authentic long-term contribution accumulates recognition organically rather than requiring tactical mobilization at a specific moment.

**CROSS integration.** An alternative to the reviewer panel for the completion verification gate in retroactive obligation rounds. Community members stake tokens to recognize completed work. The conviction accumulation replaces or supplements reviewer scoring. Configurable parameters: the funder sets the half-life of conviction decay, the recognition threshold, and whether community conviction is the primary gate or a supplementary signal alongside reviewer assessment.

**Key design question.** Who can stake recognition tokens? Token-holder-only staking creates plutocracy risk. A reputation-weighted staking system where prior grant recipients have proportional staking rights ties recognition authority to demonstrated contribution.

**Failure mode addressed.** Recency bias and snapshot gaming in retroactive evaluation: projects that contributed consistently over time receive the same evaluation window as projects that optimized for the evaluation period specifically.

---

## Primitive 3: Streaming Milestone Gates

**What it is.** Funds flow continuously as a real-time stream rather than as lump-sum disbursements at milestone completion. The stream is governed by gate logic: it starts at grant award, pauses automatically when a gate checkpoint arrives and the grantee has not submitted evidence, and resumes automatically upon gate passage. Accelerators and decelerators adjust the flow rate based on milestone timing.

**What it solves.** Lump-sum disbursement creates a specific misalignment: grantees have all leverage before delivery and almost none after. A continuous stream maintains ongoing alignment throughout the grant period. Grantees have direct incentive to hit milestones on time because stream pauses reduce cumulative receipts. Funders have real-time visibility rather than point-in-time snapshots. Scope ambiguity between concurrent funders can be managed by pausing the stream during attribution contestation periods.

**CROSS integration.** A disbursement specification parameter in the gate architecture. Configurable parameters: stream start event (at award or at first milestone passage), pause trigger (gate checkpoint with no evidence submitted within the window), resume trigger (gate passage), and treatment of accrued unstreamed balance if a gate fails (return to funder, vest to grantee proportionally, or hold in escrow pending appeal). Requires streaming protocol infrastructure (Superfluid or equivalent).

**Key design question.** What happens to the accrued unstreamed balance if a gate fails? The CROSS gate configuration must specify this in the infrastructure declaration before the round opens.

**Failure mode addressed.** Post-disbursement accountability collapse: once lump-sum funds are released, the funder has limited recourse if subsequent milestones are not met. Streaming maintains ongoing accountability throughout the grant period.

---

## Primitive 4: Community-Validated Attribution

**What it is.** When a grantee declares attribution fractions (what percentage of outcome credit goes to which funder), a structured contestation window opens. During this window, other funders and community stakeholders signal disagreement with the declared fractions. A quadratic-weighted round in which participants allocate weight to "who materially caused this outcome" produces a community-derived attribution estimate. If the community estimate and the grantee's self-declaration diverge beyond a configured threshold, a structured reviewer clarification is triggered.

**What it solves.** Attribution under Part VI-A of the CROSS standard is currently a self-report with no external validation mechanism. Grantees have an incentive to over-attribute outcomes to the funder they are applying to, which distorts the attribution record over time. Community-validated attribution adds an external signal to the attribution question without replacing the grantee's obligation to declare a defensible position.

**CROSS integration.** An optional extension to Part VI-A. The funder activates a contestation window of configurable length after the grantee submits their attribution statement. The community signal produces a weighted median attribution estimate displayed alongside the grantee's declaration. Divergence above the configured threshold triggers a structured reviewer clarification request, not automatic rejection.

**Key design question.** Who qualifies to participate in the contestation window? Token holders only creates concentration risk. Prior grant recipients within the same program create a peer accountability dynamic. Other funded projects in the same round create a peer-review incentive. The participation criteria determine whether the signal is informative or easily gamed.

**Failure mode addressed.** Attribution inflation: self-reported attribution systematically over-credits the funder being reported to, degrading the attribution record and making cross-funder comparison unreliable.

---

## Primitive 5: Maintenance Prize

**What it is.** A standing prize that pays any team maintaining a piece of critical public infrastructure above a defined reliability and responsiveness threshold, continuously, for a specified period. Criteria are automated where possible: security response time (critical vulnerability patched within a specified window), release cadence (minimum releases per period), dependency health (no unpatched high-severity dependencies), and documentation currency (documentation updated within a defined window of breaking changes). Any team meeting all criteria for the measurement period receives the prize. Multiple teams can compete for the same prize if the infrastructure is forkable.

**What it solves.** Maintenance is systematically underfunded because it is invisible: nothing dramatic happens, nothing is launched, and there is no compelling narrative for a grant application. Maintenance prizes make the work visible and reward it on a continuous basis. They also address the organizational continuity problem: a prize can be paid to whoever does the work without requiring the recipient to maintain a formal legal entity or produce deliverable-based milestones.

**CROSS integration.** A new indicator type in Part V: "maintain indicator above threshold for period X." The measurement is continuous rather than point-in-time. The obligation is ongoing rather than completed once. The award structure is periodic (monthly or quarterly) rather than project-based. The funder specifies the infrastructure, the threshold criteria, and the prize amount per measurement period. Multiple teams can claim the prize for the same infrastructure if they maintain independent deployments above the threshold.

**Key design question.** How is maintenance quality verified at scale without expensive human review each period? Automated checks handle a significant portion (release activity via repository APIs, vulnerability status via public CVE databases, dependency health via package registries). A combination of automated checks with lightweight human review on a random sample is the baseline approach.

**Failure mode addressed.** Maintenance funding gap: no standard grant mechanism (quadratic funding, retroactive public goods funding, conviction voting, direct grants) reliably surfaces and funds ongoing maintenance of existing infrastructure, because all of them require narrative application against a new-work framing.

---

## Primitive Combinations

These primitives are not independent. Natural combinations produce compounded effects:

**Pre-registered pull with conviction-weighted retroactive recognition.** The funder announces the outcome; teams self-fund toward it; community conviction determines retroactive recognition weight when multiple teams partially achieve the outcome simultaneously. Addresses both selection bias and point-in-time evaluation bias.

**Streaming gates with community-validated attribution.** Funds stream while work is in progress; the stream pauses during the attribution contestation window after completion. The pause creates a structured accountability moment without requiring a separate process.

**Maintenance prize with community-validated attribution.** The community validates that a team's maintenance contribution is genuine before the prize is released, preventing teams from meeting mechanical criteria while providing low-quality maintenance.

**Pre-registered pull with streaming gates.** The outcome specification is locked before teams begin; funds stream to teams as they demonstrate progress toward the specified outcome; the stream terminates if progress stalls. Removes the application stage entirely while maintaining continuous accountability.

All five primitives assume the eligibility-mechanism boundary is variable: the pre-registered pull eliminates the application stage, the maintenance prize eliminates the legal entity requirement, community-validated attribution substitutes external signal for internal declaration. The CROSS configurator should be able to express all of these as combinations of existing primitive fields rather than requiring new parts of the standard for each.

---

## Constraint Interactions

Each primitive introduces constraints that interact with others when combined:

The pre-registered pull requires outcome specification precision before teams begin. This constrains the funder: once the specification is locked, goalpost movement is a conformance violation. Combined with streaming gates, it requires that the stream's pause-and-resume logic is tied to the pre-registered specification, not to a milestone schedule defined after the fact.

Conviction-weighted retroactive recognition requires a defined staking community. This constrains participation: only those who qualify to stake can influence the recognition signal. Combined with community-validated attribution, the same staking community is making two different evaluations, which creates a conflict of interest unless the two participation pools are defined separately.

The maintenance prize requires automated verification infrastructure. This constrains which infrastructure qualifies: infrastructure with no public APIs, no repository activity, and no public CVE surface cannot be automatically verified. The prize is only operationalizable for infrastructure that exposes sufficient public signals.

Streaming gates require streaming protocol infrastructure. This constrains program design: funders without on-chain infrastructure cannot operate streaming gates. Off-chain approximations (milestone escrow with automated release) can substitute for some use cases.

Constraints are not failures; they are design signals. A constraint that cannot be satisfied in a given context indicates that the primitive is not appropriate for that context, which is itself useful information for runbook selection.

---

## Changelog

| Version | Date | Summary |
|---|---|---|
| 0.1.0 | 2026-05-15 | Initial draft. Five primitives: pre-registered pull, conviction-weighted retroactive recognition, streaming milestone gates, community-validated attribution, maintenance prize. Primitive combinations and constraint interactions documented. |
