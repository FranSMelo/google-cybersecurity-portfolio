# Data Leak Incident Analysis & Least Privilege Assessment

## Overview

This document evaluates a data security incident involving an unauthorized leak of confidential internal business materials to an external business partner. The analysis identifies key breakdowns in information privacy practices, reviews applicable control guidance from NIST SP 800-53: AC-6 (Least Privilege), and outlines actionable recommendations to mitigate future exposure risks.

---

## Data Leak Worksheet

### Control

**Least Privilege**

### Issue(s)

The incident occurred because a sales manager shared a folder containing internal-only documents with the team and forgot to revoke access after the meeting. Afterwards, a sales representative intended to share only promotional materials during a partner call but accidentally provided a link to the entire unsegregated folder, which was then published on social media.

### Review

NIST SP 800-53: AC-6 addresses the principle of least privilege, requiring that users, processes, and user accounts are granted only the minimum access and authorizations necessary to perform their specified operational duties. The framework emphasizes enforcing role-based restrictions to prevent individuals from operating with permissions beyond what is required for their current business functions.

### Recommendation(s)

1. Automatically revoke access to information after a specified period of time.
2. Restrict access to sensitive resources strictly based on user role.

### Justification

Automating access expiration prevents sensitive folders from remaining accessible indefinitely due to human oversight by managers. Enforcing role-based access restrictions ensures employees can only view and share files aligned with their immediate duties, minimizing the risk of accidental exposure during external communications.

## Control Enhancement Matrix (NIST SP 800-53: AC-6 Reference)

| Control Enhancement                        | Security Objective                                                                | Implementation Strategy                                                                           |
| :----------------------------------------- | :-------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------ |
| **Access Auto-Revocation**           | Eliminate persistent elevated privileges resulting from administrative oversight. | Configure file-sharing permissions to expire automatically after a predefined time limit.         |
| **Role-Based Access Control (RBAC)** | Enforce strict boundaries around sensitive internal documentation.                | Limit document access based on job functions and restrict sharing permissions for internal files. |
| **User Activity Logging**            | Provide visibility into file access and external link creation.                   | Retain logs of provisioned user accounts and shared links to support security audits.             |
| **Privilege Audits**                 | Regularly assess user permission levels across cloud repositories.                | Perform periodic reviews of folder access control lists (ACLs) to clean up legacy permissions.    |

## Summary

By integrating automated revocation mechanisms and role-based access policies aligned with NIST SP 800-53: AC-6, organizations can effectively enforce the principle of least privilege. These enhancements reduce reliance on manual user compliance, close unauthorized sharing vectors, and strengthen information privacy controls across internal data repositories.
