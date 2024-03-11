---
question: 8
title: What is considered to be “comparable” when discussing “compensating controls?” If agencies wish to use a compensating control, does it need to be “equivalent” to the original normative control?
---

The Digital Identity Guidelines are intended to provide a baseline of controls that can be consistently applied at different agencies to support interoperability and consistent risk mitigation across agencies. However, we also seek to provide agencies with the flexibility they need to address their specific user populations and threat environments. As such, under section 5.4 of NIST SP 800-63-3 it is stated that: 

> Agencies MAY determine alternatives to the NIST-recommended guidance, for the assessed xALs, based on their mission, risk tolerance, existing business processes, special considerations for certain populations, availability of data that provides similar mitigations to those described in this suite, or due to other capabilities that are unique to the agency.

> Agencies SHALL demonstrate comparability of any chosen alternative, to include any compensating controls, when the complete set of applicable SP 800-63 requirements is not implemented.

As used in the guidance the concept of “comparability” refers to the capacity of different controls to mitigate the same risks – to the greatest degree possible - when a normative control may not be technically viable or implementable for an organization's user population. This concept exists in NIST guidance to allow agencies a degree of flexibility in implementation. Controls designed to address risks in one step in the identity lifecycle do not by default address risks in another step, however, and agencies should be careful to avoid conflating different controls’ purpose and value. For example, agencies should not seek to replace a verification method – such as a physical comparison of the facial portrait on a piece of identity evidence to the face of the individual – with additional validation methods, such as collecting more data to validate against an authoritative source. These controls do not address the same risks (theft or misuse of valid evidence) and are therefore not comparable in nature. 

All alternatives need to be documented and justified in the Agency’s Digital Identity Risk Acceptance statement. It is also recommended that any potential residual risks related to the use of compensating controls are included in any documentation – though this is not explicitly required by current guidance. 
