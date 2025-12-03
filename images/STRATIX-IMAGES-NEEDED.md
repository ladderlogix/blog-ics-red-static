# Images Needed for Stratix 5400 Security Research Blog Post

The Stratix 5400 blog post requires the following screenshots/images:

## Device & Setup Images

### 1. stratix-5400-device.png
**Description**: Photo of the Cisco Stratix 5400 switch
**Content**: Physical device showing model number, ports, and industrial design
**Alternative**: Stock photo from Cisco/Rockwell documentation

### 2. stratix-testing-setup.png
**Description**: Lab environment showing testing setup
**Content**: Network diagram or photo showing switch connected to test equipment
**Could show**: Switch, laptop, network cables, test environment

## Vulnerability Discovery Images

### 3. stratix-rce-endpoint.png
**Description**: Code showing the RCE endpoint in web interface
**Content**: Browser developer tools or text editor showing wrapperXhrPost JavaScript function
**Highlight**: The `url: "%24a%0A"` line and command parameter

### 4. stratix-rce-success.png
**Description**: Terminal showing successful RCE execution
**Content**: Screenshot of HTTP request/response or Python script output
**Should show**:
- POST request to /%24a%0A endpoint
- Command being sent (e.g., "show version")
- Device response with output
- Success confirmation

### 5. stratix-hash-exposure.png
**Description**: Browser showing password hash in page source
**Content**: Browser with "View Page Source" open
**Should show**:
- URL: /useraccounts.shtml
- HTML source code
- <textarea id="USER_SUMMARY"> element
- Admin password hash visible: $1$P4Bi$...
- Highlight the hash with red box or arrow

### 6. stratix-hashcat-cracking.png
**Description**: Hashcat terminal showing password being cracked
**Content**: Terminal running Hashcat
**Should show**:
- Command: `hashcat -m 500 -a 0 hash.txt rockyou.txt`
- Hash rate (e.g., "10.5 GH/s")
- Cracked password: "Stephen13"
- Time elapsed
- Status: Cracked

## Attack Chain & Impact Images

### 7. stratix-attack-chain.png
**Description**: Visual diagram of the complete attack chain
**Content**: Flow diagram showing attack progression
**Stages to show**:
1. Initial Access (password spray)
2. Authentication (weak password)
3. RCE Exploitation (command execution)
4. Persistence (backdoor creation)
5. Lateral Movement (ICS compromise)

**Tool suggestions**: Draw.io, Lucidchart, or hand-drawn diagram

### 8. stratix-industrial-impact.png
**Description**: Diagram showing impact on industrial systems
**Content**: Network topology showing switch connecting ICS devices
**Could show**:
- Industrial switch in center
- Connected devices: PLCs, HMIs, SCADA servers
- Red arrows/highlights showing compromise propagation
- Impact zones labeled

### 9. stratix-config-hardening.png
**Description**: Terminal showing security configuration commands
**Content**: SSH session applying security configs
**Commands to show**:
```
configure terminal
username admin privilege 15 algorithm-type scrypt secret [password]
access-list 99 permit 192.168.103.0 0.0.0.255
ip http access-class 99
no ip http server
write memory
```

### 10. stratix-disclosure-timeline.png
**Description**: Timeline for responsible disclosure
**Content**: Timeline diagram or table
**Phases**:
- Day 0: Discovery
- Day 1: Initial report to vendor
- Day 7: Vendor acknowledgment
- Day 90: Patch development
- Day 100: Coordinated disclosure
- Day 101: Public advisory & CVE

### 11. stratix-assessment-complete.png
**Description**: Final dashboard or summary showing all vulnerabilities
**Content**: Table or dashboard view
**Should show**:
- ✅ 7 vulnerabilities found
- 🔴 2 Critical (RCE, Privesc)
- 🟠 3 High (CSRF, XSS, etc.)
- 🟡 2 Medium
- CVSS scores for each
- Overall risk rating

## Optional Images

### 12. stratix-web-interface.png
**Description**: Screenshot of Device Manager login page
**Content**: Web interface at https://[IP]
**Shows**: Cisco branding, login form

### 13. stratix-user-accounts-page.png
**Description**: Screenshot of user accounts management page
**Content**: /useraccounts.shtml loaded in browser
**Shows**: User interface with admin functionality

## How to Create These Images

1. **Screenshots**: Use scrot, flameshot, or built-in screenshot tools
2. **Diagrams**: Use Draw.io, Lucidchart, or Mermaid diagrams
3. **Terminal outputs**: Can be recreated or sanitized from actual testing
4. **Stock photos**: Cisco/Rockwell product pages for device images

## Image Specifications

- **Format**: PNG (preferred) or JPG
- **Resolution**: Minimum 1200px wide for full-width images
- **DPI**: 72-150 dpi (web resolution)
- **File size**: Keep under 500KB each
- **Naming**: Use exact filenames listed above

## Sanitization Reminders

- ❌ Remove real IP addresses (use 192.168.103.143 or sanitize)
- ❌ Remove real passwords (already redacted in examples)
- ❌ Remove serial numbers and MAC addresses
- ✅ OK to show firmware versions (15.2(8)E6)
- ✅ OK to show example commands and responses

## Placement in Post

Images are already referenced in the blog post markdown at:
- Line 17: stratix-5400-device.png
- Line 51: stratix-testing-setup.png
- Line 93: stratix-rce-endpoint.png
- Line 133: stratix-rce-success.png
- Line 182: stratix-hash-exposure.png
- Line 227: stratix-hashcat-cracking.png
- Line 287: stratix-attack-chain.png
- Line 502: stratix-industrial-impact.png
- Line 596: stratix-config-hardening.png
- Line 738: stratix-disclosure-timeline.png
- Line 860: stratix-assessment-complete.png

Simply add the images to `/static/images/` and rebuild Hugo to see them in the post.
