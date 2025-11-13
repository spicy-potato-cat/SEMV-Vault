
- Identification is the act of asserting who a person is.
- Authentication is proving that asserted identity.

such recognition occurs between people, computer processes (executing programs), network connections, devices, and similar active entities. In security, all these entities are called **==subjects==**.
### Authentication Basics and Passwords

**Fundamentals of Access Control and Authentication**
- Information security principles include **authentication**, along with confidentiality, integrity, and availability (the C.I.A. triad).
- All access control approaches rely on four fundamental mechanisms: Identification, **Authentication**, Authorization, and Accountability.
- **Identification** is the process where an unverified entity seeking access provides a label (an identifier or ID) by which the system knows them.
- **Authentication** is the access control mechanism used to validate and verify an unauthenticated entity’s purported identity.

**Authentication Factors**

Authentication relies on three widely used factors:

1. **Something you know:** Relies on what the unverified user or system knows and can recall, such as a **password**, **passphrase**, or a Personal Identification Number (PIN).
2. **Something you have:** Refers to possessing an object (e.g., a card or token).
3. **Something you are (or can produce):** Relies on individual biological characteristics (e.g., fingerprints or retina scans), often referred to as biometrics, or something produced on demand (e.g., voice patterns or signatures).

**Passwords and Passphrases**

- A **password** is a private word or combination of characters that only the user should know and is used to authenticate the user.
- Password complexity is debated in the industry; a password must be difficult to guess (not based on personal information like names, phone numbers, or dates) yet still easy for the user to remember.
- A **passphrase** is typically a phrase longer than a password, which can be used to derive a **virtual password**. For example, the phrase "MayTheForceBeWithYouAlways" might be represented as the virtual password "MTFBWYA".
- Hash functions are used in password verification systems to confirm user identity by comparing a stored hash value (message digest) calculated from the original password against a newly calculated hash from the user's input.

**Password Attacks and Protection**

Password attacks fall under the category of espionage or trespass:

- **Brute Force Password Attack:** This involves the application of computing resources to try every possible password combination. Controls that limit unsuccessful access attempts within a certain time are very effective against this method.
- **Dictionary Password Attack:** This is a variation of the brute force attack that uses a dictionary of common passwords and often includes information related to the target user (such as names of relatives or familiar numbers) to narrow the field of guesses. Rules requiring special characters make this attack less effective.
- **Rainbow Tables:** A more sophisticated attack where an attacker who gains access to an encrypted password file (such as the Security Account Manager or SAM data file) uses a **rainbow table**—a database of precomputed hash values and their corresponding plaintext values—to look up the password. This is a time-memory trade-off attack.

**Mitigation Strategies for Passwords**

- The **10.4 password rule** recommends that passwords be at least 10 characters long and contain at least one uppercase letter, one lowercase letter, one number, and one special character, which greatly enhances their strength.
- Organizations can use dictionaries to prevent employees from selecting easily guessed passwords during the reset process.
- To defend against rainbow table attacks, organizations must protect the file of hashed passwords and implement strict limits on login attempts.
- **Password hash salting** is another defense technique, involving providing a random piece of data to the hashing function when the hash is initially calculated, which defeats the time-memory trade-off used by rainbow cracking.

