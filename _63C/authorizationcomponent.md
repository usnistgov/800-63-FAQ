---
question: C04
title: What's an "authorization component", how do I get one, and how do I use it?
---
The term "authorization component" refers to an item that authorizes the RP to fetch additional information about the subscriber at runtime. This is provided to the RP alongside the assertion, but is separate from the assertion itself. It is used with an API providing additional subscriber information which can be optionally called by the RP when needed. The most common example of such an item is the OAuth 2 Access Token that is available in OpenID Connect alongside the ID Token assertion. The access token allows the RP to query the IdP's User Information Endpoint, which is an API that serves subscriber attributes. 

The authorization component could also allow the RP to access other APIs on behalf of the subscriber, which may or may not have anything to do with identity and authentication. It is common for an OAuth access token to be applied to a set of services related to the current user in addition to providing identity information with the OpenID Connect protocol. This layering allows for a powerful composition of services alongside identity.

We chose the term "authorization component" because the term "token" has an unfortunately overloaded set of definitions in this space and we wanted to avoid confusion. The definition of this term has been added in the second set of errata for 800-63C.
