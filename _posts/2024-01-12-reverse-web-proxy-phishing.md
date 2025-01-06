---
# title: "EVILGINX : Reverse web proxy tool "
# categories:
# - Phishing
# - Evilginx
# tags:
# - Phishing
# - Evilginx
toc: true
---

# EVILGINX : Reverse web proxy tool

[Evilginx](https://github.com/kgretzky/evilginx2) is a man in the middle framework used for phishing login credentials along with session cookies, which in turn allows to bypas 2-factor authentication.

It is a custom version of nginx HTTP Server (a web proxy server) acting as a reverse proxy to phish and capture the cookie and bypass 2-factor auth with the real legitimate website but with a different domain pointing to our webserver

I used aws EC2 insatnce to setup my webserver with Ubuntu free tier setted up the security features to ssh my local machine and http/s and DNS from anywhere in the world and took a domain from    hostinger and change its name server configuration to aws Route 53 and pointed the domain to my webserver's public ip.

These above configuration steps are necessory to run evilginx then run as described in the documentaion like install go on your aws machine as it is a standalone application rewritten in Go, the evilginx v3.0.0 --> make it and then in build directory you will have evilginx executable file.
```bash
sudo ./build/evilginx -p ./phishlets/ 
```
specify the phishlets in the phishlets directory, it is also an important part to craft your phishlets very nicely so that it uses all the domains of the website credentials to be phished.

examples of phishlets can be found on github...