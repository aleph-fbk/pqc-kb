---
date: '2025-08-01T10:05:13+02:00'
draft: false
title: 'Appendix: Lattice problems'
math: true
weight: 291
---

A quick primer to essential notions useful in post-quantum cryptography. While this aims to be precise, it cannot and will not be exhaustive; please check out the wealth of resources available to students of cryptography[^Menezes24].

## SIS problem

> [!important] (Inhomogenous) Short Integer Solutions problem [^Ajtai96]
> Given
> - $A \overset{R}{\leftarrow}\mathbb{Z}_q^{n\times m}$, an $(n\times m)$ matrix with random entries in $\mathbb{Z}_q$,
> - $b \overset{R}{\leftarrow}\mathbb{Z}_q^{m}$, an $(m \times 1)$ vector with random entries in $\mathbb{Z}_q$,
> 
> find $z \in\mathbb{Z}^{m}$ such that $Az=b\pmod{q}$ and $z\in[-B,B]^m$.


<br>
<div class=tikz>
<script type="text/tikz">
    \definecolor{prussianblue}{HTML}{113285}
    \definecolor{marigold}{HTML}{FFB11B}
    \definecolor{rosered}{HTML}{D0104C}
  \begin{tikzpicture}[scale=1,
    A/.style={draw=prussianblue!60, fill=prussianblue!10, line width=1mm, minimum size=15mm, font={\bfseries\Large}},
    S/.style={draw=rosered!60, fill=rosered!10, line width=1mm, minimum size=15mm, font={\bfseries\Large}},
    Eq/.style={font={\bfseries\Huge},anchor=base}
    ]
    %\draw[A] (0,0) rectangle ++(2,.5);
    %\draw[A] (2,2) rectangle ++(2,.5);
    \foreach  \x/\y/\style/\row/\col/\text[count=\c] in {%
      0/0/A/2/4/$A$,
      4.5/-2/S/4/1/$z$,
      7/0/A/2/1/$b$}
    {% \node [left] at (0,\y) {\l};
      \draw [\style] (\x,\y) rectangle (\x+\col,\y+\row);
      \node [Eq] at (\x+\col/2,\y+\row-1.3) {\text};
    }
    \node [Eq] at (6.2,.7) {$=$};
    \node [Eq] at (9.7,.7) {$\pmod{q}$};
  \end{tikzpicture}
</script>
</div>


### Parameters
- If $n>m$, no solution exists.
- If $(2B+1)^m \gg q^n$ i.e., $m \gg (n \log q)/\log(2B + 1)$, a solution is likely to exist.

### Equivalence: SIS

Inhomogeneous indicates that $b\neq 0$. The SIS problem with $b=0$ is of equivalent difficulty.


## LWE problem

> [!important] Learning With Errors problem [^Regev05]
> Let 
> - $s \overset{R}{\leftarrow}\mathbb{Z}_q^{n}$ a vector with random entries in $\mathbb{Z}_q$ -- a secret;
> - $e \overset{R}{\leftarrow} [-B,B]^m$ with $B \ll q/2$ -- a small error.
> 
> Given
> - $A \overset{R}{\leftarrow}\mathbb{Z}_q^{m\times n}$ an $m\times n$ matrix with random entries in $\mathbb{Z}_q$,
> - $b = As+e \pmod{q}$,
> 
> find $s$.

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
    %\draw[A] (0,0) rectangle ++(2,.5);
    %\draw[A] (2,2) rectangle ++(2,.5);
    \foreach  \x/\y/\style/\row/\col/\text[count=\c] in {%
      0/-\row+2/A/4/2/$A$,
      2.4/0/S/2/1/$s$,
      4.5/-\row+2/E/4/1/$e$,
      7/-2/A/4/1/$b$}
    {% \node [left] at (0,\y) {\l};
      \draw [\style] (\x,\y) rectangle (\x+\col,\y+\row);
      \node [Eq] at (\x+\col/2,\y+\row-1.3) {\text};
    }
    \node [Eq] at (4,.7) {$+$};
    \node [Eq] at (6.2,.7) {$=$};
    \node [Eq] at (9.7,.7) {$\pmod{q}$};
  \end{tikzpicture}
</script>
</div>

### Parameters
- If $e=0$ ($B=0$), a solution is easy to find.
- If $B=(q-1)/2$, a solution is impossible to find; assume $B<q/4$.
- If $m\gg n$, an unique solution is likely to exist.
  - However, if also $B\ll\sqrt{n}$, a solution can be easy to find.

### Equivalence: DLWE, ss-LWE

The difficulty of solving the LWE problem has been proved equivalent to:

- the Decisional LWE (DLWE) problem: distinguish whether a given $\tilde{b}$ is a solution to an LWE instance or a random vector in $\mathbb{Z}_q^{m}$;
- the short-secret LWE (ss-LWE) problem: same as LWE but with smaller coefficients in $s$, more precisely $s \overset{R}{\leftarrow}[-B,B]^m$ a vector with random entries in $[-B,B]^m$ rather than $\mathbb{Z}_q$.

## References

[^Ajtai96]: Ajtai, M. (1996). Generating hard instances of lattice problems
(extended abstract). *STOC 96*, 99–108.
https://doi.org/10.1145/237814.237838

[^Menezes24]: Menezes, A. J. (2024). *Cryptography 101*.
<https://cryptography101.ca/>.

[^Regev05]: Regev, O. (2005). On lattices, learning with errors, random linear
codes, and cryptography. *STOC 96*, 84–93.
https://doi.org/10.1145/1060590.1060603