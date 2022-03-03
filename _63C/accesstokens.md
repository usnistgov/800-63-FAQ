---
question: C08
title: Are APIs and access tokens covered by FAL?
---

No, API access and any tokens used for API access are not covered by FAL. The federated assurance level is meant to cover the conveyance of identity information from an IdP to an RP through an assertion. This constitutes a federated login event to the RP. However, if that RP accesses an API, this is outside of the federated login. When that API dereferences or interprets the access token, this is not a login event since the user may or may not be present when the client is acting on the user's behalf. Therefore, both of these aspects are outside the scope of SP 800-63C and the FAL designations.

For example, let's say that you've got an email client that's using an OpenID Connect (OIDC) login and getting an OAuth access token to call a cloud-based email API. The FAL covers the process of logging in to the email client itself, so that the email client knows who the user is through the ID Token. The FAL does not cover the use of the access token to call the email API, nor does it cover the process that the email API uses to figure out which user is represented by the access token. 
