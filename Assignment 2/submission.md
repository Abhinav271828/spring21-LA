# Assignment 2  
## MA3.101: Linear Algebra  
## Spring 2021  

### Answers  
1. The given transformation is $T(x_1,x_2) = (4x_1 - 2x_2,3|x_2|)$. To show that it is not linear, it is sufficient to show that $T(c(x_1,x_2)) = cT(x_1,x_2)$ for some $c$.  
Consider $c = -1$. Then, $T(-(x_1,x_2)) = T(-x_1,-x_2) = (4(-x_1) - 2(-x_2),3|-x_2|) = (2x_2 - 4x_1,3|x_2|)$, which is not the same as $-T(x_1,x_2)$. Hence $T$ is not linear.  

2. Since $T$ projects points from space onto the plane, it must be defined as $T(x_1,x_2,x_3) = (x_1,x_2)$.
A basis of $\mathbb{R}^3$ is $[(1,0,0),(0,1,0),(0,0,1)]$, and a basis of $\mathbb{R}^2$ is $[(1,0),(0,1)]$. Therefore the matrix representation of $T$ w.r.t these bases is
$$\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \end{bmatrix}.$$  

3. (i) $D: P^3 \to P^2$, $D(p(x)) = \frac{d}{dx}p(x)$.  
    The identity element of $P^2$ is the polynomial identically equal to 0, *i.e.*, $p(x) = 0$. Therefore the kernel is the set of antiderivatives of this polynomial, which is the set of all constant functions, *i.e.* $\ker f = \{p(x) | \exists c \in \mathbb{R}$, $\forall x p(x) = c\}$.
    The range of this function is $\mathbb{R}$ since all polynomials have an antiderivative, *i.e.*, are integrable.  
    (ii) $S: P^1 \to \mathbb{R}$, $S(p(x)) = \int_{0}^{1}p(x)dx$.  
    Consider an arbitrary $p(x) \in P^1$, $p(x) = ax + b$. Then $S(p(x)) = S(ax+b) = [\frac{a}{2}x^2 + bx]_{x = 0}^{x = 1} = \frac{a}{2} + b$.  
    The identity in $\mathbb{R}$ is 0; therefore $\ker f = \{ax + b | a + 2b = 0\}$.  
    The range of this function is the range of $\frac{a}{2} + b$ as $a, b$ range over $\mathbb{R}$. This is nothing but $\mathbb{R}$.  
    (iii) $T: M_{22} \to M_{22}$, $T(A) = A^T$.  
    The identity in $M_{22}$ is the null matrix. Therefore the kernel is the transpose of this, which is also the null matrix. Hence,
    $$\ker f = \begin{bmatrix} 0 & 0 \\ 0 & 0 \end{bmatrix}.$$
    Since transposition is idempotent, the range is simply $M_{22}$.  

4. We know that the scalar field has $p^n$ elements and the dimension is $k$, and therefore the basis has $k$ elements. All elements in the vector space can be formed by a scalar combination of the basis vectors; clearly, there are $(p^n)^k$ ways for this. Therefore the vector space has $p^{nk}$ elements.
    (a) A linear transformation is completely determined by the images of the basis vectors. For a general mapping, each basis vector can be mapped to any vector in the space. Therefore there are $(p^{nk})^k = p^{nk^2}$ different mappings.
    (b) A linear transformation is invertible if it is one-one and onto. Since we are considering transformations from $V$ to $V$, and $V$ is a finite set, being one-one is equivalent to being onto*, so we only need to prove one of the properties.  
    The transformation is onto iff the basis vectors map to another basis. This can be proved as follows:  
        (i) forward implication: Let $B$ be a basis and $C$, its image, also be a basis. Then an arbitrary $v \in V$ can be represented in the form $v = \alpha_1 c_1 + \alpha_2 c_2 + \cdots + \alpha_k c_k$. But this is nothing but $\alpha_1 T(b_1) + \alpha_2 T(b_2) + \cdots + \alpha_k T(b_k)$, which, by the linearity of $T$, is $T(\alpha_1 b_1 + \alpha_2 b_2 + \cdots + \alpha_k b_k)$, where $w = \alpha_1 b_1 + \alpha_2 b_2 + \cdots + \alpha_k b_k$ is also a vector in $V$.  
    Hence, for all $v \in V$, there is a $w \in V$ such that $T(w) = v$, which means that $T$ is onto, which makes it one-one, which makes it invertible.  
        (ii) backward implication: Let $T: V \to W$ be an onto transformation, and let $C$ be the image of the basis $B$. Then, range($T$) = $span(T(B)) = span(C)$. But $span(C) \subsetneq W$, since it is linearly dependent and has cardinality equal to the basis. This contradicts the fact that $T$ is onto; therefore $C$ must be LI and hence a basis.  
        
    Now, any set of k linearly independent vectors form a basis, and therefore, for $T$ to be invertible, the image of B can be any set of $k$ LI vectors. We therefore need to find the number of sets of LI vectors, which can be done as follows:  
    Let the first vector be $c_1 = x_1b_1 + x_2b_2 + \cdots + x_kb_k$. The $x_i$ can take any value in $F$ except all 0, so there are $((p^n)^k - 1)$ ways to select $c_1$. Then, $c_2$ can be any vector which is not a scalar multiple of $c_1$ (to preserve linear independence), which gives us $((p^n)^k - p^n)$ ways to select it. Then $c_3$ can be any vector which is not of the form $\mu c_1 + \nu c_2$, which means there are $((p^n)^k - (p^n)^2)$ ways to select it. Proceeding in this manner till $c_k$, we find that there are $(p^{nk} - 1)(p^{nk} - p^n)(p^{nk} - p^{2n}) \cdots (p^{nk} - p^{n(k-1)})$ possibilities for $C$ (including ordering).
    Therefore, the number of ways to map $B$ to another basis is $(p^{nk} - 1)(p^{nk} - p^n)(p^{nk} - p^{2n}) \cdots (p^{nk} - p^{n(k-1)})$, which is also the number of invertible linear transformations.  
    (c) The number of linear transformations with determinant 1 is $2^k$. To prove this, we consider the distinct $k \times k$ matrices (upto ordering of columns). Clearly the only ways for the determinant of such a matrix to be 1 is if the principal diagonal has an even number of $-1$s and remaining 1s or if the secondary diagonal has an odd number of $-1$s and remaining 1s.
    There are ${k \choose 0} + {k \choose 2} + \cdots$ ways for the first option; this total is $2^{k-1}$. Similarly, for the second option, we have ${k \choose 1} + {k \choose 3} + \cdots = 2^{k-1}$.  
    Therefore the total number of ways is $2^{k-1} + 2^{k-1} = 2^k$.
    
    `*` If a transformation is one-one, all elements have a unique image. Therefore the cardinality of the range is the same as that of the domain. For a transformation from $V$ to $V$, this means its range is the whole set $V$ and it is therefore onto.  
    If a transformation from $V$ to $V$ is onto, all vectors in $V$ have at least one pre-image; therefore the cardinality of the domain is at least the cardinality of the range. (It will be greater if some vector has more than one pre-image.) Since the cardinality of the domain is the same as the cardinality of the range, the transformation must be one-one.  

5. We need to prove that if $S$ is a subspace of $V$, then $span(S) = S$. We know that $span(S) = \{(a_1s_1 + a_2s_2 + \cdots + a_ns_n) | a_i \in F, s_i \in S\}$.
    (i) $span(S) \subseteq S$  
    We will use induction on $n$ to show that $(a_1s_1 + a_2s_2 + \cdots + a_ns_n) \in S$.  
    Base case ($n = 1$): $\forall a_1 \in F$, $s_1 \in S \implies a_1s_1 \in S$. This follows from the property of subspaces that $(ax + by) \in S$ whenever $a, b \in F$ and $x, y \in S$, setting $a = a_1, x = s, b = 0$.  
    Induction step: Suppose that $s = (a_1s_1 + a_2s_2 + \cdots + a_{n-1}s_{n-1}) \in S$ for all $a_i \in F$ and $s_i \in S$. Therefore, $s' = (a_1s_1 + a_2s_2 + \cdots + a_{n-1}s_{n-1} + a_ns_n) = s + a_ns_n \in S$. This follows from the property of subspaces that $(ax + by) \in S$ whenever $a, b \in F$ and $x, y \in S$, setting $a = 1, x = s, b = a_n, y = s_n$.  
    Therefore $span(S) \subseteq S$.
    (ii) $S \subseteq span(S)$  
    This is trivial; for any $s \in S$, setting $a_1 = 1, s_1 = s$ and all other $a_i$ to 0, we get that $s \in span(S)$. Therefore $S \subseteq span(S)$.  
From (i) and (ii), we see that $S$ is closed under linear combination, *i.e.* $S = span(S)$, QED.  

6. $T : V \to V$, such that
$$T(x^2) = x + m$$
$$T(x) = (m-1)x$$
$$T(1) = x^2 + m$$
    (a) $B = \{x^2,x,1\}$ is a basis.
        (i) $B$ is linearly independent. This can be proved by assuming that for some $c_i$, $c_2x^2 + c_1x + c_0 = 0$. Comparing the coefficients of $x^i$, we see that all $c_i = 0$, which means $B$ is linearly independent.
        (ii) $B$ spans $V$. We know that an arbitrary polynomial in $V$ is of the form $ax^2 + bx + c$, which is clearly a linear combination of the elements of $B$.  
    From (i) and (ii), we see that $B$ forms a basis of $V$, QED.  
    (b) [skipped]  
    (c) The columns of the matrix are the coordinate vectors of the images of each of the basis vectors. Therefore, the columns are
    $$[T(x^2)]_B = [x+m]_B = \begin{bmatrix} 0 \\ 1 \\ m \end{bmatrix}$$  
    $$[T(x)]_B = [(m-1)x]_B = \begin{bmatrix} 0 \\ m-1 \\ 0 \end{bmatrix}$$  
    $$[T(1)]_B = [x^2 + m]_B = \begin{bmatrix} 1 \\ 0 \\ m \end{bmatrix}.$$
    This makes the transformation matrix
    $$A = \begin{bmatrix} 0 & 0 & 1 \\ 1 & m-1 & 0 \\ m & 0 & m \end{bmatrix}.$$
    (d) We need to find all $a, b, c$ such that $T(ax^2 + bx + c) = 0$. From this equation, we get $aT(x^2) + bT(x) + cT(1) = a(x + m) + b((m-1)x) + c(x^2 + m) = cx^2 + (a + b(m-1))x + (a + c)m = 0$.  
    The trivial solution to this is $a = b = c = 0$, *i.e.*, $0 \in \ker T$ for all values of m.  
    We see that regardless of the value of $m$, $c = 0$. For the values of $a$ and $b$, we distinguish three cases:  
    * If $m = 0$, then $a+c = a$ can take any value. However, from the coefficient of $x$, $a - b = 0 \implies a = b$. Therefore $\ker T = \{a(x^2 + x) | a \in F\}$, which includes 0.  
    * If $m = 1$, then from the constant term, $a + c = 0 \implies a = -c = 0$. This makes the coefficient of $x$ 0 in all cases and is therefore sufficient; hence the kernel in this case is $\{bx | b \in F\}$, which also includes 0.  
    * For any other value of $m$, we see that $am = 0 \implies a = 0$, and $b(m-1) = 0 \implies b = 0$. Therefore the kernel consists of 0 alone.  
    (e) We have seen above that $T(ax^2 + bx + c) = cx^2 + (a + b(m-1))x + (a + c)m.$ Here again, we distinguish three cases based on the value of $m$:  
    * If $m = 0$, the image reduces to $cx^2 + (a - b)x$. This covers all polynomials with no constant term; therefore the image of $T$ is $\{ax^2 + bx\}$.  
    * If $m = 1$, the image reduces to $cx^2 + ax + (a+c)$. This covers all polynomials whose constant term is the sum of their other two coefficients; therefore the image of $T$ is $\{ax^2 + bx + (a+b)\}$.  
    * For any other value of $m$, let $cx^2 + (a + b(m-1))x + (a + c)m = px^2 + qx + r$, an arbitrary polynomial. Then, we see that
    $$a = \frac{r}{m} - p, b = \frac{1}{m-1}(q - \frac{r}{m} + p), c = p,$$
    which are well-defined for all $p, q, r$. Therefore the image of $T$ in this case is $V$ itself.  
7. Let $S: V \to W$ and $T: U \to V$ be two linear transformations that are onto. We need to prove that $S \circ T$ is onto.  
Consider an arbitrary $w \in W$. Now, since $S$ is onto, there exists some $v \in V$ such that $S(v) = w$. Also, since $T$ is onto, there exists some $u \in U$ such that $T(u) = v$. Substituting the latter equation in the former, we see that for any $w \in W$, there exists $u \in U$, such that $S(T(u)) = (S \circ T)(u) = w$. This proves that $S \circ T$ is onto.    
8. Let $S: V \to W$ and $T: U \to V$ be two linear transformations such that $S \circ T$ is one-one. We need to prove that $T$ is one-one. We will prove this by contradiction; suppose that $S \circ T$ is one-one, but $T$ is not.  
Since $T$ is not one-one, there exist some $w_1, w_2 \in W$ such that $w_1 \neq w_2$ and $T(w_1) = T(w_2)$. From the latter equation, we see that $S(T(w_1) = S(T(w_2))$. Therefore there exist $w_1, w_2 \in W$ such that $w_1 \neq w_2$ but $S(T(w_1) = S(T(w_2))$; this means that $S \circ T$ is not one-one, which is contrary to our assumption. Therefore $T$ must be one-one, QED.  
9. Let $S: V \to W$ and $T: U \to V$ be two linear transformations such that $S \circ T$ is onto. We need to prove that $S$ is onto. We will prove this by contradiction; suppose that $S \circ T$ is onto, but $S$ is not.  
Since $S \circ T$ is onto, for all $w \in W$, there exists some $u \in U$ such that $S(T(u)) = w$. However, since $S$ is not onto, there is some $w' \in W$, for which there is no $v \in V$ such that $S(v) = w'$.  
Setting $w = w'$ in the first equation, we see that there must be some $u \in U$ such that $S(T(u)) = w'$. But $v = T(u) \in V$ is such that $S(v) \in w'$, which is a contradiction. Therefore $S$ must be onto, QED.  
10. Let $A$ be the matrix representation of $T$ in with respect to the bases $B$ and $C$. Since $[T(b_i)]_C$ can take only one value, there is only one $A$ for $T$.  
    If another linear transformation $S$ has the same matrix representation $A$ with respect to bases $B$ and $C$, then for all $v \in V$, $[S(v)]_C = A[v]_B = [T(v)]_C \implies S(v) = T(v)$, which means $S = T$. Therefore, given a matrix representation, it can correspond to only one transformation.  
11. $T: V \to W$ is a linear transformation and $A = [T]_{C \leftarrow B}$ is its matrix representation. We need to show that nullity($T$) = nullity($A$).  
    Consider a vector $v \in \ker T$; we know that $T(v) = 0$, which means that $[T(v)]_C = A[v]_B = 0$. Therefore $[v]_B \in N(A)$, where $N(A)$ is the null space of $A$.  
    Similarly, let $x \in V$ be a vector such that $A[x]_B = 0$, *i.e.* $[x]_B$ is in $N(A)$. Then $[T(x)]_C = 0$, which means that $T(x) =0$. Therefore $x \in \ker T$.  
    The above shows that $N(A) = \{[v]_B | v \in \ker T\}$.  
    Now, consider a basis of $\ker T$, $K = \{k_1, k_2, ..., k_n\}$, and the corresponding set $K_B = \{[k_1]_B, [k_2]_B, ..., [k_n]_B\}$ in $N(A)$.  
    We know that $K$ is linearly independent, and that the coordinate vectors of a set of LI vectors is also LI. This allows us to conclude that $K_B$ is linearly independent.  
    Further, $span(K) = \ker T$. Given an arbitrary vector $k \in \ker T$, we can write $k = c_1k_1 + c_2k_2 + \cdots c_nk_n$. Taking the coordinate vectors on both sides, we get $[k]_B = c_1[k_1]_B + c_2[k_2]_B + \cdots + c_n[k_n]_B$. Therefore, all vectors $[k]_B \in N(A)$ belong to $span(K_B)$.  
    The above two properties of $K_B$ show that it is a basis of $N(A)$.  
    Now, $|K| = |K_B|$ by definition. But $|K| = \dim (\ker T)$, and $|K_B| = \dim N(A)$. Therefore $\dim (\ker T) = \dim N(A)$, *i.e.* the nullity of $T$ is equal to the nullity of $A$, QED.  
12. (a) The equations are
        $$x + 3y + 5z = 14$$
        $$2x - y - 3z = 3$$
        $$4x + 5y - z = 5$$
        Therefore the augmented matrix is
        $$\begin{bmatrix} 1 & 3 & 5 & 14 \\ 2 & -1 & -3 & 3 \\ 4 & 5 & -1 & 5 \end{bmatrix}$$
        $R_3 \to R_3 - 2R_2$ and $R_2 \to R_2 - 2R_1$
        $$\begin{bmatrix} 1 & 3 & 5 & 14 \\ 0 & -7 & -13 & -25 \\ 0 & 7 & 5 & -1 \end{bmatrix}$$
        $R_3 \to R_3 + R_2$
        $$\begin{bmatrix} 1 & 3 & 5 & 14 \\ 0 & -7 & -13 & -25 \\ 0 & 0 & -8 & -26 \end{bmatrix}$$
        $R_3 \to -\frac{1}{2}R_3$ and $R_2 \to -R_2$
        $$\begin{bmatrix} 1 & 3 & 5 & 14 \\ 0 & 7 & 13 & 25 \\ 0 & 0 & 4 & 13 \end{bmatrix}$$
        This is the row echelon form. Converting back to linear equations, we have  
        $$x + 3y + 5z = 14$$
        $$7y + 13z = 25$$
        $$4z = 13$$
        We can solve these using backsubstition, getting the answer
        $$x = \frac{36}{7}, y = -\frac{69}{28}, z = \frac{13}{4}.$$
    (b) The equations are
        $$y + z = 4$$
        $$3x + 6y - 3z = 3$$
        $$-2x - 3y + 7z = 10$$
        Therefore the augmented matrix is
        $$\begin{bmatrix} 0 & 1 & 1 & 4 \\ 3 & 6 & -3 & 3 \\ -2 & -3 & 7 & 10 \end{bmatrix}$$
        $R_2 \to \frac{1}{3}R_2$ and $R_2 \leftrightarrow R_1$
        $$\begin{bmatrix} 1 & 2 & -1 & 1 \\ 0 & 1 & 1 & 4 \\ -2 & -3 & 7 & 10 \end{bmatrix}$$
        $R_3 \to R_3 + 2R_1$
        $$\begin{bmatrix} 1 & 2 & -1 & 1 \\ 0 & 1 & 1 & 4 \\ 0 & 1 & 5 & 12 \end{bmatrix}$$
        $R_3 \to R_3 - R_2$
        $$\begin{bmatrix} 1 & 2 & -1 & 1 \\ 0 & 1 & 1 & 4 \\ 0 & 0 & 4 & 8 \end{bmatrix}$$
        $R_3 \to \frac{1}{4}R_3$ and $R_1 \to R_1 - 2R_2$
        $$\begin{bmatrix} 1 & 0 & -3 & -7 \\ 0 & 1 & 1 & 4 \\ 0 & 0 & 1 & 2 \end{bmatrix}$$
        $R_1 \to R_1 + 3R_3$ and $R_2 \to R_2 - R_3$
        $$\begin{bmatrix} 1 & 0 & 0 & -1 \\ 0 & 1 & 0 & 2 \\ 0 & 0 & 1 &  2\end{bmatrix}$$
        This is the reduced row echelon form. Converting back to linear equations, we directly get the answer
        $$x = -1, y = 2, z = 2.$$
    (c) The equations are
        $$\sqrt{2}x + y + 2z = 1$$
        $$\sqrt{2}y - 3z = -\sqrt{2}$$
        $$-y + \sqrt{2}z = 1$$
        Therefore the augmented matrix is
        $$\begin{bmatrix} \sqrt{2} & 1 & 2 & 1 \\ 0 & \sqrt{2} & -3 & -\sqrt{2} \\ 0 & -1 & \sqrt{2} & 1 \end{bmatrix}$$
        $R_3 \to R_3 - \frac{1}{\sqrt{2}}R_2$
        $$\begin{bmatrix} \sqrt{2} & 1 & 2 & 1 \\ 0 & \sqrt{2} & -3 & -\sqrt{2} \\ 0 & 0 & -\frac{1}{\sqrt{2}} & 0 \end{bmatrix}$$
        $R_3 \to-\sqrt{2}R_3$ and $R_1 \to R_1 - \frac{1}{\sqrt{2}}R_2$
        $$\begin{bmatrix} \sqrt{2} & 0 & (2+\frac{3}{2}\sqrt{2}) & 2 \\ 0 & \sqrt{2} & -3 & -\sqrt{2} \\ 0 & 0 & 1 & 0 \end{bmatrix}$$
        $R_1 \to R_1 - (2 + \frac{3}{2}\sqrt{2})R_1$
        $$\begin{bmatrix} \sqrt{2} & 0 & 0 & 2 \\ 0 & \sqrt{2} & -3 & -\sqrt{2} \\ 0 & 0 & 1 & 0 \end{bmatrix}$$
        $R_1 \to \frac{1}{\sqrt{2}}R_1$ and $R_2 \to R_2 + 3R_3$
        $$\begin{bmatrix} 1 & 0 & 0 & \sqrt{2} \\ 0 & \sqrt{2} & 0 & -\sqrt{2} \\ 0 & 0 & 1 & 0 \end{bmatrix}$$
        $R_2 \to \frac{1}{\sqrt{2}}R_2$
        $$\begin{bmatrix} 1 & 0 & 0 & \sqrt{2} \\ 0 & 1 & 0 & -1 \\ 0 & 0 & 1 & 0 \end{bmatrix}$$
        This is the reduced row echelon form. Converting back to linear equations, we directly get the answer
        $$x = \sqrt{2}, y = -1, z = 0.$$  
13. We need to show that $\langle u+v,u-v \rangle = \Vert u \Vert^2 - \Vert v \Vert ^2$.  
    Applying the distributive law twice to the LHS, we see that $\langle u+v,u-v \rangle = \langle u, u - v \rangle + \langle v, u - v \rangle = \langle u, u \rangle - \langle u,v \rangle +\langle v, u \rangle - \langle v, v \rangle$.  
    From here, we apply the commutative law and the definition of norm to get $\Vert u \Vert ^2 - \langle u,v \rangle + \langle u,v \rangle - \Vert v \Vert ^2$.  
    Cancelling, we see that $\langle u+v,u-v \rangle = \Vert u \Vert^2 - \Vert v \Vert ^2$, QED.  
14. We need to show that $\Vert u \Vert ^2 + \Vert v \Vert ^2 + 2\langle u,v\rangle = \Vert u+v \Vert ^2$.  
    Applying the definition of norm and the commutative law to the LHS, we see that it is equal to $\langle u,u \rangle + \langle u, v \rangle + \langle v, v \rangle + \langle v, u \rangle$.  
    From here, we apply the distributive law twice to get $\langle u,u+v \rangle + \langle v, v + u \rangle = \langle u+v,u+v \rangle$.  
    By the definition of norm, this is the same as the RHS. Therefore, $\Vert u \Vert ^2 + \Vert v \Vert ^2 + 2\langle u,v\rangle = \Vert u+v \Vert ^2$, QED.  
15. We need to show both directions of implication for this. We will use the definition of orthogonality: $\langle u,v \rangle = 0$.  
    (i) $\Vert u+v \Vert = \Vert u-v \Vert \implies \langle u,v \rangle = 0$.  
        First, we square both sides and apply the identity proved in 14 (above), to get $\Vert u+v \Vert = \Vert u-v \Vert \implies \Vert u+v \Vert^2 = \Vert u-v \Vert^2 \implies \Vert u \Vert ^2 + \Vert v \Vert ^2 + 2\langle u,v\rangle = \Vert u \Vert ^2 + \Vert -v \Vert ^2 + 2\langle u,-v\rangle$.  
        However, we know that $\langle u,-v \rangle  = -\langle u,v \rangle$. Applying this to $\Vert -v \Vert ^2 = \langle -v,-v \rangle$ and to $\langle u,-v\rangle$, we get the above equality to be the same as $\langle u,v \rangle = -\langle u,v \rangle$.  
        This means that $\langle u,v \rangle = 0$, *i.e.* $u$ and $v$ are orthogonal.  
    (ii) $\langle u,v \rangle = 0 \implies \Vert u+v \Vert = \Vert u-v \Vert$.  
        Since $\langle u,v \rangle = 0$, we can say that $2\langle u,v \rangle = -2\langle u, v \rangle = 2\langle u, -v \rangle$.  
        We add $\Vert u \Vert^2$ on both sides. Then, we add $\Vert v \Vert^2$ on the LHS and $\Vert -v \Vert^2$ on the RHS to get $\Vert u \Vert ^2 + \Vert v \Vert ^2 + 2\langle u,v\rangle = \Vert u \Vert ^2 + \Vert -v \Vert ^2 + 2\langle u,-v\rangle$.  
        From the identities proved in 14 (above), we see that this is equivalent to $\Vert u+v \Vert^2 = \Vert u-v \Vert^2$. We can take the positive root on both sides as the inner product always takes nonnegative values; hence we conclude that $\Vert u+v \Vert = \Vert u-v \Vert$.  
    From (i) and (ii), we can say that $\Vert u+v \Vert = \Vert u-v \Vert$ iff $u$ and $v$ are orthogonal.  
16. $T: P_2 \to P_2$, $T(p(x)) = p(2x-1)$. The basis of $P_2$ is $B = [1, x, x^2]$.  
    Therefore,  
    $$T(1) = 1$$
    $$T(x) = 2x-1$$
    $$T(x^2) = (2x-1)^2 = 4x^2 - 4x + 1.$$
    Expressing these in the same basis, we get the coordinate vectors to be  
    $$[T(1)]_B = \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}$$
    $$[T(x)]_B = \begin{bmatrix} -1 \\ 2 \\ 0 \end{bmatrix}$$
    $$[T(x^2)]_B = \begin{bmatrix} 1 \\ -4 \\ 4 \end{bmatrix},$$  
    and therefore the matrix representation of $T$ is  
    $$A = \begin{bmatrix} 1 & -1 & 1 \\ 0 & 2 & -4 \\ 0 & 0 & 4 \end{bmatrix}.$$  
    To calculate $T(3 + 2x - x^2)$, we multiply $A$ with the coordinate vector of $3 + 2x - x^2$, which is $(3,2,-1)$.  
    $$T(3 + 2x - x^2) = \begin{bmatrix} 1 & -1 & 1 \\ 0 & 2 & -4 \\ 0 & 0 & 4 \end{bmatrix} \begin{bmatrix} 3 \\ 2 \\ -1 \end{bmatrix} = \begin{bmatrix} 0 \\ 8 \\ -4 \end{bmatrix}.$$  
    This is the coordinate representation of the image. Converting it back to a polynomial, we see that $T(3 + 2x - x^2) = 8x - 4x^2$.  
