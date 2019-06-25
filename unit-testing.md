# Unit Test

## Intro
* **Unit Test**: Specify and test one point of the contract of single method of a class. This should have a very narrow and well defined scope. Complex dependencies and interactions to the outside world are **stubbed** or **mocked**
* ** Integration Test**: Test the correct inter-operation of multiple subsystems. There is whole spectrum there from testing integration between two classes to testing integration with the production environment.
* ** Smoke Test(Sanity Check) **: A simple integration test where we just check that when the system under test is invoked  it returns normally and does not blow up.
* **Regression Test**: A test that was written when a bug was fixed. It ensures specific bug will not occur again.
* Others include Acceptance Test, System Test, Pre-flight check



Test types for a front end app are
* Unit Tests -- Testing of individual functions or classes by supplying input and making sure the output is as expected.
* Integration Tests
* UI(functional) Tests

## Testing Tools
* Testing structure(Mocha, Jasmine, Jest, Cucumber)
	*  Organizing tests. Generally tests are organized in BDD(Behavior Driven Development)
* Assertion functions(Chai, Jasmine, Jest, Unexpected)
	* To make sure tested variables contain expected value.
* Display and Watch Test results( Mocham Jasmine, Jest, Karma)
* Generate and compare **sanpshot** of component to make sure changes from previous runs are inteded.
	* snapshot is when comparing a data structure to a an expected one.
* Provide mocks, Spies, and stubs(Sinon, Jasmine, enzyme, Jest, testdouble)
	* Spies provide information about functions(how many times they called, in what cases, and by whom), used in integration tests.
	* Stubbing/Dubbing(like doubles in movies) replaces selected functions with selected functions to ensure expected behavior in selected modules.
	* Mocks/ Fakes -- faking certain modules or behaviors to test different parts of a process. 
* Generate **Code Coverage** reports(Istanbul, Jest, Blanket)
	* Istanbul is javascript test coverage tool. 
* Provide browser or browser like environment with a control on their scenario execution(Protractor, Nightwatch, Phantom, Casper)
	* jsdom --- a pure javascript environment that simulates real browser.
	* Headless Broser Environment ---  A browser that run without  UI for the purpose of making browser respond faster.
	* Real Browser Environment --- an actual browser that opens and runs tests.

### Putting it all together
* should create two diffent processes
	* one for running unit and integration tests.
	* another for running UI(functional) tests
* Unit tests  are one of the reasons for functional programming and pure functions.
* Not all units are pure, not all units are testable.


## What isn't a unit test
* Touches database
* Makes network requests
* Touches file system

## How to unit test
Jest
* Testing framework from facebook.
* Test runner
* Test blocks(e.g., describe and it)
* Assertions(e.g., expect(1+2).equal(3))
* Snapshot testing
Enzyme
* Shallow Rendering
* Inspecting Component Trees

BDD is better suited to UI based testing.

## TDD
* Test Driven Development process allows first to write test cases which should fail. Development should be written in such a way to pass these tests.

## Mocha
* Most used library
* Mocha can be used with third parth assertion library.
* **Mocha** is library that allows us to run tests, and **Chai** contains some helpful functions that can be used to verify our test results.

## Jest 
* recommended by facebook, based on jasmine. Code coverage tool is based on Istanbul.

## BDD
### Principles
* Define a test set for the unit first 
* Make the tests fail
* Then implement the unit
* Finally verify the implementations of the Unit makes the tests succeed.

## Unit vs Functional vs Integration Tests
* All of them are automated tests.
* These will enhance software stability.
* Provides safety net allows developers to make changes without fear that they will unknowingly break something in the process.
* Each of the test has a unique role to play, make sure each category of tests run in isolation from othes.


### Cost of neglecting Tests
TDD takes a little more time up front, but bugs that reach customers cost more in many ways.
* Interrupt UX
* Bug fix interruptions which cause a costly contextual switch.


## References
[1]. [An Overview of javascript Unit testing](https://medium.com/welldone-software/an-overview-of-javascript-testing-in-2018-f68950900bc3)
[2]. [Unit Testing](https://gist.github.com/wmonk/4adba68a5ff499c8ce884df2f2dd1694)
[3]. [Testing Frameworks](http://2016.stateofjs.com/2016/testing/)
[4]. [BDD](https://en.wikipedia.org/wiki/Behavior-driven_development)
[5]. [Unit vs Functional vs Integration Tests](https://www.sitepoint.com/javascript-testing-unit-functional-integration/)
[6]. [Simplified Angular Unit Testing](https://logrocket.com/blog/angular-unit-testing/)
[7]. [Angular Official Guide to Unit Testing](https://angular.io/guide/testing)
