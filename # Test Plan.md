# Test Plan

## Project Name
** Login Application**

**Test Plan ID:** TP-SLA-001  
**Version:** 1.0  
**Prepared By:** ABC Tester  
**Date:** 05-Aug-2026

---

# 1. Test Scope

## In Scope

The following functionalities will be tested:

### Functional Testing
- User Login
- Username Validation
- Password Validation
- Successful Login
- Invalid Login Attempts
- Logout Functionality
- Error Message Validation

### Input Validation
- Empty Username
- Empty Password
- Invalid Credentials
- Maximum and Minimum Password Length
- Special Character Handling

### Test Design Techniques
The following Black Box Test Design Techniques will be applied:

- Equivalence Partitioning (EP)
- Boundary Value Analysis (BVA)
- Error Guessing

### Testing Levels Covered
- Unit Testing
- Integration Testing
- System Testing
- User Acceptance Testing (UAT)

## Out of Scope

The following functionalities are excluded from this testing cycle:

- User Registration
- Forgot Password
- Password Change
- Admin Module
- Performance Testing
- Security Testing
- Mobile Application

---

# 2. Test Objectives

The objectives of testing are:

- Verify successful login using valid credentials.
- Ensure invalid users cannot access the application.
- Validate username and password input fields.
- Verify proper error messages for invalid inputs.
- Verify logout functionality.
- Ensure application behaves correctly under normal and invalid conditions.
- Detect defects before deployment.

---

# 3. Assumptions

The following assumptions are considered during testing:

- Software requirements are finalized and approved.
- Login module has been completely developed.
- Test environment is stable.
- Test database contains valid user accounts.
- Testers have access to all required resources.
- No major requirement changes occur during testing.

---

# 4. Risk Analysis

| Risk | Impact | Mitigation |
|------|--------|------------|
| Delay in software delivery | High | Adjust testing schedule |
| Requirement changes | High | Update test cases and perform regression testing |
| Test environment unavailable | Medium | Maintain backup environment |
| Browser compatibility issues | Medium | Test on multiple browsers |
| Incorrect test data | Medium | Prepare verified test datasets |
| Incomplete software build | High | Perform Smoke Testing before execution |

---

# 5. Test Design

## Test Design Techniques

### Equivalence Partitioning (EP)

The following input classes will be tested:

- Valid Username
- Invalid Username
- Valid Password
- Invalid Password
- Empty Username
- Empty Password

### Boundary Value Analysis (BVA)

Boundary conditions include:

- Minimum password length
- Maximum password length
- Username character limits

Example:

- Password length = 7 (Invalid)
- Password length = 8 (Valid)
- Password length = 9 (Valid)

### Error Guessing

Additional scenarios based on tester experience:

- SQL Injection attempts
- Special characters in username
- Very long input strings
- Copy-Paste into password field
- Multiple rapid login attempts
- Browser Refresh during login

### Sample Test Scenarios

- Login with valid username and password.
- Login with incorrect password.
- Login with empty username.
- Login with empty password.
- Login with invalid username.
- Logout after successful login.

---
---

# 5.1 Test Cases

The following high-level test cases will be executed during the testing phase.

| Test Case ID | Test Scenario | Test Data | Expected Output | Priority |
|--------------|---------------|-----------|-----------------|----------|
| TC-001 | Login with valid username and password | Valid Username, Valid Password | User is successfully logged in and redirected to Dashboard | High |
| TC-002 | Login with invalid password | Valid Username, Invalid Password | Error message "Invalid Username or Password" displayed | High |
| TC-003 | Login with invalid username | Invalid Username, Valid Password | Error message displayed | High |
| TC-004 | Login with both username and password invalid | Invalid Username, Invalid Password | Error message displayed | High |
| TC-005 | Login with empty username | Blank Username | Validation message "Username is required" | High |
| TC-006 | Login with empty password | Blank Password | Validation message "Password is required" | High |
| TC-007 | Login with both fields empty | Blank Username and Password | Validation messages displayed for both fields | High |
| TC-008 | Password length below minimum limit | Password with 7 characters | Validation error displayed | Medium |
| TC-009 | Password at minimum valid length | Password with 8 characters | Login processed normally | Medium |
| TC-010 | Username exceeds maximum length | Username > Maximum Limit | Validation error displayed | Medium |
| TC-011 | Password exceeds maximum length | Password > Maximum Limit | Validation error displayed | Medium |
| TC-012 | Login using special characters in username | @#$%^ | Validation/Error message displayed | Medium |
| TC-013 | SQL Injection attempt | `' OR '1'='1` | Login denied and input safely handled | High |
| TC-014 | Logout after successful login | Logged-in User | User is logged out and redirected to Login Page | High |
| TC-015 | Access Dashboard without login | Direct Dashboard URL | Redirect to Login Page | High |

---

# 5.2 Expected Results Summary

| Module | Expected Behaviour |
|--------|--------------------|
| Login | Valid users should be authenticated successfully. |
| Authentication | Invalid credentials should never grant access. |
| Input Validation | Mandatory fields should display validation messages. |
| Session Management | Session should be created after successful login. |
| Logout | Session should be terminated and redirected to Login page. |
| Authorization | Unauthorized users should not access protected pages. |
| Error Handling | Appropriate error messages should be displayed without exposing system details. |

---

# 5.3 Test Coverage Matrix

| Requirement ID | Requirement | Test Cases |
|----------------|-------------|------------|
| RQ-001 | User Login | TC-001 to TC-013 |
| RQ-002 | Input Validation | TC-005 to TC-012 |
| RQ-003 | Authentication | TC-001 to TC-004, TC-013 |
| RQ-004 | Session Management | TC-001, TC-014 |
| RQ-005 | Authorization | TC-015 |

---

# 5.4 Test Design Coverage

| Technique | Test Cases Covered |
|-----------|-------------------|
| Equivalence Partitioning | TC-001, TC-002, TC-003, TC-004 |
| Boundary Value Analysis | TC-008, TC-009, TC-010, TC-011 |
| Error Guessing | TC-012, TC-013, TC-015 |
| Positive Testing | TC-001, TC-009, TC-014 |
| Negative Testing | TC-002 to TC-008, TC-010 to TC-013, TC-015 |

# 6. Roles & Responsibilities

| Role | Responsibility |
|------|----------------|
| Project Manager | Approve Test Plan and monitor project |
| Test Lead | Prepare Test Plan and review testing progress |
| Tester | Design, execute, and document test cases |
| Developer | Fix reported defects |
| Client/User | Perform User Acceptance Testing |

---

# 7. Test Schedule & Resources

## Schedule

| Activity | Duration |
|-----------|----------|
| Test Planning | 1 Day |
| Test Case Design | 2 Days |
| Test Data Preparation | 1 Day |
| Test Execution | 3 Days |
| Bug Fixing | 2 Days |
| Regression Testing | 1 Day |
| UAT | 1 Day |

## Resources

### Hardware

- Laptop/Desktop
- Minimum 4 GB RAM
- Internet Connection

### Software

- Windows 11
- Google Chrome
- Microsoft Edge
- MySQL Database

---

# 8. Test Data Management

The following categories of test data will be maintained:

## Valid Test Data

| Username | Password |
|----------|----------|
| student01 | pass12345 |

## Invalid Test Data

| Username | Password |
|----------|----------|
| invalidUser | pass12345 |
| student01 | wrongPass |

## Boundary Test Data

| Password Length | Expected |
|-----------------|----------|
| 7 Characters | Invalid |
| 8 Characters | Valid |
| 20 Characters | Valid |

## Special Test Data

- Blank Username
- Blank Password
- Special Characters
- Long Strings
- SQL Injection Strings

Test data will be reset before every execution cycle.

---

# 9. Test Environment

### Hardware

- Intel i5 Processor
- 4 GB RAM

### Software

- Windows 11
- Chrome Latest Version
- Microsoft Edge
- MySQL Server

### Application Build

- Version 1.0

---

# 10. Communication Approach

- Daily status updates among testing team members.
- Weekly review meeting with Project Manager.
- Critical defects reported immediately.
- Defects tracked using JIRA.
- Final Test Summary Report shared after completion.

---

# 11. Test Tools

| Tool | Purpose |
|------|---------|
| Microsoft Excel | Test Cases and Reports |
| JIRA | Defect Tracking |
| Selenium | Automation Testing |
| MySQL | Test Database |
| Chrome DevTools | Browser Debugging |

---

# Approval

| Name | Designation | Signature |
|------|-------------|-----------|
| Project Manager | Project Manager | __________ |
| Test Lead | QA Lead | __________ |
| Client | Customer | __________ |

---

