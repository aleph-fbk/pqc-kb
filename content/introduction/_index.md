---
date: '2025-07-22T13:58:15+02:00'
title: 'Introduction and FAQ'
weight: 100
---

> [!NOTE]
> Why is it happening?

{{< tabs items="In a nutshell,Cryptography,Compliance" >}}

    {{< tab >}}
    Our online safety is at risk from Bad Guys getting a hold of a powerful enough quantum computer, in the not too distant future.
    {{< /tab >}}

    {{< tab >}}
    A quantum computing adversary can recover a private key from any public key, for systems based on RSA or discrete logarithm -- e.g., factor RSA public keys into their prime factors $N=pq$, or solve the ECDLP to find $m$ such that $mP=Q$ for generator $P$ and any point $Q$.
    {{< /tab >}}
    
    {{< tab >}}
    Cybersecurity agencies are publishing new standards and authorities are mandating a switch-over to new cryptography.
    {{< /tab >}}
    
{{< /tabs >}}

> [!WARNING]
> What could happen if we don't switch before the Bad Guys get a hold of a powerful enough quantum computer?

{{< tabs items="In a nutshell,Cryptography,Compliance" >}}

    {{< tab >}}
    - Goodbye online shopping, email, and social media. You won't be able to tell a genuine website from a fake one, ever again.
    - Goodbye online banking, monetization, and storage. Bad guys could pretend to be you, and steal all your money and your content, or rack up bills in your name.
    - Goodbye bitcoin. And ethereum. And any cryptocurrency based on legacy digital signatures. Bad guys could generate valid transactions for any wallet.
    - Goodbye software downloads -- from games to software to OS and BIOS updates. It will be impossible to tell whether a patch is genuine or malware that will take over your PC.
    The list is endless, these are just some of the highlights.
    {{< /tab >}}

    {{< tab >}}
    Public key cryptography underpins authentication of websites and identities, from digital signatures for authentication to Diffie-Hellman for key exchange. It is also the basis of code signing.
    {{< /tab >}}
    
    {{< tab >}}
    Anyone using legacy algorithms will be unable to demonstrate compliance with any standard or legislation mandating the use of *strong cryptography*, *high assurance*, *data protection*, *strong customer authentication*, *approved algorithms* etc.
    {{< /tab >}}
    
{{< /tabs >}}

See [Impact](./impact) for more potential consequences.


> [!TIP]
> What can we do about it?

{{< tabs items="In a nutshell,Cryptography,Compliance" >}}

    {{< tab >}}
    Plan ahead. Budget for change. Follow through.
    You will most likely be sent new cards by your bank. You may need to buy a new mobile phone. Keep your browser and apps up to date.
    {{< /tab >}}

    {{< tab >}}
    New standards for key exchange and digital signature are being published. Libraries and hardware will need to implement them. Standards will need to recommend them. Protocols like TLS, SSH, Wireguard etc. will need to be updated. Analysis will need to show that the updated protocols attain their security goals.
    {{< /tab >}}
    
    {{< tab >}}
    Leverage will need to be applied to cajole an entire ecosystem to switch over.
    {{< /tab >}}
    
{{< /tabs >}}