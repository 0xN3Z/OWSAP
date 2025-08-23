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


      


  - Horizontal privilege escalation  : نفس المستوى لكن يستغل بيانات/وظائف مستخدم تاني (user A → user B)
    **Horizontal privilege escalation can escalate into vertical privilege escalation.**

    
    **note  IDOR : هو Technique إنك تغيّري الـ ID أو أي parameter في الـ URL فتوصلي لحاجة مش مصرحالك بيها (Privilege).**

`https://insecure-website.com/myaccount?id=101   ← حسابي
https://insecure-website.com/myaccount?id=102   ← حساب مستخدم تاني
`
    2. 





