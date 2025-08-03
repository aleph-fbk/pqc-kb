---
date: '2025-07-29T16:52:48+02:00'
draft: false
title: 'Standards'
math: true
weight: 280
---

## NIST standardization winners

| Type          | Key Encapsulation Mechanism        | Digital Signature Algorithm            |
| ---           | ---                                | ---                  |
| Lattice-based | ML-KEM[^FIPS_203] ([Kyber][Kyber]) | ML-DSA[^FIPS_204] ([Dilithium][Dilithium]) <br> ¿ FN-DSA ([Falcon][Falcon])  |
| Code-based    | [HQC][HQC]                         |                      |
| Hash-based    |                                    | SLH-DSA[^FIPS_205] ([SPHINCS][SPHINCS]$^+$) |

[HQC]: https://pqc-hqc.org/
[SPHINCS]: https://sphincs.org/
[Kyber]: https://pq-crystals.org/kyber/
[Dilithium]: https://pq-crystals.org/dilithium/
[Falcon]: https://falcon-sign.info/



## References

[^FIPS_203]: National Institute of Standards and Technology (NIST). (2024a).
Module-lattice-based digital signature standard. In *FIPS* (Vol. 204).
<https://csrc.nist.gov/pubs/fips/204/final​>.

[^FIPS_204]: National Institute of Standards and Technology (NIST). (2024b).
Module-lattice-based key-encapsulation mechanism standard. In *FIPS*
(Vol. 203). <https://csrc.nist.gov/pubs/fips/203/final​>.

[^FIPS_205]: National Institute of Standards and Technology (NIST). (2024c).
Stateless hash-based digital signature standard. In *FIPS* (Vol. 205).
<https://csrc.nist.gov/pubs/fips/205/final​>.