# Assignment 1  
## MA3.101: Linear Algebra  
## Spring 2021  

### Answers  
1. The properties to be checked are:  (i) $V$ forms an abelian group (V1-5), (ii) $F$ forms a field (F1-11) (iii) $V$ is closed under scalar multiplication, both distributive laws are followed, scalar multiplication is associative and the unit scalar is the identity of scalar multiplication (V6-10).  
(a) **$V = \mathbb{R}, F = \mathbb{N}$**: $V$ does not form a valid vector space over $F$. This is because $\mathbb{N}$ is *not* a field; in general, elements do not have additive or multiplicative inverses ($\forall x \in \mathbb{N}, -x \notin \mathbb{N}$ and $\frac{1}{x} \notin \mathbb{N}$, in general).  
(b) **$V = \mathbb{Q}, F = \mathbb{R}$**: $V$ does not form a valid vector space over $F$. This is because $\mathbb{Q}$ is *not* closed under scalar multiplication with $\mathbb{R}$ (one example is $1 \in \mathbb{Q}, \sqrt{2} \in \mathbb{R}$, but $\sqrt{2} \cdot 1 \notin \mathbb{Q}$).  
(c) **$V = \mathbb{R}, F = \mathbb{Q}$**: $V$ forms a valid vector space over $F$. The proof is as follows:  
* $\mathbb{R}$ forms an abelian group. This follows from the fact that the real numbers are closed, associative and commutative under addition. 1 is the identity element. The inverse of $x \in \mathbb{R}$ is $-x \in \mathbb{R}$.  
* $\mathbb{Q}$ forms a field. This follows from the fact the rational numbers are closed, associative and commutative under multiplication and addition. The multiplicative and additive identities are 1 and 0 respectively (1 is the scalar unit). All nonzero elements $x \in \mathbb{Q}, x \neq 0$ have a multiplicative inverse $\frac{1}{x} \in \mathbb{Q}$ and all elements $x \in \mathbb{Q}$ have an additive inverse $-x \in \mathbb{Q}$. Further, multiplication distributes over addition in $\mathbb{Q}$.  
* Since $\mathbb{Q} \subseteq \mathbb{R}$, the closure, distributivity and associativity of scalar multiplication follow from the corresponding properties of $\mathbb{R}$. Further, the scalar unit 1 is the identity in $\mathbb{R}$ as well.  
(d) **$V = \mathbb{R}, F = \mathbb{C}$**: $V$ does not form a valid vector space over $F$. This is because $\mathbb{R}$ is *not* closed under scalar multiplication with $\mathbb{C}$ (one example if $1 \in \mathbb{R}, i \in \mathbb{C}$, but $i \cdot 1 \notin \mathbb{R}$).  

2. **XOR** is defined as:  
$0 \oplus 0 = 0$  
$0 \oplus 1 = 1$  
$1 \oplus 0 = 1$  
$1 \oplus 1 = 0$,  
and **AND** is defined as:  
$0 \cdot 0 = 0$  
$0 \cdot 1 = 0$  
$1 \cdot 0 = 0$  
$1 \cdot 1 = 1$.  
* $F = \{0,1\}$ forms an abelian group under **XOR**. Clearly, **XOR** is closed as well as commutative. When we note that it is equivalent to $+_{2}$, we can conclude that it is associative, since modular addition is always associative. The identity is 0 and the inverse of either element is itself. Hence, $F$ forms an abelian group under **XOR**.  
* $F - \{0\}$ is nothing but the singleton set $\{1\}$. This set is a group under multiplication, whose only element is the identity. Since commutativity is not contradicted, we can say that it is an abelian group as well. Hence the nonzero elements of $F$ form an abelian group under **AND**.  
* The distributivity can be proved as follows:  
$\forall x, y \in F, 0 \cdot (x \oplus y) = 0$, from the property of fields that $\forall a \in F, 0 \cdot a = 0$. But $0 \cdot x \oplus 0 \cdot y = 0 \oplus 0 = 0$, from the same property.  
$\forall x, y \in F, 1 \cdot (x \oplus y) = x \oplus y$, since 1 is the multiplicative identity. But $1 \cdot x \oplus 1 \cdot y = x \oplus y$, for the same reason.  
The above equations prove the dsitributivity of multiplication over addition in $F$.  
Hence, $F$ is a field under the operations of **XOR** and **AND**.  

3. A set $A \subseteq V$ is a subspace of $V$ if $\forall x, y \in A, \forall a, b \in F, ax + by \in A$, *i.e.*, it is closed under linear combination.  
(a) $A$ is not a subspace of $V$.  
Suppose $X$ and $Y$ are both invertible $n \times n$ matrices, *i.e.*, $X, Y \in A$. Then, $aX + bY$ is not necessarily invertible for all $a, b \in F$. One counterexample is if $X = I_{n}$ and $Y = -I_{n}$; then $1 \cdot X + 1 \cdot Y = I^{n} - I^{n} = 0_{n}$, the null matrix, which is not invertible.  
(b) $A$ is not a subspace of $V$.  
Suppose $X$ and $Y$ are both non-invertible $n \times n$ matrices, *i.e.*, $X, Y \in A$. Then, $aX + bY$ is not necessarily non-invertible for all $a, b \in F$. One counterexample is if $X = \begin{bmatrix} 1 & 2 & 3 \\ 1 & 2 & 3 \\ 0 & 1 & 0 \end{bmatrix}$ and $Y = \begin{bmatrix} 0 & 1 & 0 \\ 3 & 2 & 1 \\ 3 & 2 & 1 \end{bmatrix}$, both of which are clearly singular and therefore non-invertible. However, $1 \cdot X + 1 \cdot Y = X + Y = \begin{bmatrix} 1 & 3 & 3 \\ 4 & 4 & 4 \\ 3 & 3 & 1 \end{bmatrix}$, which has a determinant of 16 and is therefore invertible.  
(c) $A$ is a subspace of $V$.  
Suppose that $X$ and $Y$ are both such that $XB = BX$ and $YB = BY$. Then, for arbitrary $a, b \in F$,  
$(aX + bY) \cdot B = aXB + bYB$ (distributivity of matrix multiplication over addition) $= aBX + bBY$ (by assumption). This is equal to $B(aX) + B(bY)$ (proved below), and by distributivity of matrix multiplication over addition, to $B \cdot (aX + bY)$. Hence $aX + bY \in A$, and $A$ is indeed a subspace.  
We need to prove that $aPQ = P(aQ)$ for any $a \in F$ and $P, Q \in V$. We know that $$[PQ]_{ij} = (\sum_{k = 1}^{k = n} p_{ik}q_{kj}).$$ Hence, $$[aPQ]_{ij} = a \cdot (\sum_{k = 1}^{k = n} p_{ik}q_{kj}) = (\sum_{k = 1}^{k = n} ap_{ik}q_{kj}) = (\sum_{k = 1}^{k = n} p_{ik}(aq_{kj})) = [P(aQ)]_{ij}.$$ Therefore, $aPQ = P(aQ)$.  
(d) $A$ is not a subspace of $V$.  
Suppose that $X$ and $Y$ are idempotent, *i.e.*, $X, Y \in A$. Then, $aX + bY$ is not necessarily idempotent for all $a, b \in F$. One counter example is if $X = Y = I_{n}$. Then, $1 \cdot X + 1 \cdot Y = I_{n} + I_{n} = 2I_{n}$. But $(2I_{n})^{2} = 4I_{n} \neq 2I_{n}$, which means $aX + bY$ is not idempotent.  

4. (a) Let this set be $C$. $C$ is a subspace of $V$.  
Suppose $f : \mathbb{R} \to \mathbb{R}$ and $g : \mathbb{R} \to \mathbb{R}$ are two continuous functions, *i.e.*, $f, g \in C$. Then, consider the function $af + bg$ for arbitrary $a, b \in \mathbb{R}$ (assuming $\mathbb{R}$ is the scalar field). For all $c \in \mathbb{R}$, $$\lim_{x \to c} (af + bg) = \lim_{x \to c} af + \lim_{x \to c} bg = a\lim_{x \to c} f + b\lim_{x \to c} g = af(c) + bg(c) = (af + bg)(c),$$ by the properties of limits. Therefore, $af + bg$ is also continuous and belongs to $C$; hence $C$ is indeed a subspace.  
(b) Let this set by $S$. $S$ is not a subspace of $V$. One counterexample is if $f(x) = x$, the identity function, and $g(x) = 1$, the constant function with value 1. Then $1 \cdot f(x) + 1 \cdot g(x) = x + 1$. But, in general, $(x + 1)^2 \neq x + 1$. Hence $S$ is not a subspace.  
(c) Let this set be $D$. $D$ is not a subspace of $V$. Suppose $f : \mathbb{R} \to \mathbb{R}$ and $g : \mathbb{R} \to \mathbb{R}$ are two functions such that $f(3) - f(-5) = g(3) - g(-5)$, *i.e.*, $f, g \in C$. Then, consider the function $af + bg$ for $a = 2, b = 3$.  
$(2f + 3g)(3) - (2f + 3g)(-5) = 2\{f(3) - f(-5)\} + 3\{g(3) - g(-5)\} = 2 + 3 = 5 \neq 1$, which means $(2f + 3g) \notin D$. Therefore $D$ is not a subspace.  

5. We know that $V$ is a vector space. Suppose $S_{2} \subseteq V$ and $S_{2}$ is linearly independent. We will assume $S_{1} \subseteq S_{2}$ is linearly dependent and derive a contradiction.  
If $S_{1}$ is linearly dependent, there are vectors $v_{1}, v_{2}, \cdots , v_{k} \in S_{1}$ which have a linear combination equal to 0. But since  $S_{1} \subseteq S_{2}$, all of $v_{1}, v_{2}, \cdots, v_{k}$ belong to $S_{2}$ as well. This means that there are vectors in $S_{2}$ which have a linear combination equal to 0. This contradicts the assumption that $S_{2}$ is linearly independent. Hence, $S_{1}$ must also be linearly independent, QED.

6. In order to show that $Z$ forms a vector space over $F$, we need to prove that (i) $Z$ forms an abelian group (V1-5), (ii) $F$ is a field (F1-11) and (iii) $Z$ is closed under scalar multiplication, both distributive laws are followed, scalar multiplication is associative and the unit scalar is the identity of scalar multiplication (V6-10).  
(i) Since $V$ and $W$ are vector spaces over $F$, they are also abelian groups. Hence, we can prove the various axioms for $Z$ to be an abelian group as follows:  
* **Closure** Let $(v_{1},w_{1}), (v_{2},w_{2}) \in Z$. Then, $v_{1} + v_{2} \in V$ by closure of $V$, and $w_{1} + w_{2} \in W$ by closure of $W$.  
Hence, $(v_{1}, w_{1}) + (v_{2},w_{2}) = (v_{1} + v_{2}, w_{1} + w_{2}) \in Z$. Therefore $Z$ is also closed.  
* **Associativity** Let $(v_{1},w_{1}), (v_{2},w_{2}), (v_{3},w_{3}) \in Z$. Then, $(v_{1} + v_{2}) + v_{3} = v_{1} + (v_{2} + v_{3})$, by associativity of $V$, and  $(w_{1} + w_{2}) + w_{3} = w_{1} + (w_{2} + w_{3})$, by associativity of $W$.  
Then, $((v_{1}, w_{1}) + (v_{2}, w_{2})) + (v_{3},w_{3}) = (v_{1} + v_{2}, w_{1} + w_{2}) + (v_{3} + w_{3}) = ((v_{1} + v_{2}) + v_{3}), (w_{1} + w_{2}) + w_{3}) = (v_{1} + (v_{2} + v_{3}), w_{1} + (w_{2} + w_{3}))$, by the associativity of $V$ and $W$.  
Now, this is equal to $(v_{1}, w_{1}) + (v_{2} + v_{3}, w_{2} + w_{3}) = (v_{1}, v_{2}) + ((v_{2}, w_{2}) + (v_{3}, w_{3}))$; hence $Z$ is also associative.  
* **Commutativity** Let $(v_{1},w_{1}), (v_{2},w_{2}) \in Z$. Then, $v_{1} + v_{2} = v_{2} + v_{1}$ by commutativity of $V$, and $w_{1} + w_{2} = w_{2} + w_{1}$ by commutativity of $W$.  
Hence, $(v_{1}, w_{1}) + (v_{2} + w_{2}) = (v_{1} + v_{2}, w_{1} + w_{2}) = (v_{2} + v_{1}, w_{2} + w_{1})$, by the commutativity of $V$ and $W$.  
This is equal to $(v_{2}, w_{2}) + (v_{1}, w_{1})$. Therefore $Z$ is also commutative.  
* **Existence of Identity** Let $e_{V} \in V$ and $e_{W} \in W$ be the identities of $V$ and $W$. Then $e_{Z} = (e_{V},e_{W}) \in Z$ is the identity of $Z$, since $(v, w) + (e_{V},e_{W}) = (e_{V}, e_{W}) + (v,w) = (v + e_{V}, w + e_{W}) = (v,w)$. Therefore $Z$ also has an identity element.
* **Existence of Inverse** Let $v \in V$ and $w \in W$ be arbitrary elements of $V$ and $W$. Then, if $-v \in V$ and $-w \in W$ are their respective inverses, the inverse of $(v,w) \in Z$ is $(-v,-w) \in Z$.  
This is because $(v,w) + (-v,-w) = (v + (-v), w + (-w)) = (e_{V}, e_{W}) = e_{Z}$. Therefore all elements of $Z$ have inverses.  
By the above properties (V1-5), $Z$ is an abelian group under addition.  
(ii) We know that $F$ is a field, since $V$ and $W$ form vector spaces over it.  
(iii) We can prove that $Z$ has the relevant properties from the corresponding properties of $V$ and $W$, as follows:  
* **Closure under scalar multiplication** $V$ and $W$ are both closed under scalar multiplication, *i.e.*, $\forall c \in F, v \in V, w \in W$, we have $cv \in V, cw \in W$.  
Hence, if $(v,w) \in Z$, then $c(v,w) = (cv,cw) \in Z$ as well, for all $c \in F$. Therefore $Z$ is also closed under scalar multiplication.  
* **Distributive laws** We know the distributive laws hold in $V$ and $W$. Let $(v_{1}, w_{1}), (v_{2}, w_{2}) \in Z$, and $c_{1}, c_{2} \in F$.  
Then $c_{1} \cdot ((v_{1},w_{1}) + (v_{2},w_{2})) = c_{1} (v_{1} + v_{2}, w_{1} + w_{2}) = (c_{1} \cdot (v_{1} + v_{2}), c_{1} \cdot (w_{1} + w_{2})) = (c_{1}v_{1} + c_{1}v_{2}, c_{1}w_{1} + c_{1}w_{2})$, by the first distributive law in $V$ and $W$.  
This is equal to $(c_{1}v_{1},c_{1}w_{1}) + (c_{1}v_{2}, c_{1}w_{2}) = c_{1}(v_{1},w_{1}) + c_{1}(v_{2},w_{2})$. This proves the first distributive law.  
Also, $(c_{1} + c_{2}) \cdot (v_{1},w_{1}) = ((c_{1} + c_{2}) \cdot v_{1}, (c_{1} + c_{2}) \cdot w_{1}) = (c_{1}v_{1} + c_{2}v_{1}, c_{1}w_{1} + c_{2}w_{1})$, by the second distributive law in $V$ and $W$.  
This is equal to $(c_{1}v_{1}, c_{1}w_{1}) + (c_{2}v_{1}, c_{2}w_{1}) = c_{1}(v_{1},w_{1}) + c_{2}(v_{1},w_{1})$. This proves the second distributive law.  
* **Associativity of scalar multiplication** We know that scalar multiplication is associative in $V$ and $W$. Let $c_{1}, c_{2} \in F$, and $(v,w) \in F$; then we know that $(c_{1}c_{2})v = c_{1}(c_{2}v)$ and $(c_{1}c_{2})w = c_{1}(c_{2}w)$.  
Then $(c_{1}c_{2})(v,w) = ((c_{1}c_{2})v, (c_{1}c_{2})w) = (c_{1}(c_{2}v), c_{1}(c_{2}w))$, from the associativity of scalar multiplication in $V$ and $W$.  
This is equal to $c_{1}(c_{2}v,c_{2}w) = c_{1}(c_{2}(v,w))$. Therefore scalar multiplication is associative in $Z$.  
* **Unit scalar is identity** Let $e \in F$ be the unit scalar. We know it is the identity of scalar multiplication in $V$ and $W$. If $(v,w) \in Z$, then $e(v,w) = (ev, ew) = (v,w)$, which proves that $e$ is the identity of scalar multiplication in $Z$ as well.  
From the above properties, we can conclude that $Z$ also forms a vector space over the field $F$ with the given operations, QED.  

7. Let $B = \{u,v,w\}$. If $B$ is a basis for $V$, then it is a linearly independent set and $L(B) = V$. We will prove these properties for $C = \{u+v+w,v+w,w\}$ also.  
(i) $C$ is linearly independent. To prove this, let us assume the contrary, *i.e.*, $C$ is linearly dependent. This means that there exist scalars $c_{i}$, not all zero, such that $c_{1}(u+v+w) + c_{2}(v+w) + c_{3}(w) = 0$. Rearranging, we see that $(c_{1})u + (c_{1} + c_{2})v + (c_{1} + c_{2} + c_{3})w = 0$. Since the $c_{i}$ are not all zero, the coefficients in this equation are not all zero either, which means that $B$ is linearly dependent. This is a contradiction; hence $C$ is indeed linearly independent.  
(ii) $L(C) = V$. Given an arbitrary vector $a \in V$, we know $a \in L(B)$, *i.e.*, it is possible to write it as $a = c_{1}u + c_{2}v + c_{3}w$. From this equation, we obtain $a = c_{1}(u+v+w) + (c_{2} - c_{1})(v+w) + (c_{3} - c_{2})w$. This means that $a \in L(C)$. Thus we conclude that $V = L(B) \subseteq L(C)$. However, by closure of vector addition, $L(C) \subseteq V$. This implies that $L(C) = V$.  
From the above properties, we see that $C$ is also a basis of $V$, QED.  

8. We can prove this by contradiction. Let us assume that $f$ and $g$ are linearly dependent, *i.e.* there exists some $c_{1},c_{2} \in \mathbb{R}$, not both 0, such that $c_{1}f + c_{2}g = 0$.  
Now, if either $c_{1} = 0$ or $c_{2} = 0$, then one of $f$ and $g$ must be identically equal to 0. Both being exponential functions, this is not possible; therefore both $c_{1}$ and $c_{2}$ are nonzero.  
Hence we can write $f(t) = -\frac{c_{2}}{c_{1}}g(t)$, *i.e.*, $e^{rt} = ce^{st}$ for some constant $c = -\frac{c_{1}}{c_{2}}$.  
$e^{st}$ is always nonzero, so we divide both sides by it to get $e^{(r-s)t} = c$, for all $t \in \mathbb{R}$. Since no exponential function can have a constant value, this is a contradiction; hence $f$ and $g$ are in fact linearly independent, QED.  

9. The set $S$ does generate $\mathbb{R}^{3}$ and is linearly independent. The proof is as follows:  
(i) $S$ generates $\mathbb{R}^{3}$. Consider an arbitrary element $(x,y,z) \in \mathbb{R}^{3}$. Clearly, $$(x,y,z) = (\frac{x+y-z}{2})(1,1,0) + (\frac{x-y+z}{2})(1,0,1) + (\frac{-x+y+z}{2})(0,1,1),$$ where all the coefficients are real numbers. This proves that $L(S) = \mathbb{R}^{3}$.  
(ii) $S$ is linearly independent. Assume that $c_{1}(1,1,0) + c_{2}(1,0,1) + c_{3}(0,1,1) = (0,0,0)$ for some $c_{1}, c_{2}, c_{3} \in \mathbb{R}$. From this, we get the equations $$c_{1} + c_{2} = 0,$$ $$c_{2} + c_{3} = 0,$$ and $$c_{3} + c_{1} = 0.$$ The only solution to this system of equation is $c_{1} = c_{2} = c_{3} = 0$, which means that $S$ is in fact linearly independent.  

10. Consider the vector space $\mathbb{R}^{2}$ over the field $\mathbb{R}$. Two of its subspaces are the sets $X = \{(x,0) | x \in \mathbb{R}\}$ and $Y = \{(0,y) | y \in \mathbb{R}\}$, *i.e.*, the X and Y axes (proved below). The union of these two subspaces is not a subspace, as it is not closed under vector addition. For example, $(0,3) + (4,0) = (4,3)$ which does not lie on either axis. This proves that the union of two subspaces of a vector space may not be a subspace.  
To prove that $X$ is a subspace, it is sufficient to show that $a(x_{1},0) + b(x_{2},0) \in X$ for all $x_{1}, x_{2}, a, b \in \mathbb{R}$, since by the definition of $X$, $(x_{1}, 0), (x_{2}, 0) \in X$ for all $x_{1}, x_{2} \in \mathbb{R}$.  
Now, $a(x_{1}, 0) + b(x_{2}, 0) = (ax_{1}, a \cdot 0) + (bx_{2}, b \cdot 0) = (ax_{1} + bx_{2}, 0)$ since $x \cdot 0 = 0$ for all $x \in \mathbb{R}$. But $(ax_{1} + bx_{2}, 0) \in X$ because $ax_{1} + bx_{2} \in \mathbb{R}$; hence $X$ is a subspace.  
Similarly, to prove that $Y$ is a subspace, it is sufficient to show that $a(0,y_{1}) + b(0,y_{2}) \in Y$ for all $y_{1}, y_{2}, a, b \in \mathbb{R}$, since by the definition of $Y$, $(0,y_{1}), (0,y_{2}) \in X$ for all $y_{1}, y_{2} \in \mathbb{R}$.  
Now, $a(0,y_{1}) + b(0,y_{2}) = (a \cdot 0, ay_{1}) + (b \cdot 0, by_{2}) = (0, ay_{1} + by_{2})$ since $y \cdot 0 = 0$ for all $y \in \mathbb{R}$. But $(0, ay_{1} + by_{2}) \in Y$ because $ay_{1} + by_{2} \in \mathbb{R}$; hence $Y$ is a subspace.  
