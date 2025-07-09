**Purpose**: Comprehensive testing framework

---

@include shared/universal-constants.yml#Universal_Legend

## Command Execution
Execute: immediate. --plan→show plan first
Legend: Generated based on symbols used in command
Purpose: "[Action][Subject] in $ARGUMENTS"

Create or run comprehensive test suites for code specified in $ARGUMENTS using modern testing frameworks and methodologies.

@include shared/flag-inheritance.yml#Universal_Always

Examples:
- `/test --tdd` - Test-driven development workflow
- `/test --coverage` - Generate coverage report
- `/test --watch` - Continuous test mode
- `/test --integration` - Run integration tests
- `/test --e2e` - Run end-to-end tests

## Command-Specific Flags
--tdd: "Test-driven development workflow (write failing test→implement→pass)"
--coverage: "Generate detailed coverage reports w/ uncovered lines"
--integration: "Run integration tests across components/services"
--e2e: "Run end-to-end tests w/ real browser/environment"
--unit: "Focus on unit tests only (default)"
--mutation: "Run mutation testing to verify test quality"
--snapshot: "Update/verify snapshot tests"
--watch: "Run tests continuously on file changes"
--bail: "Stop on first test failure"
--parallel: "Run tests in parallel workers"
--update-snapshots: "Update all snapshot tests"

## Testing Approaches

**Unit Testing:** Isolated component/function tests | Mock all dependencies | Fast execution | High coverage target

**Integration Testing:** Component interaction tests | Real service calls | Database transactions | API endpoint tests

**E2E Testing:** Full user workflows | Browser automation | Real environment | Critical path coverage

**TDD Workflow:** Red→Green→Refactor cycle | Write minimal code | Comprehensive coverage | Design emergence

## Testing Patterns

**Test Structure:** Arrange-Act-Assert (AAA) | Given-When-Then (BDD) | Setup→Execute→Verify→Teardown

**Coverage Targets:** Statements: 80%+ | Branches: 75%+ | Functions: 90%+ | Lines: 80%+

**Test Organization:** 
- `__tests__/` or `test/` directories
- `*.test.{js,ts}` or `*.spec.{js,ts}` naming
- Mirror source structure in test directories
- Group by feature or component

@include shared/quality-patterns.yml#Test_Quality_Standards

## Framework Support

**JavaScript/TypeScript:** Jest (default) | Mocha + Chai | Vitest | Testing Library

**Bun Runtime:** Bun test (built-in) | Jest compatibility | Fast execution | TypeScript support

**Solid.js:** Solid Testing Library | Jest + jsdom | Vitest | Component testing

**Astro:** Astro test utils | Vitest | E2E with Playwright | Component islands testing

**Rust:** cargo test (built-in) | Tokio test | Integration tests | Benchmark tests
- **Axum:** Tower test utilities | HTTP request testing | Middleware testing
- **Tonic (gRPC):** tonic-build test client | Service testing | Mock servers
- **Async-GraphQL:** Schema testing | Query validation | Subscription testing

**Go:** Built-in testing | Testify | Ginkgo/Gomega
- **gRPC:** grpc-go test client | Service testing | Mock generation

**Python:** pytest (default) | unittest | nose2 | doctest
- **FastAPI:** TestClient | Async testing | Dependency injection testing

**Mojo:** Mojo test framework | Performance testing | ML model validation

**Android (Jetpack Compose):** 
- **Unit:** JUnit 5 | Mockito | Robolectric
- **UI:** Compose Testing | Espresso | UI Automator
- **Integration:** Hilt testing | Room testing | Navigation testing

**iOS (SwiftUI):**
- **Unit:** XCTest | Quick + Nimble | SwiftTesting
- **UI:** SwiftUI Testing | XCUITest | ViewInspector
- **Integration:** Core Data testing | Combine testing | Navigation testing

**Other:** Framework-specific best practices | Native test runners

## Deliverables

**Test Files:** Created in appropriate test directories | Following naming conventions | Comprehensive test cases

**Coverage Reports:** HTML report in `coverage/` | Console summary | Uncovered line identification

**CI Configuration:** GitHub Actions | CircleCI | Jenkins | GitLab CI

**Documentation:** Test plan | Test cases | Coverage goals | CI/CD integration

@include shared/universal-constants.yml#Standard_Messages_Templates