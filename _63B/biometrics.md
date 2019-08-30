---
question: B13
title: Is the use of biometrics acceptable in multifactor authentication?
---
NIST SP 800-63B supports the use of biometrics as an authentication factor with some limitations. Biometrics may be used only as part of multi-factor authentication in conjunction with a specific physical authenticator (something you have). If biometrics are used in multi-factor authentication the following requirements apply:

* An authenticated protected channel between sensor and the verifier must be established, or the sensor must be integrated with the endpoint in a manner that resists sensor replacement
* The sensor or endpoint must be authenticated prior to capturing the biometric sample from the claimant
* The biometric system must operate with a False Match Rate (FMR) of 1 in 1000 or better [see ISO/IEC 2382-37]. This FMR applies under conditions of a conformant attack (i.e., zero-effort impostor attempt) as defined in ISO/IEC 30107-1
* The biometric system must limit consecutive failed authentication attempts
* The verifier must make a determination of sensor and endpoint performance, integrity, and authenticity based on the requirements presented above.

The unlocking of a device through biometric match may not be considered to meet these requirements since it is generally not possible for the verifier to obtain any information on how, or whether, the device was unlocked.

NIST recommends that the biometric system implement Presentation Attack Detection (PAD). NIST is considering PAD implementation as a requirement in the future.

Please see [SP 800-63B Section 5.2.3](https://pages.nist.gov/800-63-3/sp800-63b.html#biometric_use) for additional implementation guidance for the use of biometrics as an authentication factor.

 Most authenticators using biometrics will function as multi-factor authenticators where the biometric unlocks a secret stored in the authenticator. A memorized secret (often a PIN) can also be used to unlock the same secret, as is common in many mobile devices.