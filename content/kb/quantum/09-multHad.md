---
date: '2025-07-11'
title: 'Multiple Hadamard gate'
math: true
weight: 9
---
We introduce one the most important gates for multiple qubit systems: the multiple Hadamard gate. Note that it may not be its standard name, but surely should. 

Recall the properties of [tensor product](../07-multqsys/#tensor-product) and the [notation](../notation/#number-notation) 
  and consider the action of $\textbf{H}\otimes{\textbf{H}}$ on the state $\ket{0} \otimes \ket{0}$:

$$
(\textbf{H} \otimes \textbf{H})\ket{0} \otimes \ket{0}
= (\textbf{H}\ket{0}) \otimes (\textbf{H}\ket{0})
= \left( \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) \right) \otimes \left( \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) \right)
$$
$$
= \frac{1}{2} (\ket{0} + \ket{1}) \otimes (\ket{0} + \ket{1})
= \frac{1}{2} \left( \ket{00} + \ket{01} + \ket{10} + \ket{11} \right)
= \frac{1}{2} \sum_{i=0}^{3} \ket{i}.
$$
 
This can be generalized to :

$$
\textbf{H}^{\otimes n} \ket{0}_n = \frac{1}{\sqrt{2^n}} \sum_{0 \le x < 2^n} \ket{x}_n
\tag{$\square$}$$

where

$$
\textbf{H}^{\otimes n} = \underbrace{\textbf{H} \otimes \textbf{H} \otimes \cdots \otimes \textbf{H}}_{n\ \text{times}}.
$$
This means that Hadamard gate can be parallelized upon $n$-qubit systems, preserving its main property: creating a balanced superposition of the computational basis' states (see the relation ($\square$)).

