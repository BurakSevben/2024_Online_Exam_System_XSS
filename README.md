# 2024_Online_Exam_System_XSS

+ **Exploit Title:** Online Exam System(2024) Cross-site Scripting
+ **Date:** 2024-07-01
+ **Exploit Author:** Burak Sevben
+ **Vendor Homepage:** https://code-projects.org/online-examination-system-in-php-with-source-code/
+ **Software Link:** https://download.code-projects.org/details/6e1e8221-95b6-40a5-aa4f-627b4ce3ff5c
+ **Version:** 1.0(2024)
+ **Tested on:** Windows 11 Home + PHP 8.2.12, Apache 2.4.58
+ **CVE:** Reported, waiting for CVE number

## Description:
Onlie Exam System is vulnerable to Cross-Site Scripting via the 'question' parameter at `http://localhost/exam/admin/quesadd.php`. Online Exam System is vulnerable to a cross-site scripting vulnerability because it fails to adequately sanitize user-supplied data. An attacker could exploit this issue to run arbitrary scripting code in the browser of an unsuspecting user in the context of the affected site. This could allow an attacker to steal cookie-based authentication credentials and launch other attacks.


## Proof of Concept:
+ Go to `http://localhost/exam/admin/quesadd.php`, then type the following payload in the 'Question' section `<video/src=x onerror=alert(document.cookie)>`
+ Then click  "Quest List" `(http://localhost/exam/admin/queslist.php)`, XSS will be triggered.
+ Also, in the student session, XSS will be triggered when a question with an XSS payload is reached.


# Admin Session
![Ekran görüntüsü 2024-01-12 025138](https://github.com/BurakSevben/2024_Online_Exam_System_XSS/assets/117217689/b8f8e8f6-97fc-4382-94dc-dcd5eb299720)

![Ekran görüntüsü 2024-01-12 025248](https://github.com/BurakSevben/2024_Online_Exam_System_XSS/assets/117217689/269a1622-ef68-4eba-ac96-6ff99b82e385)

![Ekran görüntüsü 2024-01-12 025311](https://github.com/BurakSevben/2024_Online_Exam_System_XSS/assets/117217689/6c1e589e-fc1b-4544-8092-8ac1317b0b1b)


# Student Session
![Ekran görüntüsü 2024-01-12 025450](https://github.com/BurakSevben/2024_Online_Exam_System_XSS/assets/117217689/c386ab3f-2fc6-42c2-a953-c7d1c479eb2e)
