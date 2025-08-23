# Broken Authentication & Access Control
## what is the broken access control ?
### Broken access control is a critical security vulnerability that allows unauthorized users to access, modify, or delete data they should not have access to. 
### 94% of applications were tested for some form of broken access control 
### This vulnerability is considered one of the most critical web application security risks.
###  It occurs when an application fails to properly enforce access controls, allowing attackers to bypass authorization and perform tasks as if they were a legitimate user.
## types of access control
- mandatory access control (MAC)
-  Role Based Access Control (RBAC)
-  Discretionary access control (DAC)
-  Attribute-based access control (ABAC)
-  Break-glass access control
-  Rule-based access control
  ## types of broken access control
  1. Privilege escalation
  - Vertical Privilege Escalation : If a user can gain access to functionality that they are not permitted to access    ex : admin / robots.txt / The URL may be exposed in role-based JavaScript
    
    **Parameter-based access control methods**
    - A hidden field
    - A cookie
    - A preset query string parameter : The privilege is stored in a parameter in the URL
   
      Broken access control resulting from platform misconfiguration :
      1. Non-standard HTTP headers
        Frameworks (like IIS, Apache, etc.) allow additional headers such as:

          * **X-Original-URL**
          * **X-Rewrite-URL**
      2. HTTP method confusion
         * 


  - Horizontal privilege escalation  : نفس المستوى لكن يستغل بيانات/وظائف مستخدم تاني (user A → user B)
    **Horizontal privilege escalation can escalate into vertical privilege escalation.**

    
    **note  IDOR : هو Technique إنك تغيّري الـ ID أو أي parameter في الـ URL فتوصلي لحاجة مش مصرحالك بيها (Privilege).**

`https://insecure-website.com/myaccount?id=101   ← حسابي
https://insecure-website.com/myaccount?id=102   ← حساب مستخدم تاني`


**Access control vulnerabilities in multi-step processes** occur when a website enforces access checks on some steps but not all. For example, updating user details may involve:

1. Loading the form
2. Submitting changes
3. Confirming changes

If one step (e.g., confirmation) lacks access control, an attacker can skip the earlier controlled steps and directly send the final request, gaining unauthorized access.

**Referer-based Access Control**

Some websites rely on the **Referer header** to enforce access control. For example, access to `/admin/deleteUser` is only allowed if the request contains:

```
Referer: https://example.com/admin
```

However, this header can be easily manipulated using tools like Burp Suite or any HTTP editor. An attacker can forge the Referer and directly access sensitive admin functions without real authorization.



### **Location-based access control**

Some websites restrict access based on the user's **geographical location**.

* Example: **Banking apps** may block logins from outside the country.
* Example: **Media streaming services** like Netflix apply regional restrictions due to licensing laws.

  These controls can often be bypassed using:

* **VPNs** (e.g., connecting from another country).
* **Web proxies** to mask the IP.
* Manipulating **client-side geolocation** settings in the browser/device.

---

### **How to prevent access control vulnerabilities**

To prevent such issues, websites should apply a **defense-in-depth** strategy:

1. **Never rely on obfuscation alone**.

   * Example: Hiding the `/admin` URL is not real protection.

2. **Deny access by default** unless the resource is truly public.

   * Example: A banking transaction API should reject requests unless the user is authorized.

3. **Use a single, centralized mechanism** for access control.

   * Example: Instead of custom checks in each page, use one consistent authorization layer.

4. **Require developers to explicitly declare access rules in code**, with default = deny.

   * Example: A developer must define who can call `/deleteUser`, otherwise access is blocked.

5. **Audit and test access controls regularly**.

   * Example: Penetration testing and automated security scans to catch flaws.







