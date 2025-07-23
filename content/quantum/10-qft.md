---
date: '2025-07-14'
draft: true
title: 'Quantum Fourier Transform'
math: true
weight: 10
---
Here we make use of [this notation](../notation/#number-notation).


We define the quantum Fourier transform (QFT) as a $n$-qubit gate $\mathrm{QFT}$ such that:

$$
\mathrm{QFT} \ket{x}_n = \frac{1}{\sqrt{2^n}} \sum_{y=0}^{2^{n}-1} e^{2\pi i x y / 2^n} \ket{y}_n
$$

where $xy$ is the ordinary product. We will often omit the subscript $n$ in the computational basis.

>[!REMARK]
> - If $x \neq \bar{x}$, then $\mathrm{QFT}\ket{x}$ is orthogonal to $\mathrm{QFT}\ket{\bar{x}}$
> - $\mathrm{QFT}\ket{x}$ is a normal vector for every $\ket{x}$ in the computational basis;

{{% details title="More on the QFT" closed="true" %}}

- For an arbitrary state $\sum_{x=0}^{2^n - 1} \gamma(x) \ket{x} $ , we have:
$$\mathrm{QFT} \left( \sum_{x=0}^{2^n - 1} \gamma(x) \ket{x} \right)=\sum_{x=0}^{2^n - 1} \tilde{\gamma}(x) \ket{x}$$
where
$$\tilde{\gamma}(x) = \frac{1}{\sqrt{2^n}} \sum_{y=0}^{2^n - 1} e^{2\pi i x y / 2^n} \gamma(y)$$ 
are the discrete Fourier transform of the amplitudes $\gamma(x)$.

- The Fast Fourier Transform (FFT) can be implemented with a $\mathcal{O}(N\log{N})$ time complexity, where $N$ is the length of the input vector or sequence.
The QFT can be performed with a $\mathcal{O}(n^2)$ time complexity (i.e. number of elementary gates), where $n$ is the number of qubits. Since $n=\log{N}$, complexity can be written $\mathcal{O}((\log{N})^2)$: an exponential speed-up with respect to the FFT. Of course, one have to consider that the state obtained by the QFT is not determined, as it is for the FFT.

{{% /details %}}