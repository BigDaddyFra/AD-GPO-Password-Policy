# AD GPO Password Policy Project

## 🎯 Objective
Strengthen Active Directory (AD) security by enforcing complex password requirements to mitigate brute-force attacks.

---

## 🔧 Key Steps & Technical Highlights

### 🛠️ GPO Creation
- Created a custom Group Policy Object (GPO) named `ECCPassword Policy` linked to the `NDE.com` domain using **Group Policy Management Console (GPMC)**.

### 🔐 Policy Settings
- Enforced password complexity: uppercase, lowercase, numbers, and special characters.
- Minimum length: 6+ characters.
- Blocked use of username fragments in passwords.
- Enabled "User must change password at next logon" for testing.

### 📢 Policy Enforcement
- Marked the GPO as **Enforced** to override conflicting policies (e.g., Default Domain Policy).
- Used **Security Filtering** to apply the policy only to user `martin@nde.com`.

### 🧪 Validation & Testing
- **Simulated attack:** `test123` denied as weak password.
- **Successful test:** `Test@123` accepted, confirming policy enforcement.
- Ran `gpupdate /force` on domain-joined web server to apply policy.

### 🌐 Domain Integration
- Web server successfully joined to `NDE.com` domain.
- Policy applied across devices.

---

## 🔒 Standout Features
- **Least-Privilege Test:** Targeted one user (`Martin`) for isolated testing.
- **Defense-in-Depth:** Used "Enforced" flag to ensure policy took precedence.
- **Real-World Validation:** Demonstrated rejection of weak passwords.

---

## 🧰 Technical Environment
- **Tools Used:** `gpmc.msc`, `dsa.msc`, `Command Prompt (gpupdate)`
- **Domain:** `NDE.com`
- **Test User:** `martin@nde.com`

---

## 💡 Why This Project Matters
This project showcases hands-on expertise in enterprise security hardening using native Windows tools. It is a real-world demonstration of how Group Policy can defend against common credential-based attacks, with clear validation and impact.

---

## 📁 Structure

---

## 🚀 Future Improvements
- Add PowerShell scripts for GPO export/import
- Capture event logs showing password rejection
- Include screenshots (if available)

---
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

