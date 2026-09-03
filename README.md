# 🛒 E-Commerce Web Application — End-to-End Manual Testing

![Manual Testing](https://img.shields.io/badge/Testing-Manual%20Testing-blue)
![Domain](https://img.shields.io/badge/Domain-E--Commerce-orange)
![Testing Type](https://img.shields.io/badge/Testing-End--to--End-green)
![Methodology](https://img.shields.io/badge/Methodology-Agile%2FScrum-purple)
![Status](https://img.shields.io/badge/Status-Portfolio%20Project-yellow)


---

## 📌 Table of Contents

* [Project Overview](#-project-overview)
* [Application Under Test](#-application-under-test)
* [Business Context](#-business-context)
* [Project Objectives](#-project-objectives)
* [Testing Scope](#-testing-scope)
* [Application Modules](#-application-modules)
* [Critical Business Workflow](#-critical-business-workflow)
* [Testing Strategy](#-testing-strategy)
* [Test Design Techniques](#-test-design-techniques)
* [Test Coverage](#-test-coverage)
* [Requirements & Traceability](#-requirements--traceability)
* [Test Data](#-test-data)
* [Test Suites](#-test-suites)
* [Defect Management](#-defect-management)
* [Retesting & Regression](#-retesting--regression)
* [Test Execution](#-test-execution)
* [QA Deliverables](#-qa-deliverables)
* [Repository Structure](#-repository-structure)
* [Tools & Technologies](#-tools--technologies)
* [Agile QA Workflow](#-agile-qa-workflow)
* [Risk-Based Testing](#-risk-based-testing)
* [Evidence & Reporting Policy](#-evidence--reporting-policy)
* [Scope Limitations](#-scope-limitations)
* [Key QA Learnings](#-key-qa-learnings)
* [Interview Discussion Points](#-interview-discussion-points)
* [Future Improvements](#-future-improvements)
* [Author](#-author)

---

# 📋 Project Overview

This project demonstrates a structured **end-to-end manual testing approach** for an e-commerce web application.

The application under test is **SauceDemo / Swag Labs**, a publicly accessible demo application commonly used for software testing practice.

The testing approach follows a realistic QA lifecycle:

```text
Requirement Analysis
        ↓
Test Planning
        ↓
Risk Identification
        ↓
Test Scenario Design
        ↓
Test Case Design
        ↓
Test Data Preparation
        ↓
Test Execution
        ↓
Defect Reporting
        ↓
Retesting
        ↓
Regression Testing
        ↓
RTM Update
        ↓
Test Summary
        ↓
Test Closure
```

The project focuses on the complete customer journey from **authentication to order completion and logout**.

---

# 🌐 Application Under Test

**Application:** SauceDemo / Swag Labs

**Application URL:**
https://www.saucedemo.com/

**Domain:** E-Commerce / Retail

**Application Type:** Web Application

**Testing Type:** Manual Testing

**Testing Approach:** Risk-Based Testing

**Methodology:** Agile / Scrum

---

# 💼 Business Context

An e-commerce application converts product discovery into a completed customer order.

The core customer journey is:

```text
Login
  ↓
Product Listing
  ↓
Product Selection
  ↓
Product Details
  ↓
Add to Cart
  ↓
Cart Management
  ↓
Checkout
  ↓
Customer Information
  ↓
Order Summary
  ↓
Order Completion
  ↓
Confirmation
  ↓
Logout
```

Failures in authentication, cart state, checkout, totals, or order completion can directly affect the core business journey.

Therefore, these workflows receive higher testing priority than cosmetic UI issues.

---

# 🎯 Project Objectives

The primary objectives of this project are:

* Validate critical e-commerce customer workflows.
* Verify authentication and session behavior.
* Validate product discovery and selection.
* Verify sorting functionality.
* Validate product detail information.
* Verify cart operations.
* Validate checkout fields and error handling.
* Verify order summary and totals.
* Validate order completion.
* Verify logout and session behavior.
* Apply positive and negative testing.
* Apply boundary and equivalence-partition testing.
* Apply decision-table and state-transition techniques.
* Perform exploratory testing.
* Design smoke and regression suites.
* Demonstrate defect lifecycle management.
* Maintain requirement-to-test traceability.
* Produce professional QA documentation.

---

# 🧪 Testing Scope

## ✅ In Scope

The following areas are covered:

* Login
* Authentication validation
* Error messages
* Inventory / product listing
* Product visibility
* Product sorting
* Product details
* Add to cart
* Remove from cart
* Cart badge/state
* Checkout
* Customer information
* Required-field validation
* Order overview
* Order totals
* Order completion
* Confirmation behavior
* Logout
* Navigation
* Session-related behavior
* Functional UI testing
* Negative testing
* Boundary testing
* Exploratory testing
* Regression testing
* Smoke testing
* Retesting
* Selected browser/compatibility checks

The source project defines the critical path as login through checkout and order completion, with validation and error handling included.

---

## ❌ Out of Scope

The following are intentionally outside the scope of this manual testing project:

* Backend API testing
* Database testing
* Load testing
* Performance testing
* Penetration testing
* Production deployment testing
* Real payment processing
* Unauthorized data collection
* Internal application architecture verification without authorized evidence

These limitations are explicitly documented so the project does not claim testing that was not actually performed.

---

# 🧩 Application Modules

| Module               | Priority    | Testing Focus                      |
| -------------------- | ----------- | ---------------------------------- |
| Login                | Critical    | Authentication, validation, errors |
| Inventory            | High        | Product visibility and content     |
| Sorting              | Medium/High | Name and price sorting             |
| Product Details      | High        | Product information consistency    |
| Cart                 | Critical    | Add, remove, state, badge          |
| Checkout             | Critical    | Required fields and navigation     |
| Customer Information | High        | Field validation                   |
| Order Summary        | Critical    | Product and total consistency      |
| Order Completion     | Critical    | Successful completion              |
| Logout               | High        | Session termination and navigation |
| UI                   | Medium      | Usability and visual consistency   |

The project prioritizes login, checkout, and order completion as critical business workflows; cart, product selection, customer information, and logout are high priority.

---

# 🔥 Critical Business Workflow

The highest-risk workflow is:

```text
Login
 ↓
Inventory
 ↓
Select Product
 ↓
Add to Cart
 ↓
Cart
 ↓
Checkout
 ↓
Customer Information
 ↓
Order Overview
 ↓
Finish Order
 ↓
Confirmation
 ↓
Logout
```

### Why is this workflow critical?

Because a failure at an early stage can prevent the user from reaching subsequent stages.

For example:

```text
Login Failure
     ↓
Cannot Access Inventory
     ↓
Cannot Select Product
     ↓
Cannot Add to Cart
     ↓
Cannot Checkout
     ↓
Cannot Complete Order
```

Therefore, this path receives the highest risk-based testing priority.

---

# 🧠 Testing Strategy

The project follows a **risk-based manual testing strategy**.

Testing priority is determined using:

```text
Business Impact
       +
Failure Probability
       +
Dependency
       +
Customer Impact
       =
Testing Priority
```

### Priority Classification

| Priority      | Description                                                  |
| ------------- | ------------------------------------------------------------ |
| P0 / Critical | Failure blocks or seriously compromises the customer journey |
| P1 / High     | Major functionality affected                                 |
| P2 / Medium   | Important functionality/UI issue with workaround             |
| P3 / Low      | Minor usability/cosmetic issue                               |

---

# 🔬 Test Design Techniques

The following techniques are incorporated into the test design:

### 1. Equivalence Partitioning

Divide input data into valid and invalid groups.

Example:

```text
Username
├── Valid
├── Invalid
└── Blank
```

---

### 2. Boundary Value Analysis

Test values around important boundaries.

Example:

```text
Minimum valid value
Minimum - 1
Minimum + 1
Maximum valid value
Maximum - 1
Maximum + 1
```

---

### 3. Decision Table Testing

Used when multiple conditions determine expected behavior.

Example:

| Valid Username | Valid Password | Expected Result  |
| -------------- | -------------- | ---------------- |
| Yes            | Yes            | Login successful |
| Yes            | No             | Login rejected   |
| No             | Yes            | Login rejected   |
| No             | No             | Login rejected   |

---

### 4. State Transition Testing

Used to validate state-dependent behavior.

Example:

```text
Logged Out
    ↓
Login
    ↓
Authenticated
    ↓
Shopping
    ↓
Checkout
    ↓
Order Completed
    ↓
Logout
    ↓
Logged Out
```

---

### 5. Exploratory Testing

Exploratory testing is used to investigate workflows beyond predefined scripted cases.

Examples:

* Navigation behavior
* Unexpected user actions
* Back-button behavior
* Repeated clicks
* Cart state changes
* Session behavior
* Recovery from validation errors

---

### 6. Positive Testing

Verify that valid inputs and expected user actions work correctly.

Example:

```text
Valid credentials
      ↓
Login
      ↓
Inventory displayed
```

---

### 7. Negative Testing

Verify that invalid inputs and unexpected actions are handled correctly.

Examples:

* Invalid username
* Invalid password
* Blank fields
* Invalid checkout information
* Invalid navigation
* Repeated actions

---

### 8. Compatibility Testing

Selected workflows can be cross-checked across supported browsers.

Example:

```text
Chrome
Firefox
Other supported browser
```

Exact browser version and execution date should be recorded during actual execution.

---

# 📊 Test Coverage

Testing coverage is organized across:

```text
Requirements
     ↓
User Stories
     ↓
Acceptance Criteria
     ↓
Test Scenarios
     ↓
Test Cases
     ↓
Execution
     ↓
Defects
     ↓
Retest
     ↓
Regression
     ↓
RTM
```

Coverage should only be considered complete when requirements have corresponding **executed test cases with recorded results**. Planned mappings alone are not execution evidence.

---

# 📝 Requirements & Traceability

Requirements are assigned unique IDs.

Example:

| Requirement ID   | Requirement                                | Priority |
| ---------------- | ------------------------------------------ | -------- |
| REQ-LOGIN-001    | Valid users can log in                     | Critical |
| REQ-LOGIN-002    | Invalid credentials are rejected           | High     |
| REQ-INV-001      | Products are displayed                     | High     |
| REQ-CART-001     | Products can be added to cart              | Critical |
| REQ-CHECKOUT-001 | Required checkout information is validated | Critical |
| REQ-ORDER-001    | Order can be completed                     | Critical |
| REQ-LOGOUT-001   | User can logout                            | High     |

The RTM connects requirements with their corresponding test cases and coverage status.

---

# 🧪 Test Data

Test data is maintained separately from test cases.

Examples:

### Authentication Data

```text
Valid username
Valid password
Invalid username
Invalid password
Blank username
Blank password
Locked-user credentials where applicable
```

### Checkout Data

```text
First Name
Last Name
Postal Code
```

### Important Rule

Only authorized demo credentials and fictional checkout information should be used.

No real customer, payment-card, or sensitive production information is required.

---

# 🚦 Test Suites

## Smoke Suite

The smoke suite verifies whether the application is stable enough for deeper testing.

Typical flow:

```text
Launch Application
      ↓
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
Complete Order
      ↓
Logout
```

---

## Sanity Suite

Sanity testing focuses on a changed or affected area after a new build/change.

Example:

```text
Checkout change
      ↓
Checkout validation
      ↓
Order overview
      ↓
Order completion
```

---

## Regression Suite

Regression testing verifies that existing functionality remains stable after changes.

High-risk regression areas include:

* Login
* Inventory
* Cart
* Checkout
* Order completion
* Logout

---

# 🐞 Defect Management

A defect should contain factual, reproducible information.

### Defect Report Structure

```text
Defect ID
Title
Environment
Precondition
Test Data
Steps to Reproduce
Expected Result
Actual Result
Severity
Priority
Evidence
Status
Reported By
Reported Date
```

### Defect Lifecycle

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

Possible alternative states include:

```text
Rejected
Duplicate
Deferred
Not a Bug
Reopened
```

The project defines the defect lifecycle as New → Assigned → Open → Fixed → Retest → Verified → Closed, with rationale required for alternative dispositions.

---

# 🔁 Retesting & Regression

## Retesting

Retesting verifies whether a specific defect has been fixed.

```text
Defect Found
     ↓
Developer Fix
     ↓
Retest Same Scenario
     ↓
Pass → Verify
Fail → Reopen
```

## Regression Testing

Regression testing verifies that the fix has not negatively affected related functionality.

```text
Bug Fix
  ↓
Retest Fixed Functionality
  ↓
Identify Impacted Areas
  ↓
Execute Regression Tests
  ↓
Evaluate Results
```

---

# 📈 Test Execution

Actual execution metrics should be entered only after executing the test cases.

| Metric           |                        Result |
| ---------------- | ----------------------------: |
| Total Test Cases | To be updated after execution |
| Passed           |                 To be updated |
| Failed           |                 To be updated |
| Blocked          |                 To be updated |
| Not Executed     |                 To be updated |
| Pass %           |              To be calculated |
| Fail %           |              To be calculated |
| Open Defects     |                 To be updated |
| Closed Defects   |                 To be updated |

### Pass Percentage

```text
Pass % = Passed Test Cases / Executed Test Cases × 100
```

### Fail Percentage

```text
Fail % = Failed Test Cases / Executed Test Cases × 100
```

> **Note:** No execution result in this repository should be presented as observed unless the test was actually executed and supported by evidence.

---

# 📦 QA Deliverables

This project contains/plans the following QA artifacts:

|  # | Deliverable                     |
| -: | ------------------------------- |
| 01 | Application Overview            |
| 02 | Requirements                    |
| 03 | Test Plan                       |
| 04 | Test Strategy                   |
| 05 | Test Scenarios                  |
| 06 | Detailed Test Cases             |
| 07 | Test Data                       |
| 08 | Requirement Traceability Matrix |
| 09 | Test Execution Report           |
| 10 | Regression Suite                |
| 11 | Test Summary Report             |
| 12 | Defect Reports                  |
| 13 | Screenshots / Evidence          |
| 14 | Evidence Index                  |

---

# 📁 Repository Structure

```text
saucedemo-ecommerce-manual-testing/
│
├── README.md
│
├── docs/
│   ├── 01_application_overview.md
│   ├── 02_requirements.md
│   ├── 03_test_plan.md
│   ├── 04_test_strategy.md
│   ├── 05_test_scenarios.md
│   ├── 06_test_cases.md
│   ├── 07_test_data.md
│   ├── 08_rtm.md
│   ├── 09_test_execution.md
│   ├── 10_regression_suite.md
│   └── 11_test_summary.md
│
├── bugs/
│   ├── README.md
│   └── defect-reports/
│
├── screenshots/
│   ├── login/
│   ├── inventory/
│   ├── product-details/
│   ├── cart/
│   ├── checkout/
│   ├── order-completion/
│   └── logout/
│
├── test-data/
│   └── test-data.md
│
├── evidence-index.md
│
└── LICENSE
```

This structure follows the project document's recommended recruiter-friendly organization.

---

# 🛠️ Tools & Technologies

| Tool / Technology                  | Purpose                         |
| ---------------------------------- | ------------------------------- |
| Web Browser                        | Application testing             |
| Browser DevTools                   | Observation and troubleshooting |
| GitHub                             | Version control & portfolio     |
| Markdown                           | QA documentation                |
| Spreadsheet / Test Management Tool | Test cases and execution        |
| Issue Tracker                      | Defect management               |
| Screenshot Utility                 | Evidence capture                |

---

# 🔄 Agile QA Workflow

The project follows an Agile/Scrum-oriented QA workflow.

### 1. Backlog Refinement

QA:

* Reviews requirements.
* Identifies ambiguity.
* Checks acceptance criteria.
* Raises clarification questions.
* Identifies testability risks.

### 2. Sprint Planning

QA estimates:

* Requirement analysis
* Test design
* Test execution
* Retesting
* Regression effort

### 3. Development Handoff

QA prepares:

* Test data
* Test cases
* Smoke tests
* Exploratory coverage

### 4. Test Execution

QA:

```text
Smoke
 ↓
Functional Testing
 ↓
Exploratory Testing
 ↓
Defect Reporting
 ↓
Retesting
 ↓
Regression
```

### 5. Sprint Demo

QA communicates:

* Test status
* Evidence
* Defects
* Known risks
* Remaining limitations

### 6. Retrospective

The team discusses:

* Escaped defects
* Environment problems
* Process issues
* Testing improvements

This workflow is aligned with the Agile QA process documented in the project.

---

# ⚠️ Risk-Based Testing

Testing effort is concentrated on high-business-impact workflows.

### Risk Matrix

| Area                 | Business Impact           | Priority   |
| -------------------- | ------------------------- | ---------- |
| Login                | Blocks customer journey   | Critical   |
| Checkout             | Blocks purchase           | Critical   |
| Order Completion     | Core business outcome     | Critical   |
| Cart                 | Incorrect purchase state  | Critical   |
| Product Selection    | Affects purchase decision | High       |
| Customer Information | Blocks checkout           | High       |
| Logout               | Session/security concern  | High       |
| Product Sorting      | Product discovery         | Medium     |
| Product Details      | Product information       | High       |
| Cosmetic UI          | Usability                 | Medium/Low |

---

# 📸 Evidence & Reporting Policy

This repository follows an evidence-based testing policy.

### Observed Result

Use only when:

```text
Test Executed
     +
Actual Result Recorded
     +
Evidence Available
```

### Planned / Sample

Use when a test has not yet been executed.

Examples:

```text
Sample / Template
```

or

```text
Potential test scenario — requires execution
```

### Important

A potential defect must **never** be presented as a confirmed defect without execution and evidence.

The source project explicitly requires unverified scenarios to remain labeled as potential scenarios.

---

# 📊 Test Completion Criteria

Testing should be considered ready for closure when:

* Critical tests are executed.
* Planned coverage is completed or formally risk-accepted.
* Failures have evidence or documented limitations.
* Critical defects are closed or formally accepted.
* Retesting is completed.
* Impacted regression testing is completed.
* Test summary is prepared and approved.

These are the project's defined exit criteria.

---

# 🚫 Scope & Credibility Statement

This is an **independent QA portfolio project** using a publicly accessible demo application.

It demonstrates structured manual testing practices rather than professional employment experience.

The project does **not** claim:

* Production testing experience
* Real customer testing
* Real payment testing
* Backend/API testing
* Database testing
* Performance testing
* Penetration testing
* Production deployment validation

This distinction keeps the portfolio accurate and interview-defensible.

---

# 🧠 Key QA Learnings

Through this project, I practiced:

* Software Testing Life Cycle (STLC)
* Software Development Life Cycle (SDLC)
* Requirement Analysis
* Test Planning
* Risk-Based Testing
* Test Scenario Design
* Test Case Design
* Positive Testing
* Negative Testing
* Boundary Value Analysis
* Equivalence Partitioning
* Decision Table Testing
* State Transition Testing
* Exploratory Testing
* Functional Testing
* UI Testing
* Smoke Testing
* Sanity Testing
* Regression Testing
* Retesting
* Defect Management
* Requirement Traceability
* Test Execution Reporting
* Test Summary Reporting
* Agile/Scrum QA Workflow

---

# 🎤 Interview Discussion Points

This project can be discussed in interviews around questions such as:

### Project-Level Questions

1. Tell me about your SauceDemo testing project.
2. Why did you choose an e-commerce application?
3. What was the most critical business workflow?
4. How did you decide testing priorities?
5. What was your testing strategy?
6. How did you design your test cases?
7. Which test design techniques did you use?
8. How did you perform negative testing?
9. How did you manage defects?
10. What is the difference between retesting and regression testing?
11. How did you maintain traceability?
12. What would you include in a smoke suite?
13. What would you include in a regression suite?
14. How would you test checkout?
15. How would you test logout?
16. How would you test cart functionality?
17. How would you test invalid login?
18. What would you do if requirements were ambiguous?
19. What are the limitations of this project?
20. How would you improve this project in a real organization?

---

# 🚀 Future Improvements

The project can be extended with:

### Automation Testing

```text
Manual Testing
      ↓
Selenium / Playwright
      ↓
Automation Framework
      ↓
Page Object Model
      ↓
Test Reporting
      ↓
CI/CD
```

### API Testing

Potential future scope:

* REST API validation
* Request/response validation
* Status-code testing
* Schema validation
* API automation

### Performance Testing

Potential future scope:

* Load testing
* Stress testing
* Response-time analysis
* Scalability testing

### CI/CD

Future integration:

```text
GitHub
   ↓
GitHub Actions
   ↓
Automated Tests
   ↓
Test Report
   ↓
Build Status
```

---

# 📚 Project Documentation

Detailed documentation is available in the `docs/` directory.

| Document             | Purpose                              |
| -------------------- | ------------------------------------ |
| Application Overview | Application and module understanding |
| Requirements         | Functional requirements              |
| Test Plan            | Testing scope and execution approach |
| Test Strategy        | Risk-based strategy                  |
| Test Scenarios       | High-level coverage                  |
| Test Cases           | Detailed validation                  |
| Test Data            | Controlled test inputs               |
| RTM                  | Requirement-to-test mapping          |
| Test Execution       | Execution results                    |
| Regression Suite     | Regression coverage                  |
| Test Summary         | Final QA assessment                  |

---

# 📌 Final QA Statement

This project demonstrates an end-to-end manual QA workflow for an e-commerce application.

The focus is not simply on writing test cases, but on demonstrating the complete QA process:

```text
Understand the Business
        ↓
Analyze Requirements
        ↓
Identify Risks
        ↓
Design Tests
        ↓
Prepare Data
        ↓
Execute Tests
        ↓
Capture Evidence
        ↓
Report Defects
        ↓
Retest Fixes
        ↓
Run Regression
        ↓
Maintain Traceability
        ↓
Report Quality Status
        ↓
Recommend Release
```

The goal is to demonstrate **structured thinking, risk awareness, evidence-based testing, defect analysis, traceability, and professional QA documentation**.

---

# 👨‍💻 Author

**Pranay Jha**

BCA Student | Aspiring QA Engineer

### Areas of Interest

* Manual Testing
* Software Quality Assurance
* Test Case Design
* API Testing
* Test Automation
* Selenium
* Playwright
* Python
* Java
* CI/CD

---

## ⭐ If you find this project useful

Feel free to explore the repository, review the QA artifacts, and use the structure as a reference for learning software testing.

**Thank you for visiting this project!**