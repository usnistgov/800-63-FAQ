---
question: B18
title: What process does "procured" refer to when talking about authenticators?
---

[800-63B section 4.2.2](https://pages.nist.gov/800-63-3/sp800-63b.html#aal2req) states that "Authenticators _procured by_ government agencies SHALL be validated to meet the requirements of FIPS 140 Level 1." (emphasis added) The intent of the _procured by_ language is to exempt user-provided ("bring-your-own") authenticators from having to meet FIPS 140 requirements, particularly in the government-to-public use case. The FIPS 140 requirement applies only to authenticators directly purchased and/or issued by a government agency.
