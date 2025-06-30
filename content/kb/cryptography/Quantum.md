---
date: '2025-06-06T13:19:11+02:00'
draft: true
title: 'Quantum threat'
math: true
---

$$
\newcommand{\1}{| 1 \rangle} 
$$

$$
\newcommand{\0}{| 0 \rangle} 
$$

$$
\newcommand{\Pstate}{| \Phi \rangle} 
$$

## Introduction

In current times, the transition to "post-quantum" cryptography is being discussed as unavoidable. But why so? The common trend in asking to this question briefly is "quantum computers are powerful". While this may be true, the feeling about this quantum kingdom-come in the common audience is just... not that grievous. But, how can you blame someone for not being scared of something that they perceive as distant and almost ethereal? As a matter of fact, the narrative about quantum computers has often the flavour of a scary story to tell kids that misbehave. Our aim is to describe the threat that quantum computers represent from a high level perspective, with a practical approach and without mistifying the topic. We're not here to scare, but inform. Whether you'll be scared or not in the end, is up to you. 

## Why do we need POST-Quantum?
Let's describe what makes a quantum computer a (supposed) threat. Before, intellectual honesty imposes a remark:

> [!REMARK]
> Quantum computers are still moving the first steps and are a THEORETICAL threat. No [quantum computer](https://www.spinquanta.com/news-detail/discover-the-worlds-largest-quantum-computer-in20250106092507) at the moment is powerful enough to make [economies fall](https://arxiv.org/html/2505.15907v1). Or to factor the number 42, for what it matters (and it does not, as 42 has 3 factors).

But there's a reason to have concern and to start taking precautions now. We don't really know WHEN (or even IF, to be honest) quantum computers will become a practical threat, but we know what will happen if stars align and the quantum threat becomes real before we took shelter. Let's make a mental game: Bohb comes from the future with his time machine. In his timeline, quantum computers replaced classical ones, to the point that every kid uses his DOLL-Atom3000 to check the weather on Mars for the weekend. Bohb is making a thesis on anthropology (a futur-ish version of it) and wants to check what would happen if quantum computers were dropped in a society not ready for them. We are his test subjects. Let's see what Bohb would put in his report.

>[!EVIDENCE1]
> [Digital signatures and certificates](https://ct.cloudflare.com/) can now be forged easily, no online transaction can be claimed secure, no website is to be trusted. 

>[!EVIDENCE2]
>Seems like some people [sitting on the riverbank](https://www.hashicorp.com/en/blog/harvest-now-decrypt-later-why-today-s-encrypted-data-isn-t-safe-forever) are having their moment. Old communications containing sensitive or secret data are now being decrypted. Many military and intelligence secrets are being leaked to the public. Now even governments aren't to be trusted ($\textit{Editor's note: assuming you trusted them before}$)

Even if we said that we aren't here to scare, it is possible you are scared now. But there are countermeasures we can apply in order to not be Bohb's guinea pigs. That countermeasures all fall under the definition of $\textbf{post-quantum cryptography}$


## What does "powerful" mean?

Here we try to elaborate on the "quantum computers are powerful" allegations with a practical perspective. First of all, we already said that quantum computers are not that powerful as we speak, but have the potential to become a threat for cybersecurity. One thing we want to clarify is: $\textit{what does powerful mean, exactly}$? 

>[!POWER] 
>The quantum computational model is [equivalent to the classical one](https://arxiv.org/abs/quant-ph/9906111). A classical Turing Machine (TM) can be simulated by a Quantum Turing Machine (QTM) in polynomial time; a QTM can be simulated by a TM with $\emph{exponential}$ time.

This is a crucial fact to learn: the quantum model can compute $\emph{exactly}$ the same functions computable by the classic model, no more and no less. Difference is, the quantum model can theoretically compute those functions generally faster. Hence, we are not talking about a revolution in expressiveness but in computational time.

>[!CAREFUL]
>The gap between theory and practice in QC is significant. The algorithms designed in theory have to clash with the reality of things: qubits and quantum circuits are implemented using extremely delicate physical systems, subject to errors and difficult to build. This delicacy is inherited by the same principle that allows QC to be so powerful: quantum systems are intrinsecally probabilistic.

We invite to check any example of how qubits are built, to give yourselves an idea on the complexity of the subject from an engineering perspective. However, it is useful to stress the fact that the biggest obstacle to the development of a powerful QC is practical, not theoretical. Theory on quantum computation is advancing independently from its technological development since the eighties (also Feynman gave an [hint on a quantum computational model](https://github.com/yousbot/Quantum-Papers/blob/master/1982%20-%20Feynman,%20Simulating%20physics%20with%20computers.pdf) in 1981).



## How power is achieved

What's up with QC being more powerful than a classical computer? What magic do qubits know that classical bits don't? That magic trick is called $\emph{superposition}$. Here we try not to go in deeper detail of quantum mechanics as we are not physicists and don't want to offend an entire category. If you want, go ask your local quantum physicist. Instead, we give a glimpse of what superposition is by intuition. This last word is something that fights with the very principles of quantum, but it is worth trying. Let's go step by step.

>[!STEP1]
> What's the probability of the 1 bit to be 1? What's the probability of the 0 bit to be 0? What's the probability of the 0 bit to be 1? And the probability of the 1 bit to be 0?

You read well, it is simple as it seems. Answer are 1, 1, 0, 0. But let's make a game. Let's denote the 0 bit as $\0$ and the 1 bit as $\1$, but keep denoting the probabilities as numbers without any kind of weird clothes on. It is now straightforward to see that 
$\begin{align} 
\1 &= \textcolor{red}{1} \cdot \1 + \textcolor{red}{0} \cdot \0  \\ 
\0 &= \textcolor{red}{1} \cdot \0 + \textcolor{red}{0} \cdot \1  \nonumber
\end{align}$

As you see, the $\textcolor{red}{red}$ numbers are exactly the probabilities said before. Therefore, we just described the bits as linear combinations of two possible $\emph{states}$ they may assume ($\0$ and $\1$) with the probabilities to assume them as coefficients.
Don't be fooled by the fancy notation, this is no more than a circular argument to represent things as themselves, but in a way that is convenient for what we will introduce later. From now on we refer to the equations in (1) as a "state" of the bit, which can be either $\0$ or $\1$ as you expect.

>[!STEP2]
> Can a bit NOT be in either $\0$ or $\1$ states?

No. A classical bit cannot be in a state that is neither $\0$ or $\1$, as its state is $\emph{deterministic}$. When information is encoded in bits and transmitted to a classical circuit to be computed, every step of the computation manipulates the bits in a predictable way and we can know beforehand the output state after each gate, assuming no errors caused by hardware (note that this sums up with the lack of true randomness in classical computing). If we think of this from an engineering perspective, bit information is transmitted through "on/off" or "up/down"-type systems like transistors, based on the presence or absence of electric current. Well, it may come with no surprise that these settings can describe a $\emph{binary}$ system (as it is what they are designed for). The question "can a bit NOT be in either $\0$ or $\1$ states?" is thus equivalent to asking "can this LED light be neither on or off?". Of course the answer is no, otherwise it would make no $\emph{physical}$ sense. The key word here is "physical", as implementations of classic bits make use of physical systems that perform everything we need from the classical information theory. The key idea behind quantum computing is: what if we exploit physical systems that have different paradigms? What if we use $\emph{intrinsecally probabilistic}$ systems instead of binary, deterministic ones? Of course, this change of paradigm must come with a new way to encode and manipulate information, so the promised gain in efficiency must be worth the effort. With the risk of causing physicists and computer scientists a pain in the head out of rage, we now introduce $\emph{qubits}$ as a way to encode information in order to finally answer "yes" to the question "can a QUbit not be in either $\0$ or $\1$ states?". For now, just take a qubit as an entity with this power, without wondering how is it possible to achieve it. Let's see an example: we have a qubit in state $\Pstate$ (from now on we will often identify a qubit with its state, when not confusing) such that
$$\begin{align}
\Pstate = \frac{1}{\sqrt{2}}\0 + \frac{1}{\sqrt{2}}\1
\end{align}$$

And note that 

$$
\sqrt{\frac{1}{\sqrt{2}}^2 + \frac{1}{\sqrt{2}}^2} = 1
$$

This strongly resembles a discrete probability distribution, to the point we actually say that, as in the classical case, our qubit is $\0$ with probability \$frac{1}{\sqrt{2}}^2 = \frac{1}{2}$ and $\1$ with  the same probability. This is somewhat similar to having a uniform distribution on the discrete set $\{\0, \1\}$, don't you think?