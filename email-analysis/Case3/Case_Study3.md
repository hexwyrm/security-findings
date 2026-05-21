# **Case Study: Suspicious LinkedIn “Recruiter” Outreach – Social Engineering Attempt (2026)**  
**Analyst:** Hexwyrm  
**Platform:** LinkedIn  
**Threat Type:** Recruitment‑style Social Engineering / Potential Equipment‑Reimbursement Scam  
**Date:** May 2026  

---

## **1. Initial Contact & Context**
A LinkedIn user with a background in **coffee commodities, sustainability, and global trade** sent a connection request. Within minutes of connecting, he initiated a conversation asking for career and salary details.

His profile summary (from the screenshot) shows:

- Senior Executive in **Coffee & Commodity Industry**  
- Sustainability, Producer Development, Strategic Partnerships  
- Based in Guatemala  
- **No cybersecurity, IT, recruiting, or U.S. federal/defense hiring background**

This mismatch sets the stage for the first red flag.

---

## **2. Transcript Review With Red‑Flag Annotations**

### **Message 1 (from him):**
> “Hi Brian, hope you're doing well? Great connection with you! I see you’re open to new opportunities—could you share the type of role you’re targeting, your salary expectations, and whether you’re aiming for entry, mid-level, senior, executive, or C-suite?”

#### **Red Flags:**
- **Red-Flag 1: Immediate probing for salary expectations.**  
  Legitimate recruiters do not ask for salary before presenting a real role.
- **Red-Flag 2: No identification of his role or employer.**  
  He never states whether he is a recruiter, consultant, or talent sourcer.
- **Red-Flag 3: Background mismatch.**  
  His profile is entirely unrelated to cybersecurity or U.S. tech recruiting.
- **Red-Flag 4: Generic, template‑like phrasing.**  
  Reads like a mass‑sent message, not a targeted outreach.

---

### **Message 2 (from me):**
> "Hi Miguel,
Thanks for reaching out. Before I share details about my background or compensation, could you clarify what specific role or opportunity you’re contacting me about? I want to be sure it aligns with my field and experience.
Best,
Brian"

### **Message 2 (from him):**
> “After looking around my network and given your preference for System Administration, Cyber Security, and Penetration Testing roles across the United States with immediate availability I wanted to share a few high-impact opportunities that stand out.”

#### **Red Flags:**
- **Red-Flag 5: Claims to have “looked around his network” despite having no industry overlap.**  
  A coffee‑industry executive does not have a cybersecurity hiring network.
- **Red-Flag 6: “Immediate availability” phrasing suggests automated scraping or AI generation.**  
  You never stated this to him.

---

### **Message 3 (from him):**
> "Hi Brian,

I hope you're having a productive week. After looking around my network and given your preference for System Administration, Cyber Security, and Penetration Testing roles across the United States with immediate availability  I wanted to share a few high-impact opportunities that stand out.

Below are 3 different roles that align with the direction you'd love to explore. Please take a close look and let me know if any align with what you're looking for.


1. Senior Cyber Security Analyst (Remote – US)

· Company: GuidePoint Security
· Role overview: A senior-level remote role leading threat detection, SIEM monitoring, incident response, and vulnerability management for Fortune 500 enterprise clients. You will also collaborate with red and blue teams to improve security posture and produce executive-level threat reports.
· Location type: Fully remote (US-based)
· Employment type: Full-time, immediate start
· Salary expectations: $135,000 – $165,000 per year + performance bonus + full benefits (health, 401k match, unlimited PTO)

2. Lead System Administrator (Hybrid – St. Louis, MO / Remote options)

· Company: Leidos (Defense & Intelligence Division)
· Role overview: A hybrid position responsible for architecting, deploying, and maintaining Windows/Linux server environments, virtualization (VMware), cloud infrastructure (AWS/Azure), and DoD-compliant security hardening. You will lead a small team of junior admins and coordinate with cybersecurity teams on STIG compliance.
· Location type: Hybrid (2 days on-site in St. Louis or remote negotiable for the right candidate)
· Employment type: Full-time, immediate start
· Salary expectations: $120,000 – $155,000 per year + sign-on bonus + annual incentive + full healthcare and 401k with matching

3. Senior Penetration Tester / Red Team Operator (On-site / Remote – US)

· Company: Trustwave (SpiderLabs)
· Role overview: A high-autonomy role conducting advanced penetration tests, red team exercises, social engineering campaigns, and physical security assessments for global enterprises and government agencies. You will author detailed exploit reports, present findings to C-level executives, and contribute to internal tool development.
· Location type: On-site (select US cities) or fully remote for senior candidates
· Employment type: Full-time, immediate start
· Salary expectations: $140,000 – $185,000 per year + performance-based bonuses + certification reimbursement + 100% remote equipment stipend


Let me know if any of these align with what you're looking for. I'm happy to share full job descriptions or facilitate a confidential introduction.

Best regards,"


---

#### **Role 1 – Senior Cyber Security Analyst (GuidePoint Security)**  
*Generic description, high salary range, no job ID, no link.*

##### **Red Flags:**
- **Red-Flag 7: No requisition number, job ID, or link to the posting.**  
  Real recruiters always include at least one.
- **Red-Flag 8: Description is generic and lacks technical depth.**  
  Reads like an AI‑generated summary of a typical cyber role.
- **Red-Flag 9: Salary range is inflated and broad.**  
  Suggests “too good to be true” bait.

---

#### **Role 2 – Lead System Administrator (Leidos)**  
*Hybrid role, high salary, “remote negotiable,” no clearance mentioned.*

##### **Red Flags:**
- **Red-Flag 10: No mention of clearance requirements.**  
  Leidos defense roles almost always require Secret/TS/SCI.
- **Red-Flag 11: “Remote negotiable for the right candidate” is unrealistic for DoD work.**  
  This is not how federal contractors operate.
- **Red-Flag 12: Again, no job ID or link.**
- **Red-Flag 13: No signature after the closing.**

---

#### **Role 3 – Senior Penetration Tester (Trustwave SpiderLabs)**  
*High salary, remote option, “100% equipment stipend.”*

##### **Red Flags:**
- **Red-Flag 14: “100% equipment stipend” is not real HR language.**  
  Legit companies say “equipment provided” or “$X stipend.”
- **Red-Flag 15: This phrasing mirrors classic reimbursement scams.**  
  (“Buy equipment, send receipt, we’ll reimburse you.”)
- **Red-Flag 16: No technical requirements listed (OSCP, exploit dev, tooling).**  
  SpiderLabs roles are extremely specific.

---

### **My Verification Message:**
I asked him to clarify his role and connection to the hiring teams.

### **His Response: Silence for 20–30+ minutes**  
Previously he responded within 5 minutes.

#### **Red Flags:**
- **Red-Flag 17: Scammers respond instantly until challenged.**  
  When asked for verification, they disappear.
- **Red-Flag 18: Legit recruiters welcome verification questions.**  
  Ghosting is a strong indicator of illegitimacy.

---

## **3. Why These Red Flags Matter**
Each red flag aligns with known patterns of:

- Lead‑generation scams  
- Résumé harvesting  
- Identity harvesting  
- Fake job funneling  
- Equipment‑purchase reimbursement scams  
- AI‑generated mass outreach  

The “100% stipend” line is especially telling — it mirrors the **Craigslist‑era scam** you correctly recognized:

> “Buy the equipment, send us the receipt, we’ll reimburse you.”  
> Then they send a fake check, ask for the difference back, and the check bounces.

This is a modern LinkedIn version of that same scam.

---

## **4. Consolidated Red‑Flag List**
- **Red-Flag 1:** Immediate salary probing  
- **Red-Flag 2:** No recruiter identity  
- **Red-Flag 3:** Background mismatch (coffee industry → cyber recruiting)  
- **Red-Flag 4:** Generic, template‑like outreach  
- **Red-Flag 5:** Claims of a “network” he clearly doesn’t have  
- **Red-Flag 6:** AI‑generated phrasing (“immediate availability”)  
- **Red-Flag 7:** No job IDs  
- **Red-Flag 8:** No links to postings  
- **Red-Flag 9:** Inflated salary ranges  
- **Red-Flag 10:** No clearance requirements for Leidos  
- **Red-Flag 11:** Unrealistic remote options for defense roles  
- **Red-Flag 12:** No technical depth in any description  
- **Red-Flag 13:** No name at the closing, makes it look like a copy/paste from ai/template  
- **Red-Flag 14:** “100% equipment stipend” (non‑existent HR term)  
- **Red-Flag 15:** Mirrors known reimbursement scams  
- **Red-Flag 16:** No cert/tooling requirements for a pentester role  
- **Red-Flag 17:** Instant replies until verification requested  
- **Red-Flag 18:** Ghosting when asked for legitimacy  

---

## **5. Determination**
This interaction is **highly likely to be a scam or fraudulent recruitment attempt**.  
The combination of behavioral, linguistic, and contextual red flags makes this a textbook example of a **LinkedIn social‑engineering attempt**.

---

## **6. Recommended Action (Which I Followed)**

### ✔️ **Report the account as “Fraud or scam.”**  
This is the correct category based on LinkedIn’s reporting options.

### ✔️ **Block the user.**  
Prevents further contact or data harvesting. However, it also prevents you from seeing the message to copy the information for use later (such as this document).

### ✔️ **Do not provide résumé, salary details, or personal information.**  
I avoided this due to personal habits and training, it is an excellent operational security measure.

---

This case demonstrates:

- Scam pattern recognition  
- Behavioral analysis  
- OSINT reasoning  
- Safe communication practices  
- Professional verification steps  
- Correct escalation and reporting  

