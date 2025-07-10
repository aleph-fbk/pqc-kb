---
date: '2025-07-01'
draft: true
title: 'How power is achieved: qubits'
math: true
weight: 4
---



>[!WARNING]
> The following is suited for everyone with a very basic knowledge of discrete probability.

 What magic do qubits know that classical bits don't? The spell is called $\textbf{superposition}$. Here we try not to go in deeper detail of quantum mechanics as we are not physicists and don't want to offend an entire category. If you want, go ask your local quantum physicist. Instead, we give a glimpse of what superposition is by intuition.


$\textbf{QUESTION 1}$:
what's the probability of the 1 bit to be 1? What's the probability of the 0 bit to be 0? What's the probability of the 0 bit to be 1? And the probability of the 1 bit to be 0?

You read well, it is simple as it seems. Answers are 1, 1, 0, 0. But follow us now. Let's denote the 0 bit as $\ket{0}$ and the 1 bit as $\ket{1}$, but keep denoting the probabilities as numbers without any kind of weird clothes on. It is now straightforward to see that 
$$
\ket{1} = \textcolor{red}{1} \cdot \ket{1} + \textcolor{red}{0} \cdot \ket{0}  \\ 
\ket{0} = \textcolor{red}{1} \cdot \ket{0} + \textcolor{red}{0} \cdot \ket{1}  
$$

As you see, the $\textcolor{red}{red}$ numbers are exactly the probabilities said before. Therefore, we just described the bits as linear combinations of two possible $\textbf{states}$ they may assume ($\ket{0}$ and $\ket{1}$) with the probabilities to assume them as coefficients.
Don't be fooled by the fancy notation, this is no more than a circular argument to represent things as themselves, but in a way that is convenient for what we will introduce later. From now on we refer to these linear combinations as the "state" of the bit, which can be either $\ket{0}$ or $\ket{1}$ as you expect.

$\textbf{QUESTION 2}$:
Can a bit NOT be in either $\ket{0}$ or $\ket{1}$ states?

{{% details title="Short Answer" closed="true" %}}
Of course not!
{{% /details %}}

{{% details title="Long Answer" closed="true" %}}
No. A classical bit cannot be in a state that is neither $\ket{0}$ or $\ket{1}$, as its state is $\textbf{deterministic}$. When information is encoded in bits and transmitted to a classical circuit to be computed, every step of the computation manipulates the bits in a predictable way and we can know beforehand the output state after each gate, assuming no errors caused by hardware (note that this sums up with the lack of true randomness in classical computing). If we think of this from an engineering perspective, bit information is transmitted through "on/off" or "up/down"-type systems like transistors, based on the presence or absence of electric current. Well, it may come with no surprise that these settings can describe a $\textbf{binary}$ system (as it is what they are designed for). The question "can a bit NOT be in either $\ket{0}$ or $\ket{1}$ states?" is thus equivalent to asking "can this LED light be neither on or off?". Of course the answer is no, otherwise it would make no $\textbf{physical}$ sense. The key word here is "physical", as implementations of classic bits make use of physical systems that perform everything we need from the classical information theory. The main idea behind quantum computing is: what if we exploit physical systems that have different paradigms? What if we use $\textbf{intrinsecally probabilistic}$ systems instead of binary, deterministic ones? Of course, this change of paradigm must come with a new way to encode and manipulate information. The physical systems that have this feature are exactly the quantum ones.
{{% /details %}}

 With the risk of causing physicists and computer scientists a pain in the head out of rage, we now introduce $\textbf{qubits}$ as a way to encode information in order to finally answer "yes" to the question "can a QUbit not be in either $\ket{0}$ or $\ket{1}$ states?". For now, just take a qubit as an entity with this power, without wondering how is it possible to achieve it (it suffices to think of them as "quantum stuff"). Let's see an example: we have a qubit in state $\ket{\Phi}$ such that
$$
\ket{\Phi} = \frac{1}{\sqrt{2}}\ket{0} + \frac{1}{\sqrt{2}}\ket{1}
$$

and note that 

$$
\sqrt{\left(\frac{1}{\sqrt{2}}\right)^2 + \left(\frac{1}{\sqrt{2}}\right)^2} = 1.
$$

This strongly resembles a discrete probability distribution, to the point we actually say that, as in the classical case, our qubit is observed to be $\ket{0}$ with probability $\left(\frac{1}{\sqrt{2}}\right)^2 = \frac{1}{2}$ and $\ket{1}$ with  the same probability. This is somewhat similar to having a uniform distribution on the discrete set $\{\ket{0}, \ket{1}\}$, don't you think? This is a simple example of superposition: our qubit is neither in the state $\ket{0}$ nor $\ket{1}$; we only know the probability of it to be in one of those state when we $\textbf{observe}$ it.
>[!WARNING]
>To "observe" a qubit means to check whether it is $\ket{1}$ or $\ket{0}$ through a physical process called $\textbf{measurement}$. Before you measure, don't be tempted to think the qubit is already in the $\ket{1}$ or $\ket{0}$ states; this is the core of superposition: the qubit is said to be in a state of superposition between $\ket{0}$ and $\ket{1}$ (weighted with probabilities) but measurement actively makes its state collapse on one or another (with according probability). Measurement actively changes the intrinsecally probabilistic state in a deterministic one, i.e., one we can actually see, if you want.

{{% details title="The cat experiment" closed="true" %}}
Superposition can be understood with the help of the well-known [Schrodinger's cat](https://en.wikipedia.org/wiki/Schr%C3%B6dinger's_cat) experiment: until you check, you must assume the qubit to be simultaneously $\ket{1}$ and $\ket{0}$ (dead AND alive). When you measure (open the box), system collapses and you find the qubit to be either $\ket{1}$ or $\ket{0}$ (dead OR alive). The probabilities to find one of the two outputs are the (norm squared of the) relative coefficents in the state before measurement.
{{% /details %}}


  In general, any state can be described as $$\ket{\Phi} = \alpha\ket{0} + \beta\ket{1}$$ with $\alpha, \beta \in \mathbb{C}$ such that $|\alpha|^2 + |\beta|^2 =1$.



 And what do we gain from this? How do we use an information encoded such as this?