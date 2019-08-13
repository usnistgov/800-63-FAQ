---
question: B1
title: What is a RESTRICTED authenticator and what do providers have to do differently if they use one?
---
As threats evolve, some authenticators become less reliable, so we established the notion of “RESTRICTED” to tag authenticators if they become of concern. We didn’t make this up: the NIST cryptography team has been using this approach for some time, and we like to be consistent with other NIST efforts so we don’t confuse our stakeholders. Implementing a [RESTRICTED authenticator](https://pages.nist.gov/800-63-3/sp800-63b.html#restricted) requires the agency to assess, understand, and accept the risk associated with that authenticator.

Therefore, the agency needs to:
- Offer subscribers at least one alternate authenticator that is not RESTRICTED.
- Provide subscribers with meaningful information on the security risks of the RESTRICTED authenticator and availability of alternatives. It’s the user’s account and personal information, so we believe the user needs to participate in the risk determination process as well.
- Include in its risk assessment any additional risk to subscribers.
- Develop a migration plan for the possibility that the RESTRICTED authenticator is no longer acceptable at some point in the future.

Currently, authenticators leveraging the public switched telephone network, including phone- and Short Message Service (SMS)-based one-time passwords (OTPs) are restricted. Other authenticator types may be added as additional threats emerge. Note that, among [other requirements](https://pages.nist.gov/800-63-3/sp800-63b.html#pstnOOB), even when using phone- and SMS-based OTPs, the agency also has to verify that the OTP is being directed to a phone and not an IP address, such as with VoIP, as these accounts are not typically protected with multi-factor authentication.