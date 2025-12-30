## Broken Access Control (BAC) – Common Scenarios & Examples

Below are the most common **Broken Access Control** scenarios you will encounter in real-world applications, along with simple examples to help you understand how attackers exploit them.

---

### 1. Unprotected Functionality – Guessable Path
Occurs when sensitive functionality is exposed via **predictable URLs** and lacks proper access checks.

**Examples:**
- `https://insecure-website.com/admin`
- `https://insecure-website.com/robots.txt`

*Attackers often discover these paths through manual guessing or by checking `robots.txt`.*

---

### 2. Unprotected Functionality – Unguessable Path
Even if the URL is **hard to guess**, access control must still be enforced server-side.

**Example:**
- `https://insecure-website.com/admin-s5yx0z`

*Security through obscurity is not security.*

---

### 3. User Role Controlled by Request Parameter
The application trusts **client-side parameters** to define user roles or privileges.

**Examples:**
- `https://insecure-website.com/login/home.jsp?admin=true`
- `https://insecure-website.com/login/home.jsp?role=1`

*Attackers can simply modify the parameter to gain admin access.*

---

### 4. Broken Access Control Due to Platform Misconfiguration
Access restrictions can be bypassed because of **incorrect server or framework configurations**.

**Examples:**
```text
#DENY: POST, /admin/deleteUser, managers
#POST / HTTP/1.1
X-Original-URL: /admin/deleteUser
```
