# NTLM Authentication

#NTLM is a type of hash name that is related to both the #LM and #NT #hash. These are authentication methods used in conjunction with #NTLMv1, and #NTLMv2 protocols. 

### LM 

#LAN Manager ( #LM / #LANMAN) is an outdated and insecure password mechanism that was introduced to #Microsoft #Windows in the late 80's. This hashes your submitted credentials into a code that is easily cracked if an attacker gains access. LM hashes can be disabled via Group Policies.

### NTHash (NTLM)

NT LAN Manager is a #challenge-response #protocol that uses hashes and three message types for authentication. These hashes are stored locally within the #SAM or NTDS.DIT #database. Two hashed password values are used to foster this authentication: and NT hash and an LM hash. 

1. #NEGOTIATE_MESSAGE is sent from a #client to a server. 
2. Server responds with a #CHALLENGE_MESSAGE used to verify the user. 
3. The client will then respond with an #AUTHENTICATE_MESSAGE.
4. Hashes are stored in the SAM database or the NTDS.DIT database on the Domain Controllers.

The NTLM hashes are stronger than LM hashes, but are still succeptible to #brute-force attacks and online dictionaries. These are vulnerable to #Pass-the-Hash type attacks.

The material used for these notes has further information about NTLMv1 and NTLMv2 protocols and how they operate.

### Domain Cached Credentials

Domain Cached Credentials ( #DCC) or #MSCache resolves an issue of a host on the domain being unable to communicate to it's local #domain controller ( #DC).  This is a more modern and secure method for authenticating credentials.