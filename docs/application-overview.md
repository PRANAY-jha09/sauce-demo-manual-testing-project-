# Application Overview

## 1. Application Name

**SauceDemo / Swag Labs**

SauceDemo is a web-based e-commerce application used for practicing and demonstrating software testing concepts. The application provides a realistic shopping workflow covering user authentication, product browsing, cart management, checkout, and order completion.

This project focuses on **manual testing of the complete e-commerce customer journey**.

---

## 2. Application Under Test

| Attribute             | Details                                                                 |
| --------------------- | ----------------------------------------------------------------------- |
| Application           | SauceDemo / Swag Labs                                                   |
| Application Type      | Web-based E-Commerce Application                                        |
| Testing Type          | Manual Testing                                                          |
| Primary Testing Focus | Functional Testing                                                      |
| Testing Approach      | Risk-Based Testing                                                      |
| Primary Workflow      | Login → Product Selection → Cart → Checkout → Order Completion → Logout |
| Target                | E-Commerce Customer Workflow                                            |

---

## 3. Business Purpose

The primary purpose of the application is to simulate an online shopping experience where a user can:

1. Log into the application.
2. View available products.
3. Sort products.
4. Open product details.
5. Add products to the shopping cart.
6. Modify cart contents.
7. Proceed to checkout.
8. Enter customer information.
9. Review order information.
10. Complete an order.
11. Logout from the application.

From a QA perspective, the application provides an end-to-end workflow suitable for validating both individual features and the complete customer journey.

---

## 4. Application Modules

The application is divided into the following major functional areas:

### 4.1 Login

The login module allows users to authenticate using username and password.

Testing includes:

* Valid login
* Invalid username
* Invalid password
* Missing username
* Missing password
* Missing username and password
* Login validation
* Authentication error messages

---

### 4.2 Inventory / Product Listing

After successful login, the user is taken to the inventory page.

The inventory module allows users to:

* View available products
* View product names
* View product prices
* View product images
* Add products to cart
* Remove products from cart
* Sort products

Sorting functionality is included as an important validation area because incorrect sorting can affect product discovery and user experience.

---

### 4.3 Product Details

Users can select a product and navigate to its detailed product page.

The product details area is validated for:

* Product name
* Product image
* Product description
* Product price
* Add-to-cart functionality
* Remove-from-cart functionality
* Navigation back to inventory

---

### 4.4 Shopping Cart

The cart module contains products selected by the user.

Testing includes:

* Adding products
* Removing products
* Verifying selected products
* Verifying product quantity
* Verifying product price
* Navigating to checkout
* Returning to shopping

---

### 4.5 Checkout

The checkout process collects customer information before order completion.

The checkout workflow includes:

1. Opening checkout.
2. Entering first name.
3. Entering last name.
4. Entering postal code.
5. Continuing to order overview.
6. Reviewing order information.

Validation is performed for required fields and invalid or missing input.

---

### 4.6 Order Completion

The order completion module represents the final stage of the customer journey.

Testing focuses on:

* Order overview
* Product information
* Price information
* Order total
* Completing the order
* Confirmation message
* Navigation after order completion

This is considered a **high-priority workflow** because failures here can directly affect the successful completion of the customer's shopping journey.

---

### 4.7 Logout

The logout functionality allows an authenticated user to exit the application.

Testing includes:

* Successful logout
* Navigation after logout
* Access behavior after logout
* Session-related validation

---

## 5. Critical Business Workflow

The most important end-to-end workflow identified for this project is:

```text
Login
  ↓
Inventory
  ↓
Select Product
  ↓
Add Product to Cart
  ↓
Open Cart
  ↓
Checkout
  ↓
Enter Customer Information
  ↓
Review Order
  ↓
Complete Order
  ↓
Order Confirmation
  ↓
Logout
```

This workflow receives high testing priority because it represents the primary customer journey through the e-commerce application.

---

## 6. Testing Scope

### In Scope

The following areas are included in this manual testing project:

* Login
* Authentication validation
* Inventory/product listing
* Product sorting
* Product details
* Add to cart
* Remove from cart
* Cart validation
* Checkout information
* Checkout validation
* Order overview
* Order completion
* Logout
* End-to-end customer workflow
* Positive testing
* Negative testing
* Boundary testing
* Equivalence partitioning
* Decision table testing
* State transition testing
* Exploratory testing
* Smoke testing
* Sanity testing
* Regression testing
* Retesting
* Defect reporting
* Requirements Traceability Matrix

---

## 7. Out of Scope

The following areas are intentionally excluded from this project:

* API testing
* Database testing
* Performance/load testing
* Penetration/security testing
* Production deployment testing
* Real payment processing
* Unauthorized data collection

These areas may be considered as future extensions of the project but are not part of the current manual testing scope.

---

## 8. Testing Approach

A **risk-based testing approach** is used for this project.

Testing priority is determined according to:

* Business impact
* User impact
* Failure probability
* Criticality of the workflow
* Dependency between features

### Priority Classification

| Priority | Description                     |
| -------- | ------------------------------- |
| P0       | Critical business functionality |
| P1       | High-impact functionality       |
| P2       | Medium-impact functionality     |
| P3       | Low-impact functionality        |

The complete login-to-order workflow is given higher priority because a failure in any major step can prevent successful order completion.

---

## 9. Test Design Techniques

The project uses multiple manual test design techniques to improve coverage.

### Equivalence Partitioning

Input data is divided into valid and invalid groups to reduce redundant testing while maintaining meaningful coverage.

### Boundary Value Analysis

Boundary values are tested because defects frequently occur at input limits.

### Decision Table Testing

Different combinations of conditions and expected outcomes are evaluated.

### State Transition Testing

The behavior of the application is validated as the user moves between different application states.

Example:

```text
Logged Out
    ↓
Logged In
    ↓
Shopping
    ↓
Checkout
    ↓
Order Completed
    ↓
Logged Out
```

### Exploratory Testing

The application is explored beyond predefined test cases to identify unexpected behavior and usability issues.

---

## 10. Testing Types

The following testing types are considered in this project:

### Functional Testing

Validates whether application functionality behaves according to expected requirements.

### Positive Testing

Uses valid inputs and expected user behavior.

### Negative Testing

Uses invalid, incomplete, or unexpected inputs to validate application behavior.

### Smoke Testing

Validates critical application functionality before deeper testing.

### Sanity Testing

Performs focused validation after changes to determine whether the affected functionality is stable.

### Regression Testing

Ensures that existing functionality continues to work after application changes.

### Retesting

Verifies that previously reported defects have been fixed successfully.

### Compatibility Testing

Considers browser and responsive behavior as part of the overall quality assessment.

---

## 11. Test Environment

The application is tested as a web-based application.

The test environment should record relevant information such as:

| Environment Attribute | Example                 |
| --------------------- | ----------------------- |
| Application           | SauceDemo               |
| Browser               | Chrome / Firefox / Edge |
| Operating System      | Windows                 |
| Testing Type          | Manual                  |
| Environment           | Test/Demo Environment   |
| Test Execution        | Local Browser           |

Actual browser, operating system, execution date, and test results should be recorded based on the environment in which the tests are actually executed.

---

## 12. Evidence and Documentation

Testing evidence is maintained to support test execution and defect reporting.

Evidence may include:

* Screenshots
* Test execution results
* Defect evidence
* Expected vs actual results
* Retest evidence
* Regression evidence

Only **actual observed results** should be reported as executed results.

Planned or simulated test results must not be presented as actual execution results.

---

## 13. Defect Management

Defects identified during execution follow a standard defect lifecycle:

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

The appropriate reason should be documented whenever these statuses are used.

---

## 14. QA Deliverables

The project maintains the following QA deliverables:

* Application Overview
* Requirements Document
* Test Plan
* Test Strategy
* Test Scenarios
* Test Cases
* Test Data
* Requirements Traceability Matrix
* Test Execution Report
* Regression Suite
* Test Summary Report
* Defect Reports
* Screenshots/Evidence
* Evidence Index

---

## 15. Completion Criteria

Testing is considered complete when:

1. Critical test cases have been executed.
2. Planned test coverage is completed or remaining risk is accepted.
3. Test failures have appropriate evidence.
4. Critical defects are closed or formally accepted.
5. Retesting has been completed for fixed defects.
6. Impacted regression tests have been executed.
7. Final testing results are documented.
8. The test summary is prepared.

---

## 16. Project Objective

The objective of this project is to demonstrate the ability to perform structured manual QA on a realistic e-commerce workflow.

The project demonstrates practical knowledge of:

* SDLC
* STLC
* Agile/Scrum workflow
* Test planning
* Test strategy
* Test scenario design
* Test case design
* Test data preparation
* Functional testing
* Negative testing
* Regression testing
* Retesting
* Defect management
* Traceability
* Risk-based testing
* Test documentation
* Evidence-based reporting

---

## 17. Summary

SauceDemo provides a suitable environment for demonstrating end-to-end manual testing of an e-commerce application.

The project focuses on validating the complete customer journey from **authentication to order completion**, while also applying multiple test design techniques and structured QA documentation.

The primary goal is not only to identify defects but also to demonstrate a professional QA process involving **planning, test design, execution, defect management, retesting, regression, traceability, evidence collection, and test closure**.
