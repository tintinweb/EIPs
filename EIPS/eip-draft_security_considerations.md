---
eip: <to be assigned>
title: Security Considerations
author: tintinweb (tintinweb) <martin.ortner@consensys.net>
discussions-to: https://github.com/ethereum/EIPs/issues/XXX
status: Draft
type: Meta
created: 2019-01-20
requires: 1
---

<!--You can leave these HTML comments in your merged EIP and delete the visible duplicate text guides, they will not appear and may be helpful to refer to if you edit it again. This is the suggested template for new EIPs. Note that an EIP number will be assigned by an editor. When opening a pull request to submit your EIP, please use an abbreviated title in the filename, `eip-draft_title_abbrev.md`. The title should be 44 characters or less.-->

## Simple Summary
<!--"If you can't explain it simply, you don't understand it well enough." Provide a simplified and layman-accessible explanation of the EIP.-->

This document describes an improvement to the Ethereum Improvement Proposal (EIP) system as defined in EIP-1, so that all EIPs MUST include a "Security Considerations" section. Requirements include discussion of security considerations in the design, indicating which aspects of the protocol may be affected (networking, virtual machine, etc.), listing risks and how they have been mitigated. This proposal is adapted from the IETF's Request for Comments (RFC) system ([RFC 7322 - Section 4.8.5](https://tools.ietf.org/html/rfc7322#section-4.8.5)).

## Abstract
<!--A short (~200 word) description of the technical issue being addressed.-->

The EIP system defines a minimum set of information and criteria to be included in a proposal. Security discussions take place but important considerations are not always documented with the EIP. Furthermore, security-related information and design decisions might blend into technical documentation, lacking visibility and not being easily available for the security community posing a greater threat for changing security aspects to not be considered in later phases of the EIP (e.g. implementation phase).

Existing proposed changes to the ethereum protocol (e.g. [EIP-1057 - PoW change Ethhash to ProgPoW](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1057.md)) and a recently surfaced security vulnerability introduced with [EIP-1283](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1283.md) that was part of the initial Constantinople hard-fork demonstrate the importance of security considerations. Following discussions about maturing the EIP system to better address security in the change management process, we propose to pro-actively encourage a security discussion by adding a "Security Considerations" section to the minimum set of information provided with an EIP. It is important to document security considerations as part of the EIP to better manage and understand the risks introduced as well as to provide a basis for exploring and assessing the potential impact of the proposed change.

## Motivation
<!--The motivation is critical for EIPs that want to change the Ethereum protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the EIP solves. EIP submissions without sufficient motivation may be rejected outright.-->

The technology community established various ways of publishing memoranda to exchange important information and guidelines as well as to discuss and agree on standards and improvements that can manifest in changes to processes and technology.
Change is inherent in any organization and technology. Given the potential impact and far-reaching consequences - especially in the DLT/Blockchain ecosystem - it is critical to take an organized approach to prevent unintended consequences and therefore reduce risk.

At present individual security considerations are not part of the EIP as defined with EIP-1 and therefore not consistently documented nor easily accessible for discussion.

"Security Considerations" are part of many proposal and change management systems. In information and communications technology, one of the most widely used and understood systems is the Request for Comments (RFC) system. [RFC 1543 - Instructions to RFC Authors (1993)](https://tools.ietf.org/html/rfc1543#section-8) first introduced a "Security Considerations" section to RFC noting:

    All RFCs must contain a section near the end of the document that
    discusses the security considerations of the protocol or procedures
    that is the main topic of the RFC.

With [RFC 3552 - Guidelines for Writing RFC Text on Security Considerations (2003)](https://tools.ietf.org/html/rfc3552) an attempt was made to give further guidance and better align expectations of the information documented as well as to provide background information and describe the terminology used as well as outline important threat models to build a common ground for security discussions. "Security Considerations" is still an integral part of RFC as per [RFC 7322 - RFC Style Guide (2014)](https://tools.ietf.org/html/rfc7322#section-4.8.5).

Embedding security into the EIP system is expected to further raise the quality of submissions, encourage security discussions, provide documentation for follow-up security activities and a basis for a security triage while reducing the risk of accepting proposals that failed to sufficiently consider security.

The goals of requiring a mandatory "Security Considerations" section are as follows:

- Encourage document authors to consider security in their designs.
- Inform the reader of security relevant information, design decisions, concerns, issues, implementation notes, and status and outcome of security discussions to raise the visibility of changes that are affecting security.
- Provide input for the review phase or follow-up activities (e.g. lightweight threat and risk management and/or impact assessment) and a place to document the results.
- Fostering an open and informed discussion about explored and unexplored security aspects, allowing reviewers to verify and challenge assumptions or raise concerns.


## Specification
<!--The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Ethereum platforms (go-ethereum, parity, cpp-ethereum, ethereumj, ethereumjs, and [others](https://github.com/ethereum/wiki/wiki/Clients)).-->

The objectives outlined in the Motivations section are accomplished as follows:

- By adding a mandatory "Security Considerations" section to the EIP template ([TODO?]for all types except Informational?) documenting security relevant design information, decisions, pitfalls, implementation details, and discussions.
- By Adjusting the EIP process to reject proposals that are missing the section or blatantly fail to consider security aspects of the proposed change.
- By providing guidance on security considerations when proposing a change.

This document proposes a lightweight process for the documentation of security considerations. The idea is to provide important security related information to the security community for review in a digestible form that helps to quickly review EIPs for security implications. Address the EIP target audience. Focus on what is changing with the EIP.

**Guidance on Security Considerations**

* Design
  * Outline how security was taken into consideration for this EIP.
  * Clearly document important security relevant design decisions and changing assumptions. Note: Avoid duplicating information, reference related section of the EIP and provide security annotations.
  * Document security relevant details for implementers including edge-cases, language-specific notes, and common pitfalls.
  * How does the change affect various aspects and layers of the ethereum ecosystem?
    * What is the effect on the ecosystem? (e.g. changing incentives, inbalances, ...)
    * What is the effect on the consensus layer? (e.g. changes to the consensus algorithm)
    * What is the effect on the networking layer? (e.g. protocol changes or optimizations)
    * What is the effect on the API/RPC layer? (e.g. interface and API changes)
    * What is the effect on the application layer? (e.g. languages: solidity, viper, LLL, ...; Code: EVM/eWASM; Dapps and contracts)
  * (Optionally) Outline the threat model if available.
  * (Optionally) Think about potential threats, their impact and the likelihood of them to occur. What is the worst case scenario to happen from a security perspective?
* While in review
  * Track subject, status (open/closed) and outcome (issue/non-issue) of important security discussions and provide a link (archive discussion?) to the discussion medium if available. Note: Keep it short and simple.
  * Are there any open security discussions? Is the risk negligible or can it be accepted?
  * Document and reference security relevant audit and review results.


This EIP also encourages the proposal of another informational EIP to provide "*Guidelines for Writing EIP Text on Security Considerations*" including a description of the Ethereum Threat Model, Common Issues and Examples for writing a good "Security Considerations" section.


References:

* [Guidelines for Writing RFC Text on Security Considerations](https://tools.ietf.org/html/rfc3552)
  * section 2 - The Goal of Security
  * section 3 - The Internet Threat Model
  * section 5 - Writing Security Considerations Sections

## Implementations
<!--The implementations must be completed before any EIP is given status "Final", but it need not be completed before the EIP is accepted. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of "rough consensus and running code" is still useful when it comes to resolving many discussions of API details.-->

A section "Security Considerations" is added to the [template EIP](https://github.com/ethereum/EIPs/blob/master/eip-X.md) and EIP-1 is adapted to reflect the updated process.

## Rationale
<!--The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.-->

This document is inspired by and heavily based on the introduction of the mandatory "Security Considerations" section in the RFC process as specified in RFC 7322 (RFC Style Guide) and RFC 3552 (Guidelines for Writing RFC Text on Security Considerations). It proposes to adapt and build on top of what has worked well in other parts of the information and communication technology community avoiding to create an unsuitable process potentially being more overhead than actual benefit or completely reinventing the wheel.


## Security Considerations
<!--All EIPs must contain a section that discusses the security
    considerations relevant to the specification; see "Guidelines for
   Writing RFC Text on Security Considerations" [DRAFT EIP-XXX-THIS-EIP] for more
   information.-->

This document has no security considerations, please refer to section "Specification".


## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
