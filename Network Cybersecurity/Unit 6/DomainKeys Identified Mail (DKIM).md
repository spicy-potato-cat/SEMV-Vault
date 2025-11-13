DKIM is a security protocol. It is used to verify the authenticity of the sender of the mail. 


Process:

1. Sender signs the mail using theirs's private key
2. Once the e-mail is received to the recipient, Receiver sends a query to the sending domain to check if the sign is valid
3. Sending Domain Server validates the private key queried against the list of public keys of the authorized users
4. Based on the returned values from the Domain Server receiving server may accept/reject or perform appropriate actions to the mail

![[Pasted image 20251112152212.png|600]]