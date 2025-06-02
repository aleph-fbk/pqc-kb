---
date: '2025-06-02T07:34:48+02:00'
draft: true
title: 'Introduction'
math: true
---

# The Post-Quantum Cryptography transition

Why is it happening?

{{< tabs groupid="a" items="In a nutshell,Cryptography,Compliance" >}}

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

When is it happening?

{{< tabs groupid="a" items="In a nutshell,Cryptography,Compliance" >}}

    {{< tab >}}
    Right now. Between 2025 and 2035-ish -- before quantum computers get powerful enough. By the time we read about it in the news, it will have been much too late.
    {{< /tab >}}

    {{< tab >}}
    Before a quantum computer is capable of recovering private keys from public keys for RSA or elliptic-curve DLP-based cryptosystems.
    {{< /tab >}}
    
    {{< tab >}}
    Cybersecurity agencies recommend a planning phase up to 2030, and a switch-over phase between 2030 and 2035 - roughly speaking. See individual recommendations in the Compliance section.
    {{< /tab >}}
    
{{< /tabs >}}

What could happen if we don't switch before the Bad Guys get a hold of a powerful enough quantum computer?

{{< tabs groupid="a" items="In a nutshell,Cryptography,Compliance" >}}

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