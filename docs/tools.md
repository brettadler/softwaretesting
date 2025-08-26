# Software Testing Tools
Tool Support for Testing (Categories, Examples, Vendors)

## Summary of our Go-To Tools
**Test Mgmt**: Jira(+Xray/Zephyr/TestRail), Azure DevOps, qTest
**Defects**: Jira, Bugzilla, MantisBT
**Static Analysis**: SonarQube, ESLint, Pylint/Flake8, Checkstyle/PMD, Fortify, Coverity
**UI/Web Automation**: Selenium, Cypress, Playwright
**Unit**: JUnit/TestNG, PyTest, Jest, Mocha/Chai, xUnit/NUnit
**Mobile**: Appium, Espresso, XCTest/XCUITest
**API**: Postman, RestAssured, SuperTest, Karate
**Performance**: JMeter, LoadRunner, Gatling, k6, BlazeMeter
**Coverage**: JaCoCo, Cobertura, coverage.py, Istanbul/nyc, dotCover
**Security**: OWASP ZAP, Burp Suite, Veracode, Checkmarx
**CI/CD**: Jenkins, GitHub Actions, GitLab CI/CD, Azure Pipelines, CircleCI
**TDM/Env**: Informatica TDM, Delphix, Datprof, Mockaroo; virtualization: WireMock, Mountebank


### Unit / Component / Code-level
Jest (React/JS), Vitest + React Testing Library, PyTest (Python), JUnit/TestNG (Java), Mocha/Chai (Node), xUnit/NUnit (.NET), RSpec (Ruby).

### API / Integration
Postman, Rest Assured (https://rest-assured.io), SuperTest, Karate, SoapUI.

### Web UI / Browser
Selenium, Cypress (https://www.cypress.io), Playwright (https://playwright.dev), Katalon Studio (https://katalon.com), BrowserStack cloud grid (https://www.browserstack.com/).

### Mobile
Appium, Espresso (Android), XCTest/XCUITest (iOS).

### Performance / Load / Reliability
JMeter, k6, Gatling, LoadRunner, BlazeMeter.

### Static Analysis / Coverage
SonarQube; ESLint / Pylint / Flake8 / Checkstyle / PMD; coverage: JaCoCo, Cobertura, coverage.py, Istanbul/nyc, dotCover.

### Security (AppSec)
OWASP ZAP, Burp Suite, Veracode, Checkmarx; plus Nmap/Metasploit for network-level.

### Test Management / Defects
Jira (+Xray/Zephyr/TestRail), Azure DevOps Test Plans, qTest, PractiTest, Bugzilla/MantisBT/Redmine.

### Test Data & Environments
Informatica TDM, Delphix, Datprof, Mockaroo; service virtualization: WireMock, Mountebank.

### CI/CD & Orchestration
Jenkins, GitHub Actions, GitLab CI/CD, Azure Pipelines, CircleCI.

> **Selenium vs. BrowserStack**: Selenium = automation library. BrowserStack = cloud device/browser grid that can run Selenium/Playwright/Cypress.

---


# Testing Tools

## Unit / Component / Code-level
- **Jest** — React testing
- **Vitest / Jest + React Testing Library** (noted under framework choices)
- **RSpec / ??**
- **Mocha?**
- **Cucumber?**
- **Others?**

## API / Integration
- **Postman?**
- **Rest Assured** — <https://rest-assured.io>

## Web UI / Browser
- **Selenium** — <https://medium.com/@danielwillium9355/a-comprehensive-guide-to-automated-accessibility-testing-with-selenium-e19fb950ab7c>, <https://www.baeldung.com/selenium-accessibility-testing>
- **Cypress** — <https://www.cypress.io>
- **Microsoft Playwright** — <https://playwright.dev>
- **BrowserStack** — <https://www.browserstack.com/accessibility-testing>, <https://www.browserstack.com/docs/automate/selenium>
- **Katalon Studio** — <https://katalon.com>

---





Automation & Tooling (What’s Covered)
* Browser automation: Playwright / Cypress / Selenium (UI flows, cross‑browser/device, visual assertions, network stubbing).
* Code‑level automation: Unit & component (Jest or Vitest + React Testing Library for React/Next/TS; Pytest for Python/Django). API tests (Postman, Requests, RestAssured, SoapUI). Integration tests (service contracts, DB).
* Selenium vs BrowserStack: Selenium = automation library; BrowserStack = cloud device/browser grid (can run Selenium/Playwright/Cypress there).
* Mac setup for Selenium (Python): install Python + pip; pip install selenium webdriver-manager; use Selenium Manager or WebDriver Manager; simple pytest project; run in CI.
* Accessibility toolset: axe DevTools; Accessibility Insights for Web; TPGI ARC Toolkit; ANDI; browser helper “Web Developer” extension.
* Email testing tools: MailHog/Mailpit (dev SMTP catch‑all); Mailosaur; Ethereal Email; Mailtrap; verify content, links, headers, and deliverability separately.





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
