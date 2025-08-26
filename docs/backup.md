# Intro to Testing

Certifications
* ISTQB Certified Tester Foundation Level (CTFL): foundational testing principles. https://www.istqb.org/certifications/certified-tester-foundation-level-ctfl-v4-0/
* Certified Software Tester (CSTE): QAI – quality control principles/practices.
* Certified Associate in Software Testing (CAST): QAI – foundational testing knowledge.
* ISTQB Agile Tester Certification: testing within Agile teams (iterative development, Agile testing principles).
* Certified Software Quality Analyst (CSQA): QA principles incl. process improvement and organizational quality.

Testing metrics
* Test Coverage (%) — % of code/requirements/functionality covered by tests.
* Pass/Fail Rates — Ratio of passed vs. failed test cases in a cycle.
* Defect Density — Defects per unit of code (e.g., per 1,000 lines).
* Mean Time to Detect (MTTD) — Avg. time to find a bug after introduction.
* Mean Time to Resolve (MTTR) — Avg. time to fix/close a reported defect.
* Test Execution Rate — # test cases executed per time window.
* Escaped Defects — Bugs found in production (missed during testing).

Unit / Integration / System
* Unit testing — Verifies individual functions or classes in isolation.
* Integration testing — Checks that modules/components work together correctly.
* System / End‑to‑End (E2E) testing — Exercises real user workflows across the full stack; validates complete, integrated app against requirements.

Build Health & Change Safety
* Smoke testing — Quick check that core flows basically work (post‑build/deploy).
* Sanity testing — Focused check of a specific area after small changes or bug fixes.
* Regression testing — Ensures new changes haven’t broken existing behavior.

By Interface / Layer
* API testing — Verifies request/response behavior of services and endpoints.
* UI testing — Validates visual/interactive behavior of the interface.

Non‑Functional / Quality Attributes
* Performance testing — Assesses speed, responsiveness, and stability under load.
* Load testing — Expected peak traffic levels.
* Stress testing — Beyond limits to see how/where the system fails.
* Scalability testing — How performance changes as resources/users grow.
* Reliability/soak testing — Long‑duration runs to find leaks and stability issues.
* Security testing — Finds vulnerabilities, misconfigurations, auth/crypto flaws.
* Penetration testing — Simulated attacks to exploit security weaknesses.
* Compatibility testing — Across browsers, devices, OSes, environments.
* Accessibility testing — Ensures conformance (e.g., WCAG, Section 508).
* Localization / Internationalization testing (i18n/l10n) — Validates content, formats, layout for target locales.
* Installation / upgrade testing — Setup, migration, rollback paths.
* Data integrity testing — Data stored/transformed/retrieved correctly.
* Recovery testing — System can recover from crashes or outages.
* Backup / restore testing — Data protection and disaster recovery procedures.

Techniques & Styles
* Static testing — Review artifacts (code, docs) without executing.
* White‑box / Black‑box / Gray‑box — Use internal knowledge none/some/full to design tests.
* Exploratory testing — Skilled, unscripted testing guided by learning and observation.
* Ad hoc testing — Informal, unstructured tests without predefined cases.
* Mutation testing — Insert small code changes to check test suite effectiveness.
* Chaos engineering/testing — Inject failures in production‑like systems to test resilience.
* A/B testing — Compare variants in production to measure user impact statistically.
* Usability testing — Ease of use, clarity, user satisfaction.
* Acceptance testing (UAT) — Confirms system meets user/business needs for go‑live.

Processes & Docs You Can Reuse
* Bug reporting template (flat core fields): Title; Environment; Build/Version; URL/Screen; Steps to Reproduce; Expected; Actual; Evidence (screenshots/video/console/network); Severity/Priority; Repro rate; Assignee/Owner; Links (Jira/design/spec); Notes/Workarounds.
* Bug reporting guide (Confluence): show empathy; examples of good vs poor reports; copy‑pasteable steps template; media capture tips; triage expectations.
* QA Lead onboarding checklist: request existing test plans/cases; definitions of Ready/Done; risk register; CI results/dashboards; coverage reports; environments matrix; data management; release checklist; defect backlog/SLAs; prior incident/RCA docs. Start lightweight: triage cadence; risk‑based test planning; CI signal ownership; reporting rhythms.
* Deliverables: Test Strategy (scope, risks, approach); Test Plan (who/when/where); Test cases/charters; Data plan; Traceability; Daily status; Defect reports; Release test summary.

Strategy vs Plan
* Test Strategy: long‑lived, product/org‑level; risk‑based approach, tooling, environments, quality gates.
* Test Plan: release/feature‑specific; schedule, resources, entry/exit criteria, assignments.


Testing Tools

Unit / Component / Code‑level
* Jest — React testing
* Vitest / Jest + React Testing Library (noted under framework choices)
* RSpec / ??
* Mocha?
* Cucumber?
* Others?

API / Integration
* Postman?
* Rest Assured — https://rest-assured.io

Web UI / Browser
* Selenium — https://medium.com/@danielwillium9355/a-comprehensive-guide-to-automated-accessibility-testing-with-selenium-e19fb950ab7c and https://www.baeldung.com/selenium-accessibility-testing
* Cypress — https://www.cypress.io
* Microsoft Playwright — https://playwright.dev
* BrowserStack — https://www.browserstack.com/accessibility-testing / https://www.browserstack.com/docs/automate/selenium
* Katalon Studio — https://katalon.com



Roles & Titles
- [ ] QA Engineer / Software Tester
- [ ] Software Development Engineer in Test (SDET)
- [ ] Test Automation Engineer (QA Test Automation Engineer / Automation Test Engineer)
- [ ] QA Analyst (Quality Assurance Analyst)
- [ ] QA Lead / Manager (Quality Assurance Lead)
- [ ] Quality Engineer
- [ ] QA Software Test Engineer



Common Recruiter Keywords
* Manual testing
* Automated testing
* Test cases
* Selenium / Playwright / Cypress
* API testing (Postman / REST)
* CI/CD
* Regression
* Accessibility / WCAG
* Performance
* Python / JS / TypeScript
* Jira
* Agile / Scrum
* Defect triage





Communities & Meetups
Test Community
* Ministry of Testing
* Test Automation University Slack
* SeleniumHQ Slack
* Techwell Hub Slack
* (See ChatGPT for additional ideas)




<!--

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files. -->


<!-- # 📚 ISTQB Foundation Level – Complete Expanded Study Guide -->

> A single, consolidated guide that merges the detailed syllabus checklist, practical tool/vendor landscape, and glossary + exam prep strategies we’ve covered.

<!--
---

## Table of Contents
1. Fundamentals of Testing
2. Testing Throughout the SDLC
3. Static Testing
4. Test Techniques
5. Test Management
6. Tool Support for Testing (Categories, Examples, Vendors)
7. Glossary & Exam Prep (High-yield terms, strategies)

--- -->

## Fundamentals of Testing


### Why is Testing Necessary?
- **Defects are inevitable**: software may contain undiscovered defects; failures occur when defects are triggered.
- **Risk reduction**: testing provides information to reduce product and project risk.
- **Confidence & quality**: stakeholders rely on test results to make release decisions.
- **QA vs. QC**:
  - **Quality Assurance (QA)** = process-oriented, prevents defects (e.g., reviews, standards).
  - **Quality Control (QC)** = product-oriented, detects defects (e.g., executing tests).

### What is Testing? Objectives
- A set of activities to **evaluate quality** and **reveal defects**, providing **information** for decisions.
- Objectives: **prevent defects**, **find defects**, **build confidence**, **assess quality**, **provide status**, **meet legal/regulatory needs**.

### Seven Principles of Testing
1. Testing shows **presence**, not absence, of defects.
2. **Exhaustive testing** is impossible.
3. **Early testing** reduces cost/time.
4. **Defect clustering** (a few modules contain most defects).
5. **Pesticide paradox** (vary tests to find new defects).
6. **Context-dependent** (safety-critical vs. web app).
7. **Absence-of-errors fallacy** (a bug-free system can still be unusable).

### Fundamental Test Process
- **Plan & Control**: scope, approach, resources, schedule; define entry/exit criteria.
- **Analyze & Design**: identify test conditions, design test cases & data, trace to test basis.
- **Implement & Execute**: create procedures/scripts, set up environments, run tests, log results/defects.
- **Evaluate Exit Criteria & Report**: assess coverage/results vs. goals; report status.
- **Closure**: finalize, archive testware, lessons learned, metrics.

### Psychology of Testing
- **Independence** improves objectivity (levels range from developer testing their own code to external teams).
- **Constructive communication**: defect reports are feedback, not blame.
- **Tester mindset**: curious, skeptical, business/value-focused.

---

## Testing Throughout the SDLC

### Testing & Development Relationship
- Testing activities **mirror** development: requirements → acceptance tests; design → system/integration; code → unit.
- **Shift-left**: involve testers early (reviews, static testing).

### Test Levels
- **Component (Unit)**: individual modules; drivers/stubs; often automated.
- **Integration**: interfaces and interactions; top-down, bottom-up, big-bang, risk-based.
- **System**: end-to-end behavior against system requirements; functional & non-functional.
- **Acceptance**: business/user validation (UAT, alpha/beta, contract/regulatory).

### Test Types
- **Functional**: business rules, APIs, UI behavior.
- **Non-functional**: performance, reliability, security, usability, compatibility, accessibility, maintainability, portability.
- **Structural**: code/architecture-based (white-box).
- **Change-related**: **confirmation (re-test)** of fixes and **regression** of unchanged areas.

### Maintenance Testing
- Triggered by **changes**, **migrations**, **defect fixes**, **environment updates**.
- **Impact analysis** identifies what to re-test; **regression suites** maintained continuously.

---

## Static Testing

### Static vs. Dynamic
- **Static**: examine artifacts **without executing** code (reviews, static analysis).
- **Dynamic**: execute software with test data.

### Reviews (Work Product Evaluation)
- **Types**: Informal review, walkthrough, technical review, **inspection** (most formal).
- **Formal Review Phases**: planning → kick-off → preparation → meeting → rework → follow-up.
- **Roles**: **Moderator**, **Author**, **Reviewer(s)**, **Scribe**.

### Review Techniques
- **Ad hoc**, **Checklist-based**, **Scenario/Perspective-based**, **Reading techniques** (e.g., stepwise, usage-based).

### Static Analysis Tools (Benefits)
- Find **code smells**, **dead code**, **violations**, **complexity**, **potential vulnerabilities**.
- Benefits: early detection, lower cost to fix, consistent standards, maintainability.

---

## Test Techniques

### Black-box (Specification-based)
- **Equivalence Partitioning (EP)**: group inputs/outputs; test one per partition.
- **Boundary Value Analysis (BVA)**: test at, just below/above boundaries.
- **Decision Tables**: handle combinations of conditions/rules; identify minimal sets.
- **State Transition**: states/events/transitions (valid/invalid sequences).
- **Use Case Testing**: user goals, end-to-end flows, alternate/exception paths.

### White-box (Structural)
- **Statement Coverage**: execute every statement at least once.
- **Decision (Branch) Coverage**: each decision outcome (T/F) at least once.
- (Foundation focuses mainly on these two, higher levels add MC/DC, path, etc.)

### Experience-based
- **Error Guessing**: leverage domain/tech experience for likely faults.
- **Exploratory Testing**: simultaneous learning/design/execution with charters/timeboxes.
- **Checklist-based**: systematic prompts to avoid omissions.

---

## Test Management

### Organization & Independence
- Options: developers test, embedded testers, independent team, external org.
- Higher independence → objectivity; lower → deeper product knowledge.

### Planning & Estimation
- Inputs: risk, scope, complexity, history, skills, environments, constraints.
- Estimation: **expert judgment**, **metrics-based** (historical velocity, defect arrival curves).

### Monitoring & Control
- **Metrics**: executed/blocked/passed/failed %, defect status/age/density/leakage, coverage progress, burn-up/down.
- **Reporting**: clear visuals, risks, trends, recommendations.

### Configuration Management (CM)
- Identify and control **versions** of code, data, environments, testware.
- Ensure **traceability** and **repeatability**.

### Risk-Based Testing
- **Product risk** (quality attributes, critical features) vs. **Project risk** (schedule, people, tools).
- Prioritize **test depth & breadth** where risk and impact are highest.

### Defect Management
- Lifecycle: **new → assigned → open → fixed → re-tested → closed** (or rejected/duplicate/deferred).
- Report content: ID, title, summary, steps to reproduce, expected/actual, **severity vs. priority**, environment, attachments, links.

---

## Tool Support for Testing (Categories, Examples, Vendors)

> ISTQB expects familiarity with **tool categories**, benefits/risks, and **adoption success factors**. Below are widely used tools per category.

### 6.1 Test Management
- **Purpose**: manage test assets, traceability, execution, reporting; integrate with CI/CD and issue tracking.
- **Examples**:
  - **Jira** (Atlassian) + **Xray**, **Zephyr**, **TestRail** (commonly paired)
  - **Azure DevOps Test Plans** (Microsoft)
  - **qTest** (Tricentis), **PractiTest**, **TestLink** (OSS)

### 6.2 Defect / Issue Tracking
- **Purpose**: log, triage, track lifecycle; link to requirements/tests.
- **Examples**: **Jira**, **Bugzilla**, **MantisBT**, **Redmine**.

### 6.3 Static Analysis / Code Quality
- **Purpose**: analyze code without execution; enforce standards; detect vulnerabilities.
- **Examples**: **SonarQube**, **ESLint** (JS/TS), **Pylint/Flake8** (Python), **Checkstyle/PMD** (Java), **Fortify**, **Coverity**.

### 6.4 Test Execution & Automation
- **Web/UI**: **Selenium WebDriver**, **Cypress**, **Playwright**.
- **Unit Testing**: **JUnit**, **TestNG** (Java); **PyTest** (Python); **Jest** (JS/React); **Mocha/Chai** (Node); **xUnit/NUnit** (.NET).
- **Mobile**: **Appium**, **Espresso** (Android), **XCTest/XCUITest** (iOS).
- **API**: **Postman**, **RestAssured** (Java), **SuperTest** (Node), **Karate**.

### 6.5 Performance / Load / Reliability
- **Purpose**: throughput, latency, scalability, stability under stress/soak.
- **Examples**: **JMeter** (Apache), **LoadRunner** (Micro Focus), **Gatling**, **k6** (Grafana), **BlazeMeter**.

### 6.6 Test Data Management (TDM) & Environment
- **Purpose**: generate/mask/subset data; manage environments and virtualization.
- **Examples**: **Informatica TDM**, **Delphix**, **Datprof**, **Mockaroo**; service virtualization: **WireMock**, **Mountebank**.

### 6.7 CI/CD & Orchestration (Test Integration)
- **Purpose**: automate builds/tests/deploys; collect results & gates.
- **Examples**: **Jenkins**, **GitHub Actions**, **GitLab CI/CD**, **Azure Pipelines**, **CircleCI**.

### 6.8 Coverage Measurement
- **Purpose**: measure structural coverage (statements/branches), requirement coverage.
- **Examples**: **JaCoCo**, **Cobertura** (Java), **coverage.py** (Python), **Istanbul/nyc** (JS/TS), **dotCover** (.NET).

### 6.9 Security Testing (AppSec)
- **Purpose**: DAST/SAST/IAST; OWASP Top 10; threat modeling.
- **Examples**: **OWASP ZAP** (DAST), **Burp Suite**, **Veracode**, **Checkmarx**; network tools: **Nmap**, **Metasploit**.

### Benefits of Tools
- **Efficiency**, **repeatability**, **traceability**, **integration** with agile/DevOps, **faster feedback**.

### Risks & Challenges
- Over-reliance; maintenance overhead; learning curve; environment flakiness; false sense of coverage.

### Success Factors
- Clear **goals** and **ROI**; **pilot** first; **training/coaching**; integrate with **process/CI**; review metrics and **adapt**.

---

## Glossary & Exam Prep (High-Yield)

### 7.1 Why the Glossary Matters
- The exam favors **precise, standard phrasing**; subtle term differences are common distractors.
- Learn ISTQB’s **exact definitions** (not local team jargon).

### 7.2 Core Term Distinctions
- **Error** (human mistake) → **Defect/Fault** (in code) → **Failure** (observed deviation at runtime).
- **Verification** (“building the product right”, static) vs. **Validation** (“building the right product”, dynamic).
- **Regression** (unchanged parts still work after change) vs. **Confirmation** (re-test the fix).
- **Functional** (what it does) vs. **Non-functional** (how well: performance, security, etc.).
- **Test Basis** (source docs), **Test Condition** (what to test), **Test Case** (inputs + expected), **Test Suite** (collection).
- **Coverage** (requirements, statements, decisions), **Defect density**, **Entry/Exit criteria**.
- **Roles in reviews**: moderator, author, reviewers, scribe.
- **Independent testing** levels and **test oracle** concept.

### 7.3 Exam Format
- **40 MCQs**, **60 minutes** (or **75** if eligible for extra time).
- **Passing**: **26/40 (65%)**.
- Questions: definition-based, scenario-based, term distinctions, process sequencing, technique application (EP/BVA/decision tables).

### 7.4 Prep Strategy (Actionable)
- **Daily**: 20 minutes of glossary flashcards (Anki/Quizlet); rotate by chapter.
- **Weekly**: full **mock exam**; track weak areas; review explanations.
- Build a **mind map** linking levels → types → techniques → tools.
- Practice **mini-calcs** for BVA/decision tables; rehearse **coverage** concepts.
- Join a **study group**; teach a topic (Feynman technique).

### 7.5 Tactics During the Exam
- Read stem and **underline qualifiers**: “**best**, **most likely**, **primary**, **first**”.
- Eliminate 2 wrong options; compare remaining by **exact glossary wording**.
- Manage time: ~90 seconds/question; mark and move; return later.
- Beware of **company terminology** vs. ISTQB terms.

### 7.6 High-Yield Term Shortlist
- Error / Defect / Failure
- Verification vs. Validation
- Regression vs. Confirmation testing
- Functional vs. Non-functional testing
- Test Basis / Condition / Case / Suite
- Entry & Exit criteria
- Incident (defect) report
- Test oracle; Independence levels
- Coverage (statement, decision, requirements)

---

## Appendix: Fast Mapping (Category → Go-To Tools)
- **Test Mgmt**: Jira(+Xray/Zephyr/TestRail), Azure DevOps, qTest
- **Defects**: Jira, Bugzilla, MantisBT
- **Static Analysis**: SonarQube, ESLint, Pylint/Flake8, Checkstyle/PMD, Fortify, Coverity
- **UI/Web Automation**: Selenium, Cypress, Playwright
- **Unit**: JUnit/TestNG (Java), **PyTest** (Python), **Jest** (React/JS), Mocha/Chai, xUnit/NUnit
- **Mobile**: Appium, Espresso, XCTest/XCUITest
- **API**: Postman, RestAssured, SuperTest, Karate
- **Performance**: JMeter, LoadRunner, Gatling, k6, BlazeMeter
- **Coverage**: JaCoCo, Cobertura, coverage.py, Istanbul/nyc, dotCover
- **Security**: OWASP ZAP, Burp Suite, Veracode, Checkmarx
- **CI/CD**: Jenkins, GitHub Actions, GitLab CI/CD, Azure Pipelines, CircleCI
- **TDM/Env**: Informatica TDM, Delphix, Datprof, Mockaroo; virtualization: WireMock, Mountebank

---

### Final Tips
- Anchor your answers to **ISTQB definitions** and the **testing principles**.
- Prioritize **risk-based** thinking and **traceability** across requirements → tests → defects.
- Keep a **lightweight regression suite** + **checklists** for exploratory sessions.
- Remember: **tools amplify good processes**—they don’t replace them.

---



Artificial Intelligence in QA

Generative
* Product Requirements
* Test strategies
* Test plans
* Test scripts

Testing with AI
* QA Bots

Testing AI
* Models and training;
* Chatbots and voicebots;
* Using AI to test AI



Automation & Tooling (What’s Covered)
* Browser automation: Playwright / Cypress / Selenium (UI flows, cross‑browser/device, visual assertions, network stubbing).
* Code‑level automation: Unit & component (Jest or Vitest + React Testing Library for React/Next/TS; Pytest for Python/Django). API tests (Postman, Requests, RestAssured, SoapUI). Integration tests (service contracts, DB).
* Selenium vs BrowserStack: Selenium = automation library; BrowserStack = cloud device/browser grid (can run Selenium/Playwright/Cypress there).
* Mac setup for Selenium (Python): install Python + pip; pip install selenium webdriver-manager; use Selenium Manager or WebDriver Manager; simple pytest project; run in CI.
* Accessibility toolset: axe DevTools; Accessibility Insights for Web; TPGI ARC Toolkit; ANDI; browser helper “Web Developer” extension.
* Email testing tools: MailHog/Mailpit (dev SMTP catch‑all); Mailosaur; Ethereal Email; Mailtrap; verify content, links, headers, and deliverability separately.


CI/CD — Lean “Startup” Matrix

Must-haves
* Linting (ESLint, Ruff/Flake8)
* Type checks (TypeScript, mypy)
* Unit & component tests
* API tests (smoke)
* Build
* Basic security (npm/yarn/pip audit)
* Formatting checks (Prettier/Black)
* Docker build

Nice-to-have (phase 2)
* Playwright/Cypress smoke on PR
* Contract tests
* Accessibility smoke (axe)
* Performance budget (Lighthouse)
* Migration checks
* DB schema drift
* Seeded test data



Learning & Community
* ISTQB levels discussed: Foundation → Advanced → Specialist → Expert; prep via books/courses and sample questions.
* Events (US 2025–2026): major QA/testing conferences identified, including vendor events (e.g., Tricentis).
* Reading: industry glossaries/definitions and curated book lists for foundation prep.

Quick “Do Next” Checklist
1. Adopt the bug template and publish the reporting guide in Confluence.
2. Draft a 1-page Test Strategy (risk areas, environments, tooling, gates).
3. Stand up CI essentials (linters, types, unit tests, API smoke).
4. Pick UI automation (Playwright or Cypress) and add a single smoke flow.
5. Baseline accessibility (axe smoke) and email testing (Mailpit/Mailtrap) in dev.
6. Create a simple QA status dashboard (open defects by severity, test pass rate, release readiness).
7. Tune LinkedIn/resume with the targeted QA/SDET variant.
