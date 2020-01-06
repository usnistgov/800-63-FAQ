---
question: B17
title: SP 800-63B Section 5.1.1.2, *Memorized Secret Verifiers*, says that a memory-hard password derivation SHOULD be used. PBKDF2, which is extensively used, is not memory-hard. What are examples of memory-hard functions that meet this requirement? 
---
The text recommends, but does not require, the use of a memory-hard function for password derivation.

NIST considers the security of the hash (one-way) function used in key derivation to be of primary importance, and therefore requires the use of an approved (thoroughly vetted) one-way function in key derivation. BALLOON is a memory-hard and time-hard algorithm that allows the use of an approved underlying one-way function, but unfortunately it has not been widely deployed. Other algorithms such as ARGON2 are memory- and time-hard, but do not use an underlying one-way function that has been thoroughly analyzed.

While PBKDF2 is time-hard but not memory-hard, it is so widely deployed that it is not practical (at this time, anyway) to introduce a requirement for a memory-hard key derivation function, so we have presented this as a recommendation (i.e. "SHOULD").

The key derivation function is considered less critical than the one-way function that underlies it, so the specification is less prescriptive in this area and does not specify particular algorithms for key derivation.
