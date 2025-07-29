---
date: '2025-07-01'
title: 'How power is achieved: gates'
math: true
weight: 5
---


>[!WARNING]
> The following is suited for those with a basic knowledge of linear algebra and information theory. Some concepts are reintroduced here, but we assume a certain familiarity with circuits, gates, linear applications and associated matrices, linear combinations, basis and orthonormality.

The main problem now is: what to do with qubits? Of course we need operations that we can perform on them to manipulate the information in order to get the outputs we want: we need a model to build gates and circuits, just like in the classical setting. Now, we give some building blocks that you can take as axioms, but come from the principles of quantum mechanics. Here we assume to have a system composed of one qubit.

>[!DEFINITION]
>A linear transformation $U: \mathbb{C}^2\rightarrow \mathbb{C}^2$ is called $\textbf{unitary}$ if it preserves the norm of vectors, so: $$||U(v)|| = ||v||$$ for every $v \in \mathbb{C}^2$.

From now on we identify $U$ with its associated 2x2 matrix with complex coefficients, with respect to the canonical basis.

>[!CLAIM]
>Quantum gates can only be unitary transformations.

Reasons for this are inherited from quantum mechanics. For our scope, it may be taken as an axiom. One of the reasons for this, the more useful for us at the moment is: unitary transformations preserve the norm of vectors and a quantum state is always a complex vector with norm equal 1, as we saw in the qubit section. Therefore, unitary transformations are needed for consistency.

>[!REMARK]
>As unitary transformation, quantum gates are $\textbf{always reversible}$.

Now it's time to unveil the true nature of the notation $| \rangle$, which is called $\textbf{ket}$ and is part of the "$\textbf{Dirac notation}$". It is well suited to describe states and to perform computations on them in a way that will be clear in the future. The states $\ket{1}$ and $\ket{0}$ are special, as they encode the information just as a classical bit would: 0 and 1. We now identify them as the vectors of the canonical basis in $\mathbb{C}^2$:

$$ \ket{0} \leftrightarrow
\begin{pmatrix}
1 \\
0
\end{pmatrix} \in \mathbb{C}^2
$$ 

$$ \ket{1} \leftrightarrow
\begin{pmatrix}
0 \\
1
\end{pmatrix} \in \mathbb{C}^2
$$ 

and call them the $\textbf{computational basis}$. From now on every state $\ket{\Phi} = \alpha\ket{0} + \beta\ket{1}$ can be seen as the vector 
$$\begin{pmatrix}
\alpha \\
\beta
\end{pmatrix} \in \mathbb{C}^2
$$ 
with respect to the computational basis. 

>[!RECALL]
> Let $V$ be a vector space of dimension $n$ over a field $K$. Assume $V$ has a inner product $$\langle \cdot,\cdot \rangle:V\times V \rightarrow K.$$ A basis $\{v_1, . . . , v_n\}$ for $V$ is called orthonormal if 
> - $\left\lVert v_i \right\rVert = 1$ for all $i \in {1, ...,n}$;
> - $\langle v_i,v_j \rangle = 0$ for all $i \neq j$,  
>where the norm $\left\lVert \cdot \right\rVert$ is the one induced by the inner product.

From now on we will use the notation $v^\dagger$ ("$v$ $\textbf{dagger}$") to denote the transpose conjugate of $v$; we will use it for matrices as well to denote the same thing.

{{% details title="More on unitary matrices" closed="true" %}}
Here we recall some useful information about unitary matrices.

>[!CLAIM]
> A unitary matrix $U$ is invertible and its inverse is $U^\dagger$, i.e. $$UU^\dagger=I.$$

From which follows:

>[!CLAIM]
> The columns and the rows of a unitary matrix $U\in \mathbb{C}^{n\times n}$ are orthonormal bases for $\mathbb{C}^n$.

>[!CLAIM]
> Unitary matrices preserve scalar product, i.e. $$\langle Uv, Uw \rangle=\langle v, w \rangle$$ for every $v, w \in \mathbb{C}^n$.

Nonetheless, you can prove these to be equivalent to the definition we gave.
Finally, it holds:
>[!CLAIM]
> If $U$ is unitary, then so is $U^\dagger$.

And we invite to prove the following, using these properties:

>[!EXERCISES]
> - All eigenvalues of a unitary matrix have modulus 1, hence: every eigenvalue of a unitary matrix can be written as $e^{i\theta}$ for the right $\theta\in [0, 2\pi]$.
> - If $U$ is unitary and self-adjoint (so $U^\dagger=U$), then it is an involution (i.e. it is its own inverse).



{{% /details %}}