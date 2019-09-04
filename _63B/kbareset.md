---
question: B15
title: Is it permissible to use sets of questions and answers stored by the subscriber for password reset?
---
Self-serve password reset requires authentication of the account owner (subscriber) in order to reset the password. Response to sets of knowledge-based questions is a form of knowledge-based authentication (KBA), and is not allowed to be used as described in [FAQ B07 above](#q-b07) and [SP 800-63-3 Section 4.3.1](https://pages.nist.gov/800-63-3/sp800-63-3.html#431-authenticators):

> Knowledge-based authentication, where the claimant is prompted to answer questions that are presumably known only by the claimant, also does not constitute an acceptable secret for digital authentication.

KBA for password reset would leave the account vulnerable to takeover.

Alternative authenticators for password reset include lists of look-up secrets and out-of-band device authentication. See [NIST Special Publication 800-63B](https://pages.nist.gov/800-63-3/sp800-63b.html) for more details for these authentication processes.

