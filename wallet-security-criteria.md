# Wallet Security Document Draft

## Vision Summary
 
The Wallet Security working group enables SSI usecases with higher or diverse security requirements for issuers, wallet implementers and verifier. In the current SSI ecosystem the common trust relation is mostly observed between from the Verifier to the Issuer:

![Status Quo](/images/standard.svg)

Wallet Security tries to enable new and stronger trust relations between the wallet and the issuer as well as between wallet and verifier. One of SSI's main stength is to combine credentials and use cases of different domains in one wallet. Examples for use cases requiring different security levels might be:
 
 - Level 1: German government issues Digital Passport to recipient
 - Level 2: AWS issues “Solution Architect” certification to recipient
 - Level 3: Home Depot issues free membership card to recipient
 
These examples show the diverse requirements for issuers and wallets on how to secure this credentials within one wallet. Therefore a wallet should be able to propagate its security capabilities and proof its authenticity to the issuer, this enables higher security use cases while not excluding credentials with lower needs. On the other side the verifier can proof his authenticity to the wallet and therefore enable the user to make better decisions whether or not too reveal his data in a self-sovereign world:

![Evolution](/images/target.svg)

### Terminology

- SSI Wallet: a mobile application or a browser application that receives, stores and presents credentials about the users using W3C VC-DATA-MODEL Specification.
- Wallet authentication
- Wallet attestation
- Wallet certification
- Wallet capabilities
- User authentication
- Wallet storage
- Device authentication
- Device attestation
- Device binding

### Common Wallet security architectures

- security architecture #1
  - cloud-wallet/platform-managed
  - keys are stored/lifecycle by the platform
  - authentication is towards the platform (e.g. username/password)
  - specific features: strong recovery, web&mobile possible, SecureKey
  
- security architecture #2
  - mobile/native
  - keys are generated the edge(software or hardware)
  - keys are stored/lifecycle on filesystem/secure enclave
  - authentication is PIN/mobile OS provided mechanism
  - specific features: device binding, automated backup to cloud possible
  
### Wallet (device) Capabilities

Considerations
- Differentiate between wallet and credential requirements/capabilities
- Does level4 Wallet also provide level3/2/1 support?
- Can an issuer select level of assurance and therefore indirectly prohibit/allow backup?
  - Issuer: I issue level-x
  - Wallet: key management/recovery ability
  - Issuer: sending credential
  - Wallet: store creds according to parameters chosen by the issuer

Pro:
- users only need one wallet/less wallets
- Physical wallets support multiple security levels as well
- It's more simple

Contra:
- more complexity


||Level 1|Level 2|Level 3|
| :- | :- | :- | :- |
|Private Key Storage|Software on device/platform|Software/Hardware on device/platform|Hardware on device|
|Recoverability|In scope|In scope|Not in scope|
|Certification|Not needed|Probably not needed|Probably needed|
|||||
|||||


1. Key management 
   1. Device key management
      1. Key lifecycle of private-public key pair (creation, signing, encryption, and decryption)
      1. Key rotation
      1. Key entropy
      1. Key storage
   1. Issuer key management
      1. Key storage (HW/SW)
   1. App attestation management
      1. Storage
      1. Creation
1. Credential storage	
   1. Remote / local (native app, browser)
   1. Control - user / custodial 	
1. Back-up
   1. Cloud back-up
   1. Personal vs centralized storage
1. Recovery system
   1. Key recovery (Certificate?)
   1. Credential recovery
   1. Wallet recovery (additional personalization metadata)
1. Binding
   1. Wallet (Credentials) to the device
   1. Credential to the user (Biometrics, HW keys (FIDO), photo) 
1. Consent: documenting
1. Custodial management
1. Credential exchange protocols
1. Holder authentication	

### Attestation

Todo…

### Capabilities Groups/Security Levels

- Views:
  - Different/fragmented software/hardware base requires granularity and prevents defined presets
  - Approved wallets and their capabilities are pre-known
- Summarize properties down to groups/levels of assurances
  - Rather list or link to existing standards, avoid duplication of requirements
- Government / public service usecase wallet are analysed upfront anyway?
- LevelofAssurances originating from existing national standards/frameworks
  - Pan Canadian Trustframework 1,2,3
  - eIDAS low/substantiell/high

- Main points/questions:
  - do we apply to LoAs directly or intermediate levels described here and match existing LoAs to these
  - Does a wallet support L1,L2 and L3 ?
  - Distinguish Wallet Security LoA and IT System Security LoA, attention that we don’t mix in data input quality LoA
 
### Wallet Security Communication overview

Explain how wallet security capabilities are communicated between the parties...

- Communication entities
- Using existing communication interfaces:
  - DIDComm
  - CHAPI
  - WACI (explain: meanings WACI =  **W**allet **a**nd **C**redential **I**nteractions and means **not** W3C **W**eb **A**pplication **C**loud **I**nterface)
  - VC HTTP API
- Using background information/on a webserver/on a ledger
- Only communicating approved/well-known wallets

### Key management 

There are several keys involved in SSI wallet ecosystem: a key that the issuer used to sign the credential. It is the responsibility of the verifier to  

- Device key management
  - Key lifecycle of private-public key pair (creation, signing, encryption, and decryption)

  - Key rotation
    - Keys need to be rotated at least XXX times?
    - When you have a singular private key - you move it across devices 
    - Private key never leaves secure enclave
  - Key entropy
    - At least XXX
  - Key storage
    - HW storage: 
    - SW storage:
- Issuer key management
  - Key storage (HW/SW)
- App attestation management
  - Storage
  - Creation
- Credential storage	
  - Remote / local (native app, browser)
  - Control - user / custodial 	
- Back-up
  - Cloud back-up
  - Personal vs centralized storage
- Recovery system
  - Key recovery (Certificate?)
  - Credential recovery
  - Wallet recovery (additional personalization metadata)
- Binding
  - Wallet (Credentials) to the device
  - Credential to the user (Biometrics, HW keys (FIDO), photo) 
- Consent: documenting
- Custodial management
- Credential exchange protocols
- Holder authentication	

### Guidance and Best PRactive on Trusted Verifier Information

- Securing service endpoint
- Secure DID
- Combing well-known DID configuration
- How to show/translate that trust to the user in UI/UX decisions
- Presentation from Sam: https://hackmd.io/@TelegramSam/Hy32toMkD#/6
- 
### Evaluation against prior Art

- EU
  - <https://credential.eu/>
- W3C	
  - CCG WebKMS			
  - DID Method				
  - JSON-LD crypto suites				
- DIF
- SDS			
- EDV			
- Id Hubs
- OIDF
- Aries
  - Aries KMS	
- Kantara
