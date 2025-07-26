---
date: '2025-06-02T18:41:16+02:00'
title: 'Cryptography'
math: true
weight: 200
---
## The problem

[Shor's algorithm](https://doi.org/10.48550/arXiv.quant-ph/9508027)[^S97] allows a sufficiently powerful quantum computer to recover private keys from public keys for legacy cryptosystems, in particular by [factoring RSA public moduli](https://arxiv.org/abs/2007.10044)[^E07] and [breaking the (EC)DLP](https://eprint.iacr.org/2017/598)[^RNSL17].



## The solution

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

[^S97]: P W Shor: "Polynomial-Time Algorithms for Prime Factorization and Discrete Logarithms on a Quantum Computer". 1997. [arXiv:quant-ph/9508027](https://doi.org/10.48550/arXiv.quant-ph/9508027)
[^E07]: M Ekerå: "On completely factoring any integer efficiently in a single run of an order finding algorithm". 2007. [arXiv:2007.10044](https://doi.org/10.48550/arXiv.2007.10044)
[^RNSL17]: M Roetteler, M Naehrig, K M Svore, and K Lauter: "Quantum Resource Estimates for Computing Elliptic Curve Discrete Logarithms". 2017. [ia.cr/2017/598](https://eprint.iacr.org/2017/598)
