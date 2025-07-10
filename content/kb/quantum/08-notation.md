---
date: '2025-07-10'
draft: true
title: 'The long dark teatime of the notation'
math: true
weight: 8
---

Consider this a break to dive a little deeper in the notation. This is a page you can look up whenever you get lost in the sea of symbols.

## Dirac notation

Dirac notation is basicly composed by two symbols: a $\textbf{bra}$ ($\bra{\cdot}$) and a $\textbf{ket}$ ($\ket{\cdot}$). Given a vector $v$ in the Hilbert space ($\mathbb{C}^n$,$ \langle \cdot,\cdot \rangle$) such as
$$v = \begin{pmatrix}v_1\\ v_2\\ \vdots \\ v_n \end{pmatrix},$$

then $$\ket{v}=\begin{pmatrix}v_1\\ v_2\\ \vdots \\ v_n \end{pmatrix}$$
while $$\bra{v}= \begin{pmatrix}v_1\\ v_2\\ \vdots \\ v_n \end{pmatrix}^\dagger = \begin{pmatrix}v_1^* & v_2^* & \dots & v_n^* \end{pmatrix}$$

such that, if $$w = \begin{pmatrix}w_1\\ w_2\\ \vdots \\ w_n \end{pmatrix},$$ we can write 

$$\braket{v | w} = \begin{pmatrix}v_1^* & v_2^* & \dots & v_n^* \end{pmatrix} \begin{pmatrix}w_1\\ w_2\\ \vdots \\ w_n \end{pmatrix} = \langle v, w \rangle \in \mathbb{C}, $$

the inner product in the Hilbert space $\mathbb{C}^n$. 

Moreover: 

$$\ket{v}\bra{w} =\begin{pmatrix}v_1\\ v_2\\ \vdots \\ v_n \end{pmatrix} \begin{pmatrix}w_1^* & w_2^* & \dots & w_n^* \end{pmatrix}= \begin{bmatrix}v_1w_1^* & v_1w_2^* & \dots & v_1w_n^* \\
                                v_2w_1^* & v_2w_2^* & \dots & v_2w_n^* \\
                                \dots & \dots & \dots & \dots \\
                                v_nw_1^* & v_1w_2^* & \dots & v_nw_n^*  \end{bmatrix}\in \mathbb{C}^{n \times n}$$

{{% details title="The Riesz theorem" closed="true" %}}
In a more general setting, the bra notation is used for linear and continuous functions $$f:\mathbb{C}^n\rightarrow \mathbb{C},$$
so that $$\braket{f|v} = f(v) \in \mathbb{C}.$$

This is where [Riesz representation theorem](https://en.wikipedia.org/wiki/Riesz_representation_theorem) comes into play. It essentialy states that every function such as $f$ can be represented as the action of a vector $w\in \mathbb{C}^n$. More in detail, for every $f:\mathbb{C}^n\rightarrow \mathbb{C}$ linear and continuous, there exists a unique $w\in \mathbb{C}^n$ such that 
$$f(v) = w^\dagger v$$ for every $v\in \mathbb{C}^n$. This justifies the use of the bra notation for vectors.


{{% /details %}}

## In quantum computing
We use the Dirac notation in a more flexible way. For example, we represent vectors of the canonical basis with $\ket{0}$ and $\ket{1}$ instead of $\ket{(1, 0)}$ and $\ket{(0, 1)}$. This is for the sake of simplicity. As you know, systems of $n$ qubits are represented on $\mathbb{C}^{2^n}$: the dimension scales very fast! It would be impractical to write vectors in their extended version.

Moreover, we often take poetic licenses such as $\ket{+}$ and $\ket{-}$ which are even less significant if we take the Dirac notation too (let's say) seriously, but are very meaningful in our context because they provide compactness and clarity!