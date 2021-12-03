---
question: B19
title: Should substrings of memorized secrets be checked against the blocklist of common passwords?
---
The requirement to compare prospective memorized secrets against a list of commonly used, expected, or compromised values in [SP 800-63B Section 5.1.1.2](https://pages.nist.gov/800-63-3/sp800-63b.html#memsecretver), along with the rate limiting requirements in [Section 5.2.2](https://pages.nist.gov/800-63-3/sp800-63b.html#throttle), is intended to blunt online guessing attacks against memorized secrets. It is intended that this requirement apply to the memorized secret as a whole, and not to substrings. If applied to substrings, this might make it more difficult to construct longer memorized secrets such as passphrases. Longer memorized secrets are almost always stronger than shorter ones.

Note also that the list of commonly used memorized secrets does not need to include a dictionary of words. Some words that are commonly used, such as 'password', should be included but since the intent is to prevent the use of the most commonly selected memorized secrets, the use of the entire dictionary is probably overkill, while some non-words such as 'qwertyuiop' and '12345678' should probably be included.
