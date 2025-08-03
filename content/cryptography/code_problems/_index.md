---
date: '2025-08-03T10:20:40+02:00'
draft: false
title: 'Appendix: Code problems'
math: true
weight: 292
---

A quick primer to essential notions useful in post-quantum cryptography. While this aims to be precise, it cannot and will not be exhaustive; please check out the wealth of resources available to students of cryptography[^Lange19] [^Menezes24].



## Decoding problem

Informally, a code $C$ maps message vectors $m$ of length $k$ into code words $c$ of a greater length $n$. If transmission over a noisy channel[^Shannon48] modifies received messages $b = c + e$ by a sufficiently small error vector $e$, for appropriately chosen $C$, these errors can be corrected by an efficient decoding algorithm.

> [!note] **Linear code**
>
> An $\lbrack n,k,d\rbrack_q$ linear code of length $n$ and dimension $k$ is a subspace $C$ of the vector space $\mathbb {F}_{q}^{n}$, where $\mathbb {F} _{q}$ is the finite field with $q$ elements.
> 
> $C$ can be represented by
> - the row space of a **generating matrix** $G \in \mathbb{F}^{k\times n}$
> $$\begin{align*} C &= \lbrace mG \mid m \in \mathbb{F}^k \rbrace\end{align*}$$
> - the kernel space of a **parity-check matrix** $H \in \mathbb{F}^{(n-k)\times n}$
> $$\begin{align*} C &= \lbrace c \mid Hc^T=0, c \in \mathbb{F}^n \rbrace\end{align*}$$


If $q = 2$, the code is called binary.
- The **size of a code** is the number of codewords: $$|C|=q^k.$$
- The Hamming **weight of a codeword** is the number of its non-zero elements: $$w(c)=\left| \lbrace j \mid c(j)\neq 0 \rbrace \right|.$$
- The Hamming **distance between two codewords** is the number of elements in which they differ: $$d(c_1,c_2)=\left|\lbrace j \mid c_1(j) \neq c_2(j) \rbrace \right|.$$
- The **distance of a code** is, equivalently:
  - the minimum weight of its non-zero codewords;
  - the distance between the non-zero codeword with smallest Hamming weight, and the zero codeword;
  - the minimum distance between any two distinct codewords
$$d(C)=\min \lbrace d(c_1,c_2) \mid c_1,c_2 \in C, c_1 \neq c_2 \rbrace.$$
- The rows of $G$ are codewords forming a **basis** of $C$.

<br>
<div class=tikz>
<script type="text/tikz">
    \definecolor{prussianblue}{HTML}{113285}
    \definecolor{marigold}{HTML}{FFB11B}
    \definecolor{rosered}{HTML}{D0104C}
  \begin{tikzpicture}[scale=1,
    A/.style={draw=prussianblue!60, fill=prussianblue!10, line width=1mm, minimum size=15mm, font={\bfseries\Large}},
    S/.style={draw=rosered!60, fill=rosered!10, line width=1mm, minimum size=15mm, font={\bfseries\Large}},
    E/.style={draw=marigold!60, fill=marigold!10, line width=1mm, minimum size=15mm, font={\bfseries\Large}},
    Eq/.style={font={\bfseries\Huge},anchor=base}
    ]
    \foreach  \x/\y/\style/\row/\col/\text[count=\c] in {%
      0/-\row+2/A/4/2/$G^T$,
      2.4/0/S/2/1/$m$,
      4.5/-\row+2/E/4/1/$e$,
      7/-2/A/4/1/$b$}
    {% \node [left] at (0,\y) {\l};
      \draw [\style] (\x,\y) rectangle (\x+\col,\y+\row);
      \node [Eq] at (\x+\col/2,\y+\row-1.3) {\text};
    }
    \node [Eq] at (4,.7) {$+$};
    \node [Eq] at (6.2,.7) {$=$};
    %\node [Eq] at (9.7,.7) {$\pmod{q}$};
  \end{tikzpicture}
</script>
</div>

> [!important] Decoding problem
> Given
> - $x\in \mathbb{F}^n$,
> 
> find the closest codeword $c\in C$ to $x$.

For specific code families and known codes, efficient decoding algorithms exist. In general, the problem is considered hard.

### Equivalence: syndrome decoding

> [!important] Syndrome decoding problem
> The **syndrome** of $b$ is $s=Hb$, for a parity check matrix $H$. Note that $Hb=H(c+e)=He$.
> 
> Given $s$, compute $e$ such that $He=s$, and $w(e)$ is sufficiently small.

This is equivalent to the decoding problem because, computed $e$, $c=b-e$.




## References

[^Lange19]: Lange, T. (2019). *Code-based cryptography*. Executive school on
post-quantum cryptography.
<https://www.hyperelliptic.org/tanja/talks.html>.
https://pqcschool.org/slides/20190702-exec.pdf

[^Menezes24]: Menezes, A. J. (2024). *Cryptography 101*.
<https://cryptography101.ca/>.

[^Shannon48]: Shannon, C. E. (1948). A mathematical theory of communication. *The Bell
System Technical Journal*, *27*(3), 379–423.
https://doi.org/10.1002/j.1538-7305.1948.tb01338.x