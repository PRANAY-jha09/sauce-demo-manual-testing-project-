# Test Plan

## 1. Document Information

| Attribute              | Details                             |
| ---------------------- | ----------------------------------- |
| Project Name           | SauceDemo E-Commerce Manual Testing |
| Application Under Test | SauceDemo / Swag Labs               |
| Testing Type           | Manual Functional Testing           |
| Test Level             | System Testing                      |
| Test Approach          | Risk-Based Testing                  |
| Document Version       | 1.0                                 |
| Document Status        | Draft                               |
| Prepared By            | Pranay Jha                          |

---

# 2. Introduction

This Test Plan defines the scope, objectives, approach, resources, deliverables, risks, schedule, and completion criteria for manual testing of the **SauceDemo / Swag Labs e-commerce application**.

The project focuses on validating the core user journey through the application, including authentication, product browsing, product selection, shopping cart management, checkout, order completion, and logout.

The overall testing workflow is:

```text
Login
  ↓
Inventory
  ↓
Product Selection
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

This document serves as the primary planning artifact for the testing lifecycle.

---

# 3. Test Objectives

The objectives of this testing activity are to:

1. Validate the major functional requirements of the application.
2. Verify the end-to-end customer shopping workflow.
3. Identify functional defects.
4. Validate positive and negative test scenarios.
5. Verify mandatory field validations.
6. Validate product selection and cart functionality.
7. Verify the checkout process.
8. Validate order completion and confirmation.
9. Verify logout functionality.
10. Maintain traceability between requirements and test cases.
11. Support defect reporting and retesting.
12. Perform regression testing on impacted functionality.
13. Collect evidence for executed tests.
14. Produce a final test summary report.

---

# 4. Application Under Test

**Application Name:** SauceDemo / Swag Labs

**Application Type:** Web-based E-Commerce Application

The application allows users to simulate an online shopping journey.

The primary business flow includes:

* User authentication
* Product browsing
* Product selection
* Add/remove products
* Shopping cart management
* Checkout
* Customer information
* Order review
* Order completion
* Logout

---

# 5. Test Scope

## 5.1 In Scope

The following functional areas are included in testing.

### Authentication

* Valid login
* Invalid login
* Missing username
* Missing password
* Missing credentials
* Login validation

### Inventory

* Product listing
* Product information
* Product sorting
* Add product to cart
* Remove product from inventory

### Product Details

* Product information
* Product navigation
* Add product from details page
* Remove product from details page
* Return to inventory

### Shopping Cart

* Open shopping cart
* Verify selected products
* Verify product quantity
* Verify product price
* Remove product
* Continue shopping
* Proceed to checkout

### Checkout

* Checkout information fields
* First Name validation
* Last Name validation
* Postal Code validation
* Continue checkout

### Order Overview

* Verify selected products
* Verify price information
* Verify order total

### Order Completion

* Complete order
* Verify confirmation

### Logout

* Logout functionality
* Post-logout behavior

---

# 6. Out of Scope

The following testing activities are outside the scope of this project:

* API testing
* Database testing
* Performance testing
* Load testing
* Stress testing
* Penetration testing
* Comprehensive security testing
* Real payment gateway testing
* Production deployment testing
* Infrastructure testing

Basic usability, compatibility, and accessibility observations may be recorded when encountered, but this project does not represent a full specialist audit in these areas.

---

# 7. Test Items

The major test items are:

| Test Area        | Description                         |
| ---------------- | ----------------------------------- |
| Login            | User authentication and validation  |
| Inventory        | Product listing and sorting         |
| Product Details  | Product information and actions     |
| Cart             | Product management and verification |
| Checkout         | Customer information and validation |
| Order Overview   | Product and total verification      |
| Order Completion | Successful order completion         |
| Logout           | Session termination                 |

---

# 8. Test Approach

The project follows a **risk-based manual testing approach**.

Testing will prioritize functionality based on:

* Business criticality
* User impact
* Failure impact
* Dependency on other features
* Probability of defects

Critical workflows receive higher priority.

### Highest Priority Flow

```text
Login
 ↓
Select Product
 ↓
Add to Cart
 ↓
Checkout
 ↓
Complete Order
```

Testing includes:

* Functional testing
* Positive testing
* Negative testing
* Boundary testing
* Exploratory testing
* Smoke testing
* Regression testing
* Retesting

Detailed testing methodology is defined in:

`docs/04_test_strategy.md`

---

# 9. Test Design Techniques

The following test design techniques may be applied where appropriate.

## 9.1 Equivalence Partitioning

Inputs are divided into valid and invalid groups.

Example:

```text
Valid Credentials
      ↓
Successful Login

Invalid Credentials
      ↓
Login Rejected
```

---

## 9.2 Boundary Value Analysis

Boundary conditions are considered for applicable input fields.

Examples include:

* Empty input
* Minimum values
* Maximum values
* Values within limits
* Values outside limits

Actual boundaries should be based on observed application validation rules.

---

## 9.3 Decision Table Testing

Decision tables may be used where application behavior depends on combinations of conditions.

---

## 9.4 State Transition Testing

Application behavior is validated across different states.

Example:

```text
Logged Out
    ↓
Logged In
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

---

# 10. Test Environment

The actual execution environment must be recorded during testing.

| Environment Item | Details                     |
| ---------------- | --------------------------- |
| Application      | SauceDemo / Swag Labs       |
| Operating System | `<Update during execution>` |
| Browser          | `<Update during execution>` |
| Browser Version  | `<Update during execution>` |
| Device           | `<Update during execution>` |
| Test Environment | Web Application             |
| Tester           | Pranay Jha                  |

No environment details should be fabricated.

---

# 11. Test Data

Test data will support both positive and negative scenarios.

Test data categories include:

### Authentication Data

* Valid credentials
* Invalid credentials
* Empty username
* Empty password
* Empty credentials

### Product Data

* Single product
* Multiple products
* Product sorting options

### Checkout Data

* Valid First Name
* Valid Last Name
* Valid Postal Code
* Missing First Name
* Missing Last Name
* Missing Postal Code
* Invalid values where supported by the application

Detailed test data is maintained in:

`test-data/test-data.md`

---

# 12. Test Deliverables

The project deliverables include:

```text
README.md

docs/
├── 01_application_overview.md
├── 02_requirements.md
├── 03_test_plan.md
├── 04_test_strategy.md
├── 05_test_scenarios.md
├── 06_test_cases.md
├── 07_test_data.md
├── 08_rtm.md
├── 09_test_execution.md
├── 10_regression_suite.md
└── 11_test_summary.md

bugs/
├── README.md
└── defect-reports/

screenshots/
├── login/
├── inventory/
├── product-details/
├── cart/
├── checkout/
├── order-completion/
└── logout/

test-data/
└── test-data.md

evidence-index.md
```

---

# 13. Test Roles and Responsibilities

## QA Tester

**Responsible for:**

* Understanding requirements
* Creating test scenarios
* Designing test cases
* Preparing test data
* Executing test cases
* Recording actual results
* Reporting defects
* Capturing evidence
* Retesting fixes
* Performing regression testing
* Preparing the test summary report

**Tester:** Pranay Jha

---

# 14. Entry Criteria

Testing can begin when:

1. The application is available.
2. Required application functionality is accessible.
3. Test scope is defined.
4. Requirements are documented.
5. Test scenarios are prepared.
6. Test cases are available.
7. Required test data is available.
8. Test environment is accessible.

---

# 15. Exit Criteria

Testing can be considered complete when:

1. Critical test cases have been executed.
2. Planned testing coverage has been completed or remaining gaps are documented.
3. Actual test results have been recorded.
4. Failed tests have been documented.
5. Critical defects are resolved, accepted, or clearly reported as remaining risk.
6. Fixed defects have been retested.
7. Impacted regression tests have been executed.
8. Evidence has been collected where required.
9. Requirements traceability has been updated.
10. The final test summary has been prepared.

---

# 16. Test Suspension Criteria

Testing may be suspended when:

* The application is unavailable.
* A critical blocker prevents further testing.
* The test environment is inaccessible.
* Required functionality cannot be accessed.
* Critical test data is unavailable.
* A major defect prevents execution of dependent test cases.

Testing should resume after the blocking condition has been resolved or an alternative approach has been approved.

---

# 17. Defect Management

Defects discovered during testing should be documented with sufficient information for reproduction.

Each defect report should include:

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
* Status
* Evidence

Defect reports are maintained in:

`bugs/defect-reports/`

---

# 18. Severity Classification

| Severity | Description                                          |
| -------- | ---------------------------------------------------- |
| Critical | Critical business functionality is unavailable       |
| High     | Major functionality is significantly affected        |
| Medium   | Functionality is affected but a workaround may exist |
| Low      | Minor functional or UI issue                         |

---

# 19. Priority Classification

| Priority | Description                  |
| -------- | ---------------------------- |
| P0       | Immediate attention required |
| P1       | High priority                |
| P2       | Medium priority              |
| P3       | Low priority                 |

**Severity** represents the impact of a defect.

**Priority** represents the urgency of fixing the defect.

---

# 20. Test Execution Process

The planned test execution process is:

```text
Requirements Review
       ↓
Test Scenario Design
       ↓
Test Case Preparation
       ↓
Test Data Preparation
       ↓
Smoke Testing
       ↓
Functional Testing
       ↓
Negative Testing
       ↓
Exploratory Testing
       ↓
Defect Reporting
       ↓
Retesting
       ↓
Regression Testing
       ↓
Test Summary
```

Actual execution status must be recorded separately in:

`docs/09_test_execution.md`

---

# 21. Smoke Testing

Smoke testing verifies whether critical application functionality is stable enough for detailed testing.

The planned smoke suite includes:

1. Login with valid credentials.
2. Inventory page loading.
3. Add product to cart.
4. Open shopping cart.
5. Proceed to checkout.
6. Complete primary order workflow.
7. Logout.

A critical smoke failure may block deeper testing of dependent functionality.

---

# 22. Regression Testing

Regression testing is performed after changes or defect fixes.

Priority regression areas include:

* Login
* Inventory
* Product selection
* Add/remove product
* Cart
* Checkout
* Order completion
* Logout

The detailed regression suite is maintained in:

`docs/10_regression_suite.md`

---

# 23. Retesting

When a defect is fixed, the original defect scenario should be executed again.

The retesting workflow is:

```text
Defect Reported
      ↓
Defect Fixed
      ↓
Retest
      ↓
Pass → Verify/Close

Fail → Reopen
```

Retesting results must be recorded using actual observed behavior.

---

# 24. Risks and Mitigation

| Risk                      | Impact   | Mitigation                           |
| ------------------------- | -------- | ------------------------------------ |
| Application unavailable   | High     | Verify environment before testing    |
| Critical workflow blocked | Critical | Prioritize blocker resolution        |
| Requirements unclear      | High     | Review and document assumptions      |
| Insufficient test data    | Medium   | Prepare test data before execution   |
| Missing evidence          | Medium   | Capture screenshots during execution |
| Defect not reproducible   | Medium   | Record detailed reproduction steps   |
| Regression after fix      | High     | Execute impacted regression tests    |
| Incomplete coverage       | High     | Maintain RTM                         |

---

# 25. Assumptions

The following assumptions apply:

1. The application remains accessible during testing.
2. Test credentials are available for intended scenarios.
3. Product data is available.
4. The application can simulate the complete shopping workflow.
5. The tester has access to the required browser and environment.
6. Application behavior may change over time; execution results should reflect the actual test date.

---

# 26. Dependencies

Testing depends on:

* Application availability
* Stable internet connection
* Valid test credentials
* Supported browser access
* Availability of required product and checkout functionality
* Availability of the test environment

---

# 27. Schedule

The project follows a documentation-first testing workflow.

| Phase                 | Planned Activity                | Status  |
| --------------------- | ------------------------------- | ------- |
| Requirement Analysis  | Review application requirements | Planned |
| Test Planning         | Prepare test plan               | Planned |
| Test Strategy         | Define testing approach         | Planned |
| Test Scenario Design  | Create high-level scenarios     | Planned |
| Test Case Design      | Create detailed test cases      | Planned |
| Test Data Preparation | Prepare required data           | Planned |
| Test Execution        | Execute test cases              | Planned |
| Defect Reporting      | Log confirmed defects           | Planned |
| Retesting             | Verify fixes                    | Planned |
| Regression Testing    | Validate impacted areas         | Planned |
| Test Closure          | Prepare final summary           | Planned |

Actual dates should be added based on the real project timeline.

---

# 28. Requirements Traceability

Requirements will be mapped to test scenarios and test cases.

The traceability structure is:

```text
Requirement
    ↓
Test Scenario
    ↓
Test Case
    ↓
Execution Result
    ↓
Defect
    ↓
Retest
```

The detailed traceability matrix is maintained in:

`docs/08_rtm.md`

---

# 29. Test Metrics

The following metrics may be calculated after actual execution.

### Test Execution Metrics

```text
Pass Percentage =
(Passed Test Cases / Executed Test Cases) × 100
```

```text
Fail Percentage =
(Failed Test Cases / Executed Test Cases) × 100
```

### Defect Metrics

* Total defects
* Defects by severity
* Defects by priority
* Open defects
* Closed defects
* Retest pass/fail rate

Metrics should only be calculated from actual recorded data.

---

# 30. Test Evidence

Testing evidence may include:

* Screenshots
* Actual test execution results
* Defect evidence
* Retest evidence
* Regression evidence

Screenshot organization:

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

The evidence index is maintained in:

`evidence-index.md`

---

# 31. Important Quality Rule

> **Planned testing must not be represented as completed testing.**

Test cases should only be marked:

* PASS
* FAIL
* BLOCKED
* NOT EXECUTED

after the relevant test has actually been executed or assessed.

Similarly, defects should only be reported when an actual issue has been observed and documented.

---

# 32. Approval and Sign-Off

| Role      | Name       | Status  | Date       |
| --------- | ---------- | ------- | ---------- |
| QA Tester | Pranay Jha | Pending | `<Update>` |
| Reviewer  | `<Name>`   | Pending | `<Update>` |

---

# 33. Final Test Plan Summary

This Test Plan provides the foundation for manual testing of the SauceDemo e-commerce application.

The project follows a structured testing lifecycle:

```text
Requirements
     ↓
Test Planning
     ↓
Test Strategy
     ↓
Test Scenarios
     ↓
Test Cases
     ↓
Test Data
     ↓
Test Execution
     ↓
Defect Management
     ↓
Retesting
     ↓
Regression Testing
     ↓
Test Summary
```

The highest priority remains the successful validation of the primary e-commerce workflow:

```text
Login
  ↓
Browse Products
  ↓
Add Product to Cart
  ↓
Checkout
  ↓
Complete Order
  ↓
Logout
```

This test plan supports a structured, traceable, and evidence-based QA process suitable for a professional manual testing portfolio project.
