# Lesson 0.1 — The Cybersecurity Mindset

**Module:** 00 — Cybersecurity Mindset  
**Status:** ✅ Completed  
**Level:** Foundational  

## Core Idea

Cybersecurity is not about starting with tools or attack techniques. A security professional first understands the system and asks:

- What are we protecting?
- Who or what could cause harm?
- What assumptions does the system make?
- Where does trust change?
- What is the attack surface?
- How could security controls fail?
- What would the actual impact be?

> **Understand the security problem first. Choose the testing technique afterward.**

---

## QA Mindset → Security Mindset

**QA asks:**

> Does the system do what it is supposed to do?

**Security additionally asks:**

> Can the system be made to do something it should never do?

```text
Functionally Correct ≠ Secure
```

My QA skills in negative testing, boundary testing, API testing, and defect analysis provide a strong foundation for security testing.

---

## Basic Security Analysis

```text
Asset
  ↓
Threat Source
  ↓
Threat Event
  ↓
Vulnerability
  ↓
Exploitation
  ↓
Impact
```

- **Asset:** Something valuable that needs protection.
- **Threat Source:** Who or what could cause harm.
- **Threat Event:** The harmful event that could occur.
- **Vulnerability:** A weakness that makes harm possible.
- **Exploitation:** Using the weakness.
- **Impact:** The resulting consequence.

### Important Rule

```text
What I KNOW ≠ What I SUSPECT ≠ What I have PROVEN
```

Do not claim an impact without evidence.

---

## Security Is Often About Broken Assumptions

Examples of unsafe assumptions:

- Users will only use the UI.
- Nobody will call the API directly.
- Users will not modify parameters.
- Requests will always execute one at a time.
- Normal users will not try admin endpoints.
- Nobody will steal or reuse another user's session.

The security question is:

> **What happens when the assumption becomes false?**

---

## Authentication vs Authorization

- **Authentication:** Who are you?
- **Authorization:** What are you allowed to do?

```text
Authenticated ≠ Authorized
```

A valid normal-user token proves identity, but it should not allow access to admin functionality.

```text
Hidden UI ≠ Protected Function
```

Permissions must be enforced on the server side.

---

## Trust Boundaries

A trust boundary exists where **data, identity, control, or privilege crosses between different security contexts**.

Examples:

```text
User Device → Bank API
Normal User → Admin Function
Application Server → Database
Bank System → Third-Party Service
```

Data received across a trust boundary should not be automatically trusted.

---

## Attack Surface

A secure login does not mean the whole application is secure.

The attack surface may include:

- Login and password reset
- Sessions and tokens
- APIs
- Admin functions
- File uploads
- Business logic
- Databases
- Third-party services
- Cloud and internal infrastructure

```text
Secure Login ≠ Secure Application
```

---

## Concurrency Lesson

Two individually valid requests can produce an invalid result when processed simultaneously.

Example:

```text
Balance = ₹10,000

Request A → Transfer ₹8,000
Request B → Transfer ₹8,000
```

If both requests read the old ₹10,000 balance before either updates it, both may succeed.

> **Never assume requests will always execute one at a time.**

---

## My Key Corrections

1. Do not confuse a **threat source** with an **impact**.
2. Do not claim more impact than the evidence proves.
3. Do not automatically treat missing MFA as the root vulnerability.
4. Do not confuse **assets** with **trust boundaries**.
5. Do not start with a favorite attack technique such as SQL Injection.
6. Identify the security goal and possible failure first.

---

## Mental Models to Remember

```text
Functionally Correct ≠ Secure
Authenticated ≠ Authorized
Hidden ≠ Protected
Client-Side Validation ≠ Server-Side Security
Secure Login ≠ Secure Application
Tool Knowledge ≠ Security Understanding
```

## Next Lesson

**Lesson 0.2 — Assets, Threats, Vulnerabilities, Exposure, Impact, Risk, and Security Controls**