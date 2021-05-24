# Linear Algebra, IIIT Hyderabad  
## Spring 2021  
## Assignment 6  

### 5.1 An Equivalence  
$M \in \mathbb{R}^{n \times n}$ is a symmetric matrix. We need to show that  
1. $\forall v \in \mathbb{R}^{n}, v^TMv \geq 0$,  
2. All eigenvalues of $M$ are nonnegative,  
3. $\exists B \in \mathbb{R}^{n \times n}, M = B^TB$,  
are all equivalent. We will do this by showing that $(1) \implies (2) \implies (3) \implies (1)$.  
(i) $(1) \implies (2)$  
    By assumption, $\forall v \in \mathbb{R}^{n}$, $v^TMv \geq 0$. We will prove from this by contradiction that all eigenvalues of $M$ are nonnegative.  
    Let some eigenvalue $\lambda_i$ be negative, with the corresponding eigenvector $u_i$, *i.e.*,
    $$Mu_i = \lambda_i u_i,$$
    where $\lambda_i < 0$. Then, consider the product $u_i^TMu_i$. Using the associative property, we see that
    $$u_i^TMu_i = u_i^T(Mu_i) = u_i^T(\lambda_i u_i) = \lambda_i (u_i^Tu_i).$$
    But we know that $\langle u, v \rangle = u^Tv$, and that $\langle v, v \rangle = \|v\|^2$. Applying these properties,  
    $$u_i^TMu_i = \lambda_i \|u_i\|^2 \leq 0,$$
    But we know that $u_i^TMu_i \geq 0$; this means that $\lambda_i \|u_i\|^2 = 0$. Since $\lambda_i < 0$, we see that $\|u_i\|^2 = 0 \implies u_i = 0$, which is a contradiction as all eigenvectors are nonzero. Therefore no $\lambda_i$ can be negative, QED.  
(ii) $(2) \implies (1)$  
    Assuming that all eigenvalues of $M$ are nonnegative, we need to show that $\exists B \in \mathbb{R}^{n \times n}$ such that $M = B^TB$. We will show this by constructing $B$ and proving that it satisfies the given property.  
    Let
    $$B = \begin{bmatrix}
    \sqrt{\lambda_1}u_{11} & \sqrt{\lambda_1}u_{12} & \cdots & \sqrt{\lambda_1}u_{1n} \\
    \sqrt{\lambda_2}u_{21} & \sqrt{\lambda_2}u_{21} & \cdots & \sqrt{\lambda_2}u_{21} \\
    \vdots & \vdots & \ddots & \vdots \\
    \sqrt{\lambda_n}u_{n1} & \sqrt{\lambda_n}u_{n1} & \cdots & \sqrt{\lambda_n}u_{n1} \end{bmatrix},$$
    where $u_{ij}$ denotes the $j^\text{th}$ entry of the $i^\text{th}$ eigenvector $u_i$. $B$ is real and well-defined since all $\lambda_i \geq 0$, by assumption. Now, let us consider the product $B^TB$.  
    $$B^TB = \begin{bmatrix}
    \sqrt{\lambda_1}u_{11} & \sqrt{\lambda_2}u_{21} & \cdots & \sqrt{\lambda_n}u_{n1} \\
    \sqrt{\lambda_1}u_{12} & \sqrt{\lambda_2}u_{22} & \cdots & \sqrt{\lambda_n}u_{n2} \\
    \vdots & \vdots & \ddots & \vdots \\
    \sqrt{\lambda_1}u_{1n} & \sqrt{\lambda_2}u_{2n} & \cdots & \sqrt{\lambda_n}u_{nn} \end{bmatrix}
    \begin{bmatrix}
    \sqrt{\lambda_1}u_{11} & \sqrt{\lambda_1}u_{12} & \cdots & \sqrt{\lambda_1}u_{1n} \\
    \sqrt{\lambda_2}u_{21} & \sqrt{\lambda_2}u_{21} & \cdots & \sqrt{\lambda_2}u_{21} \\
    \vdots & \vdots & \ddots & \vdots \\
    \sqrt{\lambda_n}u_{n1} & \sqrt{\lambda_n}u_{n1} & \cdots & \sqrt{\lambda_n}u_{n1} \end{bmatrix},$$
    which we can also write as
    $$\begin{bmatrix} \sqrt{\lambda_1}u_1 & \sqrt{\lambda_2}u_2 & \cdots & \sqrt{\lambda_n}u_n \end{bmatrix}
    \begin{bmatrix} \sqrt{\lambda_1}u_1^T \\ \sqrt{\lambda_2}u_2^T \\ \vdots \\ \sqrt{\lambda_n}u_n^T \end{bmatrix}.$$
    Evaluating this, we see that
    $$B^TB = \lambda_1 u_1u_1^T + \lambda_2 u_2u_2^T + \cdots + \lambda_n u_nu_n^T = \sum_{i = 1}^{n} \lambda_i u_i u_i^T = M,$$
    QED.  
    (iii) $(3) \implies (1)$  
    Let there exist a matrix $B$ such that $M = B^TB$. We have to show that for all $v \in \mathbb{R}^n$, $v^TMv \geq 0$.  
    Substituting $B^TB$ for $M$ in the expression, we see that
    $$v^TMv = v^TB^TBv = (Bv)^T(Bv).$$
    But we know that $\langle u, v \rangle = u^Tv$, and that $\langle v, v \rangle = \|v\|^2$. Therefore,
    $$v^TMv = \langle Bv, Bv \rangle = \|Bv\|^2 \geq 0,$$
    QED.  
This completes the proof.

### 5.2  
We are given that $v \in V$ is a nonzero vector, that $\dim V = n$, and that $L: V \to V$ is a linear transformation.  
(a) RTP: $\{v, Lv, \dots, L^nv\}$ is a linearly dependent set.  
    We know that $L$ is a linear transformation from $V$ to $V$. Therefore, $L^iv \in V$ for all $0 \leq i \leq n$. This means that the given set contains $(n+1)$ vectors, all of which belong to an $n$-dimensional space; they must therefore be linearly dependent, QED.  
(b) RTP: There exist scalars $\alpha_i$, not all zero, such that $\alpha_0 v + \alpha_1 Lv + \cdots + \alpha_n L^nV = 0$.  
    Given that $\{v, Lv, \dots, L^nv\}$ are linearly dependent, this follows from the definition of linear dependence.  
(c) RTP: If $m$ is the largest integer such that $\alpha_m \neq 0$, and $p(z) = \alpha_0 + \alpha_1z + \cdots + \alpha_mz^m$, then we can write $p(z)$ as
$$\alpha_m(z - \lambda_1)(z - \lambda_2) \cdots (z - \lambda_m).$$
    Since $p(z)$ is a polynomial having real coefficients and degree $m$, by the Fundamental Theorem of Algebra, it has $m$ roots (real as well as complex).  
(d) RTP: $(L - \lambda_1I)(L - \lambda_2I) \cdots (L - \lambda_mI)v = 0$.  
    We can rewrite the LHS of the equation in (b) as
    $$(\alpha_0 + \alpha_1L + \cdots + \alpha_mL^m)v,$$
    (omitting terms with higher powers of $L$ since the corresponding coefficients are all 0) and then factorise the transformation in brackets the same way as $p(z)$, *i.e.*,
    $$\alpha_m(L - \lambda_1I)(L - \lambda_2I) \cdots (L - \lambda_mI)v = 0.$$
    However, $\alpha_m \neq 0$ by assumption. Since there are no zero-divisors in a field, we can cancel $\alpha_m$, giving us
    $$(L - \lambda_1I)(L - \lambda_2I) \cdots (L - \lambda_mI)v = 0,$$
    QED.  
(e) RTP: One of the numbers $\lambda_i$, $1 \leq i \leq m$ must be an eigenvalue of $L$.  
    Consider the following sequence of vectors:  
    $w_m = (L - \lambda_mI)v,$  
    $w_{m-1} = (L - \lambda_{m-1}I)(L - \lambda_mI)v,$  
    $\vdots$  
    $w_1 = (L - \lambda_1I)(L - \lambda_2I) \cdots (L - \lambda_mI)v.$  
    In the above sequence, the last entry is given to be zero. Let $k$ be the largest number such that $(L - \lambda_kI)(L - \lambda_{k+1}I) \cdots (L - \lambda_mI)v = 0$, or in other words, let $k$ be such that $w_k$ is the first zero entry of the above sequence. $k$ must exist because the last entry $w_1$ of the sequence is given to be zero.  
    Clearly, $w_k = (L - \lambda_kI) w_{k+1} = 0$, and $w_{k+1} \neq 0$. This means that $Lw_{k+1} = \lambda_k w_{k+1}$ (if $k < m$), or that $Lv = \lambda_mv$ (if $k = m$). In both cases, $\lambda_k$ is an eigenvalue of $L$, QED.   
