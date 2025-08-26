# Learning the Lingo & Concepts
Welcome! Think of this as your friendly tour of **software testing**—built to match the **ISTQB Foundation Level** topics. You’ll see what the words mean, why they matter, and how to use them on the job. No jargon maze, just plain-English explanations you can put to work right away.

## Core Foundations

Before we talk tools and tactics, let’s clear up the basics that show up everywhere:

- **Verification vs. Validation**
    - **Verification** = *Are we building the product right?* Check plans, designs, code, or docs against the spec—no user needed.
    - **Validation** = *Are we building the right product?* Run real flows—does it meet user/business needs?

- **Static vs. Dynamic Testing**
    - **Static**: Don’t run the code—review it (or its docs) to catch issues early.
    - **Dynamic**: Run the software and observe behavior.

- **Error → Defect → Failure**
    - **Error**: Human slip.
    - **Defect/Bug**: The slip ends up in the product.
    - **Failure**: The wrong behavior shows up at runtime.

- **Test Independence (worth knowing for ISTQB)**
    - Different eyes find different bugs. From least to most independent: **dev tests own code → peer dev → tester on the team → external/independent test group**.

- **Defect Lifecycle (quick tour)**
    - *New → Assigned → In Progress → Fixed → Re-test → Closed* (or *Reopened* if it still fails).


> **Tip:** When in doubt, ask: *What are we checking? How will we check it? What should happen?*

## Test Levels

Think of “levels” as zoom levels on a map. Same product, different focus:

- **Unit Testing** — Zoom way in. One function, method, or class at a time.
- **Integration Testing** — Zoom out a bit. Do the pieces play nicely together?
- **System / End-to-End (E2E) Testing** — Full picture. Real workflows from start to finish.
- **Acceptance Testing** — Customer view. Is it ready for real users?
  - **Alpha** (internal pilots), **Beta** (external pilots), **UAT** (business/users sign-off).

> **Maintenance Testing:** After release, fixes and small changes still need impact analysis and regression—usually at system/acceptance levels.
> **Remember:** Higher levels don’t replace lower levels. They stack.

## Build Health & Change Safety

Every change can introduce risk. These checks keep you confident:

- **Smoke Testing** — Quick “does it start and do the basics?” after a build (often automated in CI).
- **Sanity Testing** — Narrow “did this specific fix actually work?” check (often manual, targeted).
- **Regression Testing** — “Did we accidentally break something that used to work?”

> **See also:** CI/CD section for flaky-test triage and keeping smoke tests dependable.

## Interfaces & Layers

Where you point your tests depends on your goal:

- **API Testing** — Talk directly to the backend. Are requests/responses correct? Are errors helpful?
  - **Contract Testing** — Provider/consumer contracts to catch breaking API changes early.
- **UI Testing** — What the user sees and clicks. Does it look right and behave right?
  - **Lean on Component Tests** to cover UI logic without overloading E2E.

> **Warning:** Heavy UI suites can be slow and flaky. Keep critical paths there; shift logic to API/unit/component tests.

## Test Types

### Functional Testing
You’re checking **what** the software does:

- **Functional Testing** — Features match requirements.
- **System Testing** — The whole product meets the stated requirements.
- **User Acceptance Testing (UAT)** — Business/users give the thumbs-up.
- **Payments Testing** — Secure, accurate transactions (methods, currencies, edge cases).
- **Analytics Testing** — Events and reports reflect reality.
- **Localization (i18n/l10n)** — Text, formats, layouts make sense per locale.
- **Voice / AR/VR / Livestream / Mobile / Real-Device** — Hardware, sensors, and network conditions matter.

### Non-Functional Testing
You’re checking **how well** it does it:

- **Performance** — Is it responsive?
- **Load** — Can it handle normal peaks?
- **Stress** — What happens beyond the limit?
- **Scalability** — How does it behave as users/resources grow?
- **Reliability (a.k.a. Soak)** — Long runs: leaks, degradation, stability.
- **Security** — Find weaknesses and misconfigurations.
- **Penetration** — Try to exploit paths to prove impact.
- **Compatibility** — Browsers, devices, OS versions.
- **Accessibility** — Keyboard-only use, screen readers, contrast, focus order (WCAG, Section 508).
- **Installation / Upgrade** — Setup, migration, rollback.
- **Data Integrity** — Data remains correct through the flow. *(Data quality—validity/completeness rules—may sit with product/analytics, but you’ll touch it.)*
- **Recovery & Backup/Restore** — Can we bounce back from trouble?

> **Rule of thumb:** Functional answers “does it work?”; non-functional answers “does it work *well enough*?”

## Test Design Techniques

Turn requirements into smart, focused tests:

- **Black-Box Techniques (no code peek)**
    - **Equivalence Partitioning** — Group similar inputs; test one from each group.
    - **Boundary Value Analysis** — Hit the edges: *min−1, min, min+1* and *max−1, max, max+1* (catch those off-by-one bugs).
    - **Decision Tables** — Cover combinations of rules/conditions.
    - **State Transitions** — Check allowed/blocked moves between states (sequence/time matters).
    - **Use Cases** — Real-life flows from the user’s view.
    - **Combinatorial / Pairwise** — Cover many inputs with fewer tests (orthogonal arrays).

- **White-Box Techniques (peek at structure)**
    - **Statement Coverage** → **Decision/Branch Coverage** → **Condition Coverage** (ladder of rigor; MC/DC exists but is advanced).

- **Experience-Based**
    - **Exploratory Testing** — Learn, design, and test at once; use **charters**.
    - **Error Guessing** — Use your history of where things break.
    - **Checklists** — Heuristics so you don’t miss usual suspects.
    - **Session-Based Test Management (SBTM)** — Time-boxed sessions with goals and notes.

- **Advanced / Modern**
    - **Mutation Testing** — Plant tiny code changes; see if tests catch them.
    - **Chaos Testing** — Inject failures (latency, crashes) to prove resilience.
    - **A/B Testing** — Compare variants with real users (stats matter).
    - **Usability Testing** — Can people figure it out and feel good using it?

> **Pick the right tool:** Decision tables are great for static business rules; state models shine when order/sequence matters.

## Measuring & Metrics

Metrics help steer—not drive—the car:

- **Test Coverage** — Of requirements and/or code (these are different; both can help).
- **Pass/Fail Rate** — What passed vs. failed this run.
- **Defect Density** — Bugs per size (e.g., per 1,000 LOC).
- **MTTD / MTTR** — How fast we **find** and **fix** issues.
- **Test Execution Rate** — How many tests per cycle.
- **Escaped Defects** — What reached production.

> **Caution:** Metrics can be gamed. Pair numbers with risk and context.
> **Severity vs Priority:** *Severity* = impact if it happens; *Priority* = how urgently we address it.

## Documentation Process

Good notes make good teams—and easier handoffs:

- **Test Strategy** — Big-picture plan: risks, approaches, envs, quality gates.
- **Test Plan** — Release/feature plan: who/what/when, entry/exit criteria.
- **Test Cases & Charters** — Scripts or focused exploratory missions.
- **Traceability Matrix** — Map requirements ↔ tests (typical columns: *Req ID, Test IDs, Status, Risks*).


- **Test Condition** — what you verify (a rule, requirement, path).
- **Test Case** — steps, data, expected result.
- **Test Data** — values you plug in (normal, boundary, negative).
- **Test Suite** — bundle of related cases.
- **Test Environment** — your sandbox: tools, servers, configs, data.
- **Testware** — all testing artifacts (plans, cases, scripts, reports).
- **Entry / Exit Criteria** — when to start/stop (e.g., *Entry*: env ready, data loaded; *Exit*: 0 criticals, 95% high-priority tests passed).

### Bug Reporting
Bug reporting best practices include:

- **Title** -
- **Environment/OS/Browser/App Build** -
- **Version** -
- **URL/Screen** -
- **Steps** -
- **Expected vs Actual** -
- **Evidence links**  - video, screenshots, logs
- **Severity** -
- **Priority** -
- **Owner** -
- **Related links** - Jira, spec, design
- **Notes/Workarounds**

## Tools & Automation

Tools help you test faster, automate repetitive work, and ensure consistency. Here are the main categories and popular tools:

- **Browser Automation:** Automate user flows in web browsers for UI and end-to-end testing. Popular tools: *Selenium*, *Playwright*, *Cypress*
- **Unit/Component Testing:** Test individual functions, components, or modules in isolation. Popular tools: *Jest*, *Vitest (+ React Testing Library)*, *Pytest (Python/Django)*
- **API Testing:** Validate backend services, endpoints, and integrations. Popular tools: **Postman**, *RestAssured*, *SoapUI*; also CLI tools like *curl* or language SDKs
- **Accessibility Testing:** Check for compliance with accessibility standards (WCAG, Section 508). Popular tools: *axe*, *Accessibility Insights*, *ARC Toolkit*
- **Email Testing:** Simulate and verify email flows in development and staging Popular tools: *MailHog*, *Mailpit*, *Mailtrap*, *Mailosaur*
- **Device Labs:** Test across real devices and browsers in the cloud. Popular tools: *BrowserStack*, *Sauce Labs*
- **Visual Testing (optional):** Detect visual regressions and layout changes. Popular tools: *Percy*, *Applitools*

> **Test Pyramid reminder:** Many **unit/component**, some **API**, fewer **E2E**—for speed and trust.

## CI/CD & Quality Gates

Your tests belong in the pipeline so quality checks happen early and often:

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

**Gates vs Monitors**
- **Gates** block a merge/release (e.g., unit tests must pass).
- **Monitors** inform but don’t block (e.g., performance trends).

**Flaky Test Protocol**
Quarantine quickly, fix or delete, and track time-to-fix for flakies.

**Security Scan Labels (quick map)**
- **SCA** (dependencies), **SAST** (code), **DAST** (running app).

## Practical Tips for New Testers

- Hunt **boundaries and edge cases**—bugs love edges.
- For **React/Frontend**, test what users see (via RTL), not internals.
- For **APIs**, mock external systems; check happy and unhappy paths.
- Keep tests **fast** and **reliable** so the team trusts them.
- Write **clear bug reports**—future you will thank you.
- Try **negative testing**: bad inputs, timeouts, network hiccups.
- Keep **known-good** and **known-bad** datasets; plan **data reset/cleanup**.
- Heuristics to remember: **Goldilocks** (too low/too high/just right), **RCRCRC** for regression focus (Recent, Core, Risky, Changed, Repaired, Configs).

> **Mission statement:** You’re not “breaking” things—you’re building **confidence**.

## Study & Career Growth

- **ISTQB Prep** — One timed mock per week; next day, review only the wrong ones and fix the gaps.
- **Glossary Reps** — Make flashcards for look-alike terms (Validation vs Verification, Re-test vs Regression).
- **Community** — QA forums, Slack/Discord groups, meetups, conferences.
- **Agile Know-How** — Testing is part of the sprint, not after it.
- **Re-test vs Regression (exam favorite)** — **Re-test** checks the **fix**; **Regression** checks for **side effects** elsewhere.

## Final Thought

Great testing is about shining a bright, honest light on product quality. With the concepts in this chapter, you’ll speak the language, spot the risks, and help your team ship with confidence—**and** you’ll be ready for those ISTQB questions when they come your way.
