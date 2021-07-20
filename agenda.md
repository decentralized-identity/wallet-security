# DIF Wallet Security WG – Rolling Agenda & Minutes

[![hackmd-github-sync-badge](https://hackmd.io/6hUuZIjGQpeLVAqcxdakZA/badge)](https://hackmd.io/6hUuZIjGQpeLVAqcxdakZA)

{ [**WG projects**](https://github.com/topics/wg-ws) | [ DIF page](https://identity.foundation/working-groups/wallet-security.html) | [Mailing list](wallet-security@lists.identity.foundation) | [Meeting Recordings](https://docs.google.com/spreadsheets/d/1wgccmMvIImx30qVE9GhRKWWv3vmL2ZyUauuKx3IfRmA/edit#gid=194851117) }

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

## Meeting - 20 July 2021 - (1300 ET)

### Agenda

- working group meeting time slot status
- working group charter signing status
- review vacation summer status
- review current organization status of the WG
- presenting the working group document and continue work on security archtiectures/capabilities
- split prior art review as homework?

### Attendees

- Paul Bastian
- Bernard Joly


### notes
- poll for diffrent time slot:
- new sections for the document:
    - terminology/vocubalary
    - common security architecture
    - communication overview
    - capabilities overview
    - capabilities criteria
    - attestation
    - regulatory frameworks fit


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



