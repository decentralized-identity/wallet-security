# DIF Wallet Security WG – Rolling Agenda & Minutes

[![hackmd-github-sync-badge](https://hackmd.io/6hUuZIjGQpeLVAqcxdakZA/badge)](https://hackmd.io/6hUuZIjGQpeLVAqcxdakZA)

[**WG projects**](https://github.com/topics/wg-ws) | [ DIF page](https://identity.foundation/working-groups/wallet-security.html) | [Mailing list](https://lists.identity.foundation/g/wallet-security) | [Meeting Recordings](https://docs.google.com/spreadsheets/d/1wgccmMvIImx30qVE9GhRKWWv3vmL2ZyUauuKx3IfRmA/edit#gid=194851117) 

_For this call, you are encouraged to turn your video on. This is a good way to build rapport given we are a large, disparate group experiencing a lot of churn._

_This document is live-edited DURING each call, or shortly after the call, and stable/authoritative copies live on our github repo under /agenda.md .
Please note that we might not notice a pullrequest in time, but you are free to propose agenda items for future meetings via hackmd._

<details>
<summary> Meeting information - <b>Mondays 1300 ET</b></summary>

- Before your contribute - [**join DIF**](https://identity.foundation/join) and [sign the WG charter](https://bit.ly/DIF-WG-select1) (both are required!)
- Time: Every Tuesday, 13:00-14:00 ET
- [Calendar entry](https://calendar.google.com/event?action=TEMPLATE&tmeid=NGM5YnZhM2I1bXE1bmxhcGkyMDA0ZW1sMm5fMjAyMTA2MDFUMTcwMDAwWiBkZWNlbnRyYWxpemVkLmlkZW50aXR5QG0&tmsrc=decentralized.identity%40gmail.com&scp=ALL)
- [Zoom room](https://us02web.zoom.us/j/85747197140?pwd=RmJBcXd6blJidS9rZm9Fd2puclFhdz09), Meeting ID: 85747197140,
Password: 661333
</details>

## Meeting - 16 November 2021 - (6 PM CET)

### Agenda

1. restructing of the working group specification
2. advancing wg output by forming potential new work items with subgroups of common interest
 - differential credential security concept (security levels)
 - device binding
 - trusted verifier
 - user authentication, 2FA
 - wallet security information flow
 - your input
3. discussion on how to proceed with the big picture/vision

### Attendees
- Paul Bastian
- Ian Bailey
- Sebastian Bickerle
- Dirk Thatmann
- Keith Kowal
- Kai Wagner
- Thierry Thevenet
- Stephen Curran

### Notes
    
- Bernard might not participate on the next meetings, asking for help on the notes
- Keith: the group is too small to tackle these many work items
- Kai&Dirk: work items are best to get forward with diffrent opinion in the group
- chicken&egg problem, when to advertise, get wallet implementers on board?
- Keith: comparable security between wallets? customer needs..
- Ian: 2FA, key management
- agree that we can start on 1-2 work items and split work there
- how to advertise to/motivate wallet implementers?
    - gather requirements in a document?
    - comparison table of all wallets?
    - gather wallet implementers and contacts
    - google spreadsheet?
- vote 1: its good to start at least one work item
- vote 2: start with differential credential security concept
    - work item owners: Paul, Keith
    - start with a strawman proposal, continously working on it
    - google docs?
- Dirk, Paul wants to working on device binding

## Meeting - 2 November 2021 - (6 PM CET)

### Agenda

1. wg organization from DIF
2. Trusted verifiers - updates and sequence diagrams
3. Discussing wallets supporting multiple security levels for the issuer to chose

### Attendees
- Paul Bastian
- Bernard Joly
- Chris Kelly
- Kristina Yasuda
- Balazs Nemethi
- Ian Bailey
- Sebastian Bickerle
- Pieter Kasselman
- Keith Kowal
- Kai Wagner

### Notes

#### WG organization

- Wallet security document is now available in gitub. https://github.com/decentralized-identity/wallet-security/blob/main/wallet-security-criteria.md
- Get more regulators on board
- Get more wallet implementers on board
- Get more active participation
- increase visibility of the group
- **quickly understable core vision of the group**
- document needs more written text, self-readable/understandable
- ask Oliver to step down

#### vision of the group

- vision of the group similar enough for the summary document?
- scope too broad? narrow scope for first iteration?
    - example: tusted verifier off/on scope - people undecided
- what to focus on? seperate work items?
- goal?
    - vote on new work items - undecided
    - what are the motivations for issuers and verifiers?
        - understand requirements from the industry
    - discussion between levels and existing LoAs, e.g. ISO -> drifting to content discussion
    - group is undecided wether new work items will be beneficial

#### Trusted Verifier
time was over

## Meeting - 26 October 2021 - (6 PM CET)

### Agenda

1. IIW#33 review - relevant sessions
2. wg organization - attendance , cochairs, contributions, country-specific views
3. Trusted verifiers - authenticating and communicating security levels of verifier identities to the user in the wallet(UI&UX)
4. Discussing wallets supporting multiple security levels for the issuer to chose - gaining the best of all worlds

### Attendees
- Paul Bastian
- Bernard Joly
- Ian Bailey
- Dirk Thatmann
- Kai Wagner
- Tom Jones
- Thierry Thevenet
- Keith Kowal

### Notes

#### IIW recap - relevant sessions:
 - 3A - Need for hardware backed crypto on the web!
 - 11J - The future of Governance
 - 14B - UX: continuing the mid-2021 IIW UX conversation

#### WG organisation
 - shift to bi-weekly (voted pro)
 - other tooling (voted contra - not for now)
 - still lacking input of contributors
     - maybe its only the start?
     - difficult topic / SSI open-ness does not matchcurrent world?
     - target more wallet implementers?
     - another round of advertisement @DIF
 - adress also visions instead of products/projects
 - stack-indepedence?
 - more concise summary on what to achieve (not the charter)?
 - focus on specific problems to solve, e.g. german gov project?

#### Trusted verifiers (and also issuers?)
 - proposing different levels
     - how many make sense?
 - level 0: non-authenticated
     - minimum requirements (above bare minimum)
     - disallow HTTP
     - **display warning for untrusted connections**/requests (phishing)
     - display service-endpoint URL
     - do not display self-attested names? (e.g. Aries RFC0160 label)
 - level 1: authenticated
     - reusing HTTPS certificate attributes of service endpoints
     - show company name from [EV](https://en.wikipedia.org/wiki/Extended_Validation_Certificate) and [QWAC](https://en.wikipedia.org/wiki/Qualified_website_authentication_certificate) certificates
     - Public DIDs from a ledger?
     - DIDs shall be linked to service endpoints using well-known DID configuration, did:web, did:dns...
 - level 2: trusted
     - like Twitter checkmark
     - trust registries?
     - advanced trust from a trust service provider
         - as VC or inside the DID document?
 - UX challenge on how to communicate more than 2 levels
 - 2way authentication
     - this is usually handled by the proof request itself
     - awareness for MITM, but this is probably a separate topic
 - issues:
     - handle did-method specific stuff
     - handle network/ledger specific stuff
     - handle non-HTTPS protocols

#### Discussion on multiple security levels supported by the wallet
time was over 

## Meeting - 12 October 2021 - cancelled
due to IIW

## Meeting - 05 October 2021 - (6 PM CET)

### Agenda

1. Matching individual security capabilities values to the 3 proposed wallet security levels(L1,L2,L3)
2. Discussing wallets supporting multiple security levels for the issuer to chose - gaining the best of all worlds
3. Trusted verifiers - authenticating and communicating security levels of verifier identities to the user in the wallet(UI&UX)

### Attendees
- Ian Bailey
- Michael Lodder
- Kai Wagner
- Thierry Thevenet
- Bernard joly 
- Kristina Yasuda
- Tomj
- Keith Kowal

### notes
Trusted Verifiers. In germany launched the drivers licence in the new wallet. There are 300k download. There are some issues regarding the UX wallet . Trusted the verifier is an isssue. There are  different levels for the "verify". The verifiers need to improve the authentication ( not done today). Thi point will be add in the google doc for the final specifications. is the wallet will support multiple levels of security ?




## Meeting - 28 September 2021 - (1300 ET)

### Agenda

- Next meeting base on the survey ( decision by the group)
- Overview on eidas regulation/ EU wallet framework
- Review comments on "Keith  presentation"
- Review the continue discussion and work on terms, security architecture, level assurance 
- any new topics 

### Attendees
- Thierry Thevenet 
- Kai Wagner
- Bernard Joly 
- Chris Kelly
- Ralf Knobloch


### notes
Base on survey and the members presents we will move the meeting @6PM CET 

Presentation of the EU wallet status( see the slides).For the deployment There are 3 possibilties : each european members can select the model to build and distribute   the wallet  
It should be interested for all members to have a vision on the different regulations in the word for  the wallet framework. i request some volunteer to present the status for USA, ASIA, UK or others.
 
High security level, after some discussions on the "key recovery" .no recovery possibility should be the solution for the government. 
action:  Ralph will present an use case ( key recovery needs) in the next 3 weeks.

Cross border verification/Cross wallet usage : need to align the vision between all EU countries. some EU countries are more restrited today for the security requirements.



## Meeting - 7 September 2021 - (1300 ET)

### Agenda

- continue discussion and work on terms, security architecture, communication
- drafting an example workflow with credential lifecycle and the describe the wallet security aspects
- discussion on a questionnaire
- feel free to address any new topics

### Attendees

- Paul
- Ian
- Keith
- Dirk Thatmann

### notes

- we continue back to regular weekly meeting from here on
- discussion on individual capabilites vs groups/level of assurances
    - individual capabilities seem to detailed to list them/negotiate them specifically
    - rather list or link to existing standards, avoid duplication of requirements
    - group capabilites properties together
- Keith supports the discussion with presentation:
    - https://docs.google.com/presentation/d/1tk1AlUMthjIzIJJmF-ZSNZ7J3DmM1fxQztLukF5AoZQ
- Examples for diffrent Wallet Security Levels:
    - Level 1: German government issues Digital Passport to recipient
    - Level 2: AWS issues “Solution Architect” certification to recipient
    - Level 3: Home Depot issues free membership card to recipient
- Examining typical capabilites for given security levels, roughly:
    - Level 1: HW like TEE, credentials bound to device, strong user authentication, no revocery
    - Level 2: Keys are allowed in remote backup allowed with storng user encryption,  recovery allowed with complex knowledge/biometrics
    - Level 3: Keys are allowed in remote backup with platform encryption, simple user authenticaiton like username/password, platform manages credentials
- most secure relevant aspect like signature schemes, DID methods, protocols are given and already decided by the issuer
- wallet usually doesn't have too much possiblities(take it or leave it)
- verifier usually doesn't have too much choices either, maybe user authentication sometimes?
- most high security relevant questions (especially in regulated use cases) are handled upfront in the design/certification phase, therefore certification/assertion of the wallet will be highly relevant
- Main points/questions:
    -  do we apply to existing LoAs directly or define intermediate levels for groups of capabilities described here and match existing LoAs to these
    -  Does a wallet support L1,L2 and L3 ? Can we have L1 and L3 credentials at the same time?
    -  Wallets could fulfill LoA on a global/device base or on a per-credential base decided by the issuer
    -  Distinguish Wallet Security LoA and IT System Security LoA, attention that we don’t mix in data input quality LoA







## Meeting - 20 July 2021 - (1300 ET)

### Agenda

- working group meeting time slot status
- working group charter signing status
- review current organization status of the WG
- review vacation summer status
- presenting the working group document and continue work on security archtiectures/capabilities
- split prior art review as homework?

### Attendees

- Paul Bastian
- Bernard Joly
- Kristina 
- Martin Ingram
- Ian Bailey
- Keith
- Rogelio

### notes
- working group meeting time discussion
  - Bernard provide poll/thoughts about biweekly or topic-specific workshops
- summer break for next three weeks
    - starting back on 17. August
- current organization situation
    - no work items/owners of these
    - more workshop oriented/longer sessions on specific topic
- starting work on spec-like group document:
    - https://docs.google.com/document/d/1c8v7Jg0ZthvoRESeVZayTPE5xt5P_MAKIA9nz2qrCDo/edit#
    - new sections/discussion for the document:
        - terminology/vocubalary
        - common security architecture
        - capabilities criteria
        - capabilities groups/levels
        - attestation
        - communication overview
- discussion about how to continue


## Meeting - 6 July 2021 - (1300 ET)

### Agenda

- suggestion to move one hour earlier - 6pm CET
- gathering feedback/desire from wallet providers
- discussing and working on definition of security architectures

### Attendees

- Paul Bastian
- Bernard Joly
- Dirk Thatmann
- Kai Wagner
- Ian Bailey
- Rogelio Morrell
- Sebastien Bickerle
- Keith Kowal

### notes

- Sebastian Bickerle(Lissi): native apps developer: what measures can we do to participate in diffrent/regulated usecases, keeping UX as easy as possible, access to hardware is difficult, secureing indy sql-database, only starting yet
- Kai(Jolocom): similar, working with aries 2.0, starting on SSI-specific applet, figuring out how to use them, difficult crypto-alignment, german&euro market, regulated market, aligning with international standards
- Rogelio: documents & crypto wallets, consumer wallet, how to secure/store VCs etc, database with encrypotoion layer on top for now, no standardized wallet security, moved to web wallet, wallet-connect
- Keith: mobile wallet, arch changed to web wallet, diffrent key management, customer-driven, key management shifted from secure enclave/TEE, lost-password support issues, this lead to focus on recovery
- security architecture:
    - differentiation between user-managed/native-generated keys(software vs hardware) vs platform managing/cloud(similar to password management)
    - hot-wallet vs cold-wallet
    - edge vs cloud

- Keith: requirements to move to platform-based
    - browser can't store the keys securly
    - recovery
    - instability in w3c vc model, easier reissuance
- cloud wallets are hard to link to mobile secure storage, also changing the phone is difficult
- security architecture #1
    - cloud-wallet/platform-managed
    - keys are stored/lifecycle by the platform
    - authentication is towards the platform (e.g. username/password)
    - specific features: strong recovery, web&mobile possible, yubikeys
- security architecture #2
    - mobile/native
    - keys are generated the edge(software or hardware)
    - keys are stored/lifecycle on filesystem/secure enclave
    - authentication is PIN/mobile OS provided mechanism
    - specific features: device binding, automated backup to cloud possible
- mix of VC with diffrent security architectzure in one wallet?


## Meeting - 28 June 2021 - (1300 ET)

### Agenda

1. Welcome and introductions
2. Working Group signing status and meeting notes organization
3. gather/brainstorm a potential list for terminology
4. gather/brainstorm a potential list for use cases
5. continue the creation and discussion on the subcriteria excel sheet from last session
6. start discussion on security architectures

### Attendees

- Paul
- Kristina
- Bernard
- Ian Bailey
- Joachim Lohkamp
- Michael Lodder
- Kai Wagner

### notes

- signing the charter is possible now, ongoing...
- @nembal please check the link for signing up
    - @pwlb the link is [here](https://bit.ly/DIF-WG-select1). (to sign it a company must be a DIF member first) 

Michael 3 pillars:
- storage
- keys (key management and assertions)
- authentication (of the connection / access from another device)
※ user authentication out of scope

authentication of the wallet
 - user (PIN)
 - proof of possession(secure key, smartcard)
 - biometric (for mobile app)
     - mainly talking about 1:1(authetnication) rather than 1:N(identification)
     - mobile OS mechanisms
 
Design principles for higher security:
- where authentication factor belongs to: device or native app (PIN, biometrics, etc.)
- combine device & native app protection  
- key contains information only about the key - NOT about where it is used.
- Do not use non-modifiable data like biometrics alone

device authentication

device attestation
- e.g. TEE attested keys

wallet attestation
- wallet is implemented from proven/attested provider
- device checking/ app genuity
- conditional to device
- Michael mentions protocols to prove wallet, e.g. Oberon

Government Requirements
- Want to issue only to wallets provided by attested providers

Issues
- How does the issuer know it is talking to the attested app?
    - some sort of token exchange to pass the attestation/certification info
    - https://github.com/mikelodder7/oberon



## Meeting - 22 June 2021 - (1300 ET)

### Agenda

1. Welcome and introductions


### Attendees

- Paul
- Bernard
- Kristina
- Oliver
- Keith
- Michael
- Balasz
- Sebastian Bickerle

### notes

 - Sebastian from Lissi team new on the call
 - Agenda more up-to-note form next week
 - TSC approved the charter
     - join the wg by signing the charter
     - https://bit.ly/DIF-WG-select1 
 - organizing meeting notes via HackMD and sync to DIF github
 - We have done an exercise regarding prior art:

    1. We spent time breaking up high-leve criteria into sub-criterias (vertical axis)
        - key managemen into 
            - key lifecycle of private-public key pair (creation, signing, encryption, and decryption)
            -  key rotation	
            - key entrophy
            - key storage (HW/SW)
        - Credential storage into 
            - Remote / local (native app, browser)
            - Control - user / custodial 
        - Back-up into
            - back-up	Cloud back-up
            - personal vs centralized storage
        - Recovery system into
            - Key recovery (Certificate?)
            - Credential recovery
            - Wallet recovery (additional personalization metadata)
    2. and map them across prior art in various organizations: W3C, DIF, OIDF, Aries, Kantara, and implementations
    - the source is here: https://docs.google.com/spreadsheets/d/1ZvQm6zlGqrRmvSG2siAXnV824sHhVyH0qRDjmunr4p8/edit#gid=0



