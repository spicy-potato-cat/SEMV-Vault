## Program Security

### Key Questions

- **How do we keep programs free from flaws?**
    - Through secure coding practices, code reviews, and automated testing.
- **How do we protect computing resources against programs that contain flaws?**
    - By sandboxing, access control, and runtime monitoring.
- **Presented with a finished product (e.g., commercial software), how can you tell how secure it is or how to use it in its most secure way?**
    - By reviewing vendor documentation, applying patches, and configuring security settings properly.

---

## Secure Programs

- **Security implies trust**: A secure program enforces **confidentiality, integrity, and availability (CIA triad)**.
- **Assessment of security**:
    - Static and dynamic analysis of code.
    - Penetration testing and fuzzing.
    - Reviewing compliance with standards (e.g., OWASP, ISO/IEC 27001).

---

## Fixing Faults and Unexpected Behaviors

### Faults

- **Definition**: Errors in design, coding, or configuration that can lead to vulnerabilities.
- **Mitigation**:
    - Regular patching and updates.
    - Root cause analysis and corrective coding.
    - Defensive programming techniques.

### Unexpected Behaviors

- **Definition**: Program actions outside intended functionality, often exploited by attackers.
- **Mitigation**:
    - Input validation and sanitization.
    - Exception handling to prevent crashes.
    - Logging and monitoring to detect anomalies.

---

# Types of Flaws

---
## Intentional Flaws

- **Malicious**: Deliberate code inserted to exploit, harm, or compromise systems (e.g., backdoors, logic bombs).
- **Nonmalicious**: Intentionally added features that violate policy or expose risk, often for convenience or debugging.

---

## Inadvertent Flaws

- **Validation Error**: Failure to properly check input values, leading to inconsistent or unsafe behavior.
- **Domain Error**: Using values outside the expected range or type for a given operation or context.
- **Serialization and Aliasing**: Incorrect handling of object references or memory, causing unintended sharing or overwriting.
- **Inadequate Identification and Authentication**: Weak or missing mechanisms to verify user identity or access rights.
- **Boundary Condition Violation**: Errors at limits of data structures (e.g., buffer overflows, off-by-one mistakes).
- **Other Exploitable Logic Errors**: Flaws in program logic that attackers can manipulate to bypass controls or cause failure.
