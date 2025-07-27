---
date: '2025-06-02T18:41:16+02:00'
title: 'Cryptography'
math: true
weight: 200
---

> [!caution] Problem
> Shor's algorithm[^S97] allows a sufficiently powerful quantum computer to recover private keys from public keys for legacy cryptosystems, in particular by factoring RSA public moduli[^E07] and breaking the (EC)DLP[^RNSL17].
>
> This drives the need to replace all public key algorithms, particularly digital signatures and key exchange / encapsulation.

{{< cards >}}
    {{< card link="RSA/" title="RSA and integer factoring" icon="information-circle" >}}
    {{< card link="DH_DLog/" title="Diffie-Hellman and Discrete Logarithm" icon="information-circle" >}}
{{< /cards >}}

> [!important] Solution
> Post-quantum cryptography is about finding new problems that are presumed to be difficult to solve on both classical and quantum computers -- until proven otherwise -- and building new cryptosystems on these problems.

## NIST standardization winners

| Type          | KEM             | Signature            |
| ---           | ---             | ---                  |
| Lattice-based | [ML-KEM][ML-KEM] ([Kyber][Kyber]) | ML-DSA ([Dilithium][Dilithium])   |
| Code-based | [HQC][HQC]         |                      |
| Hash-based |                    | [SLH-DSA][SLH-DSA] ([SPINCS][SPINCS]$^+$) |

[ML-KEM]: https://csrc.nist.gov/pubs/fips/203/final
[ML-DSA]: https://csrc.nist.gov/pubs/fips/204/final
[SLH-DSA]: https://csrc.nist.gov/pubs/fips/205/final
[HQC]: https://pqc-hqc.org/
[SPINCS]: https://sphincs.org/
[Kyber]: https://en.wikipedia.org/wiki/Kyber
[Dilithium]: https://pq-crystals.org/dilithium/index.shtml

## References

[^E07]: Ekerå, M. (2021). On completely factoring any integer efficiently in a
single run of an order-finding algorithm. *Quantum Information
Processing*, *20*(6). https://doi.org/10.1007/s11128-021-03069-1

[^RNSL17]: Roetteler, M., Naehrig, M., Svore, K. M., and Lauter, K. (2017).
*Quantum resource estimates for computing elliptic curve discrete
logarithms*. Cryptology ePrint Archive, Paper 2017/598.
https://eprint.iacr.org/2017/598

[^S97]: Shor, P. W. (1997). Polynomial-time algorithms for prime factorization
and discrete logarithms on a quantum computer. *SIAM Journal on
Computing*, *26*(5), 1484–1509.
https://doi.org/10.1137/s0097539795293172
