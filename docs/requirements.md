# Requirements

## 1. Document Purpose

This document defines the functional requirements for the **SauceDemo / Swag Labs e-commerce application** covered by this manual testing project.

These requirements provide the foundation for:

* Test scenarios
* Test cases
* Test data
* Requirements Traceability Matrix (RTM)
* Test execution
* Regression testing
* Defect reporting
* Test summary

Each requirement is assigned a unique identifier so that it can be traced to the corresponding test scenarios and test cases.

---

## 2. Requirement Scope

The requirements covered in this project include the complete customer shopping workflow:

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

---

# 3. Functional Requirements

## 3.1 Login Requirements

### REQ-LOGIN-001 — Valid Login

The application shall allow a user with valid credentials to successfully log in.

**Expected Behavior:**

* Valid username and password are accepted.
* User is authenticated successfully.
* User is navigated to the inventory/product listing page.

**Priority:** P0
**Risk:** High

---

### REQ-LOGIN-002 — Invalid Credentials

The application shall reject invalid login credentials.

**Expected Behavior:**

* Invalid credentials should not provide access to the authenticated area.
* An appropriate validation/error message should be displayed.

**Priority:** P0
**Risk:** High

---

### REQ-LOGIN-003 — Missing Username

The application shall validate the username field when the user attempts to log in without providing a username.

**Priority:** P1
**Risk:** High

---

### REQ-LOGIN-004 — Missing Password

The application shall validate the password field when the user attempts to log in without providing a password.

**Priority:** P1
**Risk:** High

---

### REQ-LOGIN-005 — Missing Login Information

The application shall prevent login when required authentication information is not provided.

**Priority:** P1
**Risk:** High

---

# 4. Inventory Requirements

## REQ-INV-001 — Product Listing

The application shall display the available products after successful authentication.

The inventory page should provide relevant product information such as:

* Product name
* Product image
* Product price
* Product action controls

**Priority:** P0
**Risk:** High

---

## REQ-INV-002 — Product Sorting

The application shall allow users to sort products using the available sorting options.

Sorting should produce results according to the selected sorting criterion.

**Priority:** P1
**Risk:** Medium

---

## REQ-INV-003 — Add Product to Cart

The application shall allow a user to add an available product to the shopping cart.

After adding a product:

* The product should be reflected in the cart.
* The corresponding cart state should be updated.

**Priority:** P0
**Risk:** High

---

## REQ-INV-004 — Remove Product from Cart

The application shall allow a user to remove a previously selected product from the cart.

**Priority:** P1
**Risk:** Medium

---

# 5. Product Details Requirements

## REQ-PROD-001 — Product Details

The application shall allow users to open the details of an individual product.

The product details page should display relevant information including:

* Product name
* Product image
* Product description
* Product price

**Priority:** P1
**Risk:** Medium

---

## REQ-PROD-002 — Add Product from Details

The application shall allow the user to add the selected product to the cart from the product details page.

**Priority:** P1
**Risk:** Medium

---

## REQ-PROD-003 — Remove Product from Details

The application shall allow the user to remove a selected product from the cart where the corresponding action is available.

**Priority:** P2
**Risk:** Medium

---

## REQ-PROD-004 — Return to Inventory

The application shall provide navigation that allows the user to return from product details to the inventory/product listing area.

**Priority:** P2
**Risk:** Low

---

# 6. Shopping Cart Requirements

## REQ-CART-001 — View Cart

The application shall allow users to open the shopping cart and review selected products.

**Priority:** P0
**Risk:** High

---

## REQ-CART-002 — Verify Cart Products

The cart shall display the products selected by the user.

The information should be consistent with the products added from the inventory or product details area.

**Priority:** P0
**Risk:** High

---

## REQ-CART-003 — Cart Quantity

The cart shall provide the expected product quantity information for selected products.

**Priority:** P1
**Risk:** Medium

---

## REQ-CART-004 — Cart Price

The cart shall display the applicable price information for selected products.

**Priority:** P1
**Risk:** High

---

## REQ-CART-005 — Remove Cart Item

The application shall allow the user to remove a selected item from the shopping cart.

**Priority:** P1
**Risk:** Medium

---

## REQ-CART-006 — Continue Shopping

The application shall allow the user to return to shopping/product browsing from the cart.

**Priority:** P2
**Risk:** Low

---

## REQ-CART-007 — Proceed to Checkout

The application shall allow the user to proceed from the shopping cart to checkout.

**Priority:** P0
**Risk:** High

---

# 7. Checkout Requirements

## REQ-CHECKOUT-001 — Checkout Information

The checkout process shall provide fields required for customer information.

The required information includes:

* First Name
* Last Name
* Postal Code

**Priority:** P0
**Risk:** High

---

## REQ-CHECKOUT-002 — First Name Validation

The application shall validate the First Name field when required information is missing or invalid.

**Priority:** P1
**Risk:** Medium

---

## REQ-CHECKOUT-003 — Last Name Validation

The application shall validate the Last Name field when required information is missing or invalid.

**Priority:** P1
**Risk:** Medium

---

## REQ-CHECKOUT-004 — Postal Code Validation

The application shall validate the Postal Code field when required information is missing or invalid.

**Priority:** P1
**Risk:** Medium

---

## REQ-CHECKOUT-005 — Continue Checkout

The application shall allow the user to continue to the order overview when the required checkout information has been provided.

**Priority:** P0
**Risk:** High

---

# 8. Order Overview Requirements

## REQ-ORDER-001 — Order Overview

The application shall display an order overview before final order completion.

The overview should allow the user to review relevant order information.

**Priority:** P0
**Risk:** High

---

## REQ-ORDER-002 — Product Verification

The order overview shall display the products selected for the order.

**Priority:** P0
**Risk:** High

---

## REQ-ORDER-003 — Price Verification

The order overview shall display applicable price information for the selected products.

**Priority:** P1
**Risk:** High

---

## REQ-ORDER-004 — Order Total

The application shall display the applicable order total before order completion.

**Priority:** P0
**Risk:** High

---

# 9. Order Completion Requirements

## REQ-COMPLETE-001 — Complete Order

The application shall allow the user to complete the order from the order overview.

**Priority:** P0
**Risk:** Critical

---

## REQ-COMPLETE-002 — Order Confirmation

After successful order completion, the application shall provide confirmation that the order has been completed.

**Priority:** P0
**Risk:** Critical

---

## REQ-COMPLETE-003 — Post-Order Navigation

The application shall provide the expected navigation/state after successful order completion.

**Priority:** P1
**Risk:** Medium

---

# 10. Logout Requirements

## REQ-LOGOUT-001 — Logout

The application shall allow an authenticated user to log out.

**Priority:** P0
**Risk:** High

---

## REQ-LOGOUT-002 — Post-Logout Behavior

After logout, the application shall return the user to the appropriate unauthenticated state.

**Priority:** P1
**Risk:** High

---

# 11. Non-Functional / Quality Considerations

The following quality considerations are included within the testing approach where applicable.

### 11.1 Usability

The application's major user flows should be understandable and usable.

### 11.2 Compatibility

The application should be considered across relevant browser/environment combinations used during testing.

### 11.3 Responsive Behavior

Relevant screens should be reviewed for expected behavior across different viewport sizes where applicable.

### 11.4 Accessibility Awareness

Basic accessibility-related observations may be considered during exploratory testing.

> These considerations should only be reported as tested results when they have actually been executed and observed.

---

# 12. Out-of-Scope Requirements

The following areas are not covered by the current project:

| Area                           | Status       |
| ------------------------------ | ------------ |
| API Testing                    | Out of Scope |
| Database Testing               | Out of Scope |
| Performance / Load Testing     | Out of Scope |
| Penetration / Security Testing | Out of Scope |
| Production Deployment Testing  | Out of Scope |
| Real Payment Processing        | Out of Scope |
| Unauthorized Data Collection   | Out of Scope |

---

# 13. Requirement Priority Model

Requirements are categorized according to business and user impact.

| Priority | Meaning  | Example                           |
| -------- | -------- | --------------------------------- |
| P0       | Critical | Login, checkout, order completion |
| P1       | High     | Product/cart validation           |
| P2       | Medium   | Secondary navigation              |
| P3       | Low      | Lower-risk enhancements           |

Priority may be adjusted during actual project execution based on observed risk, business impact, or requirement changes.

---

# 14. Requirement-to-Test Traceability

Each requirement should eventually be mapped to one or more test cases in the Requirements Traceability Matrix.

Example:

| Requirement ID   | Requirement          | Test Case ID    |
| ---------------- | -------------------- | --------------- |
| REQ-LOGIN-001    | Valid Login          | TC-LOGIN-001    |
| REQ-LOGIN-002    | Invalid Credentials  | TC-LOGIN-002    |
| REQ-INV-001      | Product Listing      | TC-INV-001      |
| REQ-INV-003      | Add Product to Cart  | TC-INV-003      |
| REQ-CART-001     | View Cart            | TC-CART-001     |
| REQ-CART-007     | Proceed to Checkout  | TC-CART-007     |
| REQ-CHECKOUT-001 | Checkout Information | TC-CHECKOUT-001 |
| REQ-ORDER-004    | Order Total          | TC-ORDER-004    |
| REQ-COMPLETE-001 | Complete Order       | TC-COMPLETE-001 |
| REQ-LOGOUT-001   | Logout               | TC-LOGOUT-001   |

The complete mapping will be maintained in:

`docs/08_rtm.md`

---

# 15. Requirements Coverage Goal

The testing process aims to provide coverage across:

* Authentication
* Product discovery
* Product selection
* Product management
* Cart management
* Checkout
* Order review
* Order completion
* Logout
* Positive scenarios
* Negative scenarios
* Boundary conditions
* State transitions
* Business-critical workflows

Coverage should be measured using actual test execution data rather than assumed or fabricated results.

---

# 16. Requirement Change Management

If requirements change during the testing lifecycle:

1. Identify the changed requirement.
2. Update the requirement ID/documentation where necessary.
3. Analyze affected test scenarios.
4. Analyze affected test cases.
5. Update the RTM.
6. Execute impacted tests.
7. Perform regression testing where required.
8. Document the change and its testing impact.

---

# 17. Requirements Summary

The SauceDemo requirements are centered around the complete e-commerce customer journey.

The highest-priority requirements are those associated with:

```text
Authentication
     ↓
Product Selection
     ↓
Cart Management
     ↓
Checkout
     ↓
Order Completion
```

These areas receive increased testing attention because failure in a critical step can prevent successful completion of the customer's primary shopping workflow.

This requirements document serves as the baseline for subsequent **test planning, test strategy, scenario design, test case development, traceability, execution, regression, and final test reporting**.
