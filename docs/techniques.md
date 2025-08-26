## Test Techniques


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
