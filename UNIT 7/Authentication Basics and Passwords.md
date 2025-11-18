# Authentication Basics and Passwords

## Overview

**Definition**: Authentication is the process of verifying the identity of a user, device, or system attempting to access a resource. It answers the question: "Are you who you claim to be?"

Authentication is one of the three pillars of security, along with:
- **Identification** - Claiming an identity (username, ID, etc.)
- **Authentication** - Proving that identity
- **Authorization** - Determining what the authenticated entity can access

---

## Authentication Factors

Authentication methods are categorized into three main factors:

### 1. **Something You Know** (Knowledge Factor)
- Passwords
- PINs (Personal Identification Numbers)
- Passphrases
- Security questions
- Pattern locks

### 2. **Something You Have** (Possession Factor)
- Physical tokens
- Smart cards
- Security keys (e.g., YubiKey)
- Mobile devices (for SMS/app-based codes)
- One-Time Password (OTP) generators

### 3. **Something You Are** (Inherence Factor)
- Biometric authentication:
	- Fingerprints
	- Facial recognition
	- Iris/retina scans
	- Voice recognition
	- Hand geometry

### 4. **Additional Factors** (Modern Extensions)
- **Something You Do** - Behavioral biometrics (typing patterns, gait analysis)
- **Somewhere You Are** - Location-based authentication (GPS, IP address)

---

## Multi-Factor Authentication (MFA)

**Definition**: Using two or more authentication factors from different categories to verify identity.

### Types:
1. **Two-Factor Authentication (2FA)** - Uses exactly two factors
2. **Multi-Factor Authentication (MFA)** - Uses two or more factors

### Benefits:
- Significantly increases security
- Reduces risk of unauthorized access
- Protects against password theft
- Compliance with security standards

### Common MFA Implementations:
- Password + SMS code
- Password + authenticator app (Google Authenticator, Microsoft Authenticator)
- Password + biometric (fingerprint/face ID)
- Smart card + PIN

---

## Password Authentication

### What is a Password?

A password is a secret string of characters used to authenticate a user's identity. It remains the most common authentication method despite known vulnerabilities.

### Password Characteristics

#### Strong Password Requirements:
1. **Length** - Minimum 12-16 characters (longer is better)
2. **Complexity** - Mix of:
   - Uppercase letters (A-Z)
   - Lowercase letters (a-z)
   - Numbers (0-9)
   - Special characters (!@#$%^&*)
3. **Uniqueness** - Different for each account
4. **Unpredictability** - Not based on personal information
5. **Non-dictionary** - Not found in common word lists

#### Weak Password Examples:
- Dictionary words: "password", "admin"
- Personal information: birthdates, names
- Sequential patterns: "123456", "abcdef"
- Common substitutions: "P@ssw0rd"
- Keyboard patterns: "qwerty", "asdfgh"

---

## Password Security Threats

### 1. **Brute Force Attacks**
- Systematically trying all possible combinations
- Time-intensive but effective against weak passwords
- **Defense**: Account lockout policies, rate limiting

### 2. **Dictionary Attacks**
- Using lists of common words and phrases
- Much faster than brute force
- **Defense**: Avoid dictionary words, use passphrases

### 3. **Rainbow Table Attacks**
- Pre-computed hash tables for password cracking
- Effective against unsalted hashes
- **Defense**: Use salted hashing algorithms

### 4. **Credential Stuffing**
- Using leaked credentials from one breach on other services
- Exploits password reuse
- **Defense**: Unique passwords for each service

### 5. **Phishing**
- Tricking users into revealing passwords
- Social engineering attack
- **Defense**: User education, anti-phishing tools

### 6. **Keylogging**
- Recording keystrokes to capture passwords
- Malware-based attack
- **Defense**: Anti-malware software, virtual keyboards

### 7. **Shoulder Surfing**
- Observing someone entering their password
- Physical security threat
- **Defense**: Privacy screens, awareness

### 8. **Password Spraying**
- Trying common passwords against many accounts
- Avoids account lockouts
- **Defense**: Ban common passwords, implement CAPTCHA

---

## Password Management Best Practices

### For Users:

1. **Create Strong Passwords**
   - Use passphrases: "Correct-Horse-Battery-Staple"
   - Use password generators
   - Make them memorable but complex

2. **Never Reuse Passwords**
   - Each account should have a unique password
   - Use password managers to track multiple passwords

3. **Use Password Managers**
   - Examples: LastPass, 1Password, Bitwarden, KeePass
   - Encrypted storage of all passwords
   - Generate strong random passwords
   - Only need to remember one master password

4. **Enable MFA Everywhere**
   - Add extra security layer
   - Use authenticator apps over SMS when possible

5. **Regular Updates**
   - Change passwords periodically (every 90 days recommended)
   - Immediate change if breach suspected
   - Don't reuse recent passwords

6. **Secure Storage**
   - Never write down passwords
   - Don't share passwords
   - Don't store in plain text files

### For Organizations:

1. **Password Policies**
   - Minimum length requirements (12-16+ characters)
   - Complexity requirements
   - Password history (prevent reuse)
   - Maximum age (forced periodic changes)
   - Minimum age (prevent rapid changes)

2. **Password Storage**
   - **Never store passwords in plain text**
   - Use strong hashing algorithms:
     - bcrypt
     - scrypt
     - Argon2
     - PBKDF2
   - Add salt to prevent rainbow table attacks
   - Use pepper for additional security

3. **Account Lockout Policies**
   - Lock account after N failed attempts (typically 3-5)
   - Temporary lockout (15-30 minutes)
   - Admin notification for repeated lockouts

4. **Password Reset Mechanisms**
   - Secure reset process (email verification, security questions)
   - Temporary passwords that must be changed
   - Time-limited reset links

5. **User Education**
   - Security awareness training
   - Phishing simulations
   - Password hygiene guidelines

---

## Password Hashing and Encryption

### Hashing vs. Encryption

| Feature | Hashing | Encryption |
|---------|---------|------------|
| **Reversible** | No (one-way function) | Yes (with key) |
| **Purpose** | Verification | Confidentiality |
| **Output** | Fixed-size hash | Variable-size ciphertext |
| **Use Case** | Password storage | Data protection |

### Hashing Process:

```
Password → Hash Function → Hash Value (stored in database)
```

During authentication:
```
Input Password → Hash Function → Compare with Stored Hash
```

### Salting:

**Salt**: Random data added to password before hashing

```
Password + Salt → Hash Function → Salted Hash
```

**Benefits**:
- Each password has unique hash even if passwords are identical
- Defeats rainbow table attacks
- Increases computational cost for attackers

### Common Hashing Algorithms:

1. **MD5** (Message Digest 5)
   - ❌ Deprecated - Not secure
   - Fast but vulnerable to collisions

2. **SHA-1** (Secure Hash Algorithm 1)
   - ❌ Deprecated - Not secure
   - Collision attacks demonstrated

3. **SHA-256/SHA-512** (SHA-2 family)
   - ✅ Acceptable but not ideal for passwords
   - Too fast for password hashing

4. **bcrypt** ✅ Recommended
   - Built-in salt
   - Adjustable cost factor
   - Widely supported

5. **scrypt** ✅ Recommended
   - Memory-hard function
   - Resistant to hardware attacks

6. **Argon2** ✅ Most Recommended
   - Winner of Password Hashing Competition (2015)
   - Memory-hard with tunable parameters
   - Three variants: Argon2d, Argon2i, Argon2id

---

## Password Alternatives and Future Technologies

### 1. **Passwordless Authentication**
- Biometric authentication
- Hardware security keys (FIDO2)
- Magic links (email-based)
- Push notifications

### 2. **Single Sign-On (SSO)**
- One authentication for multiple applications
- Examples: Google, Microsoft, Okta
- Reduces password fatigue
- Centralized security management

### 3. **Passkeys**
- FIDO2/WebAuthn standard
- Public-key cryptography
- Phishing-resistant
- No shared secrets

### 4. **Certificate-Based Authentication**
- Digital certificates
- PKI (Public Key Infrastructure)
- Common in enterprise environments

---

## Common Password Policies

### NIST Guidelines (Updated 2017):

1. **Minimum length of 8 characters** (12-16+ recommended)
2. **No composition rules** (no mandatory special characters)
3. **No periodic password changes** (unless breach suspected)
4. **Screen passwords against breach databases**
5. **Allow all printable characters**
6. **No password hints**
7. **Rate limit authentication attempts**

### Industry Best Practices:

1. Enforce MFA for all accounts
2. Implement account lockout after failed attempts
3. Monitor for credential stuffing attacks
4. Ban commonly used passwords
5. Provide password strength meters
6. Educate users on password security
7. Implement secure password reset processes

---

## Password Security Metrics

### Password Entropy

**Entropy**: Measure of password randomness and unpredictability

**Formula**: 
$$E = \log_2(R^L)$$

Where:
- $E$ = Entropy (bits)
- $R$ = Size of character set
- $L$ = Length of password

**Character Set Sizes**:
- Lowercase only: 26
- + Uppercase: 52
- + Numbers: 62
- + Special chars: ~94

**Example**:
- 8-character lowercase: $\log_2(26^8) ≈ 37.6$ bits
- 8-character mixed case + numbers + special: $\log_2(94^8) ≈ 52.4$ bits

**Recommended Entropy**: 80+ bits for strong passwords

### Time to Crack

Depends on:
- Password complexity
- Hashing algorithm
- Attacker's computational power
- Online vs. offline attack

**Rough Estimates** (offline attack, bcrypt):
- 8-char lowercase: Minutes to hours
- 8-char complex: Days to weeks
- 12-char complex: Centuries
- 16-char complex: Millions of years

---

## Related Concepts

### Access Control
- [[Firewalls]] - Network-level access control
- [[VPNS, SSH]] - Secure remote authentication
- [[IDPS]] - Monitoring authentication attempts
- [[SIEM]] - Logging and analyzing authentication events

### Security Principles
- **Least Privilege** - Grant minimum necessary access
- **Defense in Depth** - Multiple layers of security
- **Zero Trust** - Never trust, always verify

---

## Key Takeaways

1. ✅ Passwords remain the most common authentication method
2. ✅ Strong passwords are long, complex, and unique
3. ✅ MFA significantly improves security
4. ✅ Use password managers to handle complexity
5. ✅ Organizations must hash and salt passwords
6. ✅ Never store passwords in plain text
7. ✅ Educate users on password security
8. ✅ Move toward passwordless authentication when possible
9. ✅ Regular security audits and policy updates
10. ✅ Monitor for breach databases and credential stuffing

---

## References

- NIST SP 800-63B: Digital Identity Guidelines
- OWASP Authentication Cheat Sheet
- Password Hashing Competition
- FIDO Alliance Standards

#cybersecurity #authentication #passwords #security #access-control