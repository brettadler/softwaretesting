# Deliverables in Software Testing

## Documentation Process

Clear documentation makes teamwork smoother and ensures quality at every stage. Key artifacts include:

- **Test Strategy:** Big-picture plan for a company or product, including approaches, tooling, environments, release criteria, and more.
- **Test Plan:** Release/feature specific test plans, including what to test, how to test, release criteria, resources, and more.
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

## Document Templates

### Bug Reporting Template
- Title
- Environment
- Build/Version
- URL/Screen
- Steps to Reproduce
- Expected
- Actual
- Details (screenshots/video/console/network)
- Severity/Priority
- Reproducability Rate
- Assignee/Owner
- Links (Jira/design/spec)
- Notes/Workarounds

### Bug Reporting Guide
- show empathy
- examples of good vs poor reports
- copy-pasteable steps template
- media capture tips
- triage expectations

### QA Onboarding Checklist
- existing test plans/cases
- definitions of Ready/Done
- CI results/dashboards
- coverage reports
- environments matrix
- data management
- release checklist
- defect backlog
- reporting rhythms

### Deliverables:
- Test Strategy (scope, risks, approach)
- Test Plan (who/when/where)
- Test Cases
- Data Plan
- Traceability Matrix
- Status Reports
- Defect Reports
- Release Summary

## Strategy vs Plan
- **Test Strategy:** long-lived, product/org-level; risk-based approach, tooling, environments, quality gates.
- **Test Plan:** release/feature-specific; schedule, resources, entry/exit criteria, assignments.
