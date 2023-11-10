# Password Attacks 2.4

### Attack Vectors

#### 'in-the-clear' or plaintext

When an #application does not encrypt password data, this is known as **storing them ‘ #in-the-clear’ or #plaintext.**  It would be unusual to download and app that does not encrypt data like this.  When passwords are stored in the clear, anyone with access to the #database will have access to lists of these passwords.

#Hashing is a common way to store passwords where the password is converted to a **fixed-length string of text known as a message digest.** Sometimes these generated **hashes end up being the same string for two different pieces of data** – this is known as a #collision when different inputs have the same hash.  The #hash is useful because it is a one-way conversion – once converted you cannot decrypt the data back into the original input.

#SHA-256 hash is used by many applications to generate a unique hash for password storing.

#Linux stores password hashes in the format: username / account number / hash

#Brute-Force methods for hashing include **knowing the hash of your target, and then brute forcing password attempts offline** until the password submitted produces the matching hash. These attacks happen offline because if you were to try this on the online credentials portal – you would get locked out after a few attempts. Additionally, **attackers need a lot of processing and computing power to perform these attacks,** even offline.   These attacks **can be #distributed across a #network** for faster cracking. 

#Dictionary attacks **use common words in language to narrow down possible lists of passwords** to more realistic choices people might make.

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/password-attacks-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [023 Malware](023%20Malware.md)
- [023 Anti-Malware Tools](023%20Anti-Malware%20Tools.md)
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)
- [033 Removing Malware](033%20Removing%20Malware.md)

#study #professormesser #comptia #Aplus 