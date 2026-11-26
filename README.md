# Week 4 – Web Application Penetration Testing

**Internship:** Networkwalks Cybersecurity Internship – Week 4  
**Target:** https://medirozahospital.com  
**Assessment Type:** Black-Box Web Application Penetration Testing  
**Assessment Date:** 26 November 2026  
**Scope:** Target domain only, as stated in the project brief.

## Project Overview

The Week 4 project focused on testing the target website, identifying exposed entry points and security weaknesses, examining the patient portal, analysing three PDF lab reports, and preparing a professional penetration testing report.

## Assessment Methodology

The assessment started with reviewing the website's `robots.txt` file.

The work then continued with:

- Website reconnaissance and reviewing discovered paths.
- Identifying exposed entry points.
- Inspecting the Patient Portal and login functionality.
- Testing web requests and application responses using Burp Suite.
- Reviewing exposed patient report resources.
- Analysing the three PDF files and testing their password strength.
- Examining the exposed legacy database backup.
- Preparing the final penetration testing report.

## Tools Used

1. **Networkwalks Hash Calculator**
2. **Networkwalks Password Cracker**
3. **Burp Suite**

## Key Findings

| ID | Finding | Severity |
|---|---|---|
| F-01 | Exposed patient directory and downloadable reports | Critical |
| F-02 | Exposed legacy database backup containing HR/shareholder information | Critical |
| F-03 | Weak PDF password protection; password recovery succeeded for all three PDFs | High |
| F-04 | SQL injection test payload triggered a verbose MySQL syntax error | High |

**SQL Injection Note:** The login test payload `" OR 1=1--` triggered a MySQL syntax error. This demonstrates database error disclosure during testing, but the available screenshot does not independently prove a successful login bypass.

## Project Deliverables

- `WEEK4_Pentest_Report_Mediroza_CORRECTED.pdf` – Final penetration testing report.
- `EVIDENCE/` – Screenshots collected during the assessment.

## Recommendations

1. Remove public access to patient-report directories and legacy database backups.
2. Disable directory listing and enforce proper authorization for sensitive downloads.
3. Review access logs and investigate possible unauthorized access.
4. Use authenticated downloads instead of relying on PDF passwords as primary access control.
5. Use parameterized SQL queries to prevent SQL injection.
6. Avoid displaying detailed database errors to website users.

## Data Handling Notice

Do not publish original patient reports, database dumps, staff/shareholder records, personal identifiers, or recovered passwords on public GitHub or LinkedIn. Keep original evidence in a private, access-restricted location.
