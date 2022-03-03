---
question: C05
title: Is an assertion a kind of authenticator or credential?
---
No, an assertion is not an authenticator as defined by [SP 800-63-3](https://pages.nist.gov/800-63-3/sp800-63-3.html#def-and-acr). From the definitions, an assertion is:

> A statement from a verifier to an RP that contains information about a subscriber. Assertions may also contain verified attributes.

In other words, it's a verifiable statement from an authority that a particular user exists, has logged in, and has certain specific attributes. An assertion represents the authentication event that takes place at an IdP and conveys that information, in a verifiable fashion, to the RP. It is a *message* sent from the IdP to the RP, often directly. 

On the other hand, an authenticator is defined as:

> Something the claimant possesses and controls (typically a cryptographic module or password) that is used to authenticate the claimant’s identity.

In other words, it's something that the claimant has, either in their memory (something you know), in their physical possession (something you have), or in their person (something you are). This can be presented and proved by the subscriber when challenged by the RP, without intervention of another party. Conversely, in federation using a [back channel presentation mechanism](https://pages.nist.gov/800-63-3/sp800-63c.html#back-channel), the subscriber never sees or handles the assertion itself. The authenticator itself is established with the subscriber in such a way that they can use it many times over a period of time to authenticate to the RP. In contrast, an assertion is a time-bound message from the IdP to the RP about the subscriber, and many assertions are single-use within their system. Once an assertion has been processed, the RP needs not hold any reference to it.

In addition, a credential is:

> An object or data structure that authoritatively binds an identity - via an identifier or identifiers - and (optionally) additional attributes, to at least one authenticator possessed and controlled by a subscriber.

The key mechanism here is the binding of the *identity* of the subscriber to a specific *authenticator*. In other words, a credential combines attributes about the subscriber with an authenticator. An example would be a certificate with subscriber attributes embedded within the certificate. An assertion may contain subscriber attributes, but it does not function as an authenticator, as discussed above. 
