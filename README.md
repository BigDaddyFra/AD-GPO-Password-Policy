# Project: Implementing Password Policies via Windows Group Policy

## Objective
Strengthen Active Directory (AD) security by enforcing complex password requirements to mitigate brute-force attacks.

## Key Steps & Technical Highlights

### GPO Creation
- Created a custom Group Policy Object (GPO) named `ECCPassword Policy` linked to the `NDE.com` domain using Group Policy Management Console (GPMC).

### Policy Settings
- Enforced password complexity (uppercase, lowercase, numbers, special characters).
- Required minimum length (6+ characters) and blocked passwords containing username fragments.
- Enabled "User must change password at next logon" for targeted testing.

### Policy Enforcement
- Marked the GPO as "Enforced" to override conflicting policies (e.g., Default Domain Policy).
- Applied Security Filtering to restrict the policy to user Martin (martin@nde.com).

### Validation & Testing
- **Simulated Attack**: Attempted to set a weak password (`test123`) for Martin—denied by the GPO.
- **Successful Compliance**: Complex password (`Test@123`) was accepted, proving policy effectiveness.
- Forced Group Policy update via `gpupdate /force` on the domain-joined web server.

### Domain Integration
- Joined a web server to the NDE.com domain, demonstrating cross-device policy propagation.

## Standout Features
- **Least-Privilege Approach**: Targeted policy application to a single user (Martin) for testing.
- **Defense-in-Depth**: Overrode default policies via "Enforced" flag to ensure compliance.
- **Real-World Validation**: Proved resistance to common brute-force tactics (e.g., simple passwords).

## Technical Environment
- **Tools**: GPMC (`gpmc.msc`), Active Directory Users & Computers (`dsa.msc`), Command Prompt (`gpupdate`).
- **Domain**: `NDE.com` | **User**: `martin@nde.com`

## Why This Matters
This project showcases hands-on expertise in enterprise security hardening using native Windows tools, emphasizing actionable defense strategies against credential-based attacks. The detailed validation steps (e.g., password rejection logs) make it a practical reference for AD security configurations.

