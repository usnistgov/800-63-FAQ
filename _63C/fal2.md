---
question: C10
title: Do I need to use FAL2 for backchannel assertions?
---

If identity attributes/PII are sent over the back channel, either in the assertion or in a separate request, then FAL2 is not required in order for the information to be sufficiently protected as stated in the implementation guidelines. FAL1 should provide sufficient protection in this instance because the PII is not exposed to untrusted third parties, such as the browser. This requirement can be found in [Section 4 of SP 800-63C](https://pages.nist.gov/800-63-3/sp800-63c.html#fal).
 
The goal of FAL2 as currently defined is to provide protection against disclosure of sensitive personal information contained within the assertion as well as to provide stronger audience restriction of the assertion presentation. With front-channel presentation, this protection requires assertion encryption as presented at the conclusion of the decision chart. However, with back-channel presentation, the inclusion of identity attributes/PII in the assertion does not lead to the same vulnerability surface as the assertion is not exposed to unintended third parties such as the subscriber’s browser. Furthermore, PII can be protected from disclosure by simply not including it in the assertion at all and instead relying on an identity protocol alongside the assertion, such as the OpenID Connect standard UserInfo Endpoint protected by an OAuth 2.0 access token.

The FAL selection chart, found in [Figure 6-3 in Section 6.3 of SP 800-63-3](https://pages.nist.gov/800-63-3/sp800-63-3.html#-63-selecting-fal), provides more stringent advice than what is required by the normative statements in the guidelines. However, the selection chart is intended as complementary advice and does not provide normative requirements. The FAL selection chart provides advice above what is strictly required by the text, and this inconsistency will be addressed in a future version of the guidelines.

For additional information, [Section C.2.3 of the SP 800-63-3 Implementation Resources](https://pages.nist.gov/800-63-3-Implementation-Resources/63C/SecurityParameters/#s-c-2-4) goes into more detail on selecting and reaching FAL2.