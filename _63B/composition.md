---
question: B10
title: Does SP 800-63B require that we remove our password composition (complexity) rules?
---

[SP 800-63B Section 5.1.1.2](https://pages.nist.gov/800-63-3/sp800-63b.html#memsecretver) states in part:

> Verifiers SHOULD NOT impose other composition rules (e.g., requiring mixtures of different character types or prohibiting consecutively repeated characters) for memorized secrets.

This text is a recommendation, not a normative requirement (i.e., "should" rather than "shall" in text). However, research has shown that composition rules do not significantly improve the security of selected passwords. Composition rules often have the opposite effect as users tend to avoid or shortcut the rules by making predictable changes, resulting in weaker passwords and less security. Instead, SP 800-63B requires the use of a blacklist of common passwords that are not acceptable for use. We do recommend increased password length as a key password security control, especially through encouraging the use of passphrases.

[SP 800-63B Appendix A.3](https://pages.nist.gov/800-63-3/sp800-63b.html#a3-complexity) contains a more detailed rationale for this recommendation.
