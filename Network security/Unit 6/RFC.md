Here’s the same content in pointer-style Markdown with no numbering:

---

### RFC 5322 – Internet Message Format (Text Mail Standard)

* RFC 5322 defines the standard format for Internet-based text email messages.
* It remains widely used as the basis for modern email systems.
* A message consists of two conceptual parts:
  * **Envelope** – contains transmission and delivery information.
  * **Contents** – the actual message data delivered to the recipient.
* RFC 5322 applies only to the **message contents**, not the envelope itself.
* The content format includes **header fields** that mail systems can use to generate or interpret the envelope.
* This design allows automated programs to easily process and handle messages.
* A conforming message consists of:
  * A **header section** – one or more header lines.
  * A **body section** – unrestricted text written by the sender.
* The **header and body are separated by a blank line**.
* All lines up to the first blank line are treated as **header lines**.
* Each header line follows the general structure:

  ```
  Keyword: Arguments
  ```

* Long header lines can be **folded** (continued onto multiple lines).

* Common header fields include:

  * `From`
  * `To`
  * `Subject`
  * `Date`

* Example message:

  ```
  From: alice@example.com
  To: bob@example.org
  Subject: Meeting Reminder
  Date: Tue, 12 Nov 2025 10:30:00 +0530

  Hi Bob,
  Just a reminder about our meeting this afternoon.

  Regards,
  Alice
  ```
