# TDD

1. Write an automated unit-level test case that fails
2. Writing just enough code to make the test pass
3. Refactoring both the test code and the production code
4. Repeat

as Kent Beck said, inspires confidence and tends to simplier designs.

> A bit of Fake it until you make it wont do any harm.

The unit tests used for TDD should never cross process boundaries in a program (not unit), network connections, bigger scopes etc. Not following this, introduces delays that make tests run slowly and discourage developers from running the whole suite.
But for checking the overall functionality, as database connections can be checked with the *TDD code*, here is where TDD taks about "integration tests", there are fewer of them and so run less often.

For this, enforcing a unit-testable separation is also an opportunity and a driving force to design more modular codebases, by using dependency injection, fakes and mocks. Test doubles might be usefull too *(Dummys, Stub, Spy, Mock, Simulator ...)*.


While writing the tests one will refer in a unit test, only to one UUT, that will get setup, executed, validated, and cleanup (if needed). This is also refered as AAA pattern (arrage, act, asseet). 

## What to avoid

- Having test cases depend on system state manipulated from previously executed test cases (i.e., you should always start a unit test from a known and pre-configured state).
- Dependencies between test cases. A test suite where test cases are dependent upon each other is brittle and complex. Execution order should not be presumed. Basic refactoring of the initial test cases or structure of the UUT causes a spiral of increasingly pervasive impacts in associated tests.
- Interdependent tests. Interdependent tests can cause cascading false negatives. A failure in an early test case breaks a later test case even if no actual fault exists in the UUT, increasing defect analysis and debug efforts.
- Testing precise execution, behavior, timing or performance.
- Building "all-knowing oracles". An oracle that inspects more than necessary is more expensive and brittle over time. This very common error is dangerous because it causes a subtle but pervasive time sink across the complex project.
- Testing implementation details.
- Slow running tests.