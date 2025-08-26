# Software Testing Tools
Tool Support for Testing (Categories, Examples, Vendors)

## Summary of our Go-To Tools

- **Test Mgmt**: Jira(+Xray/Zephyr/TestRail), Azure DevOps, qTest
- **Defects**: Jira, Bugzilla, MantisBT
- **Static Analysis**: SonarQube, ESLint, Pylint/Flake8, Checkstyle/PMD, Fortify, Coverity
- **UI/Web Automation**: Selenium, Cypress, Playwright
- **Unit**: JUnit/TestNG, PyTest, Jest, Mocha/Chai, xUnit/NUnit
- **Mobile**: Appium, Espresso, XCTest/XCUITest
- **API**: Postman, RestAssured, SuperTest, Karate
- **Performance**: JMeter, LoadRunner, Gatling, k6, BlazeMeter
- **Coverage**: JaCoCo, Cobertura, coverage.py, Istanbul/nyc, dotCover
- **Security**: OWASP ZAP, Burp Suite, Veracode, Checkmarx
- **CI/CD**: Jenkins, GitHub Actions, GitLab CI/CD, Azure Pipelines, CircleCI
- **TDM/Env**: Informatica TDM, Delphix, Datprof, Mockaroo; virtualization: WireMock, Mountebank

### Unit / Component / Code-level
- Jest (React/JS)
- Vitest + React Testing Library
- PyTest (Python)
- JUnit/TestNG (Java)
- Mocha/Chai (Node)
- xUnit/NUnit (.NET)
- RSpec (Ruby)

### API / Integration
- Postman
- Rest Assured (https://rest-assured.io)
- SuperTest
- Karate
- SoapUI

### Web UI / Browser
- Selenium
- Cypress (https://www.cypress.io)
- Playwright (https://playwright.dev)
- Katalon Studio (https://katalon.com)
- BrowserStack cloud grid (https://www.browserstack.com/)

### Mobile
- Appium
- Espresso (Android)
- XCTest/XCUITest (iOS)

### Performance / Load / Reliability
- JMeter
- k6
- Gatling
- LoadRunner
- BlazeMeter.

### Static Analysis / Coverage
- SonarQube; 
- ESLint / Pylint / Flake8 / Checkstyle / PMD; 
- coverage: JaCoCo, Cobertura, coverage.py, Istanbul/nyc, dotCover

### Security (AppSec)
- OWASP ZAP, Burp Suite, Veracode, Checkmarx; plus Nmap/Metasploit for network-level.

### Test Management / Defects
- Jira (+Xray/Zephyr/TestRail)
- Azure DevOps Test Plans
- qTest
- PractiTest
- Bugzilla/MantisBT/Redmine

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

  # Software Testing Tools

  This page provides an organized overview of essential tools for software testing, grouped by category. Each section includes popular tools, their purpose, and links for further exploration.

  ---

  ## Quick Reference Table

  | Category                | Key Tools & Vendors                                                                 |
  |------------------------ |-----------------------------------------------------------------------------------|
  | Test Management         | Jira (+Xray/Zephyr/TestRail), Azure DevOps, qTest, PractiTest, TestLink            |
  | Defect Tracking         | Jira, Bugzilla, MantisBT, Redmine                                                  |
  | Static Analysis         | SonarQube, ESLint, Pylint/Flake8, Checkstyle, PMD, Fortify, Coverity               |
  | UI/Web Automation       | Selenium, Cypress, Playwright, Katalon Studio, BrowserStack                        |
  | Unit Testing            | JUnit, TestNG, PyTest, Jest, Mocha/Chai, xUnit/NUnit, RSpec                        |
  | Mobile Testing          | Appium, Espresso, XCTest/XCUITest                                                  |
  | API Testing             | Postman, RestAssured, SuperTest, Karate, SoapUI                                    |
  | Performance Testing     | JMeter, LoadRunner, Gatling, k6, BlazeMeter                                        |
  | Coverage Measurement    | JaCoCo, Cobertura, coverage.py, Istanbul/nyc, dotCover                            |
  | Security Testing        | OWASP ZAP, Burp Suite, Veracode, Checkmarx, Nmap, Metasploit                      |
  | CI/CD & Orchestration   | Jenkins, GitHub Actions, GitLab CI/CD, Azure Pipelines, CircleCI                   |
  | Test Data & Environments| Informatica TDM, Delphix, Datprof, Mockaroo, WireMock, Mountebank                  |

  ---

  ## Tool Categories & Details

  ### Test Management
  Manage test assets, traceability, execution, and reporting. Integrate with CI/CD and issue tracking.
  - **Jira** (+Xray, Zephyr, TestRail)
  - **Azure DevOps Test Plans**
  - **qTest**, **PractiTest**, **TestLink**

  ### Defect / Issue Tracking
  Log, triage, and track defects. Link issues to requirements and tests.
  - **Jira**, **Bugzilla**, **MantisBT**, **Redmine**

  ### Static Analysis / Code Quality
  Analyze code for standards and vulnerabilities without execution.
  - **SonarQube**, **ESLint** (JS/TS), **Pylint/Flake8** (Python), **Checkstyle/PMD** (Java), **Fortify**, **Coverity**

  ### Test Execution & Automation
  Automate tests for web, unit, mobile, and APIs.
  - **Web/UI**: Selenium WebDriver, Cypress, Playwright, Katalon Studio, BrowserStack
  - **Unit**: JUnit, TestNG, PyTest, Jest, Mocha/Chai, xUnit/NUnit, RSpec
  - **Mobile**: Appium, Espresso (Android), XCTest/XCUITest (iOS)
  - **API**: Postman, RestAssured, SuperTest, Karate, SoapUI

  ### Performance / Load / Reliability
  Test throughput, latency, scalability, and stability under stress.
  - **JMeter**, **LoadRunner**, **Gatling**, **k6**, **BlazeMeter**

  ### Coverage Measurement
  Measure code and requirement coverage.
  - **JaCoCo**, **Cobertura** (Java), **coverage.py** (Python), **Istanbul/nyc** (JS/TS), **dotCover** (.NET)

  ### Security Testing (AppSec)
  Test for vulnerabilities, compliance, and threats.
  - **OWASP ZAP**, **Burp Suite**, **Veracode**, **Checkmarx**, **Nmap**, **Metasploit**

  ### Test Data Management & Environments
  Generate, mask, and manage test data and environments. Use virtualization for service simulation.
  - **Informatica TDM**, **Delphix**, **Datprof**, **Mockaroo**, **WireMock**, **Mountebank**

  ### CI/CD & Orchestration
  Automate builds, tests, and deployments. Integrate results and gates.
  - **Jenkins**, **GitHub Actions**, **GitLab CI/CD**, **Azure Pipelines**, **CircleCI**

  ---

  ## Special Topics & Tips

  - **Selenium vs. BrowserStack**: Selenium is an automation library; BrowserStack is a cloud device/browser grid that can run Selenium, Playwright, or Cypress tests.
  - **Accessibility Testing**: axe DevTools, Accessibility Insights for Web, TPGI ARC Toolkit, ANDI, Web Developer extension.
  - **Email Testing**: MailHog, Mailpit, Mailosaur, Ethereal Email, Mailtrap.
  - **Mac Setup for Selenium (Python)**:

    1. Install Python & pip
    2. `pip install selenium webdriver-manager`
    3. Use Selenium Manager or WebDriver Manager
    4. Create a simple pytest project and run in CI

  ---

  ## Benefits of Testing Tools

  - Efficiency and repeatability
  - Traceability and reporting
  - Integration with agile/DevOps
  - Faster feedback and automation

  ## Risks & Challenges

  - Over-reliance and maintenance overhead
  - Learning curve and environment flakiness
  - False sense of coverage

  ## Success Factors

  - Set clear goals and ROI
  - Pilot tools before full adoption
  - Provide training and coaching
  - Integrate with process and CI
  - Review metrics and adapt
