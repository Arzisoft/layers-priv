---
course: "The Industry"
module: "Module 5: Student Data Privacy & Compliance"
lesson: "Module 5: Student Data Privacy & Compliance — Exam"
type: "course_quiz"
post_id: 104112229
space_id: 24251863
source: "https://the-faction.mn.co/posts/104112229"
updated: "2026-08-10T18:15:42Z"
---

# Module 5: Student Data Privacy & Compliance — Exam

> Exam for **Module 5: Student Data Privacy & Compliance** (The Industry) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your EdTech platform uses Google Analytics on every page including pages where students view grades and assignment feedback. A district asks about FERPA compliance. What is the data exposure risk?

- **A.** Third-party tracking scripts on student data pages can transmit personally identifiable information to external services unauthorized  ✅
- **B.** Google Analytics only collects aggregated page view metrics and does not transmit any personally identifiable student information
- **C.** The platform's privacy policy already discloses third-party analytics usage which satisfies FERPA notification requirements fully
- **D.** Disabling analytics only on the login page is sufficient since student data is not visible until after successful authentication

> **Answer:** A

### Q2. A teacher exports student performance data from your platform and emails it to the school counselor using their personal Gmail account. What data handling violation occurred?

- **A.** The teacher should have password-protected the exported file before sending it through any email channel to ensure data security
- **B.** Student data must be transmitted through authorized secure channels — personal email accounts are not approved for FERPA-protected data  ✅
- **C.** Email transmission of student data is actually acceptable as long as the recipient is a school employee with a legitimate educational interest
- **D.** The export feature itself is the violation since teachers should not have the ability to download student data to personal devices

> **Answer:** B

### Q3. Your platform collects student names, emails, and grade data for educational purposes. You also collect device fingerprints and browsing behavior for your recommendation algorithm. A FERPA review questions this. Why?

- **A.** Recommendation algorithms are considered educational tools and the data powering them falls under the same educational purpose umbrella
- **B.** Students consented to the full privacy policy during account creation which covers all data collection including behavioral tracking
- **C.** Device fingerprints and browsing behavior exceed the educational purpose — FERPA limits data use to what the district contract specifies  ✅
- **D.** Collecting behavioral data is actually acceptable as long as it is stored separately from the student's official educational record in the system

> **Answer:** C

### Q4. Your district contract specifies a 48-hour breach notification window. On Friday afternoon your team discovers unauthorized access to student records. The engineer wants to wait until Monday. What should happen?

- **A.** Complete a thorough forensic investigation before notifying the district ensuring that you can provide a comprehensive incident report with findings
- **B.** Notify the district's IT department informally via phone call and defer the formal written notification until the investigation concludes
- **C.** Assess whether any data was actually exfiltrated before triggering the notification timeline since access alone may not constitute breach
- **D.** Notify the district within 48 hours as contractually required — the investigation continues in parallel but the notification clock started  ✅

> **Answer:** D

### Q5. Your platform collects assessment data for grading. The product team uses this same data to train an AI recommendation model. The district contract does not mention AI training. Is this a compliance problem?

- **A.** Using student data for AI training beyond the contracted educational purpose likely violates FERPA without explicit district authorization  ✅
- **B.** AI model training that improves the educational experience for students falls within the general educational purpose of the contract
- **C.** Anonymizing the training data before using it removes the FERPA obligation since de-identified data is actually not considered an education record
- **D.** The platform's terms of service grant broad data usage rights that override the specific limitations in individual district contracts

> **Answer:** A

### Q6. A parent requests to see all data your platform holds about their child. Your system has no way to generate a personal data report for individual students. The parent files a complaint. What mechanism should exist?

- **A.** Direct all parent data access requests to the school district primarily since FERPA designates the school as the records custodian not the vendor
- **B.** Provide parents with login credentials to their child's account so they can browse the same interface and see all stored data directly
- **C.** A parent data access mechanism — FERPA grants parents the right to inspect education records and your platform must support this export  ✅
- **D.** Publish a comprehensive data dictionary on your website documenting every data element collected so parents understand what is stored

> **Answer:** C

### Q7. Your platform operates in California, New York, and Illinois. You comply with FERPA but have not reviewed state-level student privacy laws. A California school reports a potential SOPIPA violation. What was overlooked?

- **A.** FERPA is the federal standard that preempts all state-level student privacy laws so separate state compliance reviews are unnecessary
- **B.** State laws add requirements beyond FERPA — California SOPIPA, New York Ed Law 2-d, and Illinois SOPPA each have unique provisions  ✅
- **C.** State privacy laws only apply to schools and districts, not to third-party vendors who already comply with federal FERPA requirements
- **D.** Hiring a state-specific compliance attorney is only necessary after a violation occurs, not as a proactive part of product development

> **Answer:** B

### Q8. A district contract ends in June. Your platform retains their student data through December for backup purposes. The district requests deletion and you have no process for it. What should have been built?

- **A.** Retain district data for one year after contract termination as a standard practice in case the district decides to renew their agreement
- **B.** Offer the district a data migration service to transfer their student records to their new vendor platform before your deletion process
- **C.** Archive the data to cold storage rather than deleting it since future regulatory audits may require access to historical student records
- **D.** A documented data return and deletion process — district data must be returned or purged within the contractual timeframe on termination  ✅

> **Answer:** D

### Q9. Your privacy policy is a 4,000-word legal document. A parent asks in plain language what student data you collect and how it is used. Your team cannot answer without reading the legal text. What should exist alongside it?

- **A.** A plain-language data practices summary — a clear non-legal explanation of what you collect, why, and how you protect student information  ✅
- **B.** An interactive privacy dashboard where parents can toggle individual data collection categories on and off for their child's account
- **C.** A chatbot trained on the privacy policy that can answer parent questions about data practices in conversational accessible language
- **D.** A quarterly transparency newsletter sent in order to all parents summarizing any changes to data collection practices in non-technical language

> **Answer:** A

### Q10. Your data inventory lists student names and emails as collected data. It does not include IP addresses, device types, and session timestamps that your platform also logs. An auditor finds the gap. What should the inventory cover?

- **A.** Technical log data generated by the web server infrastructure is not considered student data and does not belong in the data inventory
- **B.** Only include data elements that are directly visible to teachers and administrators in the platform's user-facing interface screens
- **C.** Create a separate technical data inventory for infrastructure logs that is maintained by the engineering team independently from student data
- **D.** The inventory must include all data collected — technical logs, metadata, and analytics — not just the obvious student-facing data fields  ✅

> **Answer:** D

### Q11. A school uses your platform under COPPA's school consent exception for educational purposes only. Your marketing team adds targeted product recommendations based on student learning data. What is the violation?

- **A.** Product recommendations based on learning patterns are considered educational enhancements and fall within the school consent exception
- **B.** The school's original COPPA consent covers all platform features including those added after the initial consent was obtained signed
- **C.** School COPPA consent covers educational use only — commercial purposes like targeted product recommendations require separate parent consent  ✅
- **D.** Displaying recommendations without collecting additional data does not constitute a new data use and remains within the original scope

> **Answer:** C

### Q12. Your encryption setup uses HTTPS for data in transit but stores student data unencrypted in the database at rest. A security review asks about at-rest encryption. What is the protection gap?

- **A.** HTTPS encryption provides sufficient protection since data is only vulnerable during transmission between the browser and the server
- **B.** Student data must be encrypted both in transit and at rest — database encryption protects data if storage media is compromised or stolen  ✅
- **C.** At-rest encryption is actually only necessary for databases storing financial or healthcare data and is not a standard requirement for education
- **D.** The cloud hosting provider's physical security controls at the data center eliminate the need for application-level at-rest encryption

> **Answer:** B

### Q13. A data breach exposes 5,000 student records. Your response plan says notify appropriate parties but does not name who, specify timelines, or detail required notification content. What was missing from the plan?

- **A.** Specific named parties, notification timelines per state law, required content for each notification, and assigned staff responsibilities  ✅
- **B.** A general incident response framework is sufficient as long as the team has access to legal counsel who can advise during active breaches
- **C.** Breach notification details should be determined during each incident based on the specific circumstances rather than predefined in advance
- **D.** The district's own incident response team handles all notification responsibilities so your plan only needs to cover internal containment

> **Answer:** A

### Q14. Your platform anonymizes student data for research by removing names but keeping school, grade level, gender, and exact date of birth. A researcher re-identifies students by combining these fields. What is the de-identification failure?

- **A.** Removing the student name field is sufficient anonymization since names are the only directly identifying element in the student record
- **B.** Quasi-identifiers like school, grade, gender, and date of birth can re-identify individuals — proper anonymization addresses all linkable fields  ✅
- **C.** True anonymization of education data is technically impossible so all research use requires explicit parental consent regardless of method
- **D.** Aggregating data to the school level rather than individual records is the only reliable anonymization approach for educational research

> **Answer:** B

### Q15. Your engineering team stores student database credentials in a shared Slack channel. A former employee who still has Slack access can see these credentials and connect to the production database. What is the security failure?

- **A.** The former employee's Slack access should have been revoked during their offboarding process which would have prevented this exposure
- **B.** Database credentials should be rotated quarterly so any credentials visible in historical Slack messages would be expired and non-functional
- **C.** Restrict the Slack channel containing credentials to a smaller group of senior engineers who require direct database access for their work
- **D.** Credentials must be stored in a secrets manager with proper access controls and audit trails — never in Slack, email, or shared documents  ✅

> **Answer:** D

### Q16. A parent opts their child out of data collection. Your platform offers only two options: full data collection or no platform access at all. The student cannot use the educational tool. What should be available?

- **A.** Inform the parent that data collection is required for platform functionality and the opt-out means the student must use paper alternatives
- **B.** Allow the opt-out but disable all platform features for that student and display a message explaining that functionality requires data consent
- **C.** A minimal-data mode letting opted-out students use core educational features without optional analytics, tracking, or recommendation data  ✅
- **D.** Provide the parent with a detailed explanation of each data element collected and let them selectively opt out of individual categories

> **Answer:** C

### Q17. Your Terms of Service include a clause allowing you to share aggregated student data with advertising partners. A district discovers this during their procurement security review. What will likely happen?

- **A.** The district will likely reject your platform — any advertising-related data sharing is a red flag in education procurement review processes  ✅
- **B.** Aggregated data cannot identify individual students so sharing it with advertising partners does not raise FERPA compliance concerns
- **C.** The clause is standard practice for free-tier platforms and districts understand that advertising partnerships subsidize platform access costs
- **D.** Removing the clause for individual districts while keeping it in the general terms satisfies procurement requirements without policy changes

> **Answer:** A

### Q18. Your vendor questionnaire asks if you comply with FERPA. Your team answers yes based on having encryption and access controls. The district follows up requesting training records, data inventories, and breach plans. You have none. What does FERPA compliance actually require?

- **A.** Encryption and access controls constitute the technical requirements of FERPA compliance and administrative documentation is supplementary
- **B.** FERPA compliance is self-certified by the vendor through a signed attestation letter and does not require supporting documentation proof
- **C.** Only schools and districts are subject to FERPA compliance requirements and vendors are held to the standards in their individual contracts
- **D.** Documented policies, staff training records, data inventories, incident response plans, and contractual controls — not just technical measures  ✅

> **Answer:** D

### Q19. Your development team uses a copy of production student data in their local development environment for testing. A developer's laptop is stolen from a coffee shop. What data practice should have prevented this?

- **A.** Never use production student data in development — use synthetic or de-identified test data that contains no real student information at all  ✅
- **B.** Require full-disk encryption on all developer laptops so stolen devices cannot be accessed without the correct authentication credentials
- **C.** Restrict development work to office-only environments where physical security controls prevent device theft during working hours entirely
- **D.** Implement remote wipe capability on all developer devices so stolen laptops can have their data erased immediately upon theft reporting

> **Answer:** A

### Q20. A new federal regulation requires an annual transparency report listing all student data categories, retention periods, and third-party sharing. Your platform has no centralized data catalog. Building one will take months. What should have been maintained?

- **A.** Build the data catalog reactively when regulations require it since maintaining one proactively consumes engineering resources unnecessarily
- **B.** A simple spreadsheet updated annually by the compliance team listing the major data categories is sufficient for regulatory transparency needs
- **C.** A living data catalog documenting all student data elements, purposes, retention periods, and sharing relationships as ongoing operations  ✅
- **D.** Rely on the database schema documentation maintained by the engineering team since it already describes all data elements technically

> **Answer:** C

### Q21. Your platform exports class data as CSV. The export includes student Social Security numbers synced from the SIS that your platform never uses for any educational purpose. What is the data handling problem?

- **A.** Encrypt the Social Security number column in all CSV exports so the data is protected even if the file is intercepted or shared broadly
- **B.** Never store data you do not use — importing and exporting SSNs without educational purpose multiplies breach exposure unnecessarily  ✅
- **C.** Restrict CSV export access to district administrators only since they are authorized to handle sensitive student identification numbers
- **D.** Mask Social Security numbers in exports by showing only the last four digits which provides identification without full number exposure

> **Answer:** B

### Q22. Your platform cookies store the student's name and grade level in plain text. A student on a shared school computer leaves the browser open. The next student sees the previous student's information. What should change?

- **A.** Implement an automatic session timeout that logs users out after five minutes of inactivity to minimize the exposure window on shared devices
- **B.** Display a reminder banner on shared school devices prompting students to log out when they finish their session before leaving the computer
- **C.** Configure the school's browser management software to clear all cookies and session data automatically between each student user session
- **D.** Cookies should never store PII in plain text — use encrypted session tokens referencing server-side data instead of client-side storage  ✅

> **Answer:** D

### Q23. A district requires all vendors to sign the Student Data Privacy Consortium's National Data Privacy Agreement before procurement. Your team has never seen the NDPA. The district will not proceed without it. What should you have done?

- **A.** Review and prepare for the NDPA proactively — most districts now require it and readiness to sign accelerates the procurement process  ✅
- **B.** Negotiate custom data privacy terms with each district individually rather than signing a standardized agreement that may be overly restrictive
- **C.** Request a 90-day review period before signing the NDPA to allow your legal team to fully evaluate every clause and propose modifications
- **D.** Sign the NDPA without review since it is a standardized industry agreement that all major EdTech vendors have already agreed to accept

> **Answer:** A

### Q24. A breach occurs and your team contains it in four hours but waits two weeks to notify the district while completing their investigation. The contract requires 72-hour notification. What is the consequence?

- **A.** The district will appreciate the thoroughness of the investigation and the delay will be forgiven given the comprehensive incident report
- **B.** The two-week delay is reasonable for complex breach investigations and most districts understand that thorough analysis takes significant time
- **C.** Contractual notification timeline violated — the district may terminate the contract and delayed notification triggers additional state penalties  ✅
- **D.** The breach was contained within four hours so the notification timeline does not begin until evidence of data exfiltration is confirmed

> **Answer:** C

### Q25. Your data processing agreement says you process student data as needed to provide the service with no specific list of data elements, purposes, or retention limits. An auditor flags this language. Why?

- **A.** Broad language provides necessary flexibility for evolving platform features without requiring contract amendments for every product update
- **B.** Agreements need specificity — list exact data elements collected, specific purposes for each, defined retention periods, and deletion procedures  ✅
- **C.** The privacy policy already contains the detailed data element lists and retention schedules ensuring that the processing agreement can reference it broadly
- **D.** Auditors expect broad language in data processing agreements and will accept it as long as the vendor can verbally explain their practices

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/104112229_
