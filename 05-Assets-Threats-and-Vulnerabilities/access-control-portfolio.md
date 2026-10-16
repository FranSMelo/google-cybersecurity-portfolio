
# Access Control Investigation & Authorization Audit

## Overview

This document details an incident investigation conducted following an unauthorized payroll deposit transaction to an unknown bank account. By performing system accounting across event logs and cross-referencing internal employee directories, this analysis identifies the threat actor, highlights critical access control vulnerabilities, and provides actionable technical, operational, and managerial recommendations to prevent future breaches.

---

## Access Control Worksheet

### Category

**Authorization / Authentication Controls**

### Note(s)

* **Threat Actor Identification:** The incident was initiated under the account credentials `Legal\Administrator`, associated with contractor **Robert Taylor Jr.** using IP address `152.207.255.255`.
* **Timing & Origin Device:** The unauthorized transaction occurred on **10/03/2023 at 8:29:57 AM** from a workstation named `Up2-NoGud` (`Payroll event added. FAUX_BANK`).

### Issue(s)

1. **Deprovisioning Breakdown:** The user's contract end date was recorded as **2019-12-27**, yet their active credentials and system access remained enabled over three years after termination.
2. **Excessive Privileges (Lack of Least Privilege):** Every employee in the company directory—including seasonal staff, contractors, and non-finance roles—holds full `Admin` authorization, allowing unauthorized users to execute critical financial and payroll events.

### Recommendation(s)

1. **Implement Automated Account Deprovisioning:** Establish strict identity lifecycle management to automatically disable credentials immediately upon an employee's or contractor's contract end date.
2. **Enforce Role-Based Access Control (RBAC) & Least Privilege:** Revoke blanket `Admin` rights across non-essential roles and restrict payroll management privileges strictly to authorized finance personnel.

---

## Forensic Accounting & Audit Findings Matrix

| Parameter                | Event Log Data          | Directory Audit Cross-Reference                 | Audit Finding                                             |
| :----------------------- | :---------------------- | :---------------------------------------------- | :-------------------------------------------------------- |
| **User / Account** | `Legal\Administrator` | Robert Taylor Jr. (Legal Attorney / Contractor) | Unauthorized activity by former contractor.               |
| **IP Address**     | `152.207.255.255`     | `152.207.255.255`                             | Match confirmed between event log and user account.       |
| **Account Status** | Active (Event Executed) | End Date: `2019-12-27`                        | Account was not deprovisioned after contract termination. |
| **Authorization**  | Administrative Access   | Role: `Admin`                                 | Excessive privileges granted to non-finance contractor.   |

---

## Summary

The investigation confirms that the unauthorized transaction was facilitated by inadequate offboarding procedures and overly permissive access policies. By implementing automated lifecycle management and role-based access controls (RBAC), the organization can enforce strict principle of least privilege standards and prevent unauthorized system actions.
