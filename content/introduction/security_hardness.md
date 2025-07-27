---
date: '2025-06-06T17:53:36+02:00'
draft: false
title: 'Cryptography, security, and hardness assumptions'
math: true
---

> [!IMPORTANT]
> Cryptography is based on finding a mathematical problem that is very hard to solve -- unless you know a secret, sometimes known as the private key.

> [!IMPORTANT]
> A key is information.

{{% details title="Analogy" closed="true" %}}

The object commonly referred to as key is the physical support on which private information is encoded. For example, the height of [bittings](https://en.wikipedia.org/wiki/Bitting_(key)) on a [tumbler lock](https://en.wikipedia.org/wiki/Tumbler_lock) key is the information needed to open and close the lock.

{{% /details %}}

> [!IMPORTANT]
> Most problems are *presumed* hard until proven easy.

It is always possible to put an *upper* bound on the work that an adversary needs to do to break a cryptosystem -- at worst, trying every possible key. Trial and error without a strategy is also known as brute force.

Putting a *lower* bound on the work an adversary needs to do -- in other words, proving that a problem is at least *this* hard to solve -- is quite rare.

{{% details title="Exception" closed="true" %}}

[Grover's quantum search algorithm is optimal](https://doi.org/10.48550/arXiv.quant-ph/9711070), in that it can search an unstructured set of $N$ items in $\sqrt{N}$ operations **and** it has been proven that no algorithm can ever do better.

{{% /details %}}

> [!caution] Problem
> Quantum computing allows the invention of some algorithms that are much more efficient than classical algorithms at solving specific problems. In particular, Shor's algorithm allows a sufficiently powerful quantum computer to recover private keys from public keys for legacy cryptosystems.
>
> This drives the need to replace all public key algorithms, particularly digital signatures and key exchange / encapsulation.

> [!important] Solution
> Post-quantum cryptography is about finding new problems that are presumed to be difficult to solve on both classical and quantum computers -- until proven otherwise -- and building new cryptosystems on these problems.

Learn more about legacy cryptosystems like RSA in the Cryptography section, and more about quantum algorithms in the Quantum Information section.

{{< cards >}}
    {{< card link="../../cryptography/" title="Cryptography" icon="key" >}}
    {{< card link="/quantum/" title="Quantum Information" icon="variable" >}}
{{< /cards >}}