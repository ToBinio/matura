IPsec is an [[Standart Organasitations|IETF]] standard that defines how a [[VPN]] can be secured across IP networks. IPsec protects and authenticates IP packets between source and destination and provides these essential security functions:
- **Confidentiality** - Uses encryption algorithms to prevent cybercriminals from reading the packet contents.
- **Integrity** - Uses hashing algorithms to ensure that packets have not been altered between source and destination.
- **Origin authentication** - Uses the Internet Key Exchange (IKE) protocol to authenticate source and destination.
- **Diffie-Hellman** – Used to secure key exchange.

---
## Technologies
- IPsec is not bound to any specific rules for secure communications.
- IPsec can easily integrate new security technologies without updating existing IPsec standards.
- The open slots in the IPsec framework shown in the figure can be filled with any of the choices that are available for that IPsec function to create a unique security association (SA).
![[ipSec Tech.png]]

### Protcol
Choosing the IPsec protocol encapsulation is the first building block of the framework.
- IPsec encapsulates packets using Authentication Header (AH) or Encapsulation Security Protocol (ESP).
- The choice of AH or ESP establishes which other building blocks are available.
	- AH is appropriate only when confidentiality is not required or permitted.
	- ESP provides both confidentiality and authentication

### Confidentiality
The degree of confidentiality depends on the encryption algorithm and the length of the key used in the encryption algorithm.    

The number of possibilities to try to hack the key is a function of the length of the key - the shorter the key, the easier it is to break.

![[IPsec Confidentiality.png]]

The encryption algorithms highlighted in the figure are all symmetric key cryptosystems:
- DES uses a 56-bit key.
- 3DES uses three independent 56-bit encryption keys per 64-bit block.
- AES offers three different key lengths: 128 bits, 192 bits, and 256 bits.
- SEAL is a stream cipher, which means it encrypts data continuously rather than encrypting blocks of data. SEAL uses a 160-bit key.

![[IPsec Confidentiality overview.png]]

### Integrity
- Data integrity means that the data has not changed in transit.
- A method of proving data integrity is required.
- The Hashed Message Authentication Code (HMAC) is a data integrity algorithm that guarantees the integrity of the message using a hash value.
- Message-Digest 5 (MD5) uses a 128-bit shared-secret key.
- The Secure Hash Algorithm (SHA) uses a 160-bit secret key.

![[IPsec Integrity.png]]

### Authorication
There are two IPsec peer authentication methods:

**Pre-shared key (PSK)** 
(PSK) value is entered into each peer manually.
- Easy to configure manually
- Does not scale well
- Must be configured on every peer

**Rivest, Shamir, and Adleman (RSA)** 
authentication uses digital certificates to authenticate the peers.
- Each peer must authenticate its opposite peer before the tunnel is considered secure.

![[Authentication.png]]

### Secure Key Exchange with Diffie - Hellman
DH provides allows two peers to establish a shared secret key over an insecure channel.

Variations of the DH key exchange are specified as DH groups:
- DH groups 1, 2, and 5 should no longer be used.
- DH groups 14, 15, and 16 use larger key sizes with 2048 bits, 3072 bits, and 4096 bits, respectivel
- DH groups 19, 20, 21 and 24 with respective key sizes of 256 bits, 384 bits, 521 bits, and 2048 bits support Elliptical Curve Cryptography (ECC), which reduces the time needed to generate keys.

![[IPsec Hellman.png]]