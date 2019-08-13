---
question: C1
title: What is an attribute reference and an attribute value, and why are these terms used?
---
[Attribute references](https://pages.nist.gov/800-63-3/sp800-63-3.html#attribute-reference) are partial attribute values, often represented as a boolean, given in response to an attribute query. Transmission of attribute references [minimizes](https://pages.nist.gov/800-63-3/sp800-63c.html#minimization) the personal information sent to a relying party (RP), enhancing the privacy of these transactions for individuals – think of the above instance of telling a RP whether a user is over a certain age as opposed to providing their full date of birth. An example that is not boolean is asserting an individual’s congressional district, rather than their full home address. An [attribute value](https://pages.nist.gov/800-63-3/sp800-63-3.html#attribute-value) is the complete value for a given attribute, like full date of birth, and is in some cases needed by the RP.

We coined the terms “reference” and “value” to effectively define methods of conveying user data and to explicitly set requirements for each. For example, credential service providers (CSPs) must provide support for both attribute references and values. We also ask that RPs, “where feasible, request attribute references rather than full attribute values.” More details can be found in [SP 800-63C](https://pages.nist.gov/800-63-3/sp800-63c.html#protecting-information).