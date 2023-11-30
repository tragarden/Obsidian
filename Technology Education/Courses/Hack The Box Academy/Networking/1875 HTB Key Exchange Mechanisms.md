# Key Exchange 

Key Exchange is when two parties share a cryptographic key that is mathematically stored and transmitted over an insecure channel that does the encryption.

### Methods

#### Diffie-Hellman

#Diffie-Hellman is a common method of key exchange where a client can generate a key and share it with an entity it has not had prior contact with. Due to the nature of this method it is vulnerable to #MITM attacks. This is not a suitable method for low power devices because it requires a notable amount of CPU resources to generate the shared keys.

#### RSA 

Rivest-Shamir-Adleman ( #RSA)  is an algorithm for key exchange that uses large prime numbers to generate keys. It is useful for digital signatures, securing data in transit, authenticating users, and encrypting personal data.

#### ECDH

Elliptic Curve Diffie-Hellman ( #ECDH ) is a method of Diffie-Hellman key exchange that utilizes elliptic curve cryptography to share keys. This is considered a more secure and practical method of sharing than the standard Diffie-Hellman. This method has forward secrecy, meaning that even if the key is compromised, prior communications are not available to the attacker.

#### ECDSA

Elliptic Cure Digital Signature Algorithm ( #ECDSA) generates digital signatures via elliptic curve cryptography. 

### Internet Key Exchange 

Internet Key Exchange ( #IKE) is a #protocol that establishes secure sessions and cryptographic tunnels for a #VPN. It is based on Diffe-Hellman key exchanges and is used in conjunction with other cryptography methods like #RSA and Advanced Encryption Standard ( #AES). It is also used to authenticate users and clients. IKE has two modes available.

#### Main Mode

Main Mode is the default setting for IKE and while it may be slower than the other mode, it is more secure and practical. This mode performs key exchange in three phases, with each phase operating within a different set of parameters and with different keys.

#### Aggressive Mode

Aggressive mode uses only two phases where all parameters and keys are shared within the first phases. This is a faster method but does not provide the protection of identity that the Main Mode offers.

### Pre-Shared Keys

A Pre-Shared Key ( #PSK) is shared between two parties in a discreet method separate from the network using it from authentication. This adds more layers of security, although this is still susceptible to #MITM attacks. 