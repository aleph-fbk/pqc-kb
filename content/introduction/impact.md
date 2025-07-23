---
date: '2025-07-22T14:14:05+02:00'
draft: true
title: 'Impact'
math: true
---

If and when the Bad Guys do get a hold of a sufficiently powerful quantum computer, what consequences could there be?

{{< tabs items="Trust,Services,Cryptography" >}}

    {{< tab >}}
    I can no longer trust:
    - any website I visit, or anything I download
    - any updates – BIOS, OS, apps, firmware
    - any clients connecting to my servers, insofar as they are who I think and they say they are
    {{< /tab >}}

    {{< tab >}}
    I can no longer guarantee service levels to my customers:
    - that only a given subscriber is able to access their own data;
    - that customer private keys are safely stored in my HSM only.

    I can no longer secure:
    - online banking services
    - interbank transfers
    - critical infrastructure
    {{< /tab >}}

    {{< tab >}}
    Any RSA or ECDSA public key ever published, anywhere, can be used to recover the correspondinprivate key.
    
    Any (EC)DH key exchange can be broken by recovering individual secrets from public shares.
    {{< /tab >}}

{{< /tabs >}}