# Case Study: Reviewing an Assessment Reporting Template
## Unit 5

### Activity Context

The activity involved reviewing a sample vulnerability assessment report from PurpleSec and considering whether its structure could provide a useful baseline for future penetration testing and security assessment.

### Review

#### Does the template provide an effective baseline?

The template provides a useful point-in-time vulnerability baseline because it documents assessment scope, scanning methodology, coverage, vulnerability severity and remediation recommendations. These elements could support comparison with later assessments.

However, a stronger reusable baseline would also record the assessment date and baseline version explicitly, provide a clearer inventory of in-scope and out-of-scope assets, document relevant system or security-control context, distinguish validated findings from scanner results requiring further verification, and provide structured remediation and retest status. These additions would make changes in security posture easier to evaluate over time.

#### Two useful lessons from the report

**1. Remediation-focused prioritisation.**  
The report demonstrates the value of translating vulnerability data into practical remediation priorities rather than presenting findings only as a list of scanner results. Grouping remediation actions that address multiple findings can make the report more operationally useful.

**2. Recognising the limitations of vulnerability scanning.**  
The report acknowledges that automated vulnerability scanning represents only one component of security assessment. This is an important methodological lesson because scanner output should be interpreted alongside contextual information and, where appropriate, additional validation or manual testing.

#### Two areas that could be improved

**1. Detailed scanner output could be separated from the main narrative.**  
Large tables of individual findings can make the main report harder to navigate. Detailed technical evidence could be retained in an appendix, while the main report focuses on consolidated, validated and prioritised findings.

**2. Prioritisation could include more context than technical severity alone.**  
Severity is useful, but remediation decisions can also consider asset criticality, exposure, exploitability and potential operational impact. Adding this context would make prioritisation more representative of organisational risk.

## Reflection

### Did you have any issues or challenges with this activity?

The main challenge was distinguishing between a vulnerability assessment report that effectively communicates scan results and one that can also provide a reusable security baseline. The PurpleSec report contains useful information about scope, methodology, vulnerability severity and remediation, but much of the report is structured around the output of a specific vulnerability scan.

This required considering the purpose of the report beyond whether the technical findings were presented correctly. In particular, a baseline intended to support future security assessments needs enough contextual information to allow meaningful comparison over time.

### How did you overcome them?

I reviewed the report in terms of both technical content and its usefulness for future assessments. I considered whether another assessor could use the document to understand what assets were tested, what methodology and controls were present, what limitations applied and how the security posture had changed since the previous assessment.

This highlighted several useful elements, including the report's remediation prioritisation and its acknowledgement that vulnerability scanning alone cannot provide a complete assessment of security posture. However, it also identified opportunities to improve asset context, evidence classification, remediation tracking and retesting information.

### How will they affect your final report?

The activity influenced how I would structure and prioritise information in my own security reporting. Rather than reproducing large amounts of scanner output, I would focus the main report on validated and contextualised findings, their business or security relevance, and clear remediation priorities, while retaining detailed technical evidence separately where necessary.

I would also document assessment scope, methodology and limitations clearly and distinguish confirmed findings from observations or potential vulnerabilities requiring further validation. This would make the report more useful as both a current assessment and a reference point for subsequent security reviews.

---

[Return to Network Security](../)
