---
question: B12
title: What is NIST's position on the use of password managers?
---
Password managers offer greater security and convenience for the use of passwords to access online services.  Greater security is achieved principally through the capability of most password manager applications to generate unique, long, complex, easily changed passwords for all online accounts and the secure encrypted storage of those passwords either through a local or cloud-based vault. Greater convenience is provided by the use of a single master password to access the password vault rather than attempting to memorize different passwords for all accounts. Most password manager applications offer additional capabilities that enhance both convenience and security such as storage of credit card and frequent flyer information and autofill functionality.

The compromise of the master secret to a password vault would require all passwords in the vault to be recreated. However, many password managers today provide two-factor capability and are designed in a way that cloud password services are not able to access the vault, even if compromised. Password managers contain much information that is valuable to cyber criminals, making them high-value targets, so securing these vaults is essential.

In SP 800-63B, NIST has not explicitly recommended the use of password managers, but recommends that verifiers permit the use of "paste" functionality so that the subscriber can use a password manager if desired. If using a password manager, subscribers should:

* Choose a long, complex passphrase for the master password to the password manager and protect it from being stolen. A passphrase can be made sufficiently long to protect against attacks while still allowing memorization.
* Create unique passwords for all accounts or use the capability of most program managers to generate random, unique, complex passwords for each account. 
* Avoid password managers that allow recovery of the master password. Any compromise of the master password through account recovery tools can compromise the entire password vault.
* Use multi-factor authentication for program manager applications that allow that capability.
* Use the password generator capability in most password managers to generate complex, random text answers to online "security" questions for those sites still using them.
