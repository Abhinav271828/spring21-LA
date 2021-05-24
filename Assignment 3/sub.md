# Assignment 3, Linear Algebra
## Spring 2021

### Answers
1. The given system of equations is $$a + b + 2c + d = 1,$$ $$a-b-c+d=0,$$ $$b+c = -1,$$ $$a+b+d=2.$$ The corresponding augmented matrix is $$\begin{bmatrix} 1 & 1 & 2 & 1 & 1 \\ 1 & -1 & -1 & 1 & 0 \\ 0 & 1 & 1 & 0 & -1 \\ 1 & 1 & 0 & 1 & 2 \end{bmatrix}.$$
We can apply the following linear transformations to reduce this matrix to its REF (Gaussian elimination):  
$R_2 \leftrightarrow R_3, R_3 \to R_3 - R_1, R_4 \to R_4 - R_1$
$$\begin{bmatrix} 1 & 1 & 2 & 1 & 1 \\ 0 & 1 & 1 & 0 & -1 \\ 0 & -2 & -3 & 0 & -1 \\  0 & 0 & -2 & 0 & 1 \end{bmatrix}$$
$R_3 \to R_3 + 3R_2$
$$\begin{bmatrix} 1 & 1 & 2 & 1 & 1 \\ 0 & 1 & 1 & 0 & -1 \\ 0 & 0 & -1 & 0 & 1 \\  0 & 0 & -2 & 0 & 1 \end{bmatrix}$$
$R_3 \to R_3 - R_4$
$$\begin{bmatrix} 1 & 1 & 2 & 1 & 1 \\ 0 & 1 & 1 & 0 & -1 \\ 0 & 0 & -1 & 0 & -3 \\  0 & 0 & -2 & 0 & 1 \end{bmatrix}$$
$R_4 \to R_4 - 2R_3$
$$\begin{bmatrix} 1 & 1 & 2 & 1 & 1 \\ 0 & 1 & 1 & 0 & -1 \\ 0 & 0 & -1 & 0 & -3 \\  0 & 0 & 0 & 0 & 5 \end{bmatrix}$$

This is the REF of the augmented matrix. When we convert it back to linear equations, we get $0 = 5$, which is clearly absurd; hence the given system of equations has no solution.

2. The given system of equations is $$2a + b = 3,$$ $$ 4a + b = 7,$$ $$2a + 5b = -1.$$ The corresponding augmented matrix is $$\begin{bmatrix} 2 & 1 & 3 \\ 4 & 1 & 7 \\ 2 & 5 & -1 \end{bmatrix}.$$
We can apply the following linear transformations to reduce this matrix to its REF (Gaussian elimination):  
$R_2 \to R_2 - 2R_1, R_3 \to R_3 - R_1$
$$\begin{bmatrix} 2 & 1 & 3 \\ 0 & -1 & 1 \\ 0 & 4 & -4 \end{bmatrix}$$
$R_4 \to R_4 + 4R_2$
$$\begin{bmatrix} 2 & 1 & 3 \\ 0 & -1 & 1 \\ 0 & 0 & 0 \end{bmatrix}$$

This is the REF of the augmented matrix. When we convert the nonzero rows back to linear equations, we get $$2a + b = 3, $$ $$-b = 1,$$ which we can solve by back-substitution to obtain the solution $$b = -1, $$ $$a = 2.$$

3. The given pair of planes is $$P_1 \equiv 3x + 2y + z = -1,$$ $$P_2 \equiv 2x - y + 4z = 5.$$ In order to find the line of intersection of these planes, we will use Gaussian elimination to solve the system of equations.  
The augmented matrix is $$\begin{bmatrix} 3 & 2 & 1 & -1 \\ 2 & -1 & 4 & 5 \end{bmatrix}.$$
We can apply the following linear transformations to reduce this matrix to its REF:  
$R_2 \to 3R_2$  
$$\begin{bmatrix} 3 & 2 & 1 & -1 \\ 6 & -3 & 12 & 15 \end{bmatrix}$$
$R_2 \to R_2 - 3R_1$
$$\begin{bmatrix} 3 & 2 & 1 & -1 \\ 0 & -7 & 10 & 17 \end{bmatrix}$$

This is the REF of the augmented matrix. We note that since there are only two equations, there must be one free variable in the system, which will act as a parameter. Let this variable be $z = t$. Converting the matrix in REF back to linear equations, we get 
$$3x + 2y + z = -1,$$
$$-7y + 10z = 17,$$
and solving by back-substitution, we see that  
$$y = \frac{10t - 17}{7},$$
$$x = \frac{27}{7}(1-t),$$
$$z = t.$$


4. The coefficient matrix is $$A = \begin{bmatrix} 1 & 1 & -1 \\ 1 & 1 & 1 \\ 1 & -1 & 0 \end{bmatrix}.$$ Its determinant is $|A| = 4$.  
The matrices obtained by substituting the constant terms are $$A_1 = \begin{bmatrix} 1 & 1 & -1 \\ 2 & 1 & 1 \\ 3 & -1 & 0 \end{bmatrix}, $$ $$A_2 = \begin{bmatrix} 1 & 1 & -1 \\ 1 & 2 & 1 \\ 1 & 3 & 0 \end{bmatrix}, $$ $$A_3 = \begin{bmatrix} 1 & 1 & 1 \\ 1 & 1 & 2 \\ 1 & -1 & 3 \end{bmatrix}.$$ Their determinants are $|A_1| = 9, |A_2| = -3, |A_3| = 2$.  
Therefore, by Cramer's Rule, we can obtain the solution $$x = \frac{|A_1|}{|A|} = \frac{9}{4}, $$ $$y = \frac{|A_2|}{|A|} = \frac{-3}{4}, $$ $$z = \frac{|A_3|}{|A|} = \frac{2}{4} = \frac{1}{2}.$$

5. The coefficient matrix is $$A = \begin{bmatrix} 2 & 1 & -3 \\ 0 & 1 & 1 \\ 0 & 0 & 1 \end{bmatrix}.$$ Its determinant is $|A| = 2$.  
The matrices obtained by substituting the constant terms are $$A_1 =\begin{bmatrix} 1 & 1 & -3 \\ 1 & 1 & 1 \\ 1 & 0 & 1 \end{bmatrix}, $$ $$A_2 = \begin{bmatrix} 2 & 1 & -3 \\ 0 & 1 & 1 \\ 0 & 1 & 1 \end{bmatrix}, $$ $$A_3 = \begin{bmatrix} 2 & 1 & 1 \\ 0 & 1 & 1 \\ 0 & 0 & 1 \end{bmatrix}.$$ Their determinants are $|A_1| = 4, |A_2| = 0, |A_3| = 2$.  
Therefore, by Cramer's Rule, we can obtain the solution $$x = \frac{|A_1|}{|A|} = \frac{4}{2} = 2, $$ $$y = \frac{|A_2|}{|A|} = \frac{0}{2} = 0, $$ $$z = \frac{|A_3|}{|A|} = \frac{2}{4} = \frac{2}{2} = 1.$$

6. We know that $det(XY) = det(X)det(Y)$ for any two matrices $X$ and $Y$. Therefore, $$det(AB) = det(A)det(B),$$ which we know is equal to $det(B)det(A)$ [commutativity of multiplication on real numbers]. But this is the same as $det(BA)$.  
Hence, we can conclude that $det(AB) = det(BA)$, QED.

7. If $A$ is idempotent, we know that $A^2 = A$. Taking the determinant on both sides, we get $det(A^2) = det(A)$. From the property proved above, we get $det(A)det(A) = det(A) \implies det(A)(det(A) - 1) = 0$. Therefore the only possible values of $det(A)$ are 0 and 1.

8. We need to show that every vector in $null(A)$ is orthogonal to every vector in $row(A)$, *i.e.*, $n \cdot r = 0$ for all $x \in null(A), r \in row(A)$.  
Let the rows of $A$ be the vectors $r_1, r_2, ..., r_m$, *i.e.*, if $$A = \begin{bmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{bmatrix},$$ then $r_i = (a_{i1}, a_{i2}, ..., a_{in})$.  
We know that, for all $x \in null(A)$, $A \cdot n = 0$. Expanding this, we see that $$\begin{bmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{bmatrix} \cdot \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ \vdots \\ 0 \end{bmatrix}.$$  
By the definition of matrix multiplication, we see that $0 = \sum_{j = 1}^{n}a_{ij} \cdot x_j = r_i \cdot x$, for all $r_i$.  
Therefore every row vector of $A$ is orthogonal to every $x \in null(A)$.  
Consider an arbitrary vector $v \in row(A)$. We can write $v = c_1r_1 + c_2r_2 + \cdots + c_kr_k$. When we take $v \cdot x$ for an arbitrary $x \in null(A)$, we get $(c_1r_1 + c_2r_2 + \cdots + c_kr_k) \cdot x = c_1(r_1 \cdot x) + c_2(r_2 \cdot x) + \cdots + c_k(r_k \cdot x)$, by the distributive law.  
Since $r_i \cdot x = 0$ for all $r_i$, this is equal to $c_1 \cdot 0 + c_2 \cdot 0 + \cdots + c_k \cdot 0 = 0$. Therefore $v \cdot x = 0$ for all $x \in null(A), v \in row(A)$, QED.  

9. We need to prove that if $U$ is invertible then $rank(UA) = rank(A)$. Consider the equivalent transformations $U_T$ and $A_T$.  
(i) First, we show that the rank of a matrix is equal to the rank of the corresponding transformations, *i.e.*, $rank(X) = rank(X_T)$. The rank of a matrix is the number of linearly independent column vectors it contains.  
Consider the set $M = \{Xv | v \in dom(X_T)\}$. By the definition of matrix multiplication, $M$ is the set of linear combinations of the columns of $X$, *i.e.*, the set spanned by the columns of $X$. Let $C$ be the set of column vectors of $X$.  
We know that if a set of linearly dependent vectors $C$ spans $M$, then there is some linearly independent subset of $C$ that spans $M$ and therefore forms a basis. Hence, if $C$ is linearly indepedent, it forms a basis for $M$; otherwise some (linearly independent) subset of $C$ does. Either way, the number of linearly independent vectors in $C$ is the dimension of $M$. Therefore, the rank of $X$ is the dimension of $M$.  
However, we can see from the definition of $M$ that it is nothing but $range(X_T)$, since $X_T(v) = Xv$. Therefore the rank of $X$ is equal to the dimension of the range of $X_T$; but this is nothing but the rank of $X_T$. Hence we can conclude that the rank of $X$ is equal to the rank of $X_T$.  
(ii) Now, let $rank(A) = n$ be the rank of the matrix $A$, which is also the rank of the linear transformation $A_T$. Let $B = \{b_1, b_2, ..., b_n\}$ be a basis of $range(A_T)$. Then, consider the set $B_U = \{U_T(b_1), U_T(b_2), ..., U_T(b_n)\}$. We will show that this set forms a basis of the transformation $U_T \circ A_T$, which corresponds to the matrix $UA$.
First, we will show that $B_U$ is linearly independent, which we can do by contradiction. Suppose $B_U$ is linearly dependent, *i.e.* $c_1U_T(b_1) + c_2U_T(b_2) + \cdots + c_nU_T(b_n) = U_T(c_1b_1 + c_2b_2 + \cdots + c_nb_n) = 0$ for some set of $c_i$ not all zero. Since $U_T$ is invertible, only the null vector 0 is such that $U_T(0) = 0$. Therefore $c_1b_1 + c_2b_2 + \cdots + c_nb_n = 0$, *i.e.*, B is linearly dependent, which is a contradiction. Therefore $B_U$ is linearly independent.  
Next, we will show that $B_U$ spans $range(U_T \circ A_T)$. Given an arbitrary vector $U_T(A_T(x)) \in range(U_T \circ A_T)$, we can express it as $U_T(c_1b_1 + c_2b_2 + \cdots + c_nb_n) = c_1U_T(b_1) + c_2U_T(b_2) + \cdots + c_nU_T(b_n) \in span(B_U)$. Therefore $range(U_T \circ A_T) \subseteq span(B_U)$. Similarly, given a vector $x = c_1U_T(b_1) + c_2U_T(b_2) + \cdots + c_nU_T(b_n) \in span(B_U)$, we can apply linearity and write $x = U_T(c_1b_1 + c_2b_2 + \cdots + c_nb_n)$. But $c_1b_1 + c_2b_2 + \cdots + c_nb_n \in range(A_T)$. Therefore $x \in range(U_T \circ A_T)$, which means that $span(B_U) \subseteq range(U_T \circ A_T)$.  
From the above, we can conclude that $span(B_U) = range(U_T \circ A_T)$. Taken together with the fact that $B_U$ is linearly independent, we see that $B_U$ is a basis of $range(U_T \circ A_T)$. This means that the dimension of $range(U_T \circ A_T)$ is $|B_U| = |B| = n$.  

Now, we have shown that $range(U_T \circ A_T) = rank(UA)$, which we know is $n$. Further, by assumption, $rank(A) = n$. Therefore $rank(UA) = rank(A)$, QED.

10. We need to prove that $rank(A+B) \leq rank(A) + rank(B)$. We have seen above that the rank of $X$ is equal to the dimension of $range(X_T)$. Further, we know that the matrix $A+B$ corresponds to the transformation $A_T + B_T$. We will prove the given statement by contradiction.  
Let $rank(A) = r,$ $rank(B) = s,$ $rank(A+B) = m$, where $m > r + s$. Further, suppose that $B_A = \{a_1, a_2, ..., a_r\}, B_B = \{b_1, b_2, ..., b_s\}, B_C = \{c_1, c_2, ..., c_m\}$ are bases of $range(A), range(B)$ and $range(A+B)$ respectively.  
Consider the set $X = B_A \cup B_B$; we know that $|X| \leq r+s$. Now, any vector $v$ in $range(A_T+B_T)$ can be expressed as $v = A_T(x) + B_T(x)$. But $A_T(x) \in range(A_T)$, and it can therefore can be expressed as a linear combination of vectors in $range(B_A)$. Similarly, $B_T(x)$ can be expressed as a linear combination of vectors in $range(B_B)$.  
This means that $v$ is also expressible as a linear combinations of the vectors in $B_A \cup B_B$, *i.e.* of the vectors in $X$. But $v$ is an arbitrary vector in $range(A_T + B_T)$, so $range(A_T + B_T) \subseteq span(X)$. Therefore $X$ spans $range(A_T + B_T)$.  
But the dimension of $range(A_T + B_T)$ is $|B_C| = m > |X|$. Therefore $range(A_T + B_T)$ is spanned by a set smaller than its basis, which is a contradiction. Therefore $m > r + s$ cannot be true.  
Therefore, $m \leq r + s$, *i.e.*, $rank(A_T + B_T) \leq rank(A_T) + rank(B_T)$. From the above property, however, $rank(A+B) \leq rank(A) + rank(B)$, QED.  

11. [Assuming that the vector space is $P^1$, the space of polynomials of degree $\leq 1$] We need to find that change of basis matrix from $B = [1,x]$ to $C = [x,x+1]$. Let this matrix be $A$.  
The columns of $A$ are simply the basis vectors in $B$, expressed in terms of the basis vectors in $C$.  
Therefore, column 1 of $A$ is $$[b_1]_C = [1]_C = [(-1) \cdot x + (1) \cdot (x+1)]_C = \begin{bmatrix} -1 \\ 1 \end{bmatrix}.$$ 
Similarly, column 2 of $A$ is $$[b_2]_C = [x]_C = [(1) \cdot x + (0) \cdot (x+1)]_C = \begin{bmatrix} 1 \\ 0 \end{bmatrix}.$$  

Hence, the change of basis matrix is $$A = \begin{bmatrix} -1 & 1 \\ 1 & 0 \end{bmatrix}.$$

We can apply this to $p(x) = 2 - x$, which is $[p(x)]_B = \begin{bmatrix} 2 \\ -1 \end{bmatrix}$. To express $p(x)$ in the basis $C$, we premultiply $[p(x)]_B$ with $A$. Therefore, $$[p(x)]_C = A[p(x)]_B = \begin{bmatrix} -1 & 1 \\ 1 & 0 \end{bmatrix} \begin{bmatrix} 2 \\ -1 \end{bmatrix} = \begin{bmatrix} -3 \\ 2 \end{bmatrix}.$$
We can verify this; $(-3) \cdot (x) + (2) \cdot (x+1) = -3x + 2x + 2 = 2 - x = p(x)$.

12. The Taylor expansion of a function $f(x)$ about $x = a$ is $$f(a) + \frac{f'(a)}{1}(x-a) + \frac{f''(a)}{2}(x-a)^2 + \frac{f'''(a)}{6}(x-a)^3 + \cdots $$
When we let $f(x) = p(x)$, we see that since $p(x)$ is a quadratic polynomial, all its derivatives of the third degree and above vanish. Therefore only the first three terms written above contribute to the Taylor expansion.  
The values of the derivatives are
$$p(-2) = [1 + 2x - 5x^2]_{x = -2} = 1 + 2(-2) - 5(-2)^2 = 1 - 4 - 20 = -23,$$
$$p'(-2) = [2 - 10x] _{x = -2} = 2 - 10(-2) = 2 + 20 = -22,$$
$$p''(-2) = [2] _{x = -2} = 2,$$ and
$$p'''(-2) = 0.$$

Therefore, the Taylor expansion of $p(x)$ is $$p(-2) + \frac{p'(-2)}{1}(x+2) + \frac{p''(-2)}{2}(x+2)^2$$ $$ = (-23) + \frac{22}{2}(x+2) + \frac{2}{6}(x+2)^2$$ $$ = -23 - 11(x+2) + \frac{1}{3}(x+2)^2.$$ 
