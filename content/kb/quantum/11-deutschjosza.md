---
date: '2025-07-11'
draft: true
title: 'Deutsch-Josza Algorithm'
math: true
weight: 11
---
Suppose we have a function:
$$f:\{0,1\}^n\rightarrow\{0,1\}^m$$
and we model it as an $\textbf{oracle}$ $O_f$. That is: we don't know who $f$ is but we can query the oracle with an input $x$ and get $f(x)$ as an output. A classical problem is: suppose we want to know a property of the function $f$; how many queries do i need to retrieve such information (if possible)?

$\textbf{NOTE}:$ this class of problems are the daily bread of cryptanalysis, do you see why?

In a quantum setting, we can model $O_f$ as a gate (thus, it must be reversible) in the following way:

![oraclegate](/images/oraclegate.png)

that is: $$O_f\ket{x}\ket{y}= \ket{x}\ket{f(x)\oplus y}$$. It is actually reversible:
$$O_fO_f\ket{x}\ket{y}=\ket{x}\ket{y}$$ (an involution, some might say).

- $x$ is the query;
- $y$ is called the "$\textbf{ancillary register}$" (it is, in fact, an auxiliary register).

## The Quantum Fourier Transform

We introduce a tool that will come in handy when confronting this class of problems: the Quantum Fourier Transform.

## Deutsch-Josza problem
