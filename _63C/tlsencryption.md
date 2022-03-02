---
question: C06
title: Does the use of TLS satisfy the requirement for assertion encryption at FAL2?
---
All assertions at FAL2 have to be encrypted such that only the RP can decrypt the assertion's contents. In most cases, TLS does not provide this level of protection and therefore does not suffice for the FAL2 requirement. In practice, FAL2 encryption is almost always accomplished by using a message-level encryption on the assertion itself, such as [JSON Web Encryption](https://tools.ietf.org/html/rfc7516) of the [ID Token in OpenID Connect](https://openid.net/specs/openid-connect-core-1_0.html#IDToken).

For all assertions passed through the front channel, the TLS encryption protects only the links between the RP and browser, and browser and IdP. Since there is no direct connection between the IdP and RP, the assertion is available directly to the browser environment regardless of the status of TLS on the individual links. 

For assertions passed through the back channel, the TLS encryption does protect the assertion from attackers. However, since the TLS connection is initiated by the RP, the IdP does not necessarily have a strong association between the identity of the RP and the encryption used at the TLS layer. If the RP uses mutually-authenticated TLS, and the IdP validates the RP's certificate, and the RP's certificate is strongly tied to the identity of the RP, then the TLS channel can be considered to be an encrypted protection of the assertion. Note that the assertion still needs to be signed by the IdP at all FALs. 
