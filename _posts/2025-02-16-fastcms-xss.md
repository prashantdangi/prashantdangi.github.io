---
title: FastCMS Template Menu menu cross site scripting  
excerpt: XSS in FastCMS - CVE-2025-1332
categories: CVE XSS
---

# Overview
## FastCMS (>=0.1.5) Template Menu menu cross site scripting

A vulnerability was found in **FastCMS up to 0.1.5** and classified as **problematic**. This issue affects some unknown processing of the file ```/fastcms.html#/template/menu``` of the component Template Menu. The manipulation leads to cross site scripting. The identification of this vulnerability is **CVE-2025-1332**. The attack may be initiated remotely. Furthermore, there is an exploit available. This product does not use versioning. This is why information about affected and unaffected releases are unavailable.

**FastCMS Website**

~~fastcms.dev~~\
~~fastcms.net~~\
[https://www.xjd2020.com/](https://www.xjd2020.com/){:target="_blank"}

**FastCMS Repository**

~~https://github.com/fastcms/webpack-config~~\
[https://gitee.com/dianbuapp_admin/fastcms](https://gitee.com/dianbuapp_admin/fastcms){:target="_blank"}



# Details 

## CVE-2025-1332

There is a storage type XSS in the FastCMS background template menu location. The manipulation with an unknown input leads to a cross site scripting vulnerability. The product incorrectly neutralizes user-controllable input before it is placed in output that is used as a web page that is served to other users. As an impact it is known to affect **integrity**. The vulnerability is named CVE-2025-1332.

![1](/assets/images/gitee1.png)

the homepage is automatically triggered

![2](/assets/images/gitee2.png)

After construction, you can get the token

![3](/assets/images/Gitee3.png)


The attack can be initiated remotely. Additional levels of successful authentication are required for exploitation. Successful exploitation requires user interaction by the victim. Technical details and also a public exploit are known. This vulnerability is assigned to [T1059.007](https://attack.mitre.org/techniques/T1059/007/){:target="_blank"} by the MITRE ATT&CK project.



Source: [Gitee](https://gitee.com/xjd2020/fastcms/issues/IBKJ1W){:target="_blank"}, [Vuldb](https://vuldb.com/?id.295942){:target="_blank"}