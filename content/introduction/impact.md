---
date: '2025-07-22T14:14:05+02:00'
title: 'Impact'
weight: 120
---

> [!caution] Q: If and when the Bad Guys do get a hold of a sufficiently powerful quantum computer, what consequences could there be?

{{< tabs items="Trust,Services,Cryptography,Protocols" >}}

    {{< tab >}}
    People can no longer trust:
    - any website we visit, because it could be fake
    - anything we download, especially important updates – BIOS, operating system, apps, firmware and drivers
    - that our online data and accounts are safe, because anyone could pretend to be us and gain access to it
    {{< /tab >}}

    {{< tab >}}
    Businesses can no longer guarantee service levels to customers:
    - that only a given subscriber is able to access their own data
    - that customer private keys are safely stored in an HSM only
    - that any clients connecting to servers are who they say they are

    Infrastructure can no longer be secured:
    - online banking services
    - interbank transfers
    - critical infrastructure
    {{< /tab >}}

    {{< tab >}}
    Any RSA or ECDSA public key ever published, anywhere, can be used to recover the correspondinprivate key.
    
    Any (EC)DH key exchange can be broken by recovering individual secrets from public shares.
    {{< /tab >}}

    {{< tab >}}
    Anything with a signature or a key exchange - most anything with an X.509 certificate. In no particular order, a non-exhaustive list includes:

    - TLS, QUIC, IPSEC, 802.11 WiFi​
    - Code signing, document signing (PDF), email S/MIME​
    - UEFI secure boot, firmware updates -- devices, drivers​
    - SSH​, Wireguard​
    - ICAO e-passport, WebAuthn​
    - OAuth, OpenID Connect and various specifications -- JOSE (JWT), COSE (CWT)​
    - SAML
    - PKCS
    {{< /tab >}}

{{< /tabs >}}

Please note: these statements are deliberately overblown to emphasize the potential impact of this threat. Even though the chances are that we won't be in this situation until 2040, bear in mind that the process of switching to new cryptography has already taken two decades in 2025, and is expected to take at least a third. If we have to rush, we'll be too late.