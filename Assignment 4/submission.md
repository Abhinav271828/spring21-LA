# Linear Algebra, IIIT Hyderabad  
## Spring 2021  
## Assignment 4  

### 5 Random Walks  
The random walk matrix $M$ of the unidrected graph $G = (V,E)$, is defined as
$$M_{ij} = \begin{cases} \frac{1}{d_j} & \{i,j\} \in E \\ 0 & \text{otherwise} \end{cases}$$
where $i, j \in V$ and $d_j = |\{\{i,j\} \in E | i \in V \}|$.  

(a) RTP: If $\lambda$ is a real eigenvalue of $M$, then $-1 \leq \lambda \leq 1$.  
Proof: Let $\lambda$ be a real eigenvalue of $M$. Then, we know that $\exists w : wM = \lambda w$ (for proof, please see 7(a) on page 4). Assuming $w$ to be the row vector consisting of $w_1, w_2, ..., w_n$, we can write this equation as
$$\begin{bmatrix} w_1 & w_2 & \cdots & w_n \end{bmatrix}
\begin{bmatrix} M_{11} & M_{12} & \cdots & M_{1n} \\ M_{21} & M_{22} & \cdots & M_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ M_{n1} & M_{n2} & \cdots & M_{nn} \end{bmatrix} = 
\begin{bmatrix} \lambda w_1 & \lambda w_2 & \cdots & \lambda w_n \end{bmatrix}$$
Let $w_k$ be the entry of $w$ with the maximum absolute value, *i.e.*, $|w_k| = \max_{1 \leq i \leq n} |w_i|$. We know the $k^{th}$ entry in the product $wM$ will be given by
$$w_1M_{1k} + w_2M_{2k} + \cdots + w_nM_{nk} = \lambda w_k$$
Taking the absolute value of the LHS and applying the triangle inequality, we see that
$$|w_1M_{1k} + w_2M_{2k} + \cdots + w_nM_{nk}| \leq |w_1M_{1k}| + |w_2M_{2k}| + \cdots + |w_nM_{nk}|$$
$$= |w_1||M_{1k}| + |w_2||M_{2k}| + \cdots + |w_n||M_{nk}|$$
$$\leq |w_k||M_{1k}| + |w_k||M_{2k}| + \cdots + |w_k||M_{nk}|$$
$$= |w_k|(M_{1k} + M_{2k} + \cdots + M_{nk}),$$
since $w_k$ has the greatest absolute value and all $M_{ij}$ are non-negative.  
But the term in the brackets is simply the sum of the entries in the $k^{th}$ column of $M$. By definition, this is equal to
$$\frac{1}{d_k} \cdot d_k.$$
Therefore the term in the brackets is 1. Substituting, we see that
$$|\lambda w_k | \leq |w_k|,$$
which means that $|\lambda||w_k| \leq |w_k|$. Since $w_k$ is nonzero (otherwise $w$ would be the null vector, which is not allowed), we can cancel it to obtain $|\lambda| \leq 1$. From this, we see that
$$-1 \leq \lambda \leq 1,$$
QED.

(b) RTP: The vector $v$ defined by
$$v_i = \frac{d_i}{\sum_{j \in V} d_j}$$
is an eigenvector of $M$ with eigenvalue 1.  
Proof: Consider the product $Mv$, which can be written as
$$\begin{bmatrix} M_{11} & M_{12} & \cdots & M_{1n} \\ M_{21} & M_{22} & \cdots & M_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ M_{n1} & M_{n2} & \cdots & M_{nn} \end{bmatrix} \begin{bmatrix} v_1 \\ v_2 \\ \vdots \\ v_n \end{bmatrix}.$$
Its $k^{th}$ entry will be given by
$$M_{k1}v_1 + M_{k2}v_2 + \cdots + M_{kn}v_n.$$
Let the vertices adjacent to vertex $k$ be $a_1, a_2, ..., a_p$. Then $d_k = p$.  
By definition of $M$, $M_{ka_i} = \frac{1}{d_{a_i}}$, and $M_{ka} = 0$ for all $a \neq a_i$.  
Therefore, the nonzero terms in the $k^{th}$ entry of the product is
$$M_{ka_1}v_{a_1} + M_{ka_2}v_{a_2} + \cdots + M_{ka_p}v_{a_p},$$
which, by definition of $v$ and $M$, is equal to
$$\frac{1}{d_{a_1}}\frac{d_{a_1}}{\sum_{j \in V} d_j} + \frac{1}{d_{a_2}}\frac{d_{a_2}}{\sum_{j \in V} d_j} + \cdots + \frac{1}{d_{a_p}}\frac{d_{a_p}}{\sum_{j \in V} d_j}.$$
Cancelling in each term, this becomes $$p \cdot \frac{1}{\sum_{j \in V} d_j}$$. But by assumption, $p = d_k$, which means the $k^{th}$ entry of $Mv$ is
$$\frac{d_k}{\sum_{j \in V} d_j}.$$
This is nothing but $v_k$. Therefore, we can conclude that $Mv = v$, QED.

(c) RTP: The maximal number of linearly independent eigenvectors with eigenvalue 1 is equal to the number of connected components in $G$.  
Proof: Let there be $n$ connected components $t_1, t_2, ..., t_n$ in $G$, such that $t_k$ contains $i_k$ vertices $t_{k1}, t_{k2}, ..., t_{ki_k}$. Then, if $k \neq l$, $M_{t_{kx}}{t_{ly}} = 0$, since $t_{kx}$ and $t_{ly}$ belong to different components in $G$.  
Let $v$ be an eigenvector of $M$ with eigenvalue . Consider the product $Mv$, which can be written as
$$\begin{bmatrix} M_{11} & M_{12} & \cdots & M_{1n} \\ M_{21} & M_{22} & \cdots & M_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ M_{n1} & M_{n2} & \cdots & M_{nn} \end{bmatrix} \begin{bmatrix} v_1 \\ v_2 \\ \vdots \\ v_n \end{bmatrix} = \begin{bmatrix} v_1 \\ v_2 \\ \vdots \\ v_n \end{bmatrix}.$$
Its $j^{th}$ entry will be given by
$$M_{j1}v_1 + M_{j2}v_2 + \cdots + M_{jn}v_n. = v_j$$
Now, vertex $j$ must belong to some component of $G$. Let this component be $t_k$, *i.e.*, $j = t_{kx}$ for some $x$. Now, only the entries in columns numbered $t_{ki_s}$ for some $s$ are nonzero, by the above property. Therefore, we see that
$$M_{t_{kx}}{t_{k1}}v_{t_{k1}} + M_{t_{kx}}{t_{k2}}v_{t_{k2}} + \cdots + M_{t_{kx}}{t_{ki_k}}v_{t_{ki_k}} = v_{t_{kx}},$$
for all $x \leq i_k$, and all $k \leq n$.  
Therefore, for each $k$, we have a system of $i_k$ linear equations relating the entries $\{v_{t_{k1}}, v_{t_{k2}}, ..., v_{t_{ki_k}} \}$, *i.e.*, $n$ independent homogeneous systems of linear equations.  
The non-trivial solution to each system gives us the corresponding entries. Therefore, for each $k$, let us define a vector $b_k$, whose $t_{kx}$-th entry is the value of $v_{t_{kx}}$ (given by the $k^{th}$ system of linear equations) for all $x \leq i_k$. All other entries of $b_k$ are 0 (the trivial solution of the linear system).  
Now, given $s$, there can be only one $b_k$ whose $s^{th}$ entry is nonzero, since $s$ can only belong to one component $t_k$. Therefore all the $b_k$ are linearly independent, and all are eigenvectors by the above property. For each eigenvector, there is a corresponding component; therefore the maximal number of eigenvectors is equal to the number of connected components in $G$, QED.  

(d)

### 6 Polynomials
$\mathcal{P}_n$ is the set of all polynomials in one variable of degree $< n$. The standard basis of $\mathcal{P}_n$ is the set of monomials, *i.e.* $\{1, x, ..., x^{n-1}\}$.  
(a) For any polynomial $q \in \mathcal{P}_n$, let $T_q : \mathcal{P}_n \to \mathcal{P}_{2n-1}$ be defined as $T_q(p) = qp$.  
$T_q$ is a linear transformation. To show this, it is sufficient to show that $T_q(as + bt) = aT_q(s) + bT_q(t)$, where $s, t \in \mathcal{P}_n$.  
We know that $T_q(as + bt) = q(as + bt)$, by definition. But polynomial multiplication is distributive over addition; therefore this is equal to $a(qs) + b(qt)$, which is clearly the same as $aT_q(s) + bT_q(t)$. Therefore $T_q$ is linear, QED.  
The columns of the matrix $M$ of $T_q$ will consist of the images of the standard basis polynomials $x_i$, which are clearly $qx_i$. But the coefficients of $qx_i$ are nothing but those of $q$, shifted by $i$ positions; that is, if $p_j = qx_i$ (which is the $j^{th}$ column of $M$), then $(p_j)_i = q_{i-j}$ (which is the entry in the $i^{th}$ row and $j^{th}$ column of $M$). Adding the relevant conditions, we can say
$$M_{ij} = \begin{cases} q_{i-j} & 0 \leq (i-j) < n \\ 0 & \text{otherwise} \end{cases}.$$

(b) The new basis vectors (in terms of the old basis vectors) are $\begin{bmatrix} 1 & 1 & 1 & 1 \end{bmatrix}^T, \begin{bmatrix} 1 & i & -1 & -i \end{bmatrix}^T, \begin{bmatrix} 1 & -1 & 1 & -1 \end{bmatrix}^T, \begin{bmatrix} 1 & -i & -1 & i \end{bmatrix}^T$. Therefore, the change of basis matrix for changing from this basis to the old one is
$$P = \begin{bmatrix} 1 & 1 & 1 & 1 \\ 1 & i & -1 & -i \\ 1 & -1 & 1 & -1 \\  1 & -i & -1 & i \end{bmatrix}.$$

Now, $T_q$ is a transformation from the standard basis in $\mathcal{P}^4$ to the standard basis in $\mathcal{P}^7$. We can convert its matrix to the transformation from the new basis in $\mathcal{P}^4$ to the standard basis in $\mathcal{P}^7$ by multiplying it on the right with $P$, as follows:  
$$T_qP = \begin{bmatrix} q_0 & q_0 & q_0 & q_0 \\ q_1+q_0 & q_1+iq_0 & q_1-q_0 & q_1-iq_0 \\ q_2+q_1+q_0 & q_2+iq_1-q_0 & q_2-q_1+q_0 & q_2-iq_1-q_0 \\ q_3+q_2+q_1+q_0 & q_3+iq_2-q_1-iq_0 & q_3-q_2+q_1-q_0 & q_3-iq_2-q_1+iq_0 \\ q_3+q_2+q_1 & iq_3-q_2-iq_1 & -q_3+q_2-q_1 & -iq_3-q_2+iq_1 \\ q_3+q_2 & -q_3-iq_2 & q_3-q_2 & -q_3+iq_2 \\ q_3 & -iq_3 & -q_3 & iq_3 \end{bmatrix}.$$


### 7 Invariance of Eigenvalues
(a) We know that $M \in \mathbb{R}^{n \times n}$.
    (i) RTP: The set of left eigenvalues of $M$ is equal to the set of right eigenvalues of $M$.  
    Proof: Let $\lambda$ be a right eigenvalue of $M$. Then, we know $\exists v : Mv = \lambda v$. From this, we obtain the condition in terms of the characteristic polynomial $\det(M - \lambda I) = 0$.  
    However, we know that $\det(A) = \det(A_T)$ for all square matrices $A$. Therefore we can say that $\det\{(M - \lambda I)^T\} = 0$. Since transpose distributes over addition and $I^T = I$, from this we see that $\det(M^T - \lambda I) = 0$. This means that $\exists w : M^T w = \lambda w$ ($w$ is the nontrivial solution to the system of equations given by $M^T - \lambda I$).  
    We can now take the transpose on both sides (using the property $(AB)^T = B^TA^T$), from which we get $w^TM = \lambda w^T$. This means that $\lambda$ is also a left eigenvalue of $M$.  
    Similarly, let $\lambda$ be a left eigenvalue of $M$. Then, we know $\exists v : vM = \lambda v$. Taking the transpose on both sides ($M^Tv^T = \lambda v^T$), we obtain the condition in terms of the characteristic polynomial $\det(M^T - \lambda I) = 0$.  
    However, we know that $\det(A) = \det(A_T)$ for all square matrices $A$. Therefore we can say that $\det\{(M^T - \lambda I)^T\} = 0$. Since transpose distributes over addition and is idempotent, and $I^T = I$, from this we see that $\det(M - \lambda I) = 0$. This means that $\exists w : M w = \lambda w$ ($w$ is the nontrivial solution to the system of equations given by $M - \lambda I$).   This means that $\lambda$ is also a right eigenvalue of $M$.  
    Therefore, each left eigenvalue of $M$ is also a right eigenvalue, and vice versa. Hence the set of left eigenvalues of $M$ is equal to the set of right eigenvalues of $M$, QED.

    (ii) The left and right eigenvectors are *not* the same. The following constitutes a counterexample:
    $$M = \begin{bmatrix} 1 & 2 \\ 3 & 6 \end{bmatrix}$$
    $$v = \begin{bmatrix} t \\ 3t \end{bmatrix}$$
    $$Mv = \begin{bmatrix} 1 & 2 \\ 3 & 6 \end{bmatrix} \begin{bmatrix} t \\ 3t \end{bmatrix} = \begin{bmatrix} 1 \cdot t + 2 \cdot 3t \\ 3 \cdot t + 6 \cdot 3t \end{bmatrix}$$
    $$ = \begin{bmatrix} 7t \\ 21 \end{bmatrix} = 7 \begin{bmatrix} t \\ 3t \end{bmatrix}$$
    $$ = 7v.$$
    Therefore $v = \begin{bmatrix} t \\ 3t \end{bmatrix}$ is a right eigenvector of $M$, with eigenvalue 7.  
    Now, consider $v_TM$:
    $$v^TM = \begin{bmatrix} t & 3t \end{bmatrix} \begin{bmatrix} 1 & 2 \\ 3 & 6 \end{bmatrix} = \begin{bmatrix}t \cdot 1 + 3t \cdot 3 & t \cdot 2 + 3t \cdot  6 \end{bmatrix}$$
    $$ = \begin{bmatrix} 10t  & 20t \end{bmatrix},$$
    which is not a scalar multiple of $v^T$.  
    Therefore $v_T$ is *not* a left eigenvector of $M$, and the set of left eigenvectors is not the same as the set of right eigenvectors of $M$, QED.

(b) $M$ and $M'$ are matrices corresponding to the same linear operator $T : V \to V$, with respect to distinct ordered bases $B$ and $B'$ respectively (say). $T$ has rank $n$ and $M$ has $n$ eigenvalues $\lambda_1, \lambda_2, ..., \lambda_n$.  
Let $P = P_{B \gets B'}$ be the change of basis matrix from $B'$ to $B$. Then, we know that $M' = P^{-1}MP$.  
    (i) RTP: The set of eigenvalues of $M$ is equal to the set of eigenvalues of $M'$.  
    Proof: Suppose $\lambda$ is an eigenvalue of $M$. This equivalent to stating that $\lambda$ is a solution to $M$'s characteristic polynomial, $\det(M - \lambda I) = 0$.  
    We know that $\det(AB) = \det(A)\det(B) = \det(BA)$. Using this property, we can multiply the above equation with $\det(P)$ on both sides, getting $\det\{(M - \lambda I)(P)\} = 0$, which implies (by the distributivity of matrix multiplication) that $\det(MP - \lambda P) = 0$. Now, we multiply this equation with $\det(P^{-1})$ on both sides, getting $\det\{(P^{-1})(MP - \lambda P)\} = 0$, which similarly implies $\det(P^{-1}MP - \lambda P^{-1}P) = \det(M' - \lambda I) = 0$. Therefore $\lambda$ is a solution to the characteristic polynomial of $M'$ as well, and is an eigenvalue of $M'$.  
    Similarly, suppose $\lambda$ is an eigenvalue of $M'$. This equivalent to stating that $\lambda$ is a solution to the characteristic polynomial of $M'$, $\det(M' - \lambda I) = 0$.  
    By definition, $P^{-1}P = I$. Substituting this and $M'$ in the above equation, we see that $\det(P^{-1}MP - \lambda P^{-1}P) = 0$. By the distributivity of matrix multiplication, this is nothing but $det\{(P^{-1})(M - \lambda I)(P)\} = 0$.  
    We know that $\det(AB) = \det(A)\det(B) = \det(BA)$. Using this property, we can separate the LHS out to $\det(P^{-1})\det(M - \lambda I)\det(P) = 0$. But $\det(P^{-1})$ and $\det(P)$ are both nonzero and can be cancelled, yielding $\det(M - \lambda I) = 0$. Therefore $\lambda$ is a solution to the characteristic polynomial of $M$ as well, and is an eigenvalue of $M$.  

    Therefore every eigenvalue of $M$ is an eigenvalue of $M'$, and vice versa. Hence the set of eigenvalues of $M$ is equal to the set of eigenvalues of $M'$, QED.

    (ii) RTP: $\det(M) = \det(M') = \prod_{i = 1}^{n} \lambda _ i$  
    Proof: Consider the expansion of $\det(\lambda I - M)$, which can also be considered the characteristic polynomial $\lambda^n + c_{n-1}\lambda^{n-1} + \cdots + c_0$ for the eigenvalues of $M$.  
    First, we will show by induction that in the recursive expansion of the determinant of an $n \times n$ matrix $A$ (where $n > 2$), each term is the product of $n$ entries, one from each row and column.  
    Base case (n = 2): If $A = \begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{bmatrix}$, then $\det(A) = a_{11}a_{22} - a_{12}a_{21}$, which satisfies the condition.  
    Inductive step: Suppose the property holds for all matrices of dimension $(n-1) \times (n-1)$. Then, expanding $\det(A)$ along the first row, each term's cofactor (by the inductive hypothesis) contains one term of each row and column of the submatrix; further, the term in row 1 of $A$ is in the only row and column missing from the cofactor. Therefore the property holds for $A$ as well.  
    Now, in the expansion of $\det(\lambda I - M)$ each term is the product of $n$ entries, one from each row and column of $\lambda I - M$. However, in the matrix, all diagonal elements are $\lambda - M_{ii}$ and all other elements are $-M_{ij}$.  
    Let the terms of $\det{\lambda I - M}$ be $S_i$ and the corresponding terms of $\det(M)$ be $T_i$. 
    We distinguish two cases for each term $S_i$:  
    * $S_i$ only contains non-diagonal elements of $\lambda I - M$. Since it is the product of $n$ such elements, each of which is the negative of a corresponding element in $M$, its value is $(-1)^nT_i$.  
    * $S_i$ contains one or more diagonal elements of $\lambda I - M$. Then, expanding all terms of the form $(\lambda - M_{ii})$ in $S_i$, we see that it is nothing but $(-1)^nT_i + p_i(\lambda)$, where $p$ is a polynomial with no constant term.  
    Therefore, taking both the above cases into account, we see that $\det(\lambda I - M) = \sum S_i = \sum (-1)^nT_i + q(\lambda)$, where $q$ is a polynomial with no constant term.  
    But this is simply the characteristic polynomial of $\lambda I - M$. Therefore we see that the constant term $c_0$ of the characteristic polynomial is simply $\sum (-1)^nT_i = (-1)^n \sum T_i = (-1)^n\det(M)$.  
    Since the eigenvalues $\lambda_i$ are the solutions of the characteristic polynomial, their product $\prod_{i = 1}^n \lambda_i = (-1)^nc_0$ (since the leading coefficient is 1). But this is equal to $(-1)^{2n}\det(M) = \det(M)$.  
    Therefore $\det(M) = \prod_{i = 1}^n \lambda_i$. Further, we know that the $\lambda_i$ are the same for $M'$ as well; therefore $\det(M') = \prod_{i = 1}^n \lambda_i$.  
    Hence, $\det(M) = \det(M') = \prod_{i = 1}^n \lambda_i$, QED.  

    (iii) As above, consider the expansion of $\det(\lambda I - M)$, which can also be considered the characteristic polynomial $\lambda^n + c_{n-1}\lambda^{n-1} + \cdots + c_0$ for the eigenvalues of $M$.  
    As shown above, each term in the expansion of the determinant of $(\lambda I - M)$ is the product of $n$ entries of $(\lambda I - M)$, one from each row and column. Consider the $\lambda^{n-1}$ term in this polynomial.  
    Clearly, in $(\lambda I - M)$, only the diagonal elements contain $\lambda$; each of them is of the form $\lambda - M_{ii}$. Therefore the $\lambda^{n-1}$ term is the sum of terms obtained by multiplying the $\lambda$ part of $n-1$ diagonal elements together. However, in each of these terms, the $n^{th}$ element cannot be anything but the remaining diagonal element's constant term (since the element cannot be in the same row or column as any of the others and the degree of $\lambda$ has to be $n-1$). This is nothing but $-M_{ii}$ for some $i$.  
    This is true of all terms. Therefore the coefficient of $\lambda^{n-1}$ in $\det(\lambda I - M)$ is simply $c_{n-1} = \sum_{i = 1}^n (-M_{ii}) = -\sum{i = 1}^n M_{ii} = -\text{trace}(M)$.  
    But we know that since the $\lambda_i$ are the roots of this polynomial, their sum must be equal to $-c_{n-1}$. Hence $\sum_{i = 1}^n \lambda_i = \text{trace}(M)$.  
    Further, we know that the $\lambda_i$ are the same for $M'$ as well; therefore $\det(M') = \sum_{i = 1}^n \lambda_i$.  
    Hence, $\text{trace}(M) = \text{trace}(M') = \sum_{i = 1}^n \lambda_i$, QED.  
