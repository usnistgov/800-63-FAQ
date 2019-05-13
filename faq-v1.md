*General*  
<a href="#q1">Q1: Why were identity proofing, authentication, and federation separated into distinct categories?</a>  
<a href="#q2">Q2: Each xAL has only three levels. Why change from four levels to three?</a>  
<a href="#q3">Q3: When does SP 800-63 apply to federal agencies?</a>
<a href="#q4">Q4: How do I know which xAL to choose?</a>

*Identity Proofing*  
<a href="#q-a1">Q-A1: What is the difference between the conventional proofing process and using a trusted referee at IAL2?</a>  
<a href="#q-a2">Q-A2: What is the difference between supervised remote identity proofing and unsupervised remote identity proofing?</a>  

*Authentication*  
<a href="#q-b1">Q-B1: What is a RESTRICTED authenticator and what do providers have to do differently if they use one?</a>  
<a href="#q-b2">Q-B2: Can you provide a more detailed description of "risk-based or adaptive authentication techniques" as mentioned in NIST SP 800-63B?</a>  
<a href="#q-b3">Q-B3: What is authentication intent?</a>  
<a href="#q-b4">Q-B4: What is verifier impersonation resistance?</a>  
<a href="#q-b5">Q-B5: Is password expiration no longer recommended?</a>  
<a href="#q-b6">Q-B6: Are password composition rules no longer recommended?</a>  
<a href="#q-b7">Q-B7: Is use of knowledge-based authentication permitted?</a>  
<a href="#q-b8">Q-B8: What should be in the list of common memorized secrets that is described in SP 800-63B section 5.1.1.2?</a>  

*Federation and Assertions*  
<a href="#q-c1">Q-C1: What is an attribute reference and an attribute value, and why are these terms used?</a>  
<a href="#q-c2">Q-C2: SP 800-63C Section 5.2 states “An IdP MAY disclose information on subscriber activities to other RPs within the federation for security purposes, such as communication of compromised subscriber accounts.” What does this mean?</a>  

## General

<a name="q1"></a>**Q1: Why were identity proofing, authentication, and federation separated into distinct categories?**

**A1:** As the market has matured, so has our guidance. Based on feedback from industry, and in consultation and collaboration with the White House Office of Management and Budget (OMB), we concluded that separating these three items is much more in line with how digital identity gets done in the marketplace. Individual assurance levels that can be mixed and matched provide agencies with opportunities for greater flexibility, more user convenience, enhanced privacy, and reduced risk. No brainer, right?

Instead of a single assurance level for identity proofing, authenticators, and federations, agencies can combine each element based on their risk tolerance, user populations, and the desired outcomes of the digital services they are offering. SP 800-63-3 includes a set of “choose your own adventure” [flowcharts](https://pages.nist.gov/800-63-3/sp800-63-3.html#sec6) to facilitate the process of selecting the appropriate identity proofing, authenticator, or federation assurance levels – also known as “xALs.” With these flowcharts, organizations perform a risk assessment, answer a set of functional questions, and, based on their responses, identify the most appropriate xAL for their system and users.

This flexibility also asks agencies to think innovatively about their system’s privacy requirements. This includes pseudonymous interactions even when strong, multi-factor authenticators are used. In a nutshell, the new version gives agencies the flexibility to deploy strong authentication while avoiding unnecessary proofing of users’ identities that would require collecting (and then protecting) sensitive information. This was not possible in previous versions of the document, where proofing and authentication requirements were bound together in a single assurance level. The new guidelines also require federated identity providers (IdPs) to support a range of options for querying data, like using attribute references (e.g., asserting whether an individual is older than a certain age as opposed to sharing the entire date of birth).

<a name="q2"></a>**Q2: Each xAL has only three levels. Why change from four levels to three?**

**A2:** A few reasons:
1.	In the old LOA model, LOA2 and LOA3 had very similar proofing processes. There were differences between them, but they were trivial and did not adequately address the risks associated with proofing an individual – especially if the proofing was performed remotely.
2.	For authenticators, LOA1 and LOA2 were very similar. In fact, the biggest difference is that the minimum size of passwords (i.e., memorized secrets) increased from six characters to eight. With today’s computing power, a difference in password size of two characters is negligible.
3.	When we conducted the analysis, we realized that LOA2 “done right” was really a composite of proofing an individual at IAL2 (at best) and then protecting their account with a password (AAL1). This is a big no-no logically and, if personal information is involved, expressly forbidden by [E.O. 13681](https://obamawhitehouse.archives.gov/the-press-office/2014/10/17/executive-order-improving-security-consumer-financial-transactions). So, almost by definition, an LOA2 implementation was either out of compliance or just insecure. To do LOA2 “right” in today’s threat environment, you need to do LOA3 anyway.

We did not take this decision lightly, as many federal systems are operating at LOA2. Yet after the analysis, and obtaining buy-in from OMB, we made the update to enable federal systems to effectively respond to modern vulnerabilities. Switching to [three levels](https://pages.nist.gov/800-63-3/sp800-63-3.html#-51-overview) within each assurance component provides greater security and privacy benefits and gives agencies flexibility to better meet their mission and constituent needs. Federation Assurance Levels (FALs) represent a complete revamp from prior versions, giving greater attention to federated architectures that are becoming – and we expect will continue to become –  more prominent over time.

<a name="q3"></a>**Q3: When does SP 800-63 apply to federal agencies?**

**A3:** Agencies make the risk determinations for their systems so we don’t set those rules. That said, OMB offers some good information in OMB Circular A-130, stating that legacy systems, specifically those in production on or before June 22, 2017, have 12 months to comply with a new publication, while systems currently in development or undergoing a major transformation need to use the current revision when deployed. For completeness, the language from [OMB Circular A-130](https://obamawhitehouse.archives.gov/sites/default/files/omb/assets/OMB/circulars/a130/a130revised.pdf) states (emphasis ours):

> “**For legacy information systems**, agencies are expected to meet the requirements of, and be in compliance with, NIST standards and guidelines **within one year** of their respective publication dates unless otherwise directed by OMB. The one-year compliance date for revisions to NIST publications applies only to new or updated material in the publications. **For information systems under development or for legacy systems undergoing significant changes**, agencies are expected to meet the requirements of, and be in compliance with, NIST standards and guidelines **immediately upon deployment** of the systems.”

Importantly, we’re not just finalizing SP 800-63 and throwing it over the wall. We’re here to help agencies get it right all the way into production. As needs are identified, we will consider additional resources to support agency implementations. These resources will not contain additional normative requirements, but will instead provide further discussion, technology-specific examples, and details to support implementation of the guidelines. As agencies implement SP 800-63 for their specific use cases, we plan to be available to answer questions, provide clarifications regarding the guidelines, and apply any implementation-specific lessons learned to future revisions.

<a name="q4"></a>**Q4: How do I know which xAL to choose?**

There is always a trade off in choosing the appropriate level across all categories. Higher levels do come with greater security and assurance, but at the cost of greater complexity, overhead, and potential for failure. Therefore, it is not always a matter of choosing the highest possible level and then conforming to that. Instead, the risks and potential attacks against a given application need to be considered alongside the costs of implementing a given level. It is always possible for an implementation of an identity system to exceed the requirements of its levels in practice, and the assurance levels themselves have been designed to be subsumptive, such that fulfilling requirements for level 3 automatically fulfills (and in fact exceeds) the requirements for level 2 and level 1 of that category as well. The [core document of 800-63-3 section 6](https://pages.nist.gov/800-63-3/sp800-63-3.html#sec6) provides detailed discussion on choosing an appropriate combination of xAL's. 

## Identity Proofing

<a name="q-a1"></a>**Q-A1: What is the difference between the conventional proofing process and using a trusted referee at IAL2?**

**A-A1:** We recognize that the language in the document is somewhat confusing. In our attempt to use standards-based terms like SHALL and SHOULD, avoiding terms like “unless” and “if,” this section got a little bloated. The requirement, in layman’s terms, is that agencies should make every effort to proof individuals according to the [conventional proofing process](https://pages.nist.gov/800-63-3/sp800-63a.html#normal) laid out in Section 4.4.1 of SP 800-63A. However, we know there are scenarios where the conventional proofing process, either remote or in person, is not going to work for all constituents. In other words, some individuals will just not be able to pass the conventional process or even have the identity evidence required by the conventional process. Nonetheless, we don’t want this to be a barrier for, say, a homeless veteran with no, or a lack of, documentation. This is why we added the ability to use “[trusted referees](https://pages.nist.gov/800-63-3/sp800-63a.html#referee),” such as notaries, that can assist agencies in establishing a digital identity for the applicant. This gives agencies greater flexibility to determine what works best for their stakeholders and their risk tolerance. Ultimately the agency needs to define a process, but there is a catch or two. First, trusted referees can be used to achieve IAL2, but not IAL3. Second, as an individual builds, or rebuilds, evidence of their identity, we want agencies to regularly attempt to re-proof any individual who has completed the trusted referee process via the conventional process.

<a name="q-a2"></a>**Q-A2: What is the difference between supervised remote identity proofing and unsupervised remote identity proofing?**

**A-A2:** [Supervised remote identity proofing](https://pages.nist.gov/800-63-3/sp800-63a.html#supervised) is an equivalent approach to in-person proofing and requires a robust set of features. This includes high-resolution video monitoring through an agency-controlled device (e.g., not an applicant’s personal phone), a trained operator on the other end of the video, and a number of other security controls. If those controls are all met, supervised remote identity proofing can achieve IAL3. Supervised remote identity proofing is also perfectly fine for IAL2. Unsupervised remote proofing can be used for IAL2 but not IAL3. It does not require that a remote operator participate in the session with the applicant, and typically involves commodity hardware and services that users and agencies can easily access.

## Authentication

<a name="q-b1"></a>**Q-B1: What is a RESTRICTED authenticator and what do providers have to do differently if they use one?**

**A-B1:** As threats evolve, some authenticators become less reliable, so we established the notion of “RESTRICTED” to tag authenticators if they become of concern. We didn’t make this up: the NIST cryptography team has been using this approach for some time, and we like to be consistent with other NIST efforts so we don’t confuse our stakeholders. Implementing a [RESTRICTED authenticator](https://pages.nist.gov/800-63-3/sp800-63b.html#restricted) requires the agency to assess, understand, and accept the risk associated with that authenticator.

Therefore, the agency needs to:
- Offer subscribers at least one alternate authenticator that is not RESTRICTED.
- Provide subscribers with meaningful information on the security risks of the RESTRICTED authenticator and availability of alternatives. It’s the user’s account and personal information, so we believe the user needs to participate in the risk determination process as well.
- Include in its risk assessment any additional risk to subscribers.
- Develop a migration plan for the possibility that the RESTRICTED authenticator is no longer acceptable at some point in the future.

Currently, authenticators leveraging the public switched telephone network, including phone- and Short Message Service (SMS)-based one-time passwords (OTPs) are restricted. Other authenticator types may be added as additional threats emerge. Note that, among [other requirements](https://pages.nist.gov/800-63-3/sp800-63b.html#pstnOOB), even when using phone- and SMS-based OTPs, the agency also has to verify that the OTP is being directed to a phone and not an IP address, such as with VoIP, as these accounts are not typically protected with multi-factor authentication.

<a name="q-b2"></a>**Q-B2: Can you provide a more detailed description of "risk-based or adaptive authentication techniques" as mentioned in NIST SP 800-63B?**

**A-B2:** [Risk-based or adaptive authentication systems](https://pages.nist.gov/800-63-3/sp800-63b.html#522-rate-limiting-throttling) evaluate a host of user, system, and environmental attributes; other such signals; and behavioral profiles to make an authentication decision. IP address, geolocation, time of day, transaction type, mouse movements, keystroke, and variances from typical usage norms are some of the signals used in these systems. These solutions do not currently count as a valid authenticator in and of themselves, as this information does not necessarily constitute a “secret,” and most solutions leverage proprietary ways of making an authentication decision.
We are eager to discover secure, standards-based ways to execute these processes. However, until we have a good way to define the requirements to properly execute these approaches, “risk-based” and “adaptive” techniques are considered added controls to digital authentication. If you have ideas on how we can add these as acceptable authenticator types in future guidance, please let us know all about it!

<a name="q-b3"></a>**Q-B3: What is authentication intent?**

**A-B3:** [Authentication intent](https://pages.nist.gov/800-63-3/sp800-63b.html#529-authentication-intent) is the process of demonstrating that an individual intended to authenticate. Establishing authentication intent – like entering an OTP from a device, inserting a smart card, or simply touching the device (known as proof of presence) – can act as a countermeasure against malware using the endpoint as a proxy for authenticating an attacker without the user’s knowledge. This makes it more difficult for the authenticator to be used for nefarious purposes outside the control of the legitimate user.  

<a name="q-b4"></a>**Q-B4: What is verifier impersonation resistance?**

**A-B4:** Verifier impersonation resistance places requirements on authenticators to reasonably thwart a phishing attack. Phishing attacks attempt to fool an individual into providing valid credentials to an attacker or a rogue site. At AAL3, [SP 800-63B](https://pages.nist.gov/800-63-3/sp800-63b.html) requires authenticators that use a verifier impersonation-resistant authentication protocol to prevent possible phishing attacks. There are a number of ways to do this, including various encryption protocols and digital signature technologies that bind the authenticator output to a specific protected channel. One example of a verifier impersonation-resistant authentication protocol is client-authenticated transport layer security (TLS). In this protocol, the client signs the authenticator output and earlier messages that are unique to the particular TLS connection being negotiated.

<a name="q-b5"></a>**Q-B5: Is password expiration no longer recommended?**

**A-B5:** [SP 800-63B Section 5.1.1.2](https://pages.nist.gov/800-63-3/sp800-63b.html#memsecretver) paragraph 9 states:

>"Verifiers SHOULD NOT require memorized secrets to be changed arbitrarily (e.g., periodically). However, verifiers SHALL force a change if there is evidence of compromise of the authenticator." 

Users tend to choose weaker memorized secrets when they know that they will have to change them in the near future. When those changes do occur, they often select a secret that is similar to their old memorized secret by applying a set of common transformations such as increasing a number in the password. This practice provides a false sense of security if any of the previous secrets has been compromised since attackers can apply these same common transformations. But if there is evidence that the memorized secret has been compromised, such as by a breach of the verifier's hashed password database or observed fraudulent activity, subscribers should be required to change their memorized secrets. However, this event-based change should occur rarely, so that they are less motivated to choose a weak secret with the knowledge that it will only be used for a limited period of time.

<a name="q-b6"></a>**Q-B6: Are password composition rules no longer recommended?**

**A-B6:** [SP 800-63B Section 5.1.1.2](https://pages.nist.gov/800-63-3/sp800-63b.html#memsecretver) paragraph 9 recommends against the use of composition rules (e.g., requiring lower-case, upper-case, digits, and/or special characters) for memorized secrets. These rules provide less benefit than might be expected because users tend to use predictable methods for satisfying these requirements when imposed (e.g., appending a ! to a memorized secret when required to use a special character). The frustration they often face may also cause them to focus on minimally satisfying the requirements rather than devising a memorable but complex secret. Instead, a blacklist of common passwords prevents subscribers from choosing very common values that would be particularly vulnerable, especially to an online attack.

Composition rules also inadvertently encourage people to use the same password across multiple systems since they often result in passwords that are difficult for people to memorize.

<a name="q-b7"></a>**Q-B7: Is use of knowledge-based authentication permitted?**

**A-B7:** Knowledge-based authentication (KBA), sometimes referred to as "security questions", is no longer recognized as an acceptable authenticator by SP 800-63. This was formerly permitted and referred to as a "pre-registered knowledge token" in SP 800-63-2 and earlier editions. The ease with which an attacker can discover the answers to many KBA questions, and relatively small number of possible choices for many of them, cause KBA to have an unacceptably high risk of successful use by an attacker.

A similar technique, knowledge-based verification (KBV), is permitted for use in resolving identities and, with restrictions, in remote identity verification during enrollment and proofing. See [SP 800-63A section 5.3.2](https://pages.nist.gov/800-63-3/sp800-63a.html#kbv) for details.

<a name="q-b8"></a>**Q-B8: What should be in the list of common memorized secrets that is described in [SP 800-63B section 5.1.1.2](https://pages.nist.gov/800-63-3/sp800-63b.html#memsecretver)?**

**A-B8:** Overall, it is important to discourage the use of very common passwords, particularly those that are most likely to be tried in an online password guessing attack. Some passwords that meet requirements of common composition rules are in fact quite common (e.g., Password1!) while others that do not meet composition rules are not common at all.

The dictionary, or blacklist, should contain likely common passwords without particular regard to how they are composed. If passwords with repetitive characters meet that criterion, include them. However, as our forthcoming implementation resource center will point out, the blacklist should not include every conceivable password; that is likely to cause user frustration, which often leads to predictable patterns of behavior that attackers are likely to anticipate.

## Federation and Assertions

<a name="q-c1"></a>**Q-C1: What is an attribute reference and an attribute value, and why are these terms used?**

**A-C1:** [Attribute references](https://pages.nist.gov/800-63-3/sp800-63-3.html#attribute-reference) are partial attribute values, often represented as a boolean, given in response to an attribute query. Transmission of attribute references [minimizes](https://pages.nist.gov/800-63-3/sp800-63c.html#minimization) the personal information sent to a relying party (RP), enhancing the privacy of these transactions for individuals – think of the above instance of telling a RP whether a user is over a certain age as opposed to providing their full date of birth. An example that is not boolean is asserting an individual’s congressional district, rather than their full home address. An [attribute value](https://pages.nist.gov/800-63-3/sp800-63-3.html#attribute-value) is the complete value for a given attribute, like full date of birth, and is in some cases needed by the RP.

We coined the terms “reference” and “value” to effectively define methods of conveying user data and to explicitly set requirements for each. For example, credential service providers (CSPs) must provide support for both attribute references and values. We also ask that RPs, “where feasible, request attribute references rather than full attribute values.” More details can be found in [SP 800-63C](https://pages.nist.gov/800-63-3/sp800-63c.html#protecting-information).

<a name="q-c2"></a>**Q-C2: [SP 800-63C Section 5.2](https://pages.nist.gov/800-63-3/sp800-63c.html#-52-privacy-requirements) states “An IdP MAY disclose information on subscriber activities to other RPs within the federation for security purposes, such as communication of compromised subscriber accounts.” What does this mean?**

**A-C2:** This is our way of saying a provider can share information with federation participants to increase protections for the user and the overall federation network. In a federation, the goal is to share the minimum amount of data about a user to protect their privacy. But SP 800-63C enables an IdP or an RP to disclose information about subscriber activities to other participants within the federation for security purposes, such as communicating the detection of a potentially compromised subscriber account. This approach, typically called a “shared signals model” is becoming more common in the market.
For example, an individual may use an email account to manage their online shopping account. If the email provider detects an anomaly, such as a possible account takeover, they can send this signal to the bank. The bank can do whatever they want with this information based on their risk profile and business rules. In some cases the bank may ignore the signal. In others, or if the bank got similar signals from multiple providers in a short period of time, it might choose to notify the user of suspicious activity associated with their account and use additional security measures the next time the user, or malicious actor, attempts to log in. Sharing information across the federation can help stop hackers from gaining unauthorized access to participating services.

