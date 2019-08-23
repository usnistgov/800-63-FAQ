---
question: B06
title: Are password composition rules no longer recommended?
---
[SP 800-63B Section 5.1.1.2](https://pages.nist.gov/800-63-3/sp800-63b.html#memsecretver) paragraph 9 recommends against the use of composition rules (e.g., requiring lower-case, upper-case, digits, and/or special characters) for memorized secrets. These rules provide less benefit than might be expected because users tend to use predictable methods for satisfying these requirements when imposed (e.g., appending a ! to a memorized secret when required to use a special character). The frustration they often face may also cause them to focus on minimally satisfying the requirements rather than devising a memorable but complex secret. Instead, a blacklist of common passwords prevents subscribers from choosing very common values that would be particularly vulnerable, especially to an online attack.

Composition rules also inadvertently encourage people to use the same password across multiple systems since they often result in passwords that are difficult for people to memorize.