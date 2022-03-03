---
question: C02
title: What is disclosure of information for security purposes?
---

SP 800-63C Section 5.2 states “An IdP MAY disclose information on subscriber activities to other RPs within the federation for security purposes, such as communication of compromised subscriber accounts.” What does this mean?
 
This is our way of saying a provider can share information with federation participants to increase protections for the user and the overall federation network. In a federation, the goal is to share the minimum amount of data about a user to protect their privacy. But SP 800-63C enables an IdP or an RP to disclose information about subscriber activities to other participants within the federation for security purposes, such as communicating the detection of a potentially compromised subscriber account. This approach, typically called a “shared signals model” is becoming more common in the market.

For example, an individual may use an email account to manage their online shopping account. If the email provider detects an anomaly, such as a possible account takeover, they can send this signal to the bank. The bank can do whatever they want with this information based on their risk profile and business rules. In some cases the bank may ignore the signal. In others, or if the bank got similar signals from multiple providers in a short period of time, it might choose to notify the user of suspicious activity associated with their account and use additional security measures the next time the user, or malicious actor, attempts to log in. Sharing information across the federation can help stop hackers from gaining unauthorized access to participating services.

See [SP 800-63C Section 5.2](https://pages.nist.gov/800-63-3/sp800-63c.html#-52-privacy-requirements).