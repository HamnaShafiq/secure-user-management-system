# User Management System - Cybersecurity Internship Project

## Overview

This project is part of a **Cybersecurity Internship** task, where the goal is to assess and strengthen the security of a **User Management System** web application. The task is divided into three phases: 

- **Week 1: Security Assessment**
  - Perform vulnerability assessment to identify common issues like XSS and SQL injection.
  - Apply basic security measures to fix the vulnerabilities.
  - Document findings and areas for improvement.
  
- **Week 2: Implementing Security Measures**
  - Implement input sanitization, password hashing, token-based authentication, and secure HTTP headers.
  
- **Week 3: Advanced Security and Final Reporting**
  - Perform penetration testing.
  - Set up logging for security purposes.
  - Create a checklist for security best practices and submit a final report.

---

## Week 1 - Security Assessment

### 1. **Security Assessment Overview**

   - **Explore the Application:**
     - Set up and explore the **User Management System** locally.
     - Investigated user actions like signing up, logging in, and viewing profiles.

   - **Vulnerability Assessment:**
     - **Tools Used:**
       - **OWASP ZAP**: Automated vulnerability scanning for common security issues.
       - **Browser Developer Tools**: Manual testing for XSS and input sanitization.
     - **Vulnerabilities Found:**
       - **Cross-Site Scripting (XSS)**: Detected in input fields.
       - **Weak Password Storage**: Passwords stored in plain text.
       - **Missing Content Security Policy (CSP)**: Application lacks a defined CSP header.
       - **SQL Injection**: Test with SQL injection payloads was successful in login fields.

   - **Document Findings:**
     - Documented vulnerabilities and provided recommendations to fix them.

---

## Key Vulnerabilities Identified

| **Vulnerability**               | **Description**                                                  | **Affected URL**               | **Recommendation**                                                                 |
|----------------------------------|------------------------------------------------------------------|--------------------------------|-----------------------------------------------------------------------------------|
| **Cross-Site Scripting (XSS)**   | Input fields were vulnerable to script injection.               | `/signup`, `/login`            | Sanitize user input to prevent script execution.                                   |
| **Weak Password Storage**       | Passwords were stored in plain text, which is insecure.         | `/signup`, `/login`            | Implement bcrypt to hash passwords before storing them in the database.           |
| **Missing Content Security Policy (CSP)** | No CSP header was defined, allowing for content to be loaded from untrusted sources. | `http://localhost:3000/sitemap.xml` | Set up a strong CSP to limit where resources can be loaded from.                  |
| **SQL Injection**               | SQL injection attempt was successful when testing login.         | `/login`                       | Use parameterized queries to prevent SQL injection vulnerabilities.               |

---

## Technologies Used

- **Backend**:
  - **Node.js**: JavaScript runtime used to build the server.
  - **Express.js**: Web framework to handle HTTP requests.
  - **MongoDB**: Database for storing user data.
  
- **Security Tools**:
  - **OWASP ZAP**: Automated vulnerability scanner.
  - **Helmet.js**: Secures HTTP headers.
  - **bcrypt**: Password hashing library.
  - **JSON Web Token (JWT)**: Token-based authentication.
  
- **Frontend**:
  - **React.js**: Frontend library for building the user interface.

---

## Setup Instructions

Follow these steps to get the application running on your local machine:

### 1. Clone the repository

```bash
git clone https://github.com/your-username/user-management-system.git
cd user-management-system
