## What is BAC?

**BAC (Broken Access Control)** is a security vulnerability that occurs when an application fails to properly enforce restrictions on what authenticated or unauthenticated users are allowed to do.  
It allows attackers to **access unauthorized data, functions, or resources**, often by manipulating URLs, parameters, or user roles.

Broken Access Control is one of the **OWASP Top 10** most critical web application security risks.

---

## Horizontal vs Vertical Broken Access Control

| Feature              | Horizontal BAC                                                                          | Vertical BAC                                                        |
| -------------------- | --------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| Definition           | Occurs when a user accesses resources of **another user with the same privilege level** | Occurs when a user accesses resources of **higher privilege roles** |
| Privilege Level      | Same role                                                                               | Different (higher) role                                             |
| Example Scenario     | User A views or modifies User B’s account details                                       | A normal user accesses admin-only pages                             |
| Common Attack Method | Changing user IDs in URLs or parameters                                                 | Accessing restricted endpoints directly                             |
| Example              | `/profile?user_id=102` → `/profile?user_id=103`                                         | `/admin/dashboard` accessed by a normal user                        |
| Impact               | Data leakage, account takeover                                                          | Full system compromise, privilege escalation                        |
| Difficulty to Detect | Medium                                                                                  | High                                                                |
| OWASP Category       | Broken Access Control                                                                   | Broken Access Control                                               |


---

## Why BAC is Dangerous

- Exposes sensitive user or system data  
- Allows unauthorized actions  
- Leads to privilege escalation  
- Can result in full application compromise  

---

## How to Prevent BAC

- Enforce **server-side access control**
- Use **role-based access control (RBAC)**
- Validate user permissions on every request
- Avoid trusting client-side checks
- Implement proper logging and monitoring

---
