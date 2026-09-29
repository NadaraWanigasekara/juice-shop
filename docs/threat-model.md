# STRIDE Threat Model and Risk Assessment

## Overview

A STRIDE-based threat model was used to identify application-specific security threats in the OWASP Juice Shop environment. The assessment considered authentication, application requests, data exposure and authorization boundaries.

## Threat Assessment

| ID | STRIDE Category | Threat | Likelihood | Impact | Risk |
|---|---|---|---|---|---|
| T1 | Spoofing | Authentication weaknesses could allow an attacker to impersonate a legitimate user. | High | High | High |
| T2 | Tampering | Attackers could manipulate application requests or input values to modify application behaviour. | High | High | High |
| T3 | Information Disclosure | Exposed application interfaces or data could reveal information to unauthorized users. | Medium | High | High |
| T4 | Elevation of Privilege | Authorization weaknesses could allow a user to access functionality or resources beyond their privileges. | Medium | High | High |

## Security Controls

### T1 – Spoofing

Authentication controls should validate user credentials securely and prevent authentication bypass attacks. Parameterized database queries help prevent SQL injection from being used to bypass authentication.

### T2 – Tampering

Application input should be validated and handled safely. Server-side validation and secure request processing reduce the possibility of manipulating application behaviour.

### T3 – Information Disclosure

Application interfaces should enforce appropriate access controls and avoid exposing sensitive information to unauthorized users.

### T4 – Elevation of Privilege

Authorization should be verified on the server side for protected resources. Users should only be allowed to access resources belonging to their authorized account.

## Connection to Vulnerability Assessment

The threat model was connected to the vulnerability assessment performed on the application. SQL injection relates to authentication weaknesses, broken access control relates to unauthorized resource access, DOM-based XSS relates to attacker-controlled input, and improper rating validation demonstrates the need for server-side validation.

## Conclusion

The STRIDE assessment provided a structured approach for identifying threats and mapping them to security controls implemented or evaluated during the project.
