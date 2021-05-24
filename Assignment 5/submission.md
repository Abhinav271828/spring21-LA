# Linear Algebra, IIIT Hyderabad  
## Spring 2021  
## Assignment 5  

### 3.1 An Orthonormal Basis for Boolean Functions  
Let $\mathcal{F}$ be the set of functions with domain $\{+1,-1\}^n$ and range $\mathbb{R}$.  
An inner product is defined on this space as  
$$\langle f, g \rangle = \frac{1}{2^n}\sum_{x \in \{+1,-1\}^n} f(x)g(x)$$
with the corresponding norm
$$\|f\| = \sqrt{\langle f,f \rangle}.$$

The following set of functions is defined:
$$\{\chi_S\}_{S \subseteq \{1,...,n\}},$$
where
$$\chi_S(x) = \prod_{i \in S}x_i.$$
If $S = \emptyset$, $\chi_S(x) = 1$ for all $x$.  


(a) RTP: The functions $\chi_S$ form an orthonormal basis under the inner product defined.  
Proof: We will first show that the $\chi_S$ are orthogonal to each other, and then that they all have unit norm.  
    (i) The $\chi_S$ are orthogonal.  
        Consider the inner product of two distinct functions, $\langle \chi_S, \chi_T \rangle$.  
        We will show by induction on $n$ that out of the $2^n$ values of $x$, $\chi_S(x) = \chi_T(x)$ for exactly $2^{n-1}$ values, and $\chi_S(x) = -\chi_T(x)$ for exactly $2^{n-1}$ values.  
        Base case, $n = 1$: There are only two basis functions, $\chi_{\emptyset}$ and $\chi_{\{1\}}$. Clearly, $$\chi_{\emptyset}(1) = \chi_{\{1\}}(1) = 1$$ and $$\chi_{\emptyset}(-1) = -\chi_{\{1\}}(-1).$$ This proves the base case.  
        Induction step: Suppose $n > 1$, and the statement is true for all smaller values.  
        Let $\mathcal{P}(\{1,...,n\}) \cap \mathcal{P}(\{1,...,n-1\})$ [$\mathcal{P}$ = powerset] be called the *first group* of subsets of $\{1,...,n\}$ (*i.e.*, those which do not include $n$). Let all other subsets of $\{1,...,n\}$ be called the *second group*. Further, let $x = (x_1, ..., x_n)$. Now, we distinguish three cases with respect to $S$ and $T$:  
        1. $S$ and $T$ both belong the first group. In this case, $x_n$ does not affect the values of $\chi_S(x)$ and $\chi_T(x)$; *i.e.*, $$\chi_S(x_1, x_2, ..., x_n) = \chi_S(x_1, x_2, ..., x_{n-1})$$ and $$\chi_T(x_1, x_2, ..., x_n) = \chi_T(x_1, x_2, ..., x_{n-1}),$$both of which exist since $S$ and $T$ are subsets of $\{1,...,n-1\}$. By the induction hypothesis, then, the statement holds.  
        2. $S$ and $T$ both belong the second group [$S' = S - \{n\}$ and $T' = T - \{n\}$]. In this case, $x_n$ is present in the expression of $\chi_S(x)$ and $\chi_T(x)$; *i.e.*, $$\chi_S(x_1, x_2, ..., x_n) = x_n \cdot \chi_{S'}(x_1, x_2, ..., x_{n-1})$$ and $$\chi_T(x_1, x_2, ..., x_n) = x_n \cdot \chi_{T'}(x_1, x_2, ..., x_{n-1}),$$ both of which exist since $S'$ and $T'$ are subsets of $\{1,...,n-1\}$. Therefore, if $\chi_{S'}(x_1, x_2, ..., x_{n-1}) = \chi_{T'}(x_1, x_2, ..., x_{n-1})$, then $\chi_S(x) = \chi_T(x)$; and if $\chi_{S'}(x1, x_2, ..., x_{n-1}) = -\chi_{T'}(x1, x_2, ..., x_{n-1})$, then $\chi_S(x) = -\chi_T(x)$, for all $x$. Therefore, by the induction hypothesis, the statement holds.  
        3. One of $S$ and $T$ belongs to the first group, and the other to the second. WLOG, say $S$ belongs to the first group and $T$ to the second [$T' = T - \{n\}$]. Then, $$\chi_S(x_1, x_2, ..., x_n) = \chi_S(x_1, x_2, ..., x_{n-1})$$ for all $x$.  
        Now, if $x_n = 1$, then $$\chi_T(x_1, x_2, ..., x_n) = \chi_{T'}(x_1, x_2,... x_{n-1}),$$which exists since $T'$ is a subset of $\{1,...,n-1\}$. Among all such values of $x$, then, half are such that $\chi_S(x) = \chi_T(x)$ and half such that $\chi_S(x) = -\chi_T(x)$.  
        If $x_n = -1$, then $$\chi_T(x_1, x_2, ..., x_n) = -\chi_{T'}(x_1, x_2, ..., x_{n-1}).$$ Therefore, if $\chi_S(x_1, x_2, ..., x_{n-1}) = \chi_{T'}(x_1, x_2, ..., x_{n-1})$, then $\chi_S(x) = -\chi_T(x)$; and if $\chi_S(x_1, x_2, ..., x_{n-1}) = -\chi_{T'}(x_1, x_2, ..., x_{n-1})$, then $\chi_S(x) = \chi_T(x)$. Therefore, among all such values of $x$, half are such that $\chi_S(x) = \chi_T(x)$ and half such that $\chi_S(x) = -\chi_T(x)$. This proves the claim.  
        
        Therefore, for all distinct $S$ and $T$, half of the values of $x$ are such that $\chi_S(x) = \chi_T(x)$, and half are such that $\chi_S(x) = -\chi_T(x)$. Then, in the sum
        $$\langle \chi_S, \chi_T \rangle = \frac{1}{2^n} \sum_{x \in \{+1,-1\}^n} \chi_S(x)\chi_T(x),$$
        exactly half the terms (those for which $\chi_S(x) = \chi_T(x)$) have the value 1, and the remaining (those for which $\chi_S(x) = -\chi_T(x)$) have the value $-1$. Hence the sum is $2^{n-1} - 2^{n-1} = 0$, QED.  
        
    (ii) The $\chi_S$ have unit norm.
        Considering definition of the norm, we see that
        $$\|\chi_S\| = \sqrt{\langle \chi_S, \chi_S \rangle} = \sqrt {\frac{1}{2^n} \sum_{x \in \{+1,-1\}^n} \chi_S^2(x) }.$$
        Clearly, $\chi_S^2(x) = 1$ for all $2^n$ values of $x$. Therefore, the term under the square root is simply $\frac{2^n}{2^n} = 1$. Therefore $\|\chi_S\| = 1$, QED. 
        
    Now, we know that all $\chi_S$ are all orthogonal (and therefore linearly independent) and have unit norm. Since $2^n$ linearly independent vectors in a space of dimension $2^n$ must span it, the $\chi_S$ span $\mathcal{F}$. Therefore, they form an orthonormal basis, QED.

(b) Let $f \in \mathcal{F}$ be a function with range $\{+1,-1\}$, such that
$$f = \sum_{S \subseteq \{1,...,n\}} \hat{f_S}\chi_S,$$
where $\hat{f_S} \in \mathbb{R}$ for all $S \subseteq \{1,...,n\}$.  
RTP: $\sum_{S \subseteq \{1,...,n\}} (\hat{f_S})^2 = 1$.  
Proof: Consider the following enumeration of the values in $\{+1,-1\}^n$, which we will write as $x^{i|n}$ for $1 \leq i \leq 2^n$:  
For $n = 1$,
$$x^{1|1} = (+1)$$
$$x^{2|1} = (-1).$$
For $n \geq 1$, $x^{1|n+1}$ to $x^{2^n|n+1}$ are respectively the values of $x^{1|n}$ to $x^{2^n|n}$, with $+1$ appended at the end of each. For all remaining $x^{i|n+1}$, we put the $x^{i|n+1}$'s in the same order as the $x^{i|n}$'s with $-1$ appended at the end of each. In other words, if we represent appending with a colon $(:)$,
$$x^{i|n+1} = \begin{cases} x^{i|n}:(+1) & 1 \leq i \leq 2^n \\ x^{i - 2^n|n}:(-1) & 2^n < i \leq 2^{n+1}. \end{cases}$$
For example,
$$x^{1|2} = (+1,+1),$$
$$x^{2|2} = (-1,+1),$$
$$x^{3|2} = (+1,-1),$$
$$x^{4|2} = (-1,-1).$$

Further, let us define an enumeration of the subsets of $\{1,...,n\}$, which we will write as $S^{i|n}$ for $1 \leq i \leq 2^n$, as follows:  
For $n = 1$,
$$ S^{1|1} = \{\}$$
$$ S^{2|1} = \{1\}.$$
For $n \geq 1$, $S^{i|n+1}$ to $S^{2^n|n+1}$ are respectively the exact same as $S^{i|n}$ to $S^{2^n|n}$. The remaining $S^{i|n+1}$ are the $S^{i|n}$ in the same order, with $n+1$ added to each. In other words,
$$S^{i|n+1} = \begin{cases} S^{i|n} & 1 \leq i \leq 2^n \\ S^{i|n} \cup \{n+1\} & 2^n < i \leq 2^{n+1}. \end{cases}$$
For example,
$$S^{1|2} = \{\}$$
$$S^{2|2} = \{1\}$$
$$S^{3|2} = \{\} \cup {2} = \{2\}$$
$$S^{4|2} = \{1\} \cup {2} = \{1,2\}.$$
This enumeration of $S^{i|n}$ is equivalent to an enumeration of the basis functions $\chi$. Here, we note an important property of this enumeration: if $j > 2^{n-1}$, then $\chi_{S^{j|n}}(x^{i|n-1}:(\xi)) = \xi \cdot \chi_{S^{j-2^{n-1}}|n}(x^{i|n-1})$. This is clear from the fact that $S^{j|n} = S^{j-2^{n-1}|n} \cup {n}$, and that the $n^{\text{th}}$ entry of $x^{i|n-1}:(\xi)$ is $\xi$.  

Now, we define a matrix $X_n$ as
$$X_n = 
\begin{bmatrix}
\chi_{S^{1|n}}(x^{1|n}) & \chi_{S^{2|n}}(x^{1|n}) & \cdots & \chi_{S^{2^n|n}}(x^{1|n}) \\
\chi_{S^{1|n}}(x^{2|n}) & \chi_{S^{2|n}}(x^{2|n}) & \cdots & \chi_{S^{2^n|n}}(x^{2|n}) \\
\vdots & \vdots & \ddots & \vdots \\
\chi_{S^{1|n}}(x^{2^n|n}) & \chi_{S^{2|n}}(x_{2^n|n}) & \cdots & \chi_{S^{2^n|n}}(x^{2^n|n}) \end{bmatrix},$$
*i.e.*, $(X_n)_{ij} = \chi_{S^{j|n}}(x^{i|n})$,
and two vectors $\hat{f}$ and $v_f$ as
$$\hat{f} =
\begin{bmatrix}
\hat{f}_{S^{1|n}} \\ \hat{f}_{S^{2|n}} \\ \vdots \\ \hat{f}_{S^{2^n|n}} \end{bmatrix},
v_f =
\begin{bmatrix}
f(x^{1|n}) \\ f(x^{2|n}) \\ \vdots \\ f(x^{2^n|n}) \end{bmatrix}.$$

From the definition of the $\hat{f}_S$, it is clear that $v_f = X_n \hat{f}$, *i.e.*, $\hat{f} = X_n^{-1}v_f$.

$X_n$ has two important properties, both of which we will prove by induction:  
(i) $X_n$ is symmetric. For the base case $n = 1$, 
    $$X_1 = \begin{bmatrix} 1 & 1 \\ 1 & -1 \end{bmatrix},$$
    which is clearly symmetric.  
    Now, we will try to build $X_{n+1}$ from $X_{n}$ (which we can assume to be symmetric) for $n \geq 1$. Consider an arbitrary element $(X_{n+1})_{ij}$; we distinguish four cases:  
    1. $1 \leq i, j \leq 2^{n}$: This element is, by definition, equal to $\chi_{S^{j|n+1}}(x^{i|n+1})$. From the constraint on $i$ and $j$, it is clear that this is the same as $\chi_{S^{j|n}}(x^{i|n}:(+1)) = \chi_{S^{j|n}}(x^{i|n})$, which is nothing but $(X_{n})_{ij}$. Therefore, the top-left quarter of $X_{n+1}$ is identical to $X_{n}$.  
        2. $1 \leq i \leq 2^{n} < j \leq 2^{n+1}$: This element is equal to $\chi_{S^{j|n+1}}(x^{i|n+1})$. From the constraint on $i$ and $j$, this is the same as $\chi_{S^{j-2^n|n} \cup \{n+1\}}(x^{i|n}:(+1))$.  By the property of the $\chi_S$ stated above, this is simply $(+1) \cdot \chi_{S^{j - 2^n|n}}(x^{i|n}) =  \chi_{S^{j-2^n|n}}(x^{i|n}) = (X_{n})_{i(j-2^{n})}$. Therefore, the top-right quarter of $X_{n+1}$ is also identical to $X_{n}$.  
        3. $1 \leq j \leq 2^{n} < i \leq 2^{n+1}$: This element is equal to $\chi_{S^{j|n+1}}(x^{i|n+1})$. From the constraint on $i$ and $j$, this is the same as $\chi_{S^{j|n}}(x^{i-2^n|n}:(-1))$. However, $S^{j|n}$ doesn't include $n+1$, and so the $(-1)$ is not part of its expansion. Hence this is the same as $\chi_{S^{j|n}}(x^{i-2^n|n})$, which is $(X_{n})_{(i-2^{n})j}$. Therefore, the bottom-left quarter of $X_{n+1}$ is also identical to $X_{n}$.  
        4. $2^{n} < i, j \leq 2^{n+1}$: This element is equal to $\chi_{S^{j|n+1}}(x^{i|n+1})$. From the constraint on $i$ and $j$, this is the same as $\chi_{S^{j-2^n|n} \cup \{n+1\}}(x^{i-2^n|n}:(-1))$. By the property of the $\chi_S$ stated above, this is simply $(-1) \cdot \chi_{S^{j-2^n|n}}(x^{i-2^n|n}) = -(X_{n})_{(i-2^{n})(j-2^{n})}$. Therefore, the bottom-right quarter of $X_{n+1}$ is identical to $-X_{n}$.  
    From the above, we can say that
    $$X_{n+1} = \begin{bmatrix} X_{n} & X_{n} \\ X_{n} & -X_{n} \end{bmatrix}.$$
    Therefore,
    $$(X_{n+1})^T = \begin{bmatrix} (X_{n})^T & (X_{n})^T \\ (X_{n})^T & (-X_{n})^T \end{bmatrix} = \begin{bmatrix} X_{n} & X_{n} \\ X_{n} & -X_{n} \end{bmatrix} = X_{n+1},$$
    and $X_{n+1}$ is also symmetric.  
(ii) $(X_n)^{-1} = -\frac{1}{2^n}X_n$: For this, let us consider the product matrix $P = (X_n)^2$. Now, by the definition of matrix multiplication, each $P_{ij}$ is the dot product of the $i^{\text{th}}$ row of $X_n$ and the $j^{\text{th}}$ column of $X_n$. Since the $i^{\text{th}}$ row is the same as the $i^{\text{th}}$ column (by symmetry), we can see that
$$P_{ij} = \chi_{S^{i|n}}(x^{1|n}) \chi_{S^{j|n}}(x^{1|n}) + \chi_{S^{i|n}}(x^{2|n}) \chi_{S^{j|n}}(x^{2|n}) + \cdots + \chi_{S^{i|n}}(x^{2^n|n}) \chi_{S^{j|n}}(x^{2^n|n}) = 2^n \cdot \langle \chi_{S^{i|n}}, \chi_{S^{j|n}} \rangle.$$
From part (a), we know that the inner product is $1$ if $i = j$ and $0$ otherwise. Therefore, $P$ is a diagonal matrix, all of whose diagonal elements are $2^n$, *i.e.*,
$$P = (X_n)^2 = 2^nI.$$
Therefore, we can premultiply by $(X_n)^{-1}$ on both sides to get $(X_n)^{-1} = \frac{1}{2^n}X_n$, QED.  

Now, we wish to find the value of
$$\sum_{S \subseteq \{1,...,n\}} (\hat{f_S})^2.$$
This is nothing but the dot product of the vector $\hat{f}$ (defined above) with itself, *i.e.*, $\hat{f}^T \cdot \hat{f}$. Therefore,
$$\hat{f}^T \cdot \hat{f} = (X_n^{-1}v_f)^T \cdot (X_n^{-1}v_f)$$
$$= (v_f^T (X_n^{-1})^T) \cdot (X_n^{-1}v_f)$$
$$= v_f^T \cdot (\frac{1}{2^n}X_n)^T \cdot \frac{1}{2^n}X_n \cdot v_f$$
$$= \frac{1}{2^{2n}} (v_f^T \cdot (X_n)^2 \cdot v_f)$$
$$= \frac{1}{2^{2n}} (v_f^T \cdot 2^nI \cdot v_f)$$
$$= \frac{1}{2^n} (v_f^T \cdot v_f)$$
$$= \frac{1}{2^n} \sum_{i = 1}^{2^n} (v_f)_i^2.$$
However, all entries of $v_f$ are either $+1$ or $-1$. Therefore, all terms of the sum are 1, which means the sum itself is $2^n$. Hence,
$$\sum_{S \subseteq \{1,...,n\}} (\hat{f_S})^2 = \hat{f}^T \cdot \hat{f} = 1,$$
QED.

### 3.2  
The inner product on the space $V$ is defined as
$$\langle f, g \rangle = \int_{0}^{1} f(x)g(x)dx.$$
We are given the basis $\{1,x,x^2,x^3\}$. Let these vectors be $v_1, v_2, v_3, v_4$ respectively. We will first use the Gram-Schmidt process to generate an orthogonal basis $w_1, w_2, w_3, w_4$, and then convert it into an orthonormal basis $w_1', w_2', w_3', w_4'$.  
For the orthogonal basis,
$$w_1 = v_1,$$
$$w_2 = v_2 - \frac{\langle v_2,w_1 \rangle}{\langle w_1, w_1 \rangle} w_1,$$
$$w_3 = v_3 - \frac{\langle v_3,w_1 \rangle}{\langle w_1, w_1 \rangle} w_1 - \frac{\langle v_3,w_2 \rangle}{\langle w_2, w_2 \rangle}w_2,$$
$$w_4 = v_4 - \frac{\langle v_4,w_1 \rangle}{\langle w_1, w_1 \rangle} w_1 - \frac{\langle v_4,w_2 \rangle}{\langle w_2, 2_2 \rangle}w_2 - \frac{\langle v_4, w_3 \rangle}{\langle w_3, w_3 \rangle}w_3.$$
First,
$$w_1 = v_1 = 1,$$
from which we get
$$\langle w_1, w_1 \rangle = \int_{0}^{1} 1 \cdot dx = [x]_{0}^{1} = 1,$$
$$\langle v_2, w_1 \rangle = \int_{0}^{1} xdx = [\frac{1}{2}x^2]_{0}^{1} = \frac{1}{2},$$
$$\langle v_3, w_1 \rangle = \int_{0}^{1} x^2dx = [\frac{1}{3}x^3]_{0}^{1} = \frac{1}{3},$$
$$]langle v_4, w_1 \rangle = \int_{0}^{1}x^3dx = [\frac{1}{4}x^4]_{0}^{1} = \frac{1}{4}.$$
Therefore,
$$w_2 = v_2 - \frac{\langle v_2,w_1 \rangle}{\langle w_1, w_1 \rangle} w_1 = x - \frac{\frac{1}{2}}{1}(1) = x - \frac{1}{2}.$$
From this we get
$$\langle w_2, w_2 \rangle = \int_{0}^{1} (x-\frac{1}{2})^2dx = [\frac{1}{3}(x-\frac{1}{2})^3]_{0}^{1} = \frac{1}{12},$$
$$\langle v_3, w_2 \rangle = \int_{0}^{1} x^2(x - \frac{1}{2})dx = [\frac{1}{4}x^4 - \frac{1}{6}x^3]_{0}^{1} = \frac{1}{12},$$
$$\langle v_4, w_2 \rangle = \int_{0}^{1} x^3(x - \frac{1}{2})dx = [\frac{1}{5}x^5 - \frac{1}{8}x^4]_{0}^{1} = \frac{3}{40}.$$
Therefore,
$$w_3 = v_3 - \frac{\langle v_3,w_1 \rangle}{\langle w_1, w_1 \rangle} w_1 - \frac{\langle v_3,w_2 \rangle}{\langle w_2, w_2 \rangle}w_2$$
$$ = x^2 - \frac{\frac{1}{3}}{1}(1) - \frac{\frac{1}{12}}{\frac{1}{12}}(x - \frac{1}{2}) = x^2 - \frac{1}{3} - x + \frac{1}{2} = x^2 - x + \frac{1}{6}.$$
From this we get
$$\langle w_3, w_3 \rangle = \int_{0}^{1} (x^2 - x + \frac{1}{6})^2dx$$
$$ = [\frac{1}{5}x^5 - \frac{1}{2}x^4 - \frac{4}{9}x^3 - \frac{1}{6}x^2 + \frac{1}{36}]_{0}^{1} = \frac{1}{5} - \frac{1}{2} - \frac{4}{9} - \frac{1}{6} + \frac{1}{36}$$
$$ = \frac{1}{180},$$
$$\langle v_4, w_3 \rangle =  \int_{0}^{1} x^3(x^2 - x + \frac{1}{6})dx = [\frac{1}{6}x^6 - \frac{1}{5}x^5 + \frac{1}{24}x^4]_{0}^{1}$$
$$ = \frac{1}{6} - \frac{1}{5} + \frac{1}{24} = \frac{1}{120}.$$
Therefore,
$$w_4 =  v_4 - \frac{\langle v_4,w_1 \rangle}{\langle w_1, w_1 \rangle} w_1 - \frac{\langle v_4,w_2 \rangle}{\langle w_2, 2_2 \rangle}w_2 - \frac{\langle v_4, w_3 \rangle}{\langle w_3, w_3 \rangle}w_3$$
$$ = x^3 - \frac{\frac{1}{4}}{1}(1) - \frac{\frac{3}{40}}{\frac{1}{12}}(x - \frac{1}{2}) - \frac{\frac{1}{120}}{\frac{1}{180}}(x^2 - x + \frac{1}{6})$$
$$ = x^3 - \frac{1}{4} - \frac{9}{10}(x - \frac{1}{2})  - \frac{3}{2}(x^2 - x + \frac{1}{6}) = x^3 - \frac{1}{4} - \frac{9}{10}x + \frac{9}{20} - \frac{3}{2}x^2 + \frac{3}{2}x - \frac{1}{4}$$
$$ = x^3 - \frac{3}{2}x^2 + \frac{3}{5}x - \frac{1}{20}.$$
From this we get
$$\langle w_4, w_4 \rangle = \int_{0}^{1} (x^3 - \frac{3}{2}x^2 + \frac{3}{5}x - \frac{1}{20})^2dx$$
$$ = [\frac{1}{7}x^7 - \frac{1}{2}x^6 + (\frac{6}{5} + \frac{9}{4})\frac{1}{5}x^5 + (-\frac{1}{10} - \frac{9}{5})\frac{1}{4}x^4 + (\frac{3}{20} + \frac{9}{25})\frac{1}{3}x^3 - \frac{3}{50}\frac{1}{2}x^2 + \frac{1}{40}x]_{0}^{1}$$
$$ = \frac{1}{7} - \frac{1}{2} + \frac{69}{100} - \frac{19}{40} + \frac{51}{300} - \frac{3}{100} + \frac{1}{40} = \frac{4}{175}.$$

Now, we have an orthogonal basis. For the orthonormal basis,
$$w_1' = \frac{w_1}{\|w_1\|} = \frac{w_1}{\sqrt{\langle w_1, w_1 \rangle}} = \frac{1}{1}(1) = 1,$$
$$w_2' = \frac{w_2}{\|w_2\|} = \frac{w_2}{\sqrt{\langle w_2, w_2 \rangle}} = \frac{1}{\frac{1}{2 \sqrt{3}}}(x - \frac{1}{2}) = \sqrt{3}(2x-1),$$
$$w_3' = \frac{w_3}{\|w_3\|} = \frac{w_3}{\sqrt{\langle w_3, w_3 \rangle}} = \frac{1}{\frac{1}{6 \sqrt{5}}}(x^2 - x + \frac{1}{6}) = \sqrt{5}(6x^2 - 6x + 1),$$
$$w_4' = \frac{w_4}{\|w_4\|} = \frac{w_4}{\sqrt{\langle w_4, w_4 \rangle}} = \frac{1}{\frac{2}{5 \sqrt{7}}}(x^3 - \frac{3}{2}x^2 + \frac{3}{5}x - \frac{1}{20})$$
$$ = \frac{\sqrt{7}}{2} (5x^3 - \frac{15}{2}x^2 + 3x - \frac{1}{4}).$$

### 3.3
The vector space $V$ is spanned by $\{\sin t, \sin 2t, \sin 3t, \sin 4t\}$ and has the inner product defined by
$$\langle f, g \rangle = \int_{0}^{2 \pi} f(x)g(x)dx.$$
We have a subspace $U = \text{span} \{\sin t + \sin 2t\}.$ We need to find its orthogonal complement $U^{\perp}$.  
Let $u = c \sin t + c \sin 2t \in U$ be an arbitrary vector in $U$, and let $v = (\alpha \sin t + \beta \sin 2t + \gamma \sin 3t + \delta \sin 4t)$ be one in $U^{\perp}$. This can only happen if
$$\int_{0}^{2 \pi} c(\sin t + \sin 2t)(\alpha \sin t + \beta \sin 2t + \gamma \sin 3t + \delta \sin 4t)dt = 0$$
$$\implies \int_{0}^{2 \pi} (c \alpha \sin ^2 t + c \beta \sin t \sin 2t + c \gamma \sin t \sin 3t + c \delta \sin t \sin 4t + c \alpha \sin t \sin 2t $$
$$ + c \beta \sin ^2 2t + c \gamma \sin 2t \sin 3t + c \delta \sin 2t \sin 4t)dt = 0$$
Now, consider the integral
$$\int_{0}^{2 \pi} sin (mx) sin (nx) dx$$
for $m \neq n$. Applying trigonometric identities, this is equal to
$$\int_{0}^{2 \pi} \frac{1}{2}[\cos{(m+n)x} - \cos{(m-n)x}] = [\frac{1}{2}(\frac{1}{m+n} \sin{(m+n)x} - \frac{1}{m-n} \sin{(m-n)x})]_{0}^{2 \pi} = \frac{1}{2}(0 - 0) = 0.$$
If $m = n$, we get
$$\int_{0}^{2 \pi} \sin ^2 (mx) dx = \int_{0}^{2 \pi} \frac{1}{2}(1 - \cos 2mx)dx = \frac{1}{2}[x - \frac{1}{2m} \sin 2mx]_{0}^{2 \pi} = \frac{1}{2}[2 \pi - 0] = \pi.$$
Applying these results to the above expansion, we see that it reduces to
$$c \alpha \pi + c \beta \pi = 0 \implies \alpha = -\beta.$$
Therefore, an arbitrary vector in $U^{\perp}$ is of the form $\alpha \sin t - \alpha \sin 2t + \gamma \sin 3t + \delta \sin 4t$ for any $\alpha, \gamma, \delta$. We can also write
$$U^{\perp} = \text{span}\{\sin t - \sin 2t, \sin 3t, \sin 4t\}.$$

From this, we can see that $\sin t - \sin 2t$ is already in $U^{\perp}$; therefore, if we wish to write it as a sum of vectors from $U$ and $U^{\perp}$, it is simply $0 + (\sin t - \sin 2t)$. We can verify this fact by evaluating the integral using the above results:
$$\int_{0}^{2 \pi} (\sin t + \sin 2t)(\sin t - \sin 2t)dt = \int_{0}^{2 \pi}(\sin ^2 t - \sin ^2 2t)dt = \pi - \pi = 0.$$
