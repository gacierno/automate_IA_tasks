# Autonomous Task Protocol v2

## 1. Global Rule
Every task MUST begin with an explicit TYPE declaration in the first line:
TYPE:
Valid modes:
 - DESIGN
 - TEST_ONLY
 - IMPLEMENTATION
 - REFACTOR
 - ANALYSIS

If TYPE is missing, the agent must stop and request clarification.

## v2. Mode Contracts (Hard Behavioral Rules)

### TYPE: DESIGN
Purpose: Architectural thinking and specification only.
Mandatory behavior:
 - Do NOT modify or create files.
 - Do NOT propose concrete implementation patches.
 - Identify ambiguities.
 - Ask clarification questions if assumptions are required.
 - Output: structured design specification.
Forbidden:
 - Writing code.
 - Suggesting execution steps.
Completion criteria:
 - All assumptions are explicit.
 - Open questions are listed.

### TYPE: TEST_ONLY
Purpose: Define expected behavior before implementation.
Mandatory behavior:
 - Create or modify test files only.
 - Do NOT modify production code.
 - If implementation is missing, write failing tests.
 - Explicitly state what behavior is being validated.
Forbidden:
 - Adding implementation logic.
 - Editing non-test files.
Completion criteria:
 - Tests compile.
 - Tests clearly express expected behavior.

### TYPE: IMPLEMENTATION
Purpose: Make existing tests pass.
Mandatory behavior:
 - Modify production code only.
 - Do NOT modify tests.
 - Respect existing design decisions.
 - Run tests after changes.
Forbidden:
 - Changing expected behavior defined in tests.
 - Refactoring unrelated code.
Completion criteria:
 - All relevant tests pass.

### TYPE: REFACTOR
Purpose: Improve internal structure without changing behavior.
Mandatory behavior.
 - Do NOT change observable behavior.
 - Do NOT modify test expectations.
 - Ensure tests pass before and after.
Forbidden:
 - Feature additions.
Completion criteria:
 - All tests pass.
