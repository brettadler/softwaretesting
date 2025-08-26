# Testing Throughout the SDLC

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
