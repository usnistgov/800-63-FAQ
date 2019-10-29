---
question: C7
title: If I accept a PIV certificate issued by another organization, is that federation?
---
Federation protocols as defined by [SP-800 63C](https://pages.nist.gov/800-63-3/sp800-63c/) require an _assertion_ to be sent as part of the federation transaction. This assertion is created as a result of the subscriber authenticating to the IdP, and in response to a federation request from the RP. The assertion is unique per federated login, tied strictly to the RP, time limited, and can carry a variety of attributes depending on what the RP needs and what it is allowed to see. 

The certificate of a PIV card, on the other hand, is a static collection of attributes bound to a private key. When using a PIV for authentication, the same certificate is presented to each RP, with the same attributes embedded therein. This qualifies the PIV as a _credential_ in the 800-63-3 model, but not as an assertion. A PIV certificate can of course be used to authenticate the subscriber to the IdP, which can then create an assertion that fits all of the required criteria. 

Federation offers a number of benefits over accepting a PIV credential directly. The assertion can carry an identifier from the IdP that will be stable across different credentials for the same subscriber over time, and other attributes can be selectively disclosed to the RP depending on the RP's needs and access. When the subscriber's account is revoked, the subscriber will not be able to generate a new assertion at the IdP and the RP doesn't need to check for credential revocation directly. Federation is also more flexible in allowing different types of client applications and APIs, many of which have a difficult time accepting and processing PIV credentials.
