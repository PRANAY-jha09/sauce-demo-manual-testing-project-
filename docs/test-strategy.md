# Test Strategy

## 1. Document Purpose

This document defines the overall testing strategy for the **SauceDemo / Swag Labs e-commerce application**.

The purpose of this strategy is to establish:

* Testing objectives
* Testing scope
* Testing approach
* Test levels
* Test types
* Test design techniques
* Risk-based prioritization
* Defect management
* Regression and retesting approach
* Test evidence requirements
* Entry and exit criteria
* Test completion conditions

This strategy provides a consistent framework for planning and executing manual testing throughout the project.

---

# 2. Application Under Test

**Application:** SauceDemo / Swag Labs

**Application Type:** Web-based E-Commerce Application

The application simulates an online shopping workflow involving:

```text
Login
  ↓
Inventory
  ↓
Product Selection
  ↓
Product Details
  ↓
Shopping Cart
  ↓
Checkout
  ↓
Order Overview
  ↓
Order Completion
  ↓
Logout
```

The primary testing focus is the **end-to-end customer shopping journey**.

---

# 3. Testing Objectives

The major objectives of this testing strategy are:

1. Validate the functional behavior of the application.
2. Verify the primary customer shopping workflow.
3. Identify defects before test completion.
4. Validate positive and negative user scenarios.
5. Verify required input validation.
6. Verify product and cart behavior.
7. Validate checkout and order completion.
8. Verify logout behavior.
9. Maintain traceability between requirements and tests.
10. Perform retesting of corrected defects.
11. Perform regression testing on impacted functionality.
12. Maintain reliable evidence for executed tests.
13. Demonstrate a structured software testing lifecycle.

---

# 4. Testing Scope

## 4.1 In Scope

The following areas are included:

### Authentication

* Login
* Valid credentials
* Invalid credentials
* Missing credentials
* Login validation

### Inventory

* Product listing
* Product information
* Product sorting
* Add to cart
* Remove from cart

### Product Details

* Product information
* Product navigation
* Add product
* Remove product
* Return to inventory

### Shopping Cart

* Cart access
* Cart contents
* Product quantity
* Product price
* Remove items
* Continue shopping
* Proceed to checkout

### Checkout

* Customer information
* First Name
* Last Name
* Postal Code
* Required-field validation
* Continue checkout

### Order

* Order overview
* Product verification
* Price verification
* Order total
* Order completion
* Order confirmation

### Logout

* Logout
* Post-logout state

---

# 5. Out of Scope

The following areas are excluded from this testing strategy:

* API testing
* Database testing
* Performance/load testing
* Penetration testing
* Security testing beyond basic application observations
* Production deployment testing
* Real payment processing
* Unauthorized data collection

These areas may be considered separately as future enhancements.

---

# 6. Testing Approach

A **risk-based manual testing approach** is used.

Testing priority is determined by considering:

* Business impact
* User impact
* Failure impact
* Workflow criticality
* Probability of failure
* Dependencies between application features

Critical customer workflows receive higher testing priority than lower-risk secondary functionality.

---

# 7. Risk-Based Testing Model

The application is divided into different risk levels.

| Risk Level | Testing Priority | Examples                                    |
| ---------- | ---------------- | ------------------------------------------- |
| Critical   | P0               | Login, Checkout, Order Completion           |
| High       | P1               | Cart, Product Selection, Product Validation |
| Medium     | P2               | Secondary Navigation, Continue Shopping     |
| Low        | P3               | Lower-risk usability observations           |

The **Login → Order Completion** workflow receives the highest priority because a failure in a major step may prevent successful completion of the customer's primary journey.

---

# 8. Testing Types

## 8.1 Functional Testing

Functional testing validates whether application functionality behaves according to defined requirements.

Major areas:

* Login
* Inventory
* Product details
* Cart
* Checkout
* Order completion
* Logout

---

## 8.2 Positive Testing

Positive testing validates expected application behavior using valid inputs and normal user actions.

Examples:

* Valid login
* Valid product selection
* Valid add-to-cart operation
* Valid checkout information
* Successful order completion

---

## 8.3 Negative Testing

Negative testing validates application behavior when invalid, incomplete, or unexpected inputs are provided.

Examples:

* Invalid login credentials
* Missing username
* Missing password
* Missing checkout information
* Invalid checkout information

---

## 8.4 Boundary Testing

Boundary conditions are considered for fields where limits or validation rules apply.

Testing may include:

* Empty values
* Minimum values
* Maximum values
* Values at accepted limits
* Values outside expected limits
* Special characters
* Whitespace

Actual validation boundaries should be determined from the application's observed behavior and documented requirements.

---

## 8.5 Equivalence Partitioning

Input values are divided into logical groups so that representative values can be tested efficiently.

For example:

```text
Valid Input
     ↓
Valid Partition

Invalid Input
     ↓
Invalid Partition
```

Representative values from each partition are selected for testing.

---

## 8.6 Decision Table Testing

Decision tables are used when application behavior depends on combinations of conditions.

The technique helps verify that different input/condition combinations produce the expected outcome.

---

## 8.7 State Transition Testing

State transition testing validates how the application behaves when moving between different states.

Example:

```text
Logged Out
    ↓
Logged In
    ↓
Browsing Products
    ↓
Product Added
    ↓
Cart
    ↓
Checkout
    ↓
Order Completed
    ↓
Logged Out
```

This is particularly useful for validating the end-to-end customer journey.

---

## 8.8 Exploratory Testing

Exploratory testing is used to identify unexpected behavior that may not be covered by predefined test cases.

Exploration may include:

* Navigation
* Browser back/forward behavior
* Repeated actions
* Add/remove operations
* Cart behavior
* Checkout behavior
* UI consistency
* Responsive behavior
* Basic accessibility observations

Any discovered issue should be documented with reproducible steps and supporting evidence.

---

# 9. Smoke Testing Strategy

Smoke testing is performed to determine whether the application is sufficiently stable for deeper testing.

The smoke suite focuses on critical functionality:

```text
Login
 ↓
Inventory
 ↓
Add Product
 ↓
Cart
 ↓
Checkout
 ↓
Order Completion
 ↓
Logout
```

If a critical smoke test fails, deeper testing of dependent functionality may be postponed until the blocking issue is resolved or the risk is formally accepted.

---

# 10. Sanity Testing Strategy

Sanity testing is used after relevant changes or fixes to verify that the affected functionality is working as expected.

For example, if a defect affecting checkout is fixed:

```text
Defect Fixed
     ↓
Sanity Check
     ↓
Affected Functionality
     ↓
Regression Testing
```

The scope of sanity testing should remain focused on the affected area.

---

# 11. Regression Testing Strategy

Regression testing verifies that existing functionality has not been negatively affected by application changes.

The regression suite prioritizes:

1. Login
2. Inventory
3. Product selection
4. Add to cart
5. Remove from cart
6. Cart validation
7. Checkout
8. Order overview
9. Order completion
10. Logout

Regression coverage should be expanded when a change has a wider impact.

The detailed regression suite is maintained in:

`docs/10_regression_suite.md`

---

# 12. Retesting Strategy

Retesting is performed after a reported defect has been marked as fixed.

The process is:

```text
Defect Reported
      ↓
Developer Fix
      ↓
Build/Change Available
      ↓
Retest
      ↓
Pass → Verify / Close
      ↓
Fail → Reopen
```

During retesting, the original defect steps should be executed again.

Evidence should be collected where required.

---

# 13. Defect Management Strategy

Defects follow the lifecycle:

```text
New
 ↓
Assigned
 ↓
Open
 ↓
Fixed
 ↓
Retest
 ↓
Verified
 ↓
Closed
```

Other possible statuses include:

* Rejected
* Duplicate
* Deferred
* Not a Bug

When such statuses are used, an appropriate reason should be documented.

Each defect should contain sufficient information for reproduction.

Recommended defect information:

* Defect ID
* Title
* Module
* Environment
* Preconditions
* Steps to reproduce
* Expected result
* Actual result
* Severity
* Priority
* Evidence
* Status
* Retest result

---

# 14. Severity Classification

| Severity | Description                                                                     |
| -------- | ------------------------------------------------------------------------------- |
| Critical | Application/business-critical functionality is unavailable or severely affected |
| High     | Major functionality is significantly affected                                   |
| Medium   | Functionality is affected but a workaround may exist                            |
| Low      | Minor functional or UI issue                                                    |

Severity describes the **impact of the defect**.

---

# 15. Priority Classification

| Priority | Description                  |
| -------- | ---------------------------- |
| P0       | Immediate attention required |
| P1       | High priority                |
| P2       | Medium priority              |
| P3       | Low priority                 |

Priority describes **how urgently the defect should be addressed**.

---

# 16. Test Data Strategy

Test data should be maintained separately from test cases.

The test data should support:

* Valid login
* Invalid login
* Missing authentication information
* Product selection
* Single-product cart
* Multiple-product cart
* Empty cart scenarios
* Valid checkout information
* Missing checkout information
* Invalid checkout information

Only data actually used during execution should be reported as execution evidence.

Test data will be maintained in:

`test-data/test-data.md`

---

# 17. Test Environment Strategy

Testing should record the environment in which execution takes place.

Recommended information:

| Attribute        | Information                 |
| ---------------- | --------------------------- |
| Application      | SauceDemo                   |
| Browser          | Actual browser used         |
| Browser Version  | Actual version              |
| Operating System | Actual OS                   |
| Screen/Viewport  | Where relevant              |
| Execution Date   | Actual execution date       |
| Tester           | Person performing execution |

Environment details should be based on actual execution rather than assumptions.

---

# 18. Compatibility Testing

Compatibility considerations include:

* Different supported browsers
* Different browser versions where applicable
* Different viewport sizes
* Responsive behavior
* UI consistency

Compatibility findings should only be reported after actual execution.

---

# 19. Accessibility Awareness

Basic accessibility observations may be included during exploratory testing.

Areas may include:

* Visible labels
* Keyboard navigation
* Focus behavior
* Readability
* Form usability
* Basic semantic/accessibility observations

This project does not claim to be a full accessibility compliance audit.

---

# 20. Test Evidence Strategy

Evidence is maintained to support executed test results and defects.

Possible evidence includes:

* Screenshots
* Test execution records
* Defect screenshots
* Expected vs actual results
* Retest evidence
* Regression evidence

Recommended screenshot organization:

```text
screenshots/
├── login/
├── inventory/
├── product-details/
├── cart/
├── checkout/
├── order-completion/
└── logout/
```

An evidence index is maintained in:

`evidence-index.md`

---

# 21. Evidence Integrity Rule

A critical project rule is:

> **Do not present planned or simulated results as actual test execution results.**

For example, do not claim:

```text
TC-001 — PASS
TC-002 — PASS
Bug Found — Login Failure
```

unless those tests have actually been executed and the results have been observed.

Actual execution should include:

* Actual result
* Execution status
* Evidence where applicable
* Defect ID where applicable

---

# 22. Entry Criteria

Testing can begin when:

1. Application is available for testing.
2. Required test environment is accessible.
3. Requirements/test scope are defined.
4. Test scenarios are prepared.
5. Required test data is available.
6. Critical application functionality is accessible.
7. Test documentation is ready for execution.

---

# 23. Exit Criteria

Testing can be considered complete when:

1. Critical test cases have been executed.
2. Planned coverage is completed or remaining risk is accepted.
3. Test failures have supporting evidence.
4. Critical defects are closed or formally accepted.
5. Fixed defects have been retested.
6. Impacted regression testing is completed.
7. Test results are documented.
8. Test summary is prepared.
9. Remaining known risks are documented.

---

# 24. Test Deliverables

The following deliverables are maintained in the project:

```text
README.md
│
├── Application Overview
├── Requirements
├── Test Plan
├── Test Strategy
├── Test Scenarios
├── Test Cases
├── Test Data
├── RTM
├── Test Execution
├── Regression Suite
├── Test Summary
├── Defect Reports
└── Test Evidence
```

---

# 25. Traceability Strategy

Requirements should be mapped to test scenarios and test cases.

The expected relationship is:

```text
Requirement
     ↓
Test Scenario
     ↓
Test Case
     ↓
Test Execution
     ↓
Defect (if applicable)
     ↓
Retest
     ↓
Regression
```

This provides end-to-end traceability throughout the testing lifecycle.

The detailed Requirements Traceability Matrix is maintained in:

`docs/08_rtm.md`

---

# 26. Agile Testing Approach

The testing strategy supports an Agile/Scrum workflow.

A typical workflow is:

```text
Requirement Refinement
        ↓
Sprint Planning
        ↓
Development
        ↓
QA Handoff
        ↓
Smoke Testing
        ↓
Functional Testing
        ↓
Exploratory Testing
        ↓
Defect Reporting
        ↓
Fix
        ↓
Retesting
        ↓
Regression Testing
        ↓
Sprint Demo
        ↓
Retrospective
```

QA activities should occur continuously throughout the development lifecycle rather than only at the end.

---

# 27. Risk Management

Potential testing risks include:

| Risk                      | Impact   | Mitigation                          |
| ------------------------- | -------- | ----------------------------------- |
| Application unavailable   | High     | Verify environment before execution |
| Requirements unclear      | High     | Clarify and document requirements   |
| Critical workflow failure | Critical | Prioritize end-to-end testing       |
| Insufficient test data    | Medium   | Prepare test data before execution  |
| Defect not reproducible   | Medium   | Capture detailed evidence           |
| Fix causes regression     | High     | Execute impacted regression suite   |
| Incomplete coverage       | High     | Maintain RTM                        |
| Missing evidence          | Medium   | Follow evidence collection rules    |

---

# 28. Testing Prioritization

When testing time is limited, the following order should be followed:

### Priority 1 — Critical Business Flow

```text
Login
 ↓
Product Selection
 ↓
Add to Cart
 ↓
Checkout
 ↓
Order Completion
```

### Priority 2 — Core Functional Areas

* Product sorting
* Product details
* Cart management
* Checkout validation
* Order information

### Priority 3 — Secondary Areas

* Secondary navigation
* Continue shopping
* Additional exploratory observations
* Compatibility observations

---

# 29. Definition of Done for Testing

A test activity can be considered complete when:

* Required test steps have been executed.
* Actual results have been recorded.
* Pass/fail status has been determined.
* Required evidence has been captured.
* Defects have been logged where applicable.
* Failed tests have been analyzed.
* Retesting has been completed where applicable.
* Impacted regression tests have been completed.

---

# 30. Final Test Strategy Summary

This project follows a **structured, risk-based manual testing strategy** for the SauceDemo e-commerce application.

The strategy focuses on the application's most important customer journey:

```text
Login
 ↓
Browse Products
 ↓
Select Product
 ↓
Cart
 ↓
Checkout
 ↓
Order Completion
 ↓
Logout
```

Multiple testing techniques are applied to improve coverage, including:

* Functional testing
* Positive testing
* Negative testing
* Boundary Value Analysis
* Equivalence Partitioning
* Decision Table Testing
* State Transition Testing
* Exploratory Testing
* Smoke Testing
* Sanity Testing
* Regression Testing
* Retesting

The overall objective is to demonstrate a professional QA process from **requirements analysis through test design, execution, defect management, retesting, regression, traceability, evidence collection, and test closure**.

All execution results and defects must be based on **actual observed behavior** and supported by appropriate evidence.
