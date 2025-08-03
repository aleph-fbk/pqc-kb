---
date: '2025-08-03T21:53:52+02:00'
draft: false
title: 'Classic McEliece'
math: true
weight: 270
---

[Classic McEliece][Classic McEliece] is a code-based NIST standardization candidate still being considered, and may become a standard after the currently ongoing ISO standardization process is concluded.

## The McEliece cryptosystem[^McEliece78] (textbook)
Let $\Gamma$ be an $\lbrack n,k,2t+1\rbrack _2$ binary Goppa code with an efficient $t$-error decoding algorithm, where $t\approx (n − k)/ \log2(n)$.
 
Public parameters are:
- $n$, the code length;
- $k$, the code dimension;
- $t$, and hence the minimum distance $2t+1$.

The private key is:
- $\Gamma$ and a $k\times n$ generator matrix $G$;
- an $n\times n$ permutation matrix $P$;
- a non-singular $k\times k$ matrix $S$.

The public key is:
- $G'=SGP$

Encrypt($m,G'$):
$$c=mG'+e$$

Decrypt$(c,P,S,\Gamma)$:
$$
\begin{align*}
    cP^{-1} &= mG'P^{-1} + eP^{-1}  \\
            &= (mS)G + eP^{-1}
\end{align*}
$$
The decoding algorithm will return $mS$, and hence recover $m$.

### The Niederreiter cryptosystem[^Niederreiter86] (textbook)

The Niederreiter proposal is a version of the McEliece proposal based on syndrome decoding, with the following differences:
- substitute the $k\times n$ generator matrix $G$ for a $(n-k)\times (n-k)$ parity check matrix $H$;
- adjust the size of $S$ accordingly, from $k\times k$ to $(n-k)\times (n-k)$;
- the public key is a version of the parity check matrix, $H'=SHP$;
- for plaintexts $m$ of weight $t$ and length $n$, akin to errors, ciphertexts are syndromes
$$c=H'm;$$
- decryption is to find $m$ such that $w(m)=t$ and $c=H'm$.

## References

[Classic McEliece]: https://classic.mceliece.org/

[^Lange19]: Lange, T. (2019). *Code-based cryptography*. Executive school on
post-quantum cryptography.
<https://www.hyperelliptic.org/tanja/talks.html>.
https://pqcschool.org/slides/20190702-exec.pdf

[^McEliece78]: McEliece, R. J. (1978). Public-key cryptosystem based on algebraic
coding theory. In *NASA DSN Congress Report* (Vols. 42–44, pp. 114–116).
<https://ipnpr.jpl.nasa.gov/progress_report2/42-44/44N.PDF>.

[^Menezes24]: Menezes, A. J. (2024). *Cryptography 101*.
<https://cryptography101.ca/>.

[^Niederreiter86]: Niederreiter, H. (1986). Knapsack-type cryptosystems and algebraic
coding theory. *Problems of Control and Information Theory*, *15*(2),
157–166. https://cir.nii.ac.jp/crid/1571980076566605568