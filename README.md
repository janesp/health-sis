# Health SSI

Healthcare use cases based on SSI

## Background

This approach was first discussed in a [DICE 2023 unConference](https://diceurope.org) [session](https://docs.google.com/document/d/1fKte0oN_bokCRNbwDJTzpMtDx5OY3wNPgA_UYfJFHt4).

## Current Situation

Various national electronic health record (EHR) initiatives are based on plain text documents («expensive dropbox»):

* Switzerland (opt-in) - Elektronisches Patientendossier (EPD)
* Germany (opt-in) - Elektronische Patientenakte (EPA)
* Austria (opt-out) - Elektronische Gesundheitsakte (ELGA)

National EHRs based on opt-in have almost no content due to serious adoption problems. Instead, personal health data is spread over many siloed platforms in a non-interoperable manner.

Based on increasing practical experiences, there is now wide agreement about a need for standardized, structured and trustworthy personal health data (both clinical and administrative).

While DACH countries typically have a quite restrictive approach for personal health data (driven by data protection representatives), nordic countries are much more pragmatic (see [webinar](https://youtu.be/8_oLi-a4Lck)). Respective standards would be readily available ([FHIR](http://www.hl7.org/fhir/), [openEHR](https://openehr.org), [SNOMED](https://www.snomed.org/)).

## Existing First Prototype

To move towards structured clinical health data, a [first prototype](https://youtu.be/T5bYmy_oXMo) was built («EPD 2.0»). Use cases were chosen along the highest «pain levels», based on workshops with representatives of health providers (hospitals, general practitioners) and a resulting roadmap:

* Medication plan
* Vaccination record
* International patient summary
* Simulated access the EPD

Using existing standards and technologies (e.g. a centralized FHIR-Server), the very first version of the prototype was completed in two months time, also implementing a clean backend and app architecture to address data protection requirements from the beginning.

See the «OnceHealth» [positioning document](https://drive.google.com/file/d/1GGJXCBIJBfN4DQXXgrpdBIyjkvemgXl4) for more information about the envisaged ehealth ecosystem and a pragmatic approach to get results quickly.

## Idea

As outlined in the [positioning document](https://drive.google.com/file/d/1GGJXCBIJBfN4DQXXgrpdBIyjkvemgXl4), the main objective is to provide a citizen centric (vs. siloed) approach for personal health data.

To address the shortcomings of centralized data stores, a proof of concept (prototype) of a wallet-based personal health record (PHR) shall be implemented («EPD 3.0»), based on existing standards and the [Swiss E-ID sandbox](https://github.com/e-id-admin/public-sandbox-trustinfrastructure) (i.e. Hyperledger Indy, aca-py). To keep the SSI-part simple, using the [Verifiable Credential Management System](https://github.com/SSI-Solutions/vcms/tree/main) (VCMS) is envisaged. VCMS provides an abstraction layer of underlying SSI technologies, which allows simplified transitions to technicial developments (e.g. upcoming sandbox 2.0).

To focus on relevant elements, the PoC is time-boxed by purpose and shall be completed in the first half of 2024, as time is a factor.

A subset of the [international patient summary](https://international-patient-summary.net/) is envisaged as scope, as specifications already exist.

The following stages are envsiaged for the PoC implementation:

* Technical proof - interaction use cases with very minimalistic verifiable credentials, based on anoncreds
* Usage and demonstration proof - extended use cases with more realistic verifiable credentials, based on json-ld (as FHIR specifications are available in this format)

The main purpose of the PoC is to demonstrate an implementation based on SSI principles to showcase tangible results to potential users and investors for further refinement and funding.

## Use Cases

To showcase the interaction of several participants of the healthcare system and their wallets, a few simple and easy to comprehend use cases are envisaged for the implementation of the PoC:

* The patient John Miller carries a wallet with information of an international patient summary (allergies, medication, etc.) and a health insurance card in the form of previously issued VCs
* John enters the office of Dr. Charles Brewster and registers through a QR code; this initiaites a proof request for insurance and health information in John's wallet, which is subsequently confirmed by John
* Dr. Brewster issues the findings of his examination as a VC and prescribes some drugs, also in the form of VCs
* After the visit, John orders the drugs through the «Universal Pharmacy» online store by presenting the prescription VCs

## References

* FHIR standards - http://www.hl7.org/fhir/
* International patient summary - https://international-patient-summary.net/
* Swiss FHIR definitions - https://fhir.ch/
* SNOMED CT - clinical standards - https://www.snomed.org/
* openEHR - https://openehr.org
* Positioning document, ehealth ecosystem «OnceHealth»
* E-ID sandbox - https://www.eid.admin.ch/eid/de/home/sandbox/sandbox.html
* Swiss E-ID Github - https://github.com/e-id-admin
* Webinar health data and cultures - https://youtu.be/8_oLi-a4Lck (see Youtube channel for more webinars)
* Working Group Health: DIDAS Statement on the Consultation EPDG - https://www.didas.swiss/de/2023/11/13/didas-stellungnahme-zur-epdg-revision/

