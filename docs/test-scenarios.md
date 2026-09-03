# Test Scenarios

## 1. Document Purpose

This document contains high-level test scenarios for the **SauceDemo / Swag Labs e-commerce application**.

Test scenarios define **what needs to be tested**, while detailed test cases will define **how each scenario will be executed**.

The scenarios cover the complete customer journey:

```text
Login
  ↓
Inventory
  ↓
Product Details
  ↓
Shopping Cart
  ↓
Checkout
  ↓
Order Completion
  ↓
Logout
```

---

# 2. Scenario Identification

| Scenario ID     | Module           | Scenario                                            |
| --------------- | ---------------- | --------------------------------------------------- |
| TS-LOGIN-001    | Login            | Verify successful login with valid credentials      |
| TS-LOGIN-002    | Login            | Verify login rejection with invalid credentials     |
| TS-LOGIN-003    | Login            | Verify validation when username is missing          |
| TS-LOGIN-004    | Login            | Verify validation when password is missing          |
| TS-LOGIN-005    | Login            | Verify validation when both credentials are missing |
| TS-INV-001      | Inventory        | Verify inventory/product listing                    |
| TS-INV-002      | Inventory        | Verify product information displayed                |
| TS-INV-003      | Inventory        | Verify product sorting                              |
| TS-INV-004      | Inventory        | Verify adding a product to cart                     |
| TS-INV-005      | Inventory        | Verify removing a product from cart                 |
| TS-PROD-001     | Product Details  | Verify product details                              |
| TS-PROD-002     | Product Details  | Verify adding product from details page             |
| TS-PROD-003     | Product Details  | Verify removing product from details page           |
| TS-PROD-004     | Product Details  | Verify navigation back to inventory                 |
| TS-CART-001     | Cart             | Verify opening the shopping cart                    |
| TS-CART-002     | Cart             | Verify selected products in cart                    |
| TS-CART-003     | Cart             | Verify product quantity                             |
| TS-CART-004     | Cart             | Verify product price                                |
| TS-CART-005     | Cart             | Verify removing cart items                          |
| TS-CART-006     | Cart             | Verify continue shopping                            |
| TS-CART-007     | Cart             | Verify proceeding to checkout                       |
| TS-CHECKOUT-001 | Checkout         | Verify checkout information fields                  |
| TS-CHECKOUT-002 | Checkout         | Verify First Name validation                        |
| TS-CHECKOUT-003 | Checkout         | Verify Last Name validation                         |
| TS-CHECKOUT-004 | Checkout         | Verify Postal Code validation                       |
| TS-CHECKOUT-005 | Checkout         | Verify continuing checkout with valid information   |
| TS-ORDER-001    | Order Overview   | Verify order overview                               |
| TS-ORDER-002    | Order Overview   | Verify selected products in order overview          |
| TS-ORDER-003    | Order Overview   | Verify price information                            |
| TS-ORDER-004    | Order Overview   | Verify order total                                  |
| TS-COMPLETE-001 | Order Completion | Verify successful order completion                  |
| TS-COMPLETE-002 | Order Completion | Verify order confirmation                           |
| TS-COMPLETE-003 | Order Completion | Verify post-order navigation                        |
| TS-LOGOUT-001   | Logout           | Verify successful logout                            |
| TS-LOGOUT-002   | Logout           | Verify post-logout application state                |

---

# 3. Login Test Scenarios

## TS-LOGIN-001 — Valid Login

**Objective:** Verify that a user can successfully authenticate using valid credentials.

**Priority:** P0
**Type:** Positive

**Expected Outcome:** User is successfully authenticated and navigated to the inventory page.

---

## TS-LOGIN-002 — Invalid Credentials

**Objective:** Verify that invalid login credentials are rejected.

**Priority:** P0
**Type:** Negative

**Expected Outcome:** User remains unauthenticated and an appropriate validation/error message is displayed.

---

## TS-LOGIN-003 — Missing Username

**Objective:** Verify login behavior when the username field is left empty.

**Priority:** P1
**Type:** Negative

**Expected Outcome:** Application prevents login and displays appropriate validation.

---

## TS-LOGIN-004 — Missing Password

**Objective:** Verify login behavior when the password field is left empty.

**Priority:** P1
**Type:** Negative

**Expected Outcome:** Application prevents login and displays appropriate validation.

---

## TS-LOGIN-005 — Missing Username and Password

**Objective:** Verify login behavior when both required authentication fields are empty.

**Priority:** P1
**Type:** Negative

**Expected Outcome:** Application prevents authentication and provides appropriate validation.

---

# 4. Inventory Test Scenarios

## TS-INV-001 — Inventory Listing

**Objective:** Verify that the inventory page displays available products after successful login.

**Priority:** P0
**Type:** Functional

**Expected Outcome:** Available products are displayed correctly.

---

## TS-INV-002 — Product Information

**Objective:** Verify that product information is displayed correctly.

Information includes:

* Product name
* Product image
* Product price
* Available product action

**Priority:** P1
**Type:** Functional

---

## TS-INV-003 — Product Sorting

**Objective:** Verify that products can be sorted using the available sorting options.

**Priority:** P1
**Type:** Functional

**Expected Outcome:** Products are displayed according to the selected sorting criterion.

---

## TS-INV-004 — Add Product to Cart

**Objective:** Verify that a product can be added to the shopping cart from the inventory page.

**Priority:** P0
**Type:** Functional

**Expected Outcome:** Selected product is added to the cart and the cart state is updated.

---

## TS-INV-005 — Remove Product from Cart

**Objective:** Verify that a selected product can be removed from the cart through the available inventory action.

**Priority:** P1
**Type:** Functional

---

# 5. Product Details Test Scenarios

## TS-PROD-001 — Product Details

**Objective:** Verify that selecting a product opens the appropriate product details page.

Verify:

* Product name
* Product image
* Product description
* Product price

**Priority:** P1

---

## TS-PROD-002 — Add Product from Details

**Objective:** Verify that a product can be added to the cart from its details page.

**Priority:** P1

---

## TS-PROD-003 — Remove Product from Details

**Objective:** Verify that a selected product can be removed using the available remove action.

**Priority:** P2

---

## TS-PROD-004 — Return to Inventory

**Objective:** Verify navigation from product details back to the inventory page.

**Priority:** P2

---

# 6. Shopping Cart Test Scenarios

## TS-CART-001 — Open Shopping Cart

**Objective:** Verify that the user can open the shopping cart.

**Priority:** P0

---

## TS-CART-002 — Verify Selected Products

**Objective:** Verify that products added by the user are correctly displayed in the cart.

**Priority:** P0

**Expected Outcome:** Cart contents match the products selected by the user.

---

## TS-CART-003 — Verify Product Quantity

**Objective:** Verify that the expected quantity information is displayed for selected products.

**Priority:** P1

---

## TS-CART-004 — Verify Product Price

**Objective:** Verify that applicable product price information is displayed correctly in the cart.

**Priority:** P1

---

## TS-CART-005 — Remove Cart Item

**Objective:** Verify that a user can remove an item from the shopping cart.

**Priority:** P1

---

## TS-CART-006 — Continue Shopping

**Objective:** Verify that the user can return from the cart to continue shopping.

**Priority:** P2

---

## TS-CART-007 — Proceed to Checkout

**Objective:** Verify that the user can proceed from the cart to the checkout process.

**Priority:** P0

**Expected Outcome:** User is navigated to the checkout information page.

---

# 7. Checkout Test Scenarios

## TS-CHECKOUT-001 — Checkout Information

**Objective:** Verify that the checkout page provides the required customer information fields.

Fields include:

* First Name
* Last Name
* Postal Code

**Priority:** P0

---

## TS-CHECKOUT-002 — First Name Validation

**Objective:** Verify validation of the First Name field when required information is missing or invalid.

**Priority:** P1
**Type:** Negative

---

## TS-CHECKOUT-003 — Last Name Validation

**Objective:** Verify validation of the Last Name field when required information is missing or invalid.

**Priority:** P1
**Type:** Negative

---

## TS-CHECKOUT-004 — Postal Code Validation

**Objective:** Verify validation of the Postal Code field when required information is missing or invalid.

**Priority:** P1
**Type:** Negative

---

## TS-CHECKOUT-005 — Continue Checkout

**Objective:** Verify that the user can continue to the order overview after providing valid required information.

**Priority:** P0
**Type:** Positive

**Expected Outcome:** User is navigated to the order overview page.

---

# 8. Order Overview Test Scenarios

## TS-ORDER-001 — Order Overview

**Objective:** Verify that the order overview is displayed before final order completion.

**Priority:** P0

---

## TS-ORDER-002 — Verify Ordered Products

**Objective:** Verify that products selected by the user are correctly displayed in the order overview.

**Priority:** P0

---

## TS-ORDER-003 — Verify Price Information

**Objective:** Verify that applicable price information is displayed correctly before order completion.

**Priority:** P1

---

## TS-ORDER-004 — Verify Order Total

**Objective:** Verify that the applicable order total is displayed before completing the order.

**Priority:** P0

---

# 9. Order Completion Test Scenarios

## TS-COMPLETE-001 — Complete Order

**Objective:** Verify that the user can successfully complete the order from the order overview.

**Priority:** P0
**Risk:** Critical

**Expected Outcome:** Order completion process executes successfully.

---

## TS-COMPLETE-002 — Order Confirmation

**Objective:** Verify that an appropriate confirmation is displayed after successful order completion.

**Priority:** P0
**Risk:** Critical

---

## TS-COMPLETE-003 — Post-Order Navigation

**Objective:** Verify that the application provides the expected navigation/state after order completion.

**Priority:** P1

---

# 10. Logout Test Scenarios

## TS-LOGOUT-001 — Successful Logout

**Objective:** Verify that an authenticated user can successfully log out.

**Priority:** P0

**Expected Outcome:** User is returned to the appropriate unauthenticated state.

---

## TS-LOGOUT-002 — Post-Logout State

**Objective:** Verify the application behavior after logout.

**Priority:** P1

**Expected Outcome:** The user should no longer remain in the authenticated shopping state.

---

# 11. End-to-End Test Scenarios

## TS-E2E-001 — Complete Customer Shopping Journey

**Objective:** Validate the complete primary customer workflow.

**Workflow:**

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

**Priority:** P0
**Risk:** Critical
**Test Type:** End-to-End

This is the **highest-priority scenario** because it validates the application's primary business workflow.

---

## TS-E2E-002 — Multiple Product Shopping Journey

**Objective:** Verify the shopping workflow when multiple products are selected.

**Coverage:**

* Product selection
* Multiple products in cart
* Cart verification
* Checkout
* Order overview
* Order completion

**Priority:** P1

---

## TS-E2E-003 — Add and Remove Product Journey

**Objective:** Verify that adding and removing products maintains the expected cart state.

**Priority:** P1

---

# 12. Negative Test Scenarios

Negative testing should cover invalid, incomplete, or unexpected user inputs.

| Scenario ID | Negative Condition                                                |
| ----------- | ----------------------------------------------------------------- |
| TS-NEG-001  | Invalid login credentials                                         |
| TS-NEG-002  | Missing username                                                  |
| TS-NEG-003  | Missing password                                                  |
| TS-NEG-004  | Missing checkout first name                                       |
| TS-NEG-005  | Missing checkout last name                                        |
| TS-NEG-006  | Missing postal code                                               |
| TS-NEG-007  | Invalid checkout information                                      |
| TS-NEG-008  | Attempt to continue checkout with incomplete required information |

---

# 13. Boundary Test Scenarios

Boundary testing should be applied to input fields where applicable.

Areas to consider:

* Minimum input length
* Maximum input length
* Empty values
* Values at accepted limits
* Values immediately outside accepted limits
* Special characters
* Whitespace
* Numeric/alphanumeric combinations where applicable

> Actual boundary values should be determined from the application's observed validation behavior and documented test requirements rather than assumed.

---

# 14. Exploratory Test Scenarios

Exploratory testing should be performed in addition to predefined scenarios.

Areas to explore include:

* Navigation between application pages
* Browser back/forward behavior
* Repeated add/remove actions
* Multiple products
* Empty cart behavior
* Repeated checkout actions
* Unexpected navigation
* UI consistency
* Responsive behavior
* Basic accessibility observations

Any issue discovered during exploratory testing should be documented with reproducible steps and supporting evidence.

---

# 15. Regression Test Scenarios

Regression testing should focus on functionality potentially affected by application changes.

High-priority regression areas include:

1. Login
2. Inventory loading
3. Product selection
4. Add to cart
5. Remove from cart
6. Cart contents
7. Checkout
8. Order overview
9. Order completion
10. Logout

The detailed regression suite will be maintained separately in:

`docs/10_regression_suite.md`

---

# 16. Smoke Test Scenarios

The smoke suite should verify that the application is sufficiently stable for deeper testing.

Recommended smoke scenarios:

| ID        | Smoke Scenario                  | Priority |
| --------- | ------------------------------- | -------- |
| SMOKE-001 | Login with valid credentials    | P0       |
| SMOKE-002 | Inventory page loads            | P0       |
| SMOKE-003 | Add product to cart             | P0       |
| SMOKE-004 | Open cart                       | P0       |
| SMOKE-005 | Proceed to checkout             | P0       |
| SMOKE-006 | Complete primary order workflow | P0       |
| SMOKE-007 | Logout                          | P0       |

---

# 17. Scenario Priority Matrix

| Priority      | Main Scenarios                                                 |
| ------------- | -------------------------------------------------------------- |
| P0 / Critical | Login, Add to Cart, Cart, Checkout, Order Completion, Logout   |
| P1 / High     | Sorting, Product Details, Cart Validation, Checkout Validation |
| P2 / Medium   | Secondary navigation, Continue Shopping                        |
| P3 / Low      | Lower-risk usability observations and enhancements             |

---

# 18. Scenario Coverage Summary

The test scenarios provide coverage across:

* Authentication
* Inventory
* Product listing
* Product sorting
* Product details
* Shopping cart
* Checkout
* Order overview
* Order completion
* Logout
* End-to-end workflow
* Positive testing
* Negative testing
* Boundary testing
* Exploratory testing
* Smoke testing
* Regression testing
* Retesting

---

# 19. Scenario-to-Requirement Mapping

| Scenario        | Requirement      |
| --------------- | ---------------- |
| TS-LOGIN-001    | REQ-LOGIN-001    |
| TS-LOGIN-002    | REQ-LOGIN-002    |
| TS-LOGIN-003    | REQ-LOGIN-003    |
| TS-LOGIN-004    | REQ-LOGIN-004    |
| TS-INV-001      | REQ-INV-001      |
| TS-INV-003      | REQ-INV-002      |
| TS-INV-004      | REQ-INV-003      |
| TS-INV-005      | REQ-INV-004      |
| TS-PROD-001     | REQ-PROD-001     |
| TS-PROD-002     | REQ-PROD-002     |
| TS-CART-001     | REQ-CART-001     |
| TS-CART-002     | REQ-CART-002     |
| TS-CART-003     | REQ-CART-003     |
| TS-CART-004     | REQ-CART-004     |
| TS-CART-005     | REQ-CART-005     |
| TS-CART-006     | REQ-CART-006     |
| TS-CART-007     | REQ-CART-007     |
| TS-CHECKOUT-001 | REQ-CHECKOUT-001 |
| TS-CHECKOUT-002 | REQ-CHECKOUT-002 |
| TS-CHECKOUT-003 | REQ-CHECKOUT-003 |
| TS-CHECKOUT-004 | REQ-CHECKOUT-004 |
| TS-CHECKOUT-005 | REQ-CHECKOUT-005 |
| TS-ORDER-001    | REQ-ORDER-001    |
| TS-ORDER-002    | REQ-ORDER-002    |
| TS-ORDER-003    | REQ-ORDER-003    |
| TS-ORDER-004    | REQ-ORDER-004    |
| TS-COMPLETE-001 | REQ-COMPLETE-001 |
| TS-COMPLETE-002 | REQ-COMPLETE-002 |
| TS-COMPLETE-003 | REQ-COMPLETE-003 |
| TS-LOGOUT-001   | REQ-LOGOUT-001   |
| TS-LOGOUT-002   | REQ-LOGOUT-002   |

---

# 20. Important QA Note

These are **test scenarios**, not execution results.

Do not mark scenarios as **Passed, Failed, Blocked, or Defective** until they have actually been executed.

Actual execution status, observed results, screenshots, and defects should be maintained separately in the project documentation.

---

# 21. Next Document

The next stage is to convert these high-level scenarios into detailed test cases.

The detailed test cases should contain:

* Test Case ID
* Requirement ID
* Scenario ID
* Test Case Title
* Preconditions
* Test Data
* Step-by-step Actions
* Expected Result
* Actual Result
* Status
* Priority
* Severity
* Evidence/Screenshot
* Defect ID

Detailed test cases will be maintained in:

`docs/06_test_cases.md`
