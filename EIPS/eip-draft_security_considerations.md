---
eip: <to be assigned>
title: Guidelines for writing EIP text on Security Considerations
author: Martin Ortner <martin.ortner@consensys.net>
discussions-to: https://github.com/ethereum/EIPs/issues/XXX
status: Draft
type: Meta
created: 2019-01-20
requires: 1
---

<!--You can leave these HTML comments in your merged EIP and delete the visible duplicate text guides, they will not appear and may be helpful to refer to if you edit it again. This is the suggested template for new EIPs. Note that an EIP number will be assigned by an editor. When opening a pull request to submit your EIP, please use an abbreviated title in the filename, `eip-draft_title_abbrev.md`. The title should be 44 characters or less.-->

## Simple Summary
<!--"If you can't explain it simply, you don't understand it well enough." Provide a simplified and layman-accessible explanation of the EIP.-->

This document describes an improvement to the Ethereum Improvment Proposal (EIP) system as defined in EIP-1 to explicitly embed security into the EIP process by adding a new mandatory "Security Considerations" section, adapted from [rfc7322 - section 4.8.5](https://tools.ietf.org/html/rfc7322#section-4.8.5).


## Abstract
<!--A short (~200 word) description of the technical issue being addressed.-->

The EIP system defines a minimum set of information and criteria to be included in a proposal. Given the potential impact and therefore risks attached with certain proposals (e.g. changing an algorithm [ref EIP ProgPoW] or parameters [ref EIP constantinople gas issue]) it is important to document security considerations in an EIP.

The goals of requiring a mandatory "Security Considerations" section are as follows:

- Encourage document authors to consider security in their designs.
- Inform the reader of relevant security concerns or issues and raise the visibility of changes that are affecting security.
- Provide input for potential follow-up activities (e.g. a security and impact assessment [XXX define process in EIP] as a final security gate before acceptance).
- Fostering an open and informed discussion about explored and unexplored security aspects, allowing reviewers to verify and challenge assumptions or raise concerns.

This will be accomplished as follows:

- By adding a mandatory "Security Considerations" section to the EIP template (for all types except Informational?).
- By Adjusting the EIP process to reject proposals that are missing the section or blatantly fail to consider security aspects of the proposed change.
- By providing guidance on security considerations when proposing a change.


## Motivation
<!--The motivation is critical for EIPs that want to change the Ethereum protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the EIP solves. EIP submissions without sufficient motivation may be rejected outright.-->

The technology community established various ways of publishing memoranda to exchange important information and guidelines as well as to discuss and agree on standards and improvements that can manifest in changes to processes and technology.
Change is inherent in any organisation and technology. Given the potential impact and far-reaching consequences - especially in the DLT/Blockchain ecosystem - it is critical to take an organised approach to prevent unintended consequences and therefore reduce risk.

At present individual security considerations are not part of the EIP as defined with EIP-1 and therefore not consistently documented nor easily accessible for discussion.

For example "Security Considerations" are part of many proposal and change management processes.In information and communications technology, one of the most widely used and understood process is the Request for Comments (RFC) system. [rfc1543 - Instructions to RFC Authors (1993)](https://tools.ietf.org/html/rfc1543#section-8) first introduced a "Security Considerations" section to RFC noting:

    All RFCs must contain a section near the end of the document that
    discusses the security considerations of the protocol or procedures
    that are the main topic of the RFC.

With [rfc3552 - Guidelines for Writing RFC Text on Security Considerations (2003)](https://tools.ietf.org/html/rfc3552) an attempt was made to give further guidance and better align expectations of the information documented as well as to provide background information and describe the terminology used as well as outline important threat models to build a common ground for security discussions. "Security Considerations" is still an integral part of RFC as per [rfc7322 - RFC Style Guide (2014)](https://tools.ietf.org/html/rfc7322#section-4.8.5).

Embedding security into the EIP system is expected to further raise the quality of submissions, encourage security discussions, provide documentation for follow-up security activities and a basis for a security triage while reducing the risk of accepting proposals that failed to sufficiently consider security.


## Specification
<!--The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Ethereum platforms (go-ethereum, parity, cpp-ethereum, ethereumj, ethereumjs, and [others](https://github.com/ethereum/wiki/wiki/Clients)).-->

//avoid to duplicate what the RFC already has?

//what is left to be said that should be in this section?

// for reference: RFCs

  - https://tools.ietf.org/html/rfc7322#section-4.8.5
  - https://tools.ietf.org/html/rfc3552#page-26
  - https://tools.ietf.org/html/rfc2223
  - https://tools.ietf.org/html/rfc1543#section-6

// for reference TOC of the RFC security guidelines

//  <-- ref to this and provide an ethereum threat model (this will take some time, I suggest to split the EIP into two parts (as done in RFC) - first part suggesting the "security considerations" being mandatory (quick benefit for next EIPs, outcome might be a bit non uniform as people will not know how to deal with this section) and second part being the guideline aligned with the TOC below.


    1. Introduction

            All EIPs are required by [EIP-XXX-this one or separate updating EIP-1?] to contain a Security
               Considerations section.  The purpose of this is both to encourage
               document authors to consider security in their designs and to inform
               the reader of relevant security issues.  This memo is intended to
               provide guidance to EIP authors in service of both ends.

               This document is structured in three parts.  The first is a
               combination security tutorial and definition of common terms; the
               second is a series of guidelines for writing Security Considerations;
               the third is a series of examples.

        1.1 Requirements
    2. The Goals of Security   // just reference --> RFC 3552
        2.1 Communication Security
            2.1.1 Confidentiality
            2.1.2 Data Integrity
            2.1.3 Peer Entity Authentication
        2.2 Non-Repudiation
        2.3 Systems Security
            2.3.1 Unauthorized Usage
            2.3.2 Inappropriate Usage
            2.3.3 Denial of Service
    3. The Internet Threat Model
            // just reference --> RFC3552
    4. The Ethereum Threat Model  --> TBD!  (is there an ethereum layer model? like OSI?)
        //EIP-4 - ethereum layer model and some basic description?
            consensus layer
                --> [high level description]
                --> [threats, impact & common mitigations if available]
            networking layer
                --> [high level description]
                        / wire protocol / network messages
                --> [threats, impact & common mitigations if available]
            api/rpc layer
                --> [high level description]
                --> [threats, impact & common mitigations if available]
            software layer
                etheruem vm?
                ewasm
                    / solidity
                    / viper
                    / LLL
                    / ...
                applications layer (dapps?)
                    --> [high level description]
                    --> [threats, impact & common mitigations if available]

    5. Common Issues
        //outline most common issues
    6. Writing Security Considerations Sections
        --> as defined in RFC3552  (copy or reference?)
        --> adapt for the ethereum threat model

        While it is not a requirement that any given protocol or system be
   immune to all forms of attack, it is still necessary for authors to
   consider as many forms as possible.  Part of the purpose of the
   Security Considerations section is to explain what attacks are out of
   scope and what countermeasures can be applied to defend against them.
   In

   There should be a clear description of the kinds of threats on the
   described protocol or technology.  This should be approached as an
   effort to perform "due diligence" in describing all known or
   foreseeable risks and threats to potential implementers and users.

    Authors MUST describe

      1.   which attacks are out of scope (and why!)
      2.   which attacks are in-scope
      2.1  and the protocol is susceptible to
      2.2  and the protocol protects against

   At least the following forms of attack MUST be considered:
   eavesdropping, replay, message insertion, deletion, modification, and
   man-in-the-middle.  Potential denial of service attacks MUST be
   identified as well.  If the protocol incorporates cryptographic
   protection mechanisms, it should be clearly indicated which portions
   of the data are protected and what the protections are (i.e.,
   integrity only, confidentiality, and/or endpoint authentication,
   etc.).  Some indication should also be given to what sorts of attacks
   the cryptographic protection is susceptible.  Data which should be
   held secret (keying material, random seeds, etc.) should be clearly
   labeled.

   If the technology involves authentication, particularly user-host
   authentication, the security of the authentication method MUST be
   clearly specified.  That is, authors MUST document the assumptions
   that the security of this authentication method is predicated upon.
   For instance, in the case of the UNIX username/password login method,
   a statement to the effect of:

      Authentication in the system is secure only to the extent that it
      is difficult to guess or obtain a ASCII password that is a maximum
      of 8 characters long.  These passwords can be obtained by sniffing
      telnet sessions or by running the 'crack' program using the
      contents of the /etc/passwd file.  Attempts to protect against
      on-line password guessing by (1) disconnecting after several
      unsuccessful login attempts and (2) waiting between successive
      password prompts is effective only to the extent that attackers
      are impatient.

      Because the /etc/passwd file maps usernames to user ids, groups,
      etc. it must be world readable.  In order to permit this usage but
      make running crack more difficult, the file is often split into
      /etc/passwd and a 'shadow' password file.  The shadow file is not
      world readable and contains the encrypted password.  The regular
      /etc/passwd file contains a dummy password in its place.

   It is insufficient to simply state that one's protocol should be run
   over some lower layer security protocol.  If a system relies upon
   lower layer security services for security, the protections those
   services are expected to provide MUST be clearly specified.  In
   addition, the resultant properties of the combined system need to be
   specified.

   Note: In general, the IESG will not approve standards track protocols
   which do not provide for strong authentication, either internal to
   the protocol or through tight binding to a lower layer security
   protocol.

   The threat environment addressed by the Security Considerations
   section MUST at a minimum include deployment across the global
   Internet across multiple administrative boundaries without assuming
   that firewalls are in place, even if only to provide justification
   for why such consideration is out of scope for the protocol.  It is
   not acceptable to only discuss threats applicable to LANs and ignore
   the broader threat environment.  All IETF standards-track protocols
   are considered likely to have deployment in the global Internet.  In
   some cases, there might be an Applicability Statement discouraging
   use of a technology or protocol in a particular environment.
   Nonetheless, the security issues of broader deployment should be
   discussed in the document.

   There should be a clear description of the residual risk to the user
   or operator of that protocol after threat mitigation has been
   deployed.  Such risks might arise from compromise in a related
   protocol (e.g., IPsec is useless if key management has been
   compromised), from incorrect implementation, compromise of the
   security technology used for risk reduction (e.g., a cipher with a
   40-bit key), or there might be risks that are not addressed by the
   protocol specification (e.g., denial of service attacks on an
   underlying link protocol).  Particular care should be taken in
   situations where the compromise of a single system would compromise
   an entire protocol.  For instance, in general protocol designers
   assume that end-systems are inviolate and don't worry about physical
   attack.  However, in cases (such as a certificate authority) where
   compromise of a single system could lead to widespread compromises,
   it is appropriate to consider systems and physical security as well.

   There should also be some discussion of potential security risks
   arising from potential misapplications of the protocol or technology
   described in the RFC.  This might be coupled with an Applicability
   Statement for that RFC.


    7. Examples
        7.1 XXX
            // todo: reproduce security considerations for an already approved EIP?

## Implementations
<!--The implementations must be completed before any EIP is given status "Final", but it need not be completed before the EIP is accepted. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of "rough consensus and running code" is still useful when it comes to resolving many discussions of API details.-->

A section "Security Considerations" is added to the [template EIP](https://github.com/ethereum/EIPs/blob/master/eip-X.md) and EIP-1 is adapted to reflect the updated process.

## Rationale
<!--The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.-->

This document is inspired by and heavily based on the introduction of the mandatory "Security Considerations" section in the RFC process as specified in rfc7322 (RFC Style Guide) and RFC-3552 (Guidelines for Writing RFC Text on Security Considerations). It proposes to adapt and build on top of what has worked well in other parts of the information and communication technology community avoiding to create an unsuitable process potentially being more overhead than actual benefit or completely reinventing the wheel.


## Security Considerations
<!--All EIPs must contain a section that discusses the security
    considerations relevant to the specification; see "Guidelines for
   Writing RFC Text on Security Considerations" [DRAFT EIP-XXX-THIS-EIP] for more
   information.-->

This document has no security considerations, please refer to section "Specification".


## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
