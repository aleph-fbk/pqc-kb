---
date: '2025-06-02T18:41:16+02:00'
draft: true
title: 'Cryptography'
math: true
weight: 200
---
## The problem

[Shor's algorithm](https://doi.org/10.48550/arXiv.quant-ph/9508027) allows a sufficiently powerful quantum computer to recover private keys from public keys for legacy cryptosystems, in particular by [factoring RSA public moduli](https://arxiv.org/abs/2007.10044) and [breaking the (EC)DLP](https://eprint.iacr.org/2017/598).



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