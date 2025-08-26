# Deliverables in Software Testing

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


# Processes & Docs You Can Reuse
- **Bug reporting template (flat core fields):** Title; Environment; Build/Version; URL/Screen; Steps to Reproduce; Expected; Actual; Evidence (screenshots/video/console/network); Severity/Priority; Repro rate; Assignee/Owner; Links (Jira/design/spec); Notes/Workarounds.
- **Bug reporting guide (Confluence):** show empathy; examples of good vs poor reports; copy-pasteable steps template; media capture tips; triage expectations.
- **QA Lead onboarding checklist:** request existing test plans/cases; definitions of Ready/Done; risk register; CI results/dashboards; coverage reports; environments matrix; data management; release checklist; defect backlog/SLAs; prior incident/RCA docs. Start lightweight: triage cadence; risk-based test planning; CI signal ownership; reporting rhythms.
- **Deliverables:** Test Strategy (scope, risks, approach); Test Plan (who/when/where); Test cases/charters; Data plan; Traceability; Daily status; Defect reports; Release test summary.


# Strategy vs Plan
- **Test Strategy:** long-lived, product/org-level; risk-based approach, tooling, environments, quality gates.
- **Test Plan:** release/feature-specific; schedule, resources, entry/exit criteria, assignments.
