---
date: '2025-07-11'
title: 'Deutsch-Jozsa Algorithm'
math: true
weight: 11
---
Suppose we have a function:
$$f:\{0,1\}^n\rightarrow\{0,1\}^m$$
and we model it as an $\textbf{oracle}$ $O_f$. That is: we don't know who $f$ is but we can query the oracle with an input $x$ and get $f(x)$ as an output. A classical problem is: suppose we want to know a property of the function $f$; how many queries do i need to retrieve such information (if possible)?

$\textbf{NOTE}:$ this class of problems are the daily bread of cryptanalysis, do you see why?

In a quantum setting, we can model $O_f$ as a gate (thus, it must be reversible) in the following way:

![oraclegate](/images/oraclegate.png)

that is: $$O_f\ket{x}\ket{y}= \ket{x}\ket{f(x)\oplus y}.$$ It is actually reversible:
$$O_fO_f\ket{x}\ket{y}=\ket{x}\ket{y}$$ (an involution, some might say).

- $x$ is the query;
- $y$ is called the "$\textbf{ancillary register}$" (it is, in fact, an auxiliary register).

## Deutsch-Jozsa problem
>[!PROBLEM]
> Given $$f:\{0,1\}^n\rightarrow \{0,1\},$$ you don't know $f$ but you know it can be either 
> - constant: $f\equiv 0$ or $f\equiv 1$;
> - balanced: $$\{x\in \{0,1\}^n \mid f(x)=1 \}= \{x\in \{0,1\}^n | f(x)=0 \}.$$
> Decide whether it is the first or the second case with the minimal amount of queries to the oracle $\mathcal{O}_f$.

In the classical setting, $\frac{N}{2}+1$ queries are necessary in the worst case (with $N=2^n$).
Let's see the quantum solution, that takes the name of $\textbf{Deutsch-Josza algorithm}$.

Thorugh preparation, the algorithm begins with the \( n+1 \) qubit state:
\[
\ket{0}^{\otimes n} \ket{1},
\]
that is, the first \( n \) qubits are in state \( \ket{0} \), and the last one is \( \ket{1} \). A Hadamard gate is applied to each qubit to obtain the state:
\[
\frac{1}{\sqrt{2^{n+1}}} \sum_{x=0}^{2^n - 1} \ket{x} (\ket{0} - \ket{1})
\]
where \( x \) runs over all \( n \)-bit strings, i.e., integers from \( 0 \) to \( 2^n - 1 \).
<!-- The oracle maps:
\[
\ket{x} \ket{y} \mapsto \ket{x} \ket{y \oplus f(x)}
\] -->
<!-- where \( \oplus \) denotes addition modulo 2.
-->
Applying the oracle $\mathcal{O}_f$ gives:\
\[
\frac{1}{\sqrt{2^{n+1}}} \sum_{x=0}^{2^n - 1} \ket{x} \left( \ket{0 \oplus f(x)} - \ket{1 \oplus f(x)} \right)
\]

Since \( f(x) \in \{0,1\} \), we can simplify:

$$
\frac{1}{\sqrt{2^{n+1}}} \sum_{x=0}^{2^n - 1} (-1)^{f(x)} \ket{x} (\ket{0} - \ket{1})
$$
At this point, the last qubit \( \frac{1}{\sqrt{2}}(\ket{0} - \ket{1}) \) is unchanged and can be ignored. The remaining state is:

$$
\frac{1}{\sqrt{2^n}} \sum_{x=0}^{2^n - 1} (-1)^{f(x)} \ket{x}
$$

We now apply a Hadamard gate to each of the $n$ qubits. The action of the $ n $-qubit Hadamard is given by:

$$
\mathrm{H}^{\otimes n} \ket{k} = \frac{1}{\sqrt{2^n}} \sum_{j\in \{0,1\}^n}(-1)^{k \cdot j} \ket{j}
$$

where $ k \cdot j = k_0 j_0 \oplus k_1 j_1 \oplus \cdots \oplus k_{n-1} j_{n-1} $ is the bitwise dot product modulo 2. Note that we switched to the bitstring representation of $j$ instead of the integer one, in order to be consistent with the dot product. This is just a notational trick, but it can be useful to get familiar with it, for the future.

 Thus, applying Hadamards:

$$
\frac{1}{\sqrt{2^n}} \sum_{x\in \{0,1\}^n} (-1)^{f(x)}
\left[
\frac{1}{\sqrt{2^n}} \sum_{y\in \{0,1\}^n} (-1)^{x \cdot y} \ket{y}
\right]=\sum_{y\in \{0,1\}^n}
\left[
\frac{1}{2^n} \sum_{x\in \{0,1\}^n} (-1)^{f(x)} (-1)^{x \cdot y}
\right]
\ket{y}
$$

The probability of measuring state $ \ket{k} $ is:

$$
\left| \frac{1}{2^n} \sum_{x\in \{0,1\}^n} (-1)^{f(x)} (-1)^{x \cdot k} \right|^2
$$

In particular, the probability of measuring \( k = 0 \), i.e., \( \ket{0}^{\otimes n} \), is:

$$
\left| \frac{1}{2^n} \sum_{x\in \{0,1\}^n} (-1)^{f(x)} \right|^2
$$

This equals 1 if $ f(x) $ is constant, and 0 if $ f(x) $ is balanced.

In other words, the final measurement yields $ \ket{0}^{\otimes n} $ if and only if $ f(x) $ is constant.

$\textbf{We just resolved the problem with only one (!!) query to the oracle!}$
