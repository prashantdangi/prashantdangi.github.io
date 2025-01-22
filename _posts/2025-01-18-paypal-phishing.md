---
title: PayPal Phishing with PayPal URL 
excerpt: Attackers using sophisticated attacks to bypass login security

categories: Phishing
---

# PayPal Phishing with Paypal URL

Fortinet CISO received a mail requesting an invoice amount to be paid, with paypal domain **paypal.com**

![](/assets/images/paypal-phishing.jpeg)

This attack involves legitimate paypal URL. According to the CISO, this attack is so clever and sophisticated that gets past PayPal's
phishing detection policy.

# This is not tagging of url to text but reverse web proxy phishing

This attack starts with an authentic email sent from *service@paypal.com* requsting money for some invoice. Exeperienced internet
users may be fooled by the email's appearance and authenticity of email with legitimate PayPal login URL.

The Pay Now button at the bottom is genuine looking redirecting to paypal's website.

It might be using reverse web Proxy phishing. With the help of tools like
[Evilginx](https://github.com/kgretzky/evilginx2)

Tools like [Evilginx](https://github.com/kgretzky/evilginx2) uses phishlets to get to legitimate websites and phishing domain lures
to get the credentials and cookies of the user to redirect to legit website and intercepting the traffic in between.

# *BUT* how did he got to know 

When he saw that it was sent to *Billingdepartments1[@]gkjyryfjy876.onmicrosoft.com* and if he might login using his credentials all 
his credentials and cookies might be gone.

![](/assets/images/fig04.jpeg)

## About the email

The attackers have registered a MS365 test domain, Which is free for three months, and then a distribution list containing the victim emails *.onmicrosoft.com*




Reference for the post: [Phish-free PayPal Phishing](https://www.fortinet.com/blog/threat-research/phish-free-paypal-phishing)