# Defensive-Documentation
Preventing a zphisher phishing attack 

## Author 
** Agboola Temiloluwa**
Defensive Security Focus

---
## Project Overview 
This documentataion explains how i **identified, analyzed, and defended** against a phishing attack that was created using **zphisher**, a phishing framework commonly used for cybersecurity awareness and educational purposes. 
The goal of this project is to demonstrate **defensive security practices**
---
# 1. Understanding the Threat 
Zphisher is a social engineering toolkit that clones popular websites (e.g., facebook, instagram, Gmail) to trick users to entering their credentials. It works by:

-Generating a fake login page
-Hosting it locally or via tunneling services
-Capturing whatever victims type 

**keypoint** 
Zphisher  only succeeds if the victim enters credentials or interacts with the malicious link.
---
# 2. How the Attack was Attempted
During the exercise, a phishing link was generated using zphisher and was sent to me, trying to make the page look like a legitimate login  portal 
### Indicators of a Phishing Attempt:
- The URL did not match the official domain
- The site lacked **HTTPS**
- The page was hosted on an **IP address** or temporary tunnel
---
# 3. Defensive Measure Taken
Below are the exact steps i followed to detect and block the phishing attempt.

## 3.1 URL verification
I inspected the link and immediately noticed:
- Different domain structure
- No SSL certificate
- Suspicious redirect patterns
- Ip-based hosting (e.g http://192.168.x.x/login)
---

## 3.2 Browser Security   Indicators 
The browser displayed:
- "Connection Not Secure" warning
- Missing certificate details
- No padlock icon
  These are strong indicators of a fake website.
---
## 3.3 Network Analysis
I checked active connections using: Netstat -tunap 
I looked for suspicious ports, unknown IPs, or tunneling connections such as:
- ngrok
- Localhost.run
- Cloudflared
Nothing matched a legitimate service.
---
## 3.4 Link Origin Validation
I checked who sent the link and noticed:
- The message was unexpected
- The tone was urgent
- The link was shortened (risk of hiding malicious content)
This helped confirm it was likely phishing.
---

# Verification Tests
To further confirm that the page was malicious, I performed controlled checks.
### Test 1 - View Page Source
I checked the Page's HTML using: Right-click and view page source
Findings:
- No security headers
- Basic HTML templates
- Form actions pointing to suspicious URLs
---
### Test 2 - WHOIS lookup
The domain ownershp didn't match any legitimate organization.
---
### Test 3 - DNA Analysis
Returned mismatched or unverified IPs.
---

# 5. Defensive Recommendations
To prevent future attacks:
-Always verify URLs before logging in
-Never trust HTTP sites for credential input
Hover over links before clicking
-Avoid opening unexpected attachments or links
-Use browser plugins like HTTPS everywhere
Educate users about social engineering
---

## 6. Lessons Learned 
This exercise helped me understood:
- How phishing kits mimic login pages
- How attackers exploit human trust
- How to analyze tunneling-based phishing attempts
- The importance of verifying digital identity
- The role of user awareness in cybersecurity defense 

