# Case Study 4 — Employment Scam Attempt: Fake “Corgan Remote System Administrator” Recruitment

## Overview
This case study documents a fraudulent recruitment attempt impersonating **Corgan**, a well‑known architecture and design firm. The attacker used a spoofed hiring domain, falsified HR identity, and a generic questionnaire to simulate a legitimate hiring process. The objective was likely to harvest personal information or deliver malware through attachments.

This analysis demonstrates my ability to identify, document, and evaluate social‑engineering threats in a real‑world context.

---

## 1. Sanitized Conversation Thread

All personal information has been removed.  
The attacker’s messages are preserved exactly as received, with only my name and email redacted.

### Email #1 — Initial Contact

**From:** Andrew Greene `<andrew@corgancareers.com>`  
**To:** Me `<myemail@outlook.com>`  
**Subject:** Remote System Administrator  
**Date:** Fri, Jun 5, 2026 3:31 PM

```text
Good Morning,

Thank you for your interest in the Remote System Administrator position at CORGAN. After reviewing your background, we’d like to move forward by inviting you to an interview.

If you’re interested in continuing, please reply with Interested to confirm your availability. Once we hear from you, we’ll follow up with details about the online interview and next steps in the process.

The interview will be an opportunity to discuss the role, compensation, and what it’s like to work at CORGAN.

We look forward to connecting with you

Kind  Regards,

Andrew Greene
HR Department | Talent manager
CORGAN
Address: 401 N Houston St Ste 500, Dallas, TX, 75202
```

### Email #2 — My Reply

From: Me <myemail@outlook.com>  
Date: Fri, Jun 5, 2026 2:23 PM
```text

Good Afternoon Andrew,

I am Interested and available to continue in the process. I look forward to learning more about CORGAN and the Remote System Administrator role.

Thank you,
Me
```

### Email #3 — Scam Escalation

From: Andrew Greene <andrew@corgancareers.com>  
To: Me <myemail@outlook.com>  
Subject: Re: Remote System Administrator
Date: Sun, Jun 7, 2026 05:14:34 -0600
```text

Hello Me,

Thank you for your interest in the Remote System Administartor at  CORGAN. We’re pleased to learn more about your background and experience.

As the next step in our hiring process, we kindly ask you to complete a brief screening questionnaire. Please find the document attached and take a few moments to respond thoughtfully and in detail.

Your response will help us better understand your fit for the role and assist in moving forward with the selection process. If hired, you’ll be invited to participate in a comprehensive onboarding program designed to support a smooth transition into your new team.

Please note that we are reviewing applications promptly and would appreciate receiving your completed questionnaire as soon as possible.

Because this is an urgent hire for the company, the questionnaire replaces the interview process. The questions that would have been asked during the interview are now included in the questionnaire.

Also, the PDF file and Word doc contain the same information.

Lastly, The job description is attached to the questionnaire.

If you have any questions, feel free to reach out. We appreciate your time and look forward to your response.

Kind  Regards,

Andrew Greene
HR Department | Talent manager
CORGAN
Address: 401 N Houston St Ste 500, Dallas, TX, 75202
```

2. Red Flags Identified

Below are the indicators that confirmed this was a fraudulent employment scam.
A. Fake Domain Impersonation

The email originated from:

andrew@corgancareers.com

This domain is not owned by Corgan. Corgan’s legitimate domain is corgan.com.

Scammers frequently register lookalike domains such as:

    companynamecareers.com

    companynamejobs.com

    companyname-hr.com

This is a classic impersonation pattern.
B. First‑Name‑Only Recruiter Email

Corporate HR departments do not use first‑name‑only inboxes for recruiting.
This is typical of scam operations because it avoids identity verification and allows burner accounts.
C. Nonexistent Job Posting

A search of Corgan’s official applicant portal for “System Administrator” returned:

    “Sorry, no jobs were found that match your search criteria.”

This confirms the job does not exist in Corgan’s real system.
D. Interview Replaced With Questionnaire

The attacker claimed:

    “Because this is an urgent hire for the company, the questionnaire replaces the interview process.”

Legitimate companies do not eliminate interviews for a six‑figure technical role. Replacing the interview with a questionnaire is a strong social‑engineering red flag.
E. Suspicious Attachments

The attacker sent both a PDF and a Word document, emphasizing they contain the same information.

    Dual formats are often used to bypass filters.

    Word documents can contain malicious macros.

This is a common malware‑delivery tactic in job scams.
F. Generic, Non‑Corgan Questionnaire

The attached “Screening Questions” document:

    Contains no Corgan branding or job ID.

    Uses generic system administrator questions.

    Does not reference Corgan’s environment, tools, or architecture.

This strongly suggests it is a reusable scam template, not a legitimate internal document.
G. Unrealistic Salary

The job description listed a salary of $125,000 – $135,000 for a remote system administrator role, which is significantly higher than typical ranges for similar positions at comparable firms. Inflated salaries are often used to lure victims into compliance.
H. Typos and Formatting Errors

Notable issues include:

    Misspelling: “Administartor”

    Double spaces: “at  CORGAN”, “Kind  Regards”

    Inconsistent capitalization: “Lastly, The job description…”

While minor individually, combined with other indicators they reinforce the scam profile.
I. Urgency Pressure

The email repeatedly emphasized urgency:

    “We are reviewing applications promptly…”

    “Because this is an urgent hire…”

Creating artificial urgency is a classic social‑engineering technique to reduce critical thinking and push quick action.
3. Likely Objectives of the Scam

Based on the structure and content, the attacker likely intended to:

    Harvest personal information via the questionnaire (work history, contact details, possibly more in later steps).

    Deliver malware through the Word document attachment.

    Potentially escalate to:

        Fake “equipment purchase” or “check reimbursement” scams.

        Requests for identity documents (ID, SSN, banking details) under the guise of onboarding.

This aligns with modern employment scam playbooks.
4. Final Assessment

This communication is conclusively identified as a fraudulent employment scam involving:

    Domain impersonation

    Identity spoofing

    Fake job posting

    Social engineering

    Potential malware delivery

The attempt was detected early. No personal information was submitted, and no attachments were opened.
5. Recommended Defensive Actions

    Block the sender’s email address.

    Do not open or execute attached Word documents.

    Report the domain and emails to:

        Email provider abuse channels.

        Appropriate national reporting bodies (e.g., FTC, APWG).

    Document the incident (this case study) as part of ongoing security awareness and portfolio evidence.
