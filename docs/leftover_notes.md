# LATEST BEFORE NEW ONE ABOVE....

# Learning the Lingo & Concepts
Welcome! Think of this as your friendly tour of **software testing**—built to match the **ISTQB Foundation Level** topics. You’ll see what the words mean, why they matter, and how to use them on the job. No jargon maze, just plain-English explanations you can put to work right away.

## Core Foundations
Before we talk tools and tactics, let’s clear up the basics that show up everywhere:

- **Verification vs. Validation**
    - **Verification** = *Are we building the product right?* You’re checking plans, designs, code, or docs against the spec—no user needed.
    - **Validation** = *Are we building the right product?* You’re checking with real flows and real expectations—does it do what users/business actually need?

- **Static vs. Dynamic Testing**
    - **Static**: You don’t run the code. You review it (or its docs) for mistakes before they turn into bugs.
    - **Dynamic**: You run the software and watch how it behaves.

- **Error → Defect → Failure**
    - **Error**: A human slip (happens to all of us).
    - **Defect/Bug**: That slip lands in the code or design.
    - **Failure**: Users see the wrong behavior in the running system.

- **Key Testing Assets**
    - **Test Condition** — the thing you want to verify (rule, requirement, path).
    - **Test Case** — the steps, data, and expected result.
    - **Test Data** — the values you plug into your test.
    - **Test Suite** — a bundle of related cases.
    - **Test Environment** — your sandbox: tools, servers, configs, data.
    - **Testware** — all your testing stuff: plans, cases, scripts, reports.

> **Tip:** When in doubt, ask: *What are we checking? How will we check it? What should happen?*

## Test Levels
Think of “levels” as zoom levels on a map. Same product, different focus:

- **Unit Testing** — Zoom way in. One function, method, or class at a time.
- **Integration Testing** — Zoom out a bit. Do the pieces play nicely together?
- **System / End-to-End (E2E) Testing** — Full picture. Real workflows from start to finish.
- **Acceptance Testing** — Customer view. Is it ready for real users? (Includes **UAT**, alpha, beta.)

> **Remember:** Higher levels don’t replace lower levels. They stack.

## Build Health & Change Safety
Every change can introduce risk. These checks keep you confident:

- **Smoke Testing** — Quick “does it start and do the basics” after a build.
- **Sanity Testing** — Narrow, “did this specific fix actually work?”
- **Regression Testing** — “Did we accidentally break something that used to work?”

## Interfaces & Layers
Where you point your tests depends on your goal:

- **API Testing** — Talk directly to the backend. Are the requests/responses correct? Do errors make sense?
- **UI Testing** — What the user sees and clicks. Does it look right and behave right?

> **Warning:** Heavy UI tests can be slow and flaky. Keep critical paths there; push logic to API/unit tests.

## Test Types

### Functional Testing
You’re checking **what** the software does:
- **Functional Testing** — Features behave like the requirements say.
- **System Testing** — The whole product meets the stated requirements.
- **User Acceptance Testing (UAT)** — Business and users give the thumbs-up.
- **Payments Testing** — Secure, accurate transactions (methods, currencies, edge cases).
- **Analytics Testing** — Events and reports show reality, not fantasy.
- **Localization (i18n/l10n)** — Text, formats, and layouts make sense for each locale.
- **Voice / AR/VR / Livestream / Mobile / Real-Device Testing** — Special areas where hardware, sensors, or networks change the game.

### Non-Functional Testing
You’re checking **how well** it does it:
- **Performance** — Is it responsive?
- **Load** — Can it handle normal peak traffic?
- **Stress** — What happens beyond the limit?
- **Scalability** — Will it behave as users/resources grow?
- **Soak / Reliability** — Does it stay stable over long runs?
- **Security** — Are we protected from misuse and attack?
- **Penetration** — Simulated attacks to find real holes.
- **Compatibility** — Browsers, devices, OS versions.
- **Accessibility** — Everyone can use it (WCAG, Section 508).
- **Installation / Upgrade** — Setup, migration, rollback work as advertised.
- **Data Integrity** — Data stays correct from end to end.
- **Recovery & Backup/Restore** — We can bounce back from trouble.

> **Remember:** Functional answers “does it work?”; non-functional answers “does it work *well enough*?”

## Test Design Techniques

This is where you turn requirements into smart, focused tests:

- **Black-Box Techniques (no code peek)**
  - **Equivalence Partitioning** — Group similar inputs; test one from each group.
  - **Boundary Value Analysis** — Check the edges (min/max and just around them).
  - **Decision Tables** — Combine conditions/rules to cover important combos.
  - **State Transitions** — Verify allowed and blocked moves between states.
  - **Use Cases** — Real-life flows from the user’s point of view.

- **White-Box Techniques (peek at code/structure)**
  - **Statement Coverage** — Every line runs at least once.
  - **Decision/Branch Coverage** — Every decision goes true and false.
  - **Condition Coverage** — Each part of a compound condition flips both ways.

- **Experience-Based**
  - **Exploratory Testing** — Learn, design, and test at the same time; follow charters.
  - **Error Guessing** — Use your spidey-sense from past bugs.
  - **Checklists** — Quick heuristics so you don’t miss the usual suspects.

- **Advanced / Modern**
  - **Mutation Testing** — Plant tiny code changes and see if tests catch them.
  - **Chaos Testing** — Inject failures (latency, crashes) to prove resilience.
  - **A/B Testing** — Compare variants with real users (stats matter!).
  - **Usability Testing** — Can people figure it out and feel good using it?

> **Tip:** Don’t try every technique on every feature. Match the technique to the risk.

## Measuring & Metrics

Metrics don’t tell the whole story, but they do help steer:

- **Test Coverage** — How much of the code/requirements is exercised.
- **Pass/Fail Rate** — How many tests passed vs. failed this run.
- **Defect Density** — Bugs per size (e.g., per 1,000 LOC).
- **MTTD** — How fast we *find* bugs.
- **MTTR** — How fast we *fix* bugs.
- **Test Execution Rate** — How many tests we run per period.
- **Escaped Defects** — Bugs that slipped into production.

> **Warning:** High coverage doesn’t guarantee good tests. Make sure important risks are covered.

## Documentation
Good notes make good teams—and easier handoffs:

- **Test Strategy** — Big-picture plan: risks, approaches, environments, quality gates.
- **Test Plan** — Near-term plan for a release/feature: who, what, when, entry/exit criteria.
- **Test Cases & Charters** — Step-by-step scripts or focused exploratory goals.
- **Traceability Matrix** — Map requirements to tests so nothing falls through the cracks.

Bug reporting best practices include:

- **Title** -
- **Environment** -
- **Build/Version** -
- **URL/Screen** -
- **Steps** -
- **Expected vs Actual** -
- **Evidence** (screens/video/logs) -
- **Severity** -
- **Priority** -
- **Owner** -
- **Links** (Jira/spec/design) -
- **Notes/Workarounds** -

> **Tip:** Clear steps + good evidence = faster fixes and happier engineers.

## Tools & Automation
Tools help you go faster and be consistent. Choose what fits your stack:

- **Browser Automation** — **Selenium**, **Playwright**, **Cypress**.
- **Unit/Component** — **Jest**/**Vitest** (+ React Testing Library) for frontend; **Pytest** for Python/Django.
- **API** — **Postman**, **RestAssured**, **SoapUI** (plus scripting if you prefer).
- **Accessibility** — **axe**, **Accessibility Insights**, **ARC Toolkit**.
- **Email** — **MailHog/Mailpit**, **Mailtrap**, **Mailosaur**.
- **Device Labs** — **BrowserStack**, **Sauce Labs** (run Selenium/Playwright/Cypress in the cloud).

> **Note:** **Selenium** is a library; **BrowserStack/Sauce** give you the cloud browsers/devices to run it on.

## CI/CD & Quality Gates

Your tests should live in the pipeline so quality checks happen early and often:

**Must-haves**
- Linting, formatting, type checks
- Unit/component tests, API smoke
- Security scans
- Build/Docker validation

**Nice-to-haves (Phase 2)**
- Cross-browser smoke on PR
- Accessibility checks
- Performance budgets (e.g., Lighthouse)
- Contract & migration checks

**Ownership Split**
- **Developers** — Units, components, contracts, static analysis.
- **QA** — Exploratory, end-to-end flows, release readiness.
- **Shared** — CI health, flaky test triage, risk reviews.

> **Tip:** Flaky tests are like leaky faucets—fix them fast or everyone starts ignoring the noise.

---

## 11) Practical Tips for New Testers

- Hunt **boundaries and edge cases**—that’s where bugs like to hide.
- For **React/Frontend**, test what users see (via RTL), not private internals.
- For **APIs**, mock external dependencies and check both happy and unhappy paths.
- Keep tests **fast** and **reliable** so the team trusts them.
- Write **clear bug reports**—future you (and your teammates) will thank you.

> **Remember:** Your mission isn’t to “break things.” It’s to build **confidence**.

---

## 12) Study & Career Growth

- **ISTQB Prep** — Do sample exams; the wording can be sneaky, so practice reading carefully.
- **Glossary Reps** — Explain terms in your own words; teach a friend or rubber duck.
- **Community** — Join QA forums, Slack/Discord groups, and attend talks or conferences.
- **Agile Know-How** — Learn Scrum rhythms; testing is part of the sprint, not after it.
- **Defect Triage** — Watch how priorities are set—it’s where risk meets reality.

---

## Final Thought

Great testing is about shining a bright, honest light on product quality. With the concepts in this chapter, you’ll speak the language, spot the risks, and help your team ship with confidence—**and** you’ll be ready for those ISTQB questions when they come your way.





# ORIGINAL -----------

## What about the 7 types of testing???

# Learning the Lingo & Concepts
A glossary of important software testing terms and concepts, with an emphasis on those commonly covered in the ISTQB Foundation Level exam.

---

## Unit / Integration / System Levels
- **Unit Testing** — Validates individual functions, methods, or classes in isolation.
- **Integration Testing** — Ensures that modules/components interact and exchange data correctly.
- **System / End-to-End (E2E) Testing** — Tests the full, integrated application against requirements by exercising real-world workflows.

---

## Build Health & Change Safety
- **Smoke Testing** — A quick check that critical application paths work after a build or deployment.
- **Sanity Testing** — A focused test of specific areas after small fixes or changes.
- **Regression Testing** — Confirms that new code changes have not broken existing functionality.

---

## Interface & Layer Testing
- **API Testing** — Verifies that APIs return correct responses, handle errors gracefully, and integrate well with other systems.
- **UI Testing** — Ensures visual correctness and interactive behavior of the user interface.

---

## Non-Functional & Quality Attributes
- **Performance Testing** — Assesses system speed, responsiveness, and stability under load or stress to ensure scalability.
- **Load Testing** — Validates behavior under expected peak usage.
- **Stress Testing** — Pushes the system beyond limits to observe breakdown points.
- **Scalability Testing** — Measures performance when resources/users grow.
- **Soak / Reliability Testing** — Long-duration testing to detect memory leaks and stability issues.
- **Security Testing** — Detects vulnerabilities, authentication flaws, and misconfigurations.
- **Penetration Testing** — Simulated malicious attacks to exploit weaknesses.
- **Compatibility Testing** — Validates across browsers, devices, operating systems, and environments.
- **Accessibility Testing** — Confirms compliance with standards (e.g., WCAG, Section 508).
- **Localization / Internationalization (i18n/l10n)** — Ensures correct formats, content, and layouts across locales.
- **Installation / Upgrade Testing** — Verifies setup, migration, and rollback procedures.
- **Data Integrity Testing** — Confirms correctness of data storage, transformation, and retrieval.
- **Recovery Testing** — Evaluates system’s ability to recover after crashes or outages.
- **Backup / Restore Testing** — Ensures reliability of disaster recovery processes.
- **Domain-Specific Checks** — E.g., **Mobile**, **Payments**, **Analytics**, **Voice**, **AR/VR**, **Livestream**, **Location-based services**, **Real-device validation**.

---

## Techniques & Testing Styles
- **Static Testing** — Reviews artifacts (code, design, docs) without executing software.
- **Black-box / White-box / Gray-box** — Test design approaches based on no/some/full internal knowledge.
- **Exploratory Testing** — Simultaneous learning, design, and execution of tests, guided by tester intuition.
- **Ad Hoc Testing** — Informal, unstructured testing without predefined cases.
- **Mutation Testing** — Injects small code changes to evaluate test suite effectiveness.
- **Chaos Engineering** — Introduces failures into production-like systems to validate resilience.
- **A/B Testing** — Compares variants in production to analyze user impact statistically.
- **Usability Testing** — Assesses intuitiveness, clarity, and satisfaction for end users.
- **Acceptance Testing (UAT)** — Confirms software meets user and business needs before release.

---

## Testing Metrics
- **Test Coverage** — Percentage of code, requirements, or functionality exercised by tests.
- **Pass/Fail Rates** — Ratio of test cases passed vs. failed.
- **Defect Density** — Defects per unit size (e.g., per 1,000 LOC).
- **Mean Time to Detect (MTTD)** — Average time to find defects after introduction.
- **Mean Time to Resolve (MTTR)** — Average time to fix and close defects.
- **Test Execution Rate** — Number of test cases executed in a given period.
- **Escaped Defects** — Bugs found in production that testing missed.

---

## Common Testing Types & Concepts
- **Functional Testing** — Verifies that features behave according to requirements.
- **User Acceptance Testing (UAT)** — Final check by business stakeholders and users.
- **Beta Testing** — Releases to a limited external group for feedback.
- **Automation Testing** — Uses scripts/tools (e.g., Selenium, Cypress, Playwright) for repeatable execution.
- **Manual Testing** — Human-executed testing, often for exploratory, usability, or ad hoc validation.
- **Mobile Testing** — Covers devices, OS versions, and performance on handhelds.
- **Real-Device Testing** — Uses actual devices rather than emulators for accuracy.
- **Payments Testing** — Validates secure, accurate, multi-currency transaction flows.
- **Analytics Testing** — Confirms correct user event tracking and reporting.
- **AR/VR Testing** — Validates augmented/virtual reality experiences.
- **Voice Testing** — Evaluates voice-command systems (e.g., Alexa, Siri).
- **Livestream Testing** — Tests video streaming quality, buffering, and latency.
- **Compatibility / Cross-Browser Testing** — Confirms consistent behavior across environments.
- **Localization Testing** — Ensures correct adaptation for specific languages and regions.
- **Defect Investigation & Validation** — Reproduction, analysis, and confirmation of bug fixes.

---

## Testing Processes & Documentation
- **Bug Reports** — Standard fields: Title, Environment, Version, Steps, Expected/Actual, Evidence, Severity, Priority.
- **Test Strategy** — Long-term, product-level: scope, risks, tools, environments, quality goals.
- **Test Plan** — Project/release-specific: schedule, resources, entry/exit criteria, assignments.
- **Test Cases & Charters** — Detailed steps or exploratory guides tied to requirements.
- **Traceability Matrix** — Maps requirements to test cases for coverage validation.

---

## Tools & Automation
- **Browser Automation** — Playwright, Cypress, Selenium (UI flows, cross-browser/device).
- **Unit & Component Testing** — Jest/Vitest for React/TS, Pytest for Python/Django.
- **API Testing Tools** — Postman, RestAssured, SoapUI.
- **Accessibility Tools** — axe DevTools, Accessibility Insights, ARC Toolkit.
- **Email Testing Tools** — Mailtrap, MailHog, Mailosaur.
- **Device Testing Platforms** — BrowserStack, Sauce Labs for cloud-based environments.

---

## CI/CD & Quality Gates
**Essential Checks**:
- Linting, formatting, type checks.
- Unit/component/API smoke tests.
- Security scanning (npm audit, pip audit).
- Docker build validation.

**Extended Checks**:
- Cross-browser smoke tests.
- Contract and migration tests.
- Accessibility smoke checks.
- Performance budgets (e.g., Lighthouse).

**Ownership Matrix**:
- **Developers** — Unit/component tests, contracts, static analysis.
- **QA/Testers** — Exploratory, end-to-end flows, release validation.
- **Shared** — CI/CD health, flaky test triage, risk-based reviews.

---

## Guidance & Study Tips
- Focus on **risk-based testing** concepts (core in ISTQB).
- Differentiate clearly between **static vs dynamic testing**, and **verification vs validation**.
- Learn **test levels vs test types** distinctions.
- Understand **black-box techniques** (equivalence partitioning, boundary value analysis) and **white-box techniques** (statement, decision coverage).
- Use ISTQB sample papers and glossaries for preparation.
- Engage with QA communities, study groups, and events to deepen practical understanding.

# ------------------------------

# Learning the Lingo & Concepts

## Testing Types/Terms
* AR/VR Testing – Tests augmented and virtual reality applications for user experience, performance, and hardware compatibility.
* Accessibility Testing (Section 508 and WCAG compliance) – Ensures software is usable by people with disabilities, meeting legal standards like Section 508 and WCAG.
* Analytics Testing – Checks that user actions are accurately tracked and reported by analytics platforms for data-driven decisions.
* Automation & Automated Testing – Uses scripts and tools to automatically execute tests, speeding up regression and repetitive testing tasks.
* Beta Testing – Releases software to a limited external audience to gather feedback before full launch, identifying real-world issues.
* Black Box, Gray Box, and White Box Testing – Refers to different levels of tester knowledge: black box (no internal knowledge), gray box (partial), white box (full code-level understanding).
* Compatibility Testing & Cross Browser/OS System Testing – Ensures consistent behavior and appearance across different browsers, devices, and operating systems.
* Decomp and Test Script Development – Reverse engineers or analyzes app builds (decomp) and writes scripts for automated or manual test execution.
* Defect Investigation and Validation – Involves analyzing, reproducing, and confirming bugs, and retesting fixes to ensure resolution.
* Exploratory Testing – Involves unscripted, hands-on testing to uncover unexpected behavior, driven by tester intuition and experience.
* Functional Testing – Verifies that software features work according to requirements, focusing on user actions and expected outcomes.
* Functional Testing and Acceptance Testing – Functional testing checks features work; acceptance testing ensures software meets business and end-user needs.
* Graphic Uniformity of Web Pages and Applications – Ensures consistent layout, styling, and branding across UI elements for a polished and professional look.
* Lifecycle Management – Manages testing activities across the software development lifecycle, from planning to release and maintenance.
* Livestream Testing – Validates the quality and stability of live video streaming, including buffering, resolution, and latency.
* Localization Testing – Validates that software is correctly adapted for different languages, regions, and cultural expectations.
* Location Testing – Tests location-based features (e.g., GPS, geofencing) to ensure accurate behavior across regions and devices.
* Mobile App Testing – Tests mobile applications on various devices and OS versions for functionality, performance, and usability.
* On-Demand Project Work – Offers flexible, short-term testing and QA services tailored to specific project needs.
* Payments Testing – Tests the payment flow, ensuring secure, accurate transactions across various methods and currencies.

* QA and Manual Writing – Documents testing processes and procedures, including step-by-step instructions for manual testers or users.
* Real-Device Testing – Tests apps or websites on actual physical devices (not emulators) to ensure accurate performance and behavior.
* Regression Testing – Re-tests existing functionality to ensure new code changes haven't introduced bugs in previously working features.
* Regression and Exploratory Testing – Combines structured re-testing of known functionality with informal testing to uncover unexpected bugs.
* Sanity Testing – Verifies that specific functionality works as expected after a bug fix or minor update.
* Smoke Testing – A quick initial test to check if the most critical functions of the application work after a new build.
* Staff Augmentation – Provides skilled QA professionals to support existing teams for short or long-term projects.
* Subjective Testing – Evaluates aspects like look-and-feel, design quality, or user preference, often based on human judgment.
* System Testing – Validates the complete and integrated software system for compliance with the requirements.
* Test Case Maintenance – Keeps existing test cases up to date with software changes and enhancements.
* Test Case Writing and Editing – Develops and maintains step-by-step test scenarios based on requirements and user stories.
* Test Design and Test Plans – Involves defining test objectives, scope, approach, and detailed test cases to systematically validate software.
* Test Plan Management – Oversees the creation, execution, and tracking of comprehensive test plans for projects.
* Usability Testing – Assesses how intuitive and user-friendly the software is by observing real users completing tasks.
* User Acceptance Testing (UAT) – Confirms that the software meets business needs and is ready for deployment by having real users validate it.
* Voice Testing – Tests voice-controlled interfaces (e.g., Siri, Alexa) for accurate recognition, response, and functionality.


* Manual testing
* Automated testing
* Test cases
* Selenium / Playwright / Cypress
* CI/CD
* Regression
* Accessibility / WCAG
* Performance
* Python / JS / TypeScript
* Jira
* Agile / Scrum
* Defect triage




Non‑Functional / Quality Attributes


* Stress testing — Beyond limits to see how/where the system fails.

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

Scenarios:
* Mobile
* Payments
* Analytics
* Voice
* AR/VR
* Livestream
* Real‑device
* Location — Domain‑specific non‑functional checks as applicable

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



* Browser automation: Playwright / Cypress / Selenium (UI flows, cross‑browser/device, visual assertions, network stubbing).
* Code‑level automation: Unit & component (Jest or Vitest + React Testing Library for React/Next/TS; Pytest for Python/Django). API tests (Postman, Requests, RestAssured, SoapUI). Integration tests (service contracts, DB).
* Selenium vs BrowserStack: Selenium = automation library; BrowserStack = cloud device/browser grid (can run Selenium/Playwright/Cypress there).
* Mac setup for Selenium (Python): install Python + pip; pip install selenium webdriver-manager; use Selenium Manager or WebDriver Manager; simple pytest project; run in CI.
* Accessibility toolset: axe DevTools; Accessibility Insights for Web; TPGI ARC Toolkit; ANDI; browser helper “Web Developer” extension.
* Email testing tools: MailHog/Mailpit (dev SMTP catch‑all); Mailosaur; Ethereal Email; Mailtrap; verify content, links, headers, and deliverability separately.

Framework choices for your stack
* Frontend (React/Next.js/TypeScript): Vitest or Jest + React Testing Library. (Vitest: faster, ESM‑first, Vite‑native. Jest: mature ecosystem; may need ESM config.)
* Backend (Python/Django/PostgreSQL): Pytest (+ pytest‑django, factory_boy, coverage).
* ESM: ECMAScript Modules — native JS module system (import/export), replacing CommonJS in modern toolchains.


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

Unit/Component Testing Advice to Devs
* Focus on pure logic first; test branches and edge cases.
* For React: test via RTL (user-visible behavior), hooks in isolation; avoid implementation details.
* Use factories/builders for data; isolate network with mocks.
* Keep tests fast and deterministic; measure coverage but prioritize critical path and risk.

Learning & Community
* ISTQB levels discussed: Foundation → Advanced → Specialist → Expert; prep via books/courses and sample questions.
* Events (US 2025–2026): major QA/testing conferences identified, including vendor events (e.g., Tricentis).
* Reading: industry glossaries/definitions and curated book lists for foundation prep.
