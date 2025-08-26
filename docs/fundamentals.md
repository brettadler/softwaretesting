# Fundamentals of Testing

## Why is Testing Necessary?
- **Defects are inevitable**: software may contain undiscovered defects; failures occur when defects are triggered.
- **Risk reduction**: testing provides information to reduce product and project risk.
- **Confidence & quality**: stakeholders rely on test results to make release decisions.
- **QA vs. QC**:
  - **Quality Assurance (QA)** = process-oriented, prevents defects (e.g., reviews, standards).
  - **Quality Control (QC)** = product-oriented, detects defects (e.g., executing tests).

## What is Testing? Objectives
- A set of activities to **evaluate quality** and **reveal defects**, providing **information** for decisions.
- Objectives: **prevent defects**, **find defects**, **build confidence**, **assess quality**, **provide status**, **meet legal/regulatory needs**.

## What is the difference between a test strategy and a test plan?

- **Test Strategy:** long-lived, product/org-level; risk-based approach, tooling, environments, quality gates.
- **Test Plan:** release/feature-specific; schedule, resources, entry/exit criteria, assignments.

## Seven Principles of Testing
1. Testing shows **presence**, not absence, of defects.
2. **Exhaustive testing** is impossible.
3. **Early testing** reduces cost/time.
4. **Defect clustering** (a few modules contain most defects).
5. **Pesticide paradox** (vary tests to find new defects).
6. **Context-dependent** (safety-critical vs. web app).
7. **Absence-of-errors fallacy** (a bug-free system can still be unusable).

## Fundamental Test Process
- **Plan & Control**: scope, approach, resources, schedule; define entry/exit criteria.
- **Analyze & Design**: identify test conditions, design test cases & data, trace to test basis.
- **Implement & Execute**: create procedures/scripts, set up environments, run tests, log results/defects.
- **Evaluate Exit Criteria & Report**: assess coverage/results vs. goals; report status.
- **Closure**: finalize, archive testware, lessons learned, metrics.

## Psychology of Testing
- **Independence** improves objectivity (levels range from developer testing their own code to external teams).
- **Constructive communication**: defect reports are feedback, not blame.
- **Tester mindset**: curious, skeptical, business/value-focused.

## Documentation Process

Clear documentation makes teamwork smoother and ensures quality at every stage. Key artifacts include:

- **Test Strategy:** Big-picture plan—risks, approaches, environments, quality gates.
- **Test Plan:** Release/feature plan—who, what, when; entry/exit criteria.
- **Test Cases & Charters:** Step-by-step scripts or focused exploratory missions.
- **Traceability Matrix:** Maps requirements to tests (e.g., Req ID, Test IDs, Status, Risks).

Essential terms:

- **Test Condition:** What you verify (rule, requirement, path).
- **Test Case:** Steps, data, expected result.
- **Test Data:** Values you use (normal, boundary, negative).
- **Test Suite:** Bundle of related cases.
- **Test Environment:** Sandbox—tools, servers, configs, data.
- **Testware:** All testing artifacts (plans, cases, scripts, reports).
- **Entry / Exit Criteria:** When to start/stop (e.g., Entry: env ready, data loaded; Exit: 0 criticals, 95% high-priority tests passed).

## Docs You Can Reuse

- **Bug reporting template (flat core fields):** Title; Environment; Build/Version; URL/Screen; Steps to Reproduce; Expected; Actual; Evidence (screenshots/video/console/network); Severity/Priority; Repro rate; Assignee/Owner; Links (Jira/design/spec); Notes/Workarounds.
- **Bug reporting guide (Confluence):** show empathy; examples of good vs poor reports; copy-pasteable steps template; media capture tips; triage expectations.
- **QA Lead onboarding checklist:** request existing test plans/cases; definitions of Ready/Done; risk register; CI results/dashboards; coverage reports; environments matrix; data management; release checklist; defect backlog/SLAs; prior incident/RCA docs. Start lightweight: triage cadence; risk-based test planning; CI signal ownership; reporting rhythms.
- **Deliverables:** Test Strategy (scope, risks, approach); Test Plan (who/when/where); Test cases/charters; Data plan; Traceability; Daily status; Defect reports; Release test summary.
