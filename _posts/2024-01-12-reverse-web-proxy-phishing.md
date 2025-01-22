---
title: "EVILGINX: Advanced Reverse Web Proxy for Security Testing"
categories:
  - Security Testing
  - Web Security
tags:
  - Evilginx
  - Penetration Testing
  - Web Proxy
toc: true
---

# EVILGINX: Advanced Reverse Web Proxy for Security Testing

## Introduction

[Evilginx](https://github.com/kgretzky/evilginx2) is a sophisticated security testing framework that operates as a man-in-the-middle (MITM) proxy. It's primarily used by security professionals to test the resilience of authentication systems, particularly those implementing 2-factor authentication (2FA).

## How It Works

Evilginx functions as a customized version of the nginx HTTP Server, acting as a reverse proxy between the user and the target website. Its key capabilities include:

- Intercepting login credentials
- Capturing session cookies
- Testing 2FA bypass scenarios
- Proxying traffic through legitimate domains

## Setup Requirements

### Infrastructure Prerequisites

1. **Cloud Server**
   - AWS EC2 instance (Ubuntu free tier recommended)
   - Properly configured security groups allowing:
     - SSH access from your IP
     - HTTP/HTTPS (ports 80/443) from anywhere
     - DNS traffic (port 53)

2. **Domain Configuration**
   - Registered domain (e.g., from Hostinger)
   - DNS configuration using AWS Route 53
   - Domain pointing to EC2 instance's public IP

### Installation Steps

1. **Install Go**
   ```bash
   sudo apt update
   sudo apt install golang-go
   ```

2. **Install Evilginx**
   ```bash
   git clone https://github.com/kgretzky/evilginx2
   cd evilginx2
   make
   ```

3. **Running the Tool**
   ```bash
   sudo ./build/evilginx -p ./phishlets/
   ```

## Phishlet Configuration

Phishlets are configuration files that define how Evilginx should interact with specific target websites. Key considerations for phishlet creation:

- Must include all relevant domain configurations
- Proper cookie handling setup
- Correct routing rules
- SSL/TLS certificate configuration

You can find example phishlets in the [official repository](https://github.com/kgretzky/evilginx2/tree/master/phishlets) or community contributions.

## Legal and Ethical Considerations

**Important:** This tool should only be used:
- In controlled testing environments
- With explicit permission
- For security research and assessment
- In compliance with local laws and regulations

## References

- [Official Evilginx Documentation](https://github.com/kgretzky/evilginx2/wiki)
- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/)
- [Route 53 Documentation](https://docs.aws.amazon.com/route53/)