# BitAgent Testing Convention

> **IMPERATIVE**: This document defines the standards and best practices for all tests in the BitAgent project. All code submissions must comply with this convention to ensure system robustness, maintainability, and reliability.

## 1. 🧪 Testing Philosophy

We write tests not just to find bugs, but to:
- **Build Confidence**: Allow us to refactor and add new features with confidence, without fear of breaking existing logic.
- **Prevent Regressions**: Ensure that once-fixed bugs do not reappear.
- **Provide Documentation**: Clear tests serve as living documentation, showing the expected behavior of the code.
- **Drive Design**: Writing testable code often leads to more modular, loosely coupled, and high-quality code.

## 2. 🔬 Types of Tests

Our project mainly includes the following types of tests:

### 2.1. Unit Tests
- **Goal**: Verify the behavior of an independent, minimal functional unit (e.g., a function or a class method).
- **Requirements**:
    - **Fast**: Must run very quickly.
    - **Isolated**: **Must** use mocking to isolate all external dependencies, such as file systems, network requests, databases, message buses, etc.
    - **Location**: Under the `tests/` directory, corresponding to the module under test.

### 2.2. Integration Tests
- **Goal**: Verify that multiple components (e.g., multiple Agents) work correctly together.
- **Requirements**:
    - **Focus on Interaction**: Emphasize testing interfaces and data flow between components, e.g., one Agent publishes an event, another Agent receives and processes it.
    - **Limited Mocking**: Can use real internal components (like `InMemoryBus`), but should still mock external dependencies (e.g., exchange APIs).
    - **Location**: Under `tests/`, filenames should reflect their integration nature, e.g., `test_data_pipeline_integration.py`.

### 2.3. End-to-End (E2E) Tests
- **Goal**: Verify that a complete business process works as expected. For example, from `StrategyLearnerAgent` discovering a strategy, to `ChiefAgent` approval, to backtest execution and result generation.
- **Requirements**:
    - **Simulate Real Environment**: Use as little mocking as possible, with production-like configuration.
    - **Run Independently**: E2E tests are usually slow and should be run separately from unit/integration tests.
    - **Location**: `tests/e2e/` (to be created).

## 3. 🗓️ When to Test

- **New Features**: **Must** write unit or integration tests for all new business logic.
- **Bug Fixes**: **Must** first write a test that reproduces the bug (which should fail), then fix it until the test passes. This ensures the bug does not regress.
- **Refactoring**: Before refactoring, **must** ensure good test coverage for related code. After refactoring, all tests should still pass, and test logic itself should not be changed.

## 4. ✍️ Conventions

### 4.1. Location & Naming
- **Directory**: All test code must be placed in the root `tests/` folder.
- **Filename**: Test files must start with `test_`, e.g., `test_strategy_learner_agent.py`.
- **Function/Method Name**: Test functions must start with `test_` and clearly describe the scenario and expected result, e.g., `test_calculate_pnl_with_positive_result`.

### 4.2. Test Structure
- **AAA Pattern**: All test cases should follow the **Arrange-Act-Assert** (AAA) pattern:
    1.  **Arrange**: Set up all prerequisites, such as initializing objects, preparing mock data, setting up mocks, etc.
    2.  **Act**: Call the code under test or perform the action under test.
    3.  **Assert**: Verify that the result matches expectations.
- **Keep Independent**: Each test case must be completely independent; its result should not depend on the execution order or state of other tests.

### 4.3. Best Practices
- **Use Mock**: Extensively use `unittest.mock` (especially `@patch`) to isolate dependencies.
- **Clear Assertions**: Use the most precise assertion methods, e.g., `assertEqual(a, b)` instead of `assertTrue(a == b)`, `assertIsNone(x)` instead of `assertTrue(x is None)`.
- **Single Responsibility**: Each test case should test only one specific behavior or scenario.
- **Readability**: Test code should be as readable and maintainable as regular code.

## 5. 🚀 Running Tests

- **Run all tests**:
  ```bash
  ./.venv/bin/python -m unittest discover tests/
  ```
- **Run a single file**:
  ```bash
  ./.venv/bin/python -m unittest tests/test_some_agent.py
  ```

---
*Version: 1.0*
*This document is the cornerstone of our code quality. All developers must strictly comply.*
