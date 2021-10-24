---
title: "MATH403: Introduction to Abstract Algebra"
author: Michael Li
geometry: margin=1cm
header-includes:
    - \usepackage{amsmath}
    - \DeclareMathOperator{\lcm}{lcm}
    - \DeclareMathOperator{\Inn}{Inn}
    - \DeclareMathOperator{\Ker}{Ker}
    - \DeclareMathOperator{\Aut}{Aut}
output: pdf_document
---

# Chapter 8 External Direct Products

**Definition**: for a finite collection of groups, the **external direct product** for $G_1, G_2, \ldots, G_n$ is $G_1 \oplus G_2 \oplus \cdots \oplus G_n = \{(g_1, g_2, \ldots, g_n) \mid g_i \in G_i\}$

- Group operation is component wise under $G_i$

**Example**: $Z_2 \oplus Z_3 = \{(0, 0), (0, 1), (0, 2), (1, 0), (1, 1), (1, 2)\}$

**Example**: Any group of order $4$ is isomorphic to $Z_4$ or $Z_2 \oplus Z_2$. It suffices to show there is only 1 way to create the operation table for a non-cyclic group $G$ of order $4$.

&nbsp; By Lagrange's Theorem, elements of $G$ (non-cyclic) only have order $1$ or $2$. Take distinct $a, b \in G$. Then $G = \{e, a, b, ab\}$ since

- $ab \neq a$, $ab \neq b$, $ab \neq e$, $ab = (ab)^{-1} = ba$
- Clearly $G \approx Z_2 \oplus Z_2$

&nbsp;

**Theorem**: $|(g_1, g_2, \ldots, g_n)| = \lcm(|g_1|, |g_2|, \ldots, |g_n|)$

&nbsp; Proof: let $s = \lcm(|g_1|, |g_2|, \ldots, |g_n|)$ and $t = |(g_1, g_2, \ldots, |g_n|)$ Then we have

&nbsp; $(g_1, g_2, \ldots, g_n)^s = (e_1, e_2, \ldots, e_n) \implies t \leq s$

&nbsp; $(g_1, g_2, \ldots, g_n)^t = (e_1, e_2, \ldots, e_n) \implies t$ is a common multiple of $|g_1|, |g_2|, \ldots, |g_n|$ and thus $s \leq t$

&nbsp; Thus, we have that $s = t$

**Example**: Number of cyclic subgroups of order $10$ in $Z_{100} \oplus Z_{25}$

- Case 1: $|a| = 10$ and $|b| = 1$ or $5$. Then we have $\phi(10) * (\phi(1) + \phi(5)) = 4 *5 = 20$
- Case 2: $|a| =2$ and $|b| = 5$. Then we have $\phi(2) * \phi(5) = 1 * 4 = 4$
- There are $24$ elements of order $10$
- Since each cyclic subgroup of order $10$ has $4$ elements of order $10$ and no 2 cyclic subgroups can share an element of order $10$, there are $24/4 = 6$ cyclic subgroups of order $10$

**Example**: For $r \mid m$ and $s \mid n$, the group $Z_m \oplus Z_n$ has a isomorphic to $\approx Z_r \oplus Z_s$

- $Z_{30} \oplus Z_{12}$ has a subgroup $\approx Z_6 \oplus Z_4$ since $\langle 5 \rangle$ is a subgroup of $Z_{30}$ with order $6$ and $\langle 3 \rangle$ is a subgroup of $Z_{12}$ with order $r$. Thus $\langle 5 \rangle \oplus \langle 3 \rangle \approx Z_6 \oplus Z_4$

&nbsp;

**Theorem**: Let $G, H$ be finite cyclic groups. $G \oplus H$ is cyclic $\iff$ $|G|, |H|$ are relatively prime

&nbsp; Proof: Let $|G| = m$ and $|H| = n \implies |G \oplus H| = mn$

&nbsp; $\implies$ $\gcd(m, n) = d$ and $(g, h)$ is a generator of $G \oplus H$. Since $(g, h)^{mn/d} = (e, e)$, we have that $nm = |(g, h)| = mn/d \implies d = 1$

&nbsp; $\impliedby$ Let $G = \langle g \rangle$, $H = \langle h \rangle$, $\gcd(|g|, |h|) = 1$. Then $|(g, h)| = \lcm(m, n) = mn = |G \oplus H|$. Thus $(g, h)$ is a generator of $G \oplus H$

**Corollaries**

- $G_1 \oplus G_2 \oplus \cdots \oplus G_n$ of finite number of finite cyclic groups $\iff$ $|G_i|, |G_j|$ are relatively prime when $i \neq j$
- Let $m = ab \cdots k$. Then $Z_m \approx Z_a \oplus Z_b \oplus \cdots \oplus Z_k$ $\iff |G_i|, |G_j|$ are relatively prime when $i \neq j$

**Example**: 

$Z_2 \oplus Z_2 \oplus Z_3 \oplus Z_5 \approx Z_2 \oplus Z_6 \oplus Z_5 \approx Z_2 \oplus Z_{30}$

$Z_2 \oplus Z_2 \oplus Z_3 \oplus Z_5 \approx Z_2 \oplus Z_6 \oplus Z_5 \oplus Z_2 \oplus Z_3 \oplus Z_2 \oplus Z_5 \approx Z_6 \oplus Z_{10}$

Thus $Z_2 \oplus Z_{30} \approx Z_6 \oplus Z_{10}$. HOWEVER, $Z_2 \oplus Z_{30} \not\approx Z_{60}$

&nbsp;

**Definition**: $U_k(n) = \{x \in U(n) \mid x \pmod{k} = 1\}$. Note that $U_k(n) \leq U(n)$

**Theorem**: Suppose that $s, t$ are relatively prime, then $U(st) \approx U(s) \oplus U(t)$, and $U_s(st) \approx U(t)$ and $U_t(st) \approx U(s)$

&nbsp; Proof: For $U(st)$ to $U(s) \oplus U(t)$, define $x \rightarrow (x \pmod{s}, x \pmod{t})$

&nbsp; For $U_s(st) \rightarrow U(t)$, define $x \rightarrow x \pmod{t}$

&nbsp; For $U_t(st) \rightarrow U(s)$, define $x \rightarrow x \pmod{s}$

**Corollary**: Let $m = n_1, n_2, \cdots n_k$ where $\gcd(n_i, n_j) = 1$ for $i \neq j$. Then $U(m) \approx U(n_1) \oplus U(n_2) \oplus \cdots \oplus U(n_k)$

**Examples**:

- $U(7) \approx U_{15}(105) = \{1, 16, 31, 46, 61, 76\}$
- $U(105) \approx U(7) \oplus U(15)$
- $U(105) \approx U(21) \oplus U(5)$
- $U(105) \approx U(3) \oplus U(5) \oplus U(7)$
- $U(105) = U(3 * 5 * 7) \approx U(3) \oplus U(5) \oplus (7) \approx Z_2 \oplus Z_4 \oplus Z_6$
- $U(144) = U(16) \oplus U(9) \approx Z_4 \oplus Z_2 \oplus Z_6$
- Thus $U(105) \approx U(144)$

# Chapter 9 Normal Subgroups and Factor Groups

**Definintion** $H \leq G$ is a **normal subgroup** if $(\forall a \in G) [aH = Ha]$, denoted $H \trianglelefteq G$

**Theorem**: $H \trianglelefteq G \iff (\forall x \in G)[xHx^{-1} \subseteq H]$

&nbsp; Proof: $\implies$ for any $x \in G, h \in H$ there is an $h; \in H$ such that $xh = h'x \implies xhx^{-1} = h' \implies xHx^{-1} \subseteq H$

&nbsp; $\impliedby$ let $x = a$ then $aHa^{-1} \subseteq H \implies aH \subseteq Ha$. Let $x = a^{-1} then $a^{-1}H(a^{-1})^{-1} \implies Ha \subseteq aH$

&nbsp; Thus $aH = Ha$

**Examples**:

- Every Abelian group is normal since $ah = ha$ for all $a \in G$ and $h \in H \leq G$
- $Z(g)$ is always normal
- $A_n$ is normal subgroup of $S_n$
- $SL(2, R)$ is normal subgroup of $GL(2, R)$ since $\det(xhx^{-1}) = 1 \implies xHx^{-1} \subseteq H$

&nbsp;

**Theorem**: Let $G \trianglelefteq G$ then $G/H = \{aH \mid a \in G\}$ is a group under operation $(aH)(bH) = abH$

&nbsp; Proof: we first show that the operation is well defined. Take $aH = a'H, bH = b'H$ and verify $aHbH = a'Hb'H \implies abH = a'b'H$

&nbsp; This will show that multiplication only depends on the cosets, not the coset representatives

&nbsp; Note that $a' = ah_1$ and $b' bh_2 \implies a'b'H = ah_1bh_2H = ah_1bH = ah_1Hb = aHb = abH$. Now we show that it's a group

- $eH = H$ is the identity
- $a^{-1}H$ is the inverse of $aH$
- $(aHbH)cH = aH(bHcH)$

**Example**: $Z/4Z$ can be constructed as $\{0 + 4Z, 1 + 4Z, 2 + 4Z, 3 + 4Z\}$

- No other left cosets are possible since $k = 4q + r \implies k + 4Z = r + 4q + 4Z = r + 4Z$
- Also worth mentioning $Z/4Z \approx Z_4$, or more generally $Z/nZ \approx Z_n$

**Example**: Let $G = Z_8 \oplus Z_4$ and $H = \langle (2, 2) \rangle \leq G$ and show that $G/H$ is isomorphic to one of $Z_8, Z_4 \oplus Z_2, Z_2 \oplus Z_2 \oplus Z_2$

- Note that $Z_8$ has elmt order $8$, $Z_4 \oplus Z_2$ has elmt of order $1, 2, 4$, and $Z_2 \oplus Z_2 \oplus Z_2$, has elmt of order $1, 2$
- For $(a, b) + H$ we have that $((a, b) + H)^4 = \begin{cases} (4, 0) + H & a \pmod{2} = 1\\ (0, 0) + H & a \pmod{2} = 0 \end{cases}$. Thus max order of elmt in $G/H$ is $4$
- However, $((1, 0) + H)^2 = (2, 0) + H \neq H \implies |(1, 0) + H| = 4$
- Thus $G/H$ cannot be isomorphic to $Z_8$ or $Z_2 \oplus Z_2 \oplus Z_2$

&nbsp;

**Theorem**: If $G/Z(G)$ is cyclic, then $G$ is Abelian

&nbsp; Proof: Since $G$ is Abelian $\implies Z(G) = G$, we show that the only element of $G/Z(G)$ is the identity coset $Z(G)$

&nbsp; Let $G/Z(G) = \langle g Z(G) \rangle$ and let $a \in G$. There there is an integer $i$ such that $aZ(G) = (gZ(G))^i = g^iZ(G)$

&nbsp; Thus a = $g^iz$ for some $z \in Z(G)$. Since $g^i, z \in C(g)$, so does $a$

&nbsp; Since $g$ was arbitrary, every element of $G$ commutes with $g \implies g \in Z(G)$. Thus $gZ(G) = Z(G)$ is the only element of $G/Z(G)$

&nbsp; **Note**: usually contrapositive is used: if $G$ is non-Abelian, then $G/Z(G)$ is not cyclic

- Using Lagrange's Theorem, a non-Abeliean group of order $pq$, for $p, q$ prime, must have a trivial center

&nbsp;

**Theorem**: $G/Z(G) \approx \Inn(G)$

&nbsp; Proof: consider $T: gZ(G) \rightarrow \phi_g = gxg^{-1}$

&nbsp; $T$ is well defined since $gZ(G) = hZ(G) \implies \phi_g = \phi(h)$ (image of a coset of $Z(G)$ only depends on the coset itself)

- $gZ(G) = hZ(G) \implies h^{-1}g \in Z(G) \implies h^{-1}gx = xh^{-1}g \implies gx^{-1} = hxh^{-1}$ thus on to one
- Clearly, $T$ is onto
- $\phi_g\phi_h = \phi(gh)$ thus $T$ is operation preserving

&nbsp;

**Cauchy Theorem for Abelian Groups**: Let $G$ be finite, Abeliean, and let $p$ be prime that divides the order of $G$. Then $G$ has an element of order $p$

&nbsp; Proof by strong induction

- Clearly base case holds for $|G| = 2$
- IH: assume that the statement is true for all Abelian groups of order less than $|G|$
- IS: Certainly $G$ has elements of prime order, so if $|x| = m = qn$ for prime $q$, then $|x^n| = q$
  
    - If $q = p$ we are done
    - Otherwise every subgroup of an Abeliean group is normal, so construct $\bar{G} = G/\langle x \rangle$. Then $p$ divides $|\bar{G}| = |G|/q$
    - Thus by induction, $\bar{G}$ has an element $y\langle x \rangle$ of order $p$. Then $(y\langle x \rangle)^p = y^p \langle x \rangle = \langle x \rangle \implies y^p \in \langle x \rangle$

      - If $y^p = e$ then done
      - Otherwise $|y^p| = q$ and $|y^q| = p$

&nbsp;

**Definition**: $G$ is the **internal direct product** of $H, K$ (denoted $G = H \times K$) if $H, K \trianglelefteq G$, $G = HK$, and $H \cap K = \{\epsilon\}$

- Can be expanded to a finite collection of normal subgroups of $G$ where $G = H_1 \times H_2 \times \cdots \times H_n$ if

  - $G = H_1H_2 \cdots H_n = \{h_1 h_2 \cdots h_n \mid h_i \in H_i\}$
  - $(H_1H_2 \cdots H_i) \cap H_{i + 1} = \{ e \}$ for $I \in \{1, 2, \ldots, n-1\}$

- Intuition behind internal direct product is to take a group $G$ and find 2 subgroups $H, K$ such that $G \approx H \oplus K$
- Intuition behind external direct product is to take 2 unrelated groups $H, K$ are produce a larger group $H \oplus K$

**Example**: if $s, t$ are relatively prime then $U(st) = U_s(st) \times U_t(st)$

**Non-Example**: take $G = S_3, H = \langle(123) \rangle, K = \langle(12)\rangle$

- $G = HK$, $H \cap K = \epsilon$, but $G \not\approx H \oplus K$ since $H \oplus K$ is cyclic but $S_3$ isn't. Also, $K$ isn't normal

&nbsp;

**Theorem**: $H_1 \times H_2 \times \cdots \times H_n \approx H_1 \oplus H_2 \oplus \cdots \oplus H_n$

&nbsp; Proof: first need to show that normality of $H$ guarantees $h$ in all $H_i$ commute. For distinct $h_i \in H_i$ and $h_j \in H_j$

&nbsp; $(h_ih_jh_i^{-1})h_j^{-1} \in H_jh_j^{-1} = H_j$ and $h_i(h_jh_i^{-1})h_j^{-1} \in h_iH_i = H_i$

&nbsp; Thus we have $h_i h_j h_i^{-1} h_j^{-1} \in H_i \cap H_i = \{e\} \implies h_i h_j = h_j h_i$

&nbsp; Next we show that there is a unique representation of $g$. Take $g = h_1h_2 \cdots h_n = h'_1h'_2 \cdots h'_n$, which can be represented as

&nbsp; $h'_nh_2^{-1} = (h_1')^{-1}h_1 \cdots (h'_{n-1})^{-1}h_{n-1} \implies h'_nh_n^{-1} \in H_1 \cdots H_{n-1} \cap H_n = \{e\}$

&nbsp; Thus $h'_nh_n^{-1} = e \implies h'_n = h_n$. This step can be recursively applied to show $h'_i = h_i$

&nbsp; Thus we can define $\phi: G \rightarrow H_1 \oplus H_2 \oplus \cdots \oplus H_n, \phi(h_1h_2 \cdots h_n) = (h_1, h_2, \ldots, h_n)$

&nbsp; **UPSHOT**: $H \oplus K$ is the product $(h_1, k_1)(h_2, k_2) = (h_1h_2, k_1k_2)$ is the same as $h_1h_2k_1k_2 \in H \times K$

&nbsp;

**Theorem**: $|G| = 2p \implies G \approx Z_{p^2}$ or $G \approx Z_p \oplus Z_p$

&nbsp; Proof: let $|G| = p^2$. Then if $G$ has an element of order $p^2$, then $G \approx Z_{p^2}$

&nbsp; Otherwise every nonidentity element of $G$ has order $p$. We need to show that for any element $a$, $\langle  a \rangle \trianglelefteq G$

&nbsp; If not, then there is $b \in G$ such that $bab^{-1} \notin \langle a \rangle \implies \langle a \rangle \cap \langle bab^{-1} \rangle = \{e \}$

&nbsp; Taking left cosets of $\langle bab^{-1} \rangle$ of the form $a^i \langle b a b^{-1} \rangle$, we know that $b^{-1}$ must lie in one of these

&nbsp; Thus $b^{-1} = a^i(bab^{-1})^j = a^i ba^jb^{-1}$ for some $i, j$

&nbsp; This gives $e = a^iba^j \implies b \in \langle a \rangle$. Contradiction since we said $b \notin \langle a \rangle$

&nbsp; Thus every subgroup $\langle a \rangle$ is normal in $G$

&nbsp; Finally we take nonidentity $x$ and an element $y \notin \langle x \rangle$. Then by comparing orders, we have that $G = \langle x \rangle \times \langle y \rangle \approx Z_p \oplus Z_p$

**Corollary**: if $|G| = p^2$ then $G$ is Abeliean

# Chapter 10 Group Homomorphisms

**Definition**: a **homomorphism** $\phi: G \rightarrow \bar{G}$ is a function that preverses operation $\phi(ab) = \phi(a)\phi(b) \quad \quad \forall a,b \ in G$


**Definition**: $\Ker(\phi) = \{x \in G \mid \phi(x) = e\}$

**Examples**:

- Any isomoprhim is a homomorphism that is a bijection. The Kernel of an isomorphism is $\{e\}$
- $\phi:GL(2, R) \rightarrow R^*$ is an homomorphism under $A \rightarrow \det(A)$. The Kernel is $SL(2, R)$
- $\phi: R^* \rightarrow R^*$ is an homomorphism under $\phi(x) = |x|$. The Kernel is $\{1, -1\}$
- $\phi: Z \rightarrow Z_n$ is a homomorphism under $\phi(m) = m \pmod{n}$. The Kernel is $\langle n \rangle$
- $\phi: R^* \rightarrow R^*$ is an homomorphism under $\phi(x) = x^2$ since $\phi(ab) = (ab)^2 = a^2b^2 = \phi(a) \phi(b)$. The Kernel is $\{1, -1\}$
- $\phi: R \rightarrow R^*$ is NOT a homomorphism under $\phi(x) = x^2$ since $\phi(a + b) = (a + b)^2 \neq a^2 + b^2 = \phi(a)\phi(b)$

**Propertiest of Elements under Homomorphisms**

1. $\phi$ carries identity of $G$ to identity of $\bar{G}$

&nbsp; &nbsp; &nbsp; $\phi(e) = \phi(e)\phi(e) = \phi(e)\phi(e) \implies \bar{e} = \phi(e)$

2. $\phi(g^n) = (\phi(g))^n$

&nbsp; &nbsp; &nbsp; For $n > 0$ follows from definition of homomorphism and induction

&nbsp; &nbsp; For $n < 0$, $e = \phi(e) = \phi(g^ng^{-n}) = \phi(g^n) \phi(g^{-n}) = \phi(g^n)(\phi(g))^{-n} \implies \phi(g^n) = (\phi(g))^n$

3. $|g| < \infty \implies |\phi(g)|$ divides $|g|$

&nbsp; &nbsp; &nbsp; $g^n = e \implies e = \phi(e) = \phi(g^n) = (\phi(g))^n \implies |\phi(g)|$ divides $n$

4. $\Ker(\phi)$ is a subgroup of $G$

&nbsp; &nbsp; &nbsp; Clearly $e \in \Ker(\phi)$

&nbsp; &nbsp; &nbsp; If $a, b \in \Ker(\phi)$, then $\phi(a)\phi(b) = ee = \phi(ab) \implies ab \in \Ker(\phi)$

&nbsp; &nbsp; &nbsp; If $a \in \Ker(\phi)$, then $\phi(a)(\phi(a))^{-1} = \phi(a)\phi(a^{-1}) = e \implies a^{-1} \in \Ker(\phi)$

&nbsp; &nbsp; &nbsp; Thus by 2 step subgroup test, $\Ker(\phi) \leq G$

5. $\phi(a) = \phi(b) \iff a \Ker(\phi) = b \Ker(\phi)$

&nbsp; &nbsp; &nbsp; $\implies e = \phi(b^{-1})\phi(a) = \phi(b^{-1}a) \implies b^{-1} a \in \Ker(\phi)$. 

&nbsp; &nbsp; &nbsp; Then by properties of cosets, we know that $a\Ker(\phi) = b\Ker(\phi) \iff ab^{-1} \in \Ker(\phi)$

&nbsp; &nbsp; &nbsp; $\impliedby$ above process can be reversed to yield desired result

6. $\phi(g) = g' \implies \phi^{-1}(g') = \{x \in G \mid \phi(x) = g'\} = g\Ker(\phi)$

&nbsp; &nbsp; &nbsp; Show that $\phi^{-1}(g') \subseteq g \Ker(\phi)$

&nbsp; &nbsp; &nbsp; Take $x \in \phi^{-1}(g')$, so $\phi(x) = g'$. Then $\phi(g) = \phi(x) \implies g\Ker(\phi) = x\Ker(\phi) \implies x \in g\Ker(\phi)$

&nbsp; &nbsp; &nbsp; Show that $g \Ker(\phi) \subseteq \phi^{-1}(g')$

&nbsp; &nbsp; &nbsp; Take $k \in \Ker(\phi) \implies \phi(gk) = \phi(g)\phi(k) = g'e = g'$. Thus $gk \in \phi^{-1}(g')$

&nbsp; &nbsp; &nbsp; Thus $\phi^{-1}(g') = g \Ker(\phi)$


**Properties of Subgroups under Homomorphisms**

1. $\phi(H) = \{\phi(h) \mid h \in H \} \leq \bar{G}$

&nbsp; &nbsp; &nbsp; We know $\phi$ carries $e \in G$ to $\bar{e} \in \bar{G}$

&nbsp; &nbsp; &nbsp; Let $a, b \in H$ then let $x = \phi(a), y = \phi(b)$. Then $xy = \phi(a)\phi(b) = \phi(ab) \in \phi(H)$ since $ab \in H$

&nbsp; &nbsp; &nbsp; Let $a, a^{-1} \in H$. Then $\phi(a^{-1}) = (\phi(a))^{-1} \in \phi(H)$

2. $H$ cyclic $\implies \phi(H)$ is cyclic

&nbsp; &nbsp; &nbsp; Let $h \in H$ be the generator. Then $\phi(h^n) = \phi(h)^n$ and generates $\phi(H)$

3. $H$ Abeliean $\implies \phi(H)$ is Abelian

&nbsp; &nbsp; &nbsp; Let $a, b \in H$ with $ab = ba$. Then $\phi(ab) = \phi(a)\phi(b) = \phi(b)\phi(a) = \phi(ba)$

4. $H \trianglelefteq G \implies \phi(H) \trianglelefteq \phi(G)$

&nbsp; &nbsp; &nbsp; Take $\phi(h) \in \phi(H)$ and $\phi(g) \in \phi(G)$, then $\phi(g) \phi(h) \phi(g^{-1}) = \phi(ghg^{-1}) \in \phi(H)$

5. $|\Ker(\phi)| = n \implies \phi$ is an $n$-to-$1$ mapping from $G$ onto $\phi(G)$

&nbsp; &nbsp; &nbsp; All cosets of $\Ker(\phi) = \phi^{-1}(e)$ have the same number of elements

6. $|H| = n \implies |\phi(H)|$ divides $n$

&nbsp; &nbsp; &nbsp; Take $\phi_H$ that only maps from $H$. Then $\phi_H$i if a homomorphism from $H$ onto $\phi(H)$.

&nbsp; &nbsp; &nbsp; Suppose $|\Ker(\phi_H)| = t$. Then we have $\phi_t$ is a $t$-to-$1$ mapping so $|\phi(H)|t = |H|$

7. $\bar{K} \leq \bar{G} \implies \phi^{-1}(\bar{K}) = \{ k \in G \mid \phi(k) \in \bar{K}\} \leq G$

&nbsp; &nbsp; &nbsp; We know that $e \in \phi^{-1}(\bar{K})$

&nbsp; &nbsp; &nbsp; For $a, b \in \phi^{-1}(\bar{K})$, we have that $\phi(a)\phi(b) = \phi(ab) \in \bar{K} \implies ab \in \phi^{-1}(\bar{K})$ by closure properties

&nbsp; &nbsp; &nbsp; For $a \in \phi^{-1}(\bar{K})$, we have that $\phi(a)(\phi(a))^{-1} = \phi(a)\phi(a^{-1}) = e \implies a^{-1} \in \phi^{-1}(\bar{K})$

&nbsp; &nbsp; &nbsp; Thus by 2 step subgroup test, $\phi^{-1}(\bar{K}) \leq G$

8. $\bar{K} \trianglelefteq \bar{G} \implies \phi^{-1}(\bar{K}) \trianglelefteq G$

&nbsp; &nbsp; &nbsp; Take $xkx^{-1}$ for $\phi(k) \in \bar{K}$.

&nbsp; &nbsp; &nbsp; Since $\bar{K} \trianglelefteq \bar{G}$, $\phi(xkx^{-1}) = \phi(x)\phi(k)(\phi(x))^{-1} \in \bar{K} \implies xkx^{-1} \in \phi^{-1}(\bar{K})$


9. If $\phi$ is onto and $\Ker(\phi) = \{e\}$, then $\phi$ is an ismorphism from $G \rightarrow \bar{G}$

&nbsp; &nbsp; &nbsp; Since $|\Ker(\phi)| = 1$, then $\phi$ is a $1$-to-$1$ mapping from $G$ onto $\phi(G)$. Onto is another necessary property of ismoprhism

**Corollary**: $\Ker(\phi) \trianglelefteq G$ (follows from property $8$)

**Example**: Consider $\phi: C^* \rightarrow C^*$ with $\phi(x) = x^4$. Since $(xy)^r = x^4 y^4$, $\phi$ is a homomorphism

&nbsp; $\Ker(\phi) = \{1, -1, i, -i\}$. Thus $\phi$ is a $4$-to-$1$ mapping. 

&nbsp; To find all elements that map to $2$, we take $\sqrt[4]{2} \Ker(\phi) = \{\sqrt[4]{2}, -\sqrt[4]{2}, \sqrt[4]{2}i, -\sqrt[4]{2}i\}$

**Example**: Let $\phi: Z_{12} \rightarrow Z_{12}$ with $\phi(x) = 3x$. For $Z_{12}, $3(a+b) = 3a + 3b$ is clearly a homomorphism

&nbsp; Direct calculations show that $\Ker(\phi) = \{0, 4, 8\}$, which means that $\phi$ is a $3$-to-$1$ mapping.

&nbsp; Since $\phi(2) = 6$, we have that $\phi^{-1}(6) = 2 + \Ker(\phi) = \{2, 6, 10\}$

&nbsp; Notice that $\langle 2 \rangle$ and $\phi(\langle 2\rangle)$ are cyclic

&nbsp; Notice that $|2| = 6$ and $|\phi(2)| = 2$ so $|\phi(2)|$ divides $|2|$

&nbsp; Notice that $\bar{K} = \{0, 6\}$, we see that $\phi^{-1}(\bar{K}) = \{0, 2, 4, 6, 8, 10\} \leq Z_{12}$

**Example**: Determine all homomorphisms from $Z_{12} \rightarrow Z_{30}$

&nbsp; We know that all homomorphisms are determined by image of $1$. So $\phi(1) = a \implies \phi(x) = xa$

&nbsp; By Lagrange's Theorem, we know that $|a|$ divides $|a|$ divides $12, 30$. So possible values of $|a| \in \{1, 2, 3, 6\}$

&nbsp; Thus $a \in \{0, 15, 10, 20, 5, 25\}$, which are all the possible homomorphisms

&nbsp;

**First Isomorphism Theorem**: Homomorphism mapping $\phi: G/\Ker(\phi) \rightarrow \phi(G)$ where $g\Ker(\phi) \rightarrow \phi(g)$, is an isormophism. So $G/\Ker(\phi) \approx \phi(G)$

&nbsp; Let $\psi$ denote $g\Ker(\phi) \rightarrow \phi(g)$. $\psi$ is $1$-to-$1$ since $\phi(a) = \phi(b) \iff a\Ker(\phi) = b\Ker(\phi)$

&nbsp; Operation Preserving: $\psi(x\Ker(\phi)y\Ker(\phi)) = \psi(xy \Ker(\phi)) = \phi(xy) = \phi(x)(\phi(y) = \psi(x\Ker(\phi)) \psi(y\Ker(\phi))$

**Corollary**: if $\phi$ is a homomorphism from $G \rightarrow \bar{G}$, then $|\phi(G)|$ divides $|G|$ and $|\bar{G}|$

**Example**: Let $H = \{A \in GL(2, R) \mid \det(A) = \pm 1\}$. Then mapping $\phi(A) = \det(A)$ from $GL(2,R)$ onto $R^*$ shows that $GL(2, R) / SL(2, R) \approx R^*$, and the mapping $\phi(A) = (\det(A))^2$ from $GL(2, R)$ onto $R^+$ shows that $GL(2, R)/H \approx R^+$

**Example**: Consider a mapping from $Z \rightarrow Z_n$. Clearly the kernel is $\langle n \rangle$. Thus $Z/\langle n \rangle \approx Z_n$

**Example**: let $H \leq H$. Let $N(H) = \{x \in G \mid xHx^{-1} = H\}$ be the **normalizer** of $H$ in and $C(H) = \{x \in G \mid xhx^{-1} = h \quad \forall h \in H\}$ be the **centralizer** of $H$. Then the mapping from $N(H)$ to $\Aut(H)$ given by $g \rightarrow \phi_g$ (inner autmorphism) is a homomorphism with kernel $C(H)$. Thus $N(H)/C(H) \approx$ subgroup of $\Aut(H)$

<!-- **Example**: Let $|G| = 35$. By Lagrange's Theorem, non identity elements have order $\in \{5, 7, 35\}$. If $G$ is NOT cyclic, then non identity elements must have order $5$ or $7$ -->

<!-- &nbsp; However, not all elements can have order $5$ since elements of order $5$ come $4$ at a time($|x| = |x^2| = |x^3| = |x^4|= 5)$ and $4$ doesn't divide $35 - 1 = 34$ -->

<!-- &nbsp; Similary, not all elements have order $7$ since elements of order $7$ come $6$ at a time -->

<!-- &nbsp; We know that $G$ has an element of order $7$, it generates a subgroup of order $7$, call it $H$ -->

<!-- &nbsp; $H$ is the only subgroup of order $7$. Otherwise there would be another subgroup $K$ of order $7$ and thus $|HK| = |H||K|/|H \cap K| = 49 > 35$. Contradiction -->

<!-- &nbsp; Since for $a \in G$, $|aHa^{-1}| = 7$, then $aHa^{-1} = H$. Thus $N(H) = G$ -->

<!-- &nbsp; Since $H$ has prime order, it is cyclic and therefore Abeliean. Thus $H \subseteq C(H)$, so $7$ divides $|C(H)|$ and $|C(H)|$ divides $35$ -->

<!-- &nbsp; Thus $C(H) = G$ or $C(H) = H$ -->

<!-- &nbsp; For $C(H) = G$, then we can create an element $x = hk$ of order $35$. Thus $G$ must be cyclic. -->

&nbsp;

**Theorem**: Every normal subgroup of $G$ is the kernel of a homomorphism of $\phi(g) = gN$ from $G \rightarrow G/N$

&nbsp; Proof: define $\gamma: G \rightarrow G/N$ with $\gamma(g) = gN$ (**natural homomorphism**). Then $\gamma(xy) = (xy)N = xNyN = \gamma(x)\gamma(y)$

&nbsp; Furthermore, $g \in \Ker(\gamma) \iff gN = \gamma(g) = N \iff g \in N$
