# Day 6 – Group Policy Management

## Overview

Implemented and configured Group Policy Objects (GPOs) within the Active Directory domain to centrally manage Windows security settings. The configured policies were deployed to a domain-joined Windows 11 client and validated to ensure successful application.

---

## Objectives

- Create and manage Group Policy Objects (GPOs)
- Configure domain security policies
- Apply password policy settings
- Enforce user restrictions through Group Policy
- Validate policy deployment on a domain-joined client

---

## Implementation

- Created a new Group Policy Object (GPO)
- Linked the GPO to the appropriate Organizational Unit (OU)
- Configured password policy settings
- Applied user restriction policies
- Updated Group Policy using `gpupdate`
- Verified applied policies using `gpresult`

---

## Outcome

The configured Group Policy settings were successfully deployed to the Windows 11 domain client. Policy enforcement was verified using built-in Windows Group Policy tools, confirming that the Active Directory environment was centrally managing endpoint configuration as expected.
