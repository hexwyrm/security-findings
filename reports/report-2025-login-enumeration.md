# Case Study: Information Disclosure in Login Flow

**Researcher:** hexwyrm  
**Date:** December 2025  

---

## Summary
During testing of a SaaS login system, I identified an information disclosure issue.  
The API endpoint responsible for handling login options revealed whether an email domain was classified as "enterprise" or "non-enterprise."  

By toggling a request parameter and observing response differences, it was possible to enumerate which domains were eligible for enterprise login flows.  
This type of vulnerability can be leveraged for reconnaissance and targeted phishing campaigns.

---

## Activities Performed
- Configured a browser to route traffic through **BurpSuite** for interception.  
- Captured login requests during the authentication flow.  
- Modified request parameters to test how the system classified different email domains.  
- Compared responses between enterprise and non-enterprise domains.  
- Documented findings with screenshots and structured notes.  

---

## Impact
- Attackers could enumerate enterprise customers of the platform.  
- This information could be used to target organizations with phishing or social engineering attacks.  

---

## Suggested Mitigation
- Normalize error responses to avoid revealing domain classification.  
- Suppress domain-specific error messages in client-facing APIs.  

---

## Notes
- Testing was performed with disposable accounts and non-sensitive email addresses.  
- No production data was accessed or modified.  
- This report has been responsibly redacted for portfolio purposes.  

---

**Disclaimer:** This case study is for demonstration only. Sensitive business names, domains, and asset details have been removed.

