# information disclosure (Information leakage ) :
## ثغرة بسببها بتقدر تشوف بيانات حساسة للمستخدمين او الموقع

### impact : Depending on the leaked data it could lead to exposure of source code, PII, credentials, or even exploitation of other vulnerabilities such as RCE or SQL Injection



## mitigation : 
- حذف أي بيانات أو ملفات خاصة بمرحلة التطوير قبل رفع المشروع إلى بيئة الإنتاج (Production).
- التاكد من عدم وجود صلاحيات للمستخدمين للوصول لأي بيانات حساسة
- التأكد من تعطيل ال Debug Mode
- عمل صفحة خاصة باظهار الاخطاء وتكون خالية من اي بيانات برمجية
- افي الـ API responses إعادة البيانات المصرح بها بس وعدم الاعتماد على الـ UI لإخفاء البيانات
  ## examples
  - الوصول لل names of hidden directories عن طريق ال robots.txt
  -  الوصول لل source code عن طريق ال temporary backups
  -   من ال error messages الوصول لمعلومات مثل ال  operating system  اللي بيستضيف الويب سيرفر او الوصول لجداول الداتابيز
    ## why information desclosure vulnerabilities  arise ?
  - failure to remove internal content from public content
  -insecure configuration of the website and related technologies
  - flawed (خطأ) design and behavior of the application
    
## How to find and exploit information disclosure vulnerabilities?
### Visible Content
- error messages 
- comments in code
- Meta Tags & HTTP Headers : EX for HTTP Headers ( Server: Apache/2.4.41 (Ubuntu)
X-Powered-By: PHP/7.4.3 )
  Ex for Meta Tags (<meta name="generator", content="WordPress 6.2">)
 ### HTTP Responses
  - أدوات مثل Burp Suite أو OWASP ZAP ونشوف الـ HTTP headers أو response body
  -  الـ API responses أحيانا الـ backend بيرجع بيانات حساسة
 ### OSINT
  - GitHub leaks:  sensitive data لو البروجيكت اوبن سورس او الديفلوبر رافع الكود وفيه
  - [Wayback ] https://web.archive.org/
  -  Google Dorking و Shodan.


    


