# Postman API Collections

This folder contains Postman collections created as part of the **Czechitas Digital Academy – Testing**.
The collections focus on **API testing fundamentals**, including authentication, positive and negative scenarios, assertions, and working with variables.

---

## 📁 Collections overview

### 1️⃣ Czechitas_DA_application.json  
**API – Get user details**

**Endpoint tested:**  
`GET /users/current`

**Purpose:**  
Verify that an authenticated active user can retrieve their own profile data via API and that the API behaves correctly for invalid scenarios.

**What is covered:**
- ✅ Happy path for all user roles (parent, master, admin)
- 🔐 Bearer token authentication
- 📦 Response body validation using **JSON Schema**
- 🚫 Invalid HTTP methods (POST, PUT, PATCH, DELETE → 405)
- ❌ Missing token → 401 Unauthenticated
- 🚷 Blocked user access (4xx response)
- 🗑️ Deleted user access → 401

**Assertions include:**
- HTTP status codes
- Required response fields (`id`, `name`, `email`, `role`)
- Data types and formats (RFC3339 date-time)
- Business rules (e.g. `is_blocked = false`)
- Role validation using enum values

**Techniques used:**
- Postman test scripts (JavaScript)
- JSON Schema validation
- Environment / collection variables
- Positive & negative test scenarios

---

### 2️⃣ TotallyVoluntaryHomeWork.json  
**End-to-end API workflow testing**

**API documentation:**  
https://praha.czechibank.ostrava.digital/api/v1/docs/page

**Purpose:**  
End-to-end testing of a simple banking workflow using API only, including user creation, account management, and transactions.

**Workflow covered:**
1. 👤 Create a new user  
   - Validate status code `201`
   - `emailVerified = false`
   - `image = null`
   - Store `apiKey` and `email` into collection variables

2. 🏦 Create a new bank account  
   - Validate status code `201`
   - `isActive = true`
   - Verify account is linked to the created user (email check)

3. ✏️ Rename bank account (optional step)

4. 🔍 Retrieve bank account numbers

5. 💸 Create two transactions  
   - Transfer money between own accounts
   - Validate status code `201`

**Assertions include:**
- HTTP status codes
- Boolean field validation
- Cross-request data validation using variables
- Data consistency checks between requests

**Techniques used:**
- API key authentication (`X-API-Key`)
- Collection variables shared across requests
- Dynamic test data (`{{$randomEmail}}`, `{{$randomFullName}}`)
- End-to-end scenario testing

---

## 🛠 Tools & skills demonstrated
- Postman
- REST API testing
- JavaScript assertions
- Authentication (Bearer token, API key)
- Positive & negative testing
- End-to-end API workflows
- Working with variables and dynamic data

---

## ℹ️ Notes
These collections were created for learning and demonstration purposes as part of QA education and are intended to showcase API testing skills rather than production-ready test suites.
