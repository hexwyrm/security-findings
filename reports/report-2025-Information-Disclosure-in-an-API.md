# Case Study: Information Disclosure in Notion API

**Researcher:** hexwyrm  
**Date:** December 2025  

---

## Summary
During testing of an SaaS platform, I identified an information disclosure issue affecting multiple API endpoints.  
The `getPublicPageData` and `loadCachedPageChunkV2` endpoints leaked sensitive workspace and page metadata when queried with unauthorized `spaceId` and `blockId` values.  

Although full page content was not returned, the responses revealed workspace names, domains, and confirmation of private page existence.  
This type of vulnerability can be leveraged for reconnaissance, enumeration of private resources, and targeted social engineering campaigns.

---

## Activities Performed
- Configured a browser to route traffic through **BurpSuite** for interception.  
- Captured API requests while logged in as Account A (hexwyrm).  
- Identified key request parameters (`spaceId`, `blockId`, `page.id`) tied to workspace and page identifiers.  
- Substituted values from Account B’s private workspace into Account A’s captured requests.  
- Replayed modified requests in Burp Repeater.  
- Observed HTTP 200 OK responses containing unauthorized metadata.  
- Documented findings with four screenshots (original and modified requests/responses for both endpoints).  

---

## Impact
- Confirms existence of private pages and workspaces belonging to other accounts.  
- Leaks workspace names (e.g., *Brian’s Space*) and domains (e.g., *wild-trombone-d10*).  
- Enables attackers to enumerate page IDs and map organizational structures.  
- Provides reconnaissance data that could be chained with other vulnerabilities (predictable IDs, phishing, privilege escalation).  
- Expected secure behavior would be a 403 Unauthorized or 404 Not Found response.

---

## Suggested Mitigation
- Enforce strict access controls on `getPublicPageData` and `loadCachedPageChunkV2`.  
- Return 403 Unauthorized or 404 Not Found when a user queries a page they do not have access to.  
- Avoid returning workspace names, domains, or privacy settings for unauthorized requests.  
- Normalize API responses to prevent metadata leakage across endpoints.

---

## Notes
- Testing was performed with disposable accounts created for research purposes (Account A: hexwyrm@outlook.com, Account B: brianscottcasey1@outlook.com).  
- No production data was modified or accessed beyond metadata leakage.  
- This report has been responsibly redacted for portfolio purposes.  
- Screenshots and logs have been archived to demonstrate the unauthorized metadata exposure.  

---

**Disclaimer:** This case study is for demonstration only. Sensitive business names, domains, and asset details have been removed.
