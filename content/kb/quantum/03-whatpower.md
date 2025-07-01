---
date: '2025-07-01'
draft: true
title: 'What is power?'
math: true
weight: 3
---

## What does "powerful" mean?

Here we try to elaborate on the "quantum computers are powerful" allegations with a practical perspective. First of all, we already said that quantum computers are not that powerful as we speak, but have the potential to become a threat for cybersecurity. One thing we want to clarify is: $\textit{what does powerful mean, exactly}$? 

>[!POWER] 
>The quantum computational model is [equivalent to the classical one](https://arxiv.org/abs/quant-ph/9906111). A classical Turing Machine (TM) can be simulated by a Quantum Turing Machine (QTM) in polynomial time; a QTM can be simulated by a TM with $\textit{exponential}$ time.

This is a crucial fact to learn: the quantum model can compute $\textit{exactly}$ the same functions computable by the classic model, no more and no less. Difference is, the quantum model can theoretically compute those functions generally faster. Hence, we are not talking about a revolution in expressiveness but in computational time.

>[!WARNING]
>The gap between theory and practice in QC is significant. The algorithms designed in theory have to clash with the reality of things: qubits and quantum circuits are implemented using extremely delicate physical systems, subject to errors and difficult to build. This delicacy is inherited by the same principle that allows QC to be so powerful: quantum systems are intrinsecally probabilistic.

We invite to check any example of how qubits are built, to give yourselves an idea on the complexity of the subject from an engineering perspective. However, it is useful to stress the fact that the biggest obstacle to the development of a powerful QC is practical, not theoretical. Theory on quantum computation is advancing independently from its technological development since the eighties (also Feynman gave an [hint on a quantum computational model](https://github.com/yousbot/Quantum-Papers/blob/master/1982%20-%20Feynman,%20Simulating%20physics%20with%20computers.pdf) in 1981).
