<!-- LTeX: language=fr -->

# Théorie et construction des ordinaux

<!--toc:start-->

- [Théorie et construction des ordinaux](#théorie-et-construction-des-ordinaux)
  - [Ordres](#ordres)
    - [Définition](#définition)
    - [Définition](#définition)
      - [Correspondance entre ordre strict et large](#correspondance-entre-ordre-strict-et-large)
        - [Preuve](#preuve)
          - [$\leq$ est un ordre](#leq-est-un-ordre)
          - [$<$ est unique](#est-unique)
    - [Ordre total](#ordre-total)
      - [Définition](#définition)
      - [Exemples](#exemples)
    - [Bon ordre](#bon-ordre)
      - [Définition](#définition)
      - [Totalité des bons ordres](#totalité-des-bons-ordres)
        - [Preuve](#preuve)
      - [Suites strictement décroissantes dans un bon ordre](#suites-strictement-décroissantes-dans-un-bon-ordre)
        - [Preuve](#preuve)
      - [Somme de bons ordres](#somme-de-bons-ordres)
        - [Preuve](#preuve)
      - [Produit cartésien de bons ordres](#produit-cartésien-de-bons-ordres)
        - [Preuve](#preuve)
      - [Puissance de bons ordres](#puissance-de-bons-ordres)
        - [Preuve](#preuve)
          - [$<$ est un ordre strict](#est-un-ordre-strict)
          - [$<$ est un bon ordre](#est-un-bon-ordre)
      - [Récurrence transfinie](#récurrence-transfinie)
        - [Preuve](#preuve)
      - [Unicité des ordinaux](#unicité-des-ordinaux)
        - [Lemme : Réciproque d'une bijection croissante](#lemme-réciproque-dune-bijection-croissante)
        - [Preuve](#preuve)
  - [Ordinaux](#ordinaux) - [Définition](#définition) - [Quelques exemples](#quelques-exemples) - [Propriétés](#propriétés) - [Les éléments d'un ordinal sont des ordinaux](#les-éléments-dun-ordinal-sont-des-ordinaux) - [Preuve](#preuve) - [Transitivité](#transitivité) - [Bon ordre](#bon-ordre) - [Ordre large sur les ordinaux](#ordre-large-sur-les-ordinaux) - [L'ordre large est inclus dans $\subseteq$](#lordre-large-est-inclus-dans-subseteq) - [$\subseteq$ est inclus dans l'ordre large](#subseteq-est-inclus-dans-lordre-large) - [$\gamma\subseteq\beta$](#gammasubseteqbeta) - [$\beta\subseteq\gamma$](#betasubseteqgamma) - [Antiréflexivité de $\in$ sur les ordinaux](#antiréflexivité-de-in-sur-les-ordinaux) - [Preuve](#preuve) - [Successeur](#successeur) - [$\alpha^+$ est un ordinal](#alpha-est-un-ordinal) - [$\alpha^+$ transitif](#alpha-transitif) - [$\in$ est un ordre](#in-est-un-ordre) - [Bon ordre](#bon-ordre) - [Passage à l'ordre large](#passage-à-lordre-large) - [$\alpha^+$ est le successeur de $\alpha$](#alpha-est-le-successeur-de-alpha) - [Totalité de $\in$](#totalité-de-in) - [Preuve](#preuve) - [Bon ordre des ensembles d'ordinaux](#bon-ordre-des-ensembles-dordinaux) - [Preuve](#preuve) - [Majorant d'un ensemble d'ordinaux](#majorant-dun-ensemble-dordinaux) - [Preuve](#preuve) - [Transitivité](#transitivité) - [Bon ordre](#bon-ordre) - [Opérations élémentaires sur les ordinaux](#opérations-élémentaires-sur-les-ordinaux)
  <!--toc:end-->

Qu'y a-t-il après l'infini dénombrable ($\#\N$) ? On sait que $\N=(\N+1)\cup\{0\}$, et pourtant il est tentant de dire que $(\N+1)\cup\{0\}$ contient un élément de plus que $\N$ (on a décalé de $1$ et ajouté $0$): les ordinaux formalisent cette notion, en ce qu'ils permettent d'ordonner différents infinis.

Naturellement, la question qui en suit est : quel ordinal représente le cardinal de $\R$ ? Étant donné que $\R\simeq\N^\N$, en notant $\omega$ l'original représentant $\N$ (nous verrons ce que cela signifie par la suite), il semble donc naturel que celui qui représente $\R$ est $\omega^\omega$ : on voit donc bien que $\R$ est "un ordre de grandeur" plus grand que $\N$. C'est un résultat assez naturel, et il permet de répondre à la question de l'ordonnancement des infinis.

Il n'est pas en revanche évident de faire l'opération inverse : étant donné un ordinal, peut-on construire un ensemble (de nombres) qui soit ainsi représenté ? Cette question est exactement celle de [l'hypothèse du continu](https://fr.wikipedia.org/wiki/Hypothèse_du_continu).

## Ordres

### Définition

On dit que $\leq$ est un ordre (large) sur $A$ lorsque :

- réflexivité : $\forall a\in A,\quad a\leq a$
- antisymétrie : $\forall (a,b)\in A^2,\quad (a\leq b)\wedge(b\leq a)\implies a=b$
- transitivité : $\forall (a,b,c)\in A^3,\quad (a\leq b)\wedge(b\leq c)\implies a\leq c$

Deux notions découlent de celle-ci :

- l'ordre strict $<$ : $a<b\iff (a\leq b)\wedge(a\neq b)$
- l'ordre réciproque $\geq$, qui est également un ordre : $a\geq b\iff b\leq a$

En revanche, on peut également définir l'ordre strict en soi et l'ordre large qui en découle :

### Définition

On dit que $<$ est un ordre strict sur $A$ lorsque :

- antiréflexivité : $\forall a\in A,\quad \neg(a<a)$
- transitivité : $\forall (a,b,c)\in A^3,\quad (a<b)\wedge(b<c)\implies a<c$

De nouveau, deux notions découlent de celle-ci :

- l'ordre large $\leq$ : $a\leq b\iff (a<b)\vee(a=b)$
- l'ordre réciproque $>$, qui est également un ordre strict : $a>b\iff b<a$

Commençons par montrer que les notions d'ordre strict découlant d'un ordre large et que l'ordre large découlant d'un ordre strict coïncident :

#### Correspondance entre ordre strict et large

Étant donné un ordre strict $<$, l'ordre large $\leq$ associé est un ordre. Réciproquement, si $\leq$ est un ordre, il existe un unique ordre strict, noté $<$.

##### Preuve

###### $\leq$ est un ordre

La transitivité est évidente car $<$ et $=$ sont transitifs ($=$ est une relation d'équivalence). Il reste donc à vérifier :

- réflexivité : évident car $=$ est un relation d'équivalence
- antisymétrie : supposons que $a\leq b$ et que $b\leq a$, i.e. :

  - $a<b$ ou $a=b$
  - $b<a$ ou $b=a$

  Si $a=b$, il n'y a rien à prouver. Si $a<b$, on ne peut avoir $a=b$, i.e. $b=a$ par antiréflexivité, donc $b<a$ et par transitivité $a<a$, ce qui est encore exclu par antiréflexivité. Donc $a=b$, et c'est bien l'antisymétrie.

###### $<$ est unique

Supposons que $<$ et $\prec$ sont deux ordres stricts associés à $\leq$, c'est-à-dire que $a\leq b\iff(a<b)\vee(a=b)\iff(a\prec b)\vee(a=b)$. Il s'agit donc de montrer que $a<b\iff a\prec b$.

Supposons que $a<b$ : a fortiori, $a\leq b$, et donc $a\prec b$ ou $a=b$. Puisque $a<b$, $a\neq b$ et donc $a\prec b$. Par symétrie des rôles de $<$ et $\prec$, on a l'équivalence recherchée.

### Ordre total

On dit qu'un ensemble est totalement ordonné lorsqu'on peut toujours comparer deux éléments. Cette propriété, assez intuitive sur les ensembles de nombres, n'est qu'assez rarement vérifiée en pratique dès qu'on sort des ordres usuels.

#### Définition

$\leq$ est total lorsque :
$$\forall (a,b)\in A^2,\quad (a\leq b)\vee(b\leq a)$$

#### Exemples

C'est l'occasion de proposer des exemples d'ordre :

- $\leq$ sur $\R$ (et sur tous ses sous-ensembles : $\N,\Z,\mathbb Q…$) : c'est un ordre total (absolument non trivial à prouver, c'est une conséquence de la construction de $\R$). On peut prouver que l'ordre est total sur $\N$ de manière bien plus simple : nous verrons cela en tant que conséquence du bon ordonnancement de $\N$.
- $\mid$ sur $\N$ (la relation de divisibilité) : c'est un ordre _partiel_, on ne peut par exemple pas comparer $2$ et $3$ avec cet ordre (car $2\nmid3$ et $3\nmid2$). Pire encore, c'est seulement un préordre (il manque l'antisymétrie) sur $\Z$ ! En effet, si $a\mid b$ et $b\mid a$, alors on n'a que $\vert a\vert=\vert b\vert$.
- l'ordre lexicographique $\leq$ sur $A^n$, où $A$ est ordonné par $\leq$ (c'est donc un abus de notation, mais c'est l'ordre le plus naturel dont on peut munir les $n$-uplets) :
  $$(a_1,\dots,a_n)\leq(b_1,\dots,b_n)\iff\begin{cases}a_1<b_1\\\vdots\\a_{n-1}<b_{n-1}&\text{si }a_1=b_1,\dots,a_{n-2}=b_{n-2}\\a_n\leq b_n&\text{si }a_1=b_1,\dots,a_{n-1}=b_{n-1}\end{cases}$$
  $$(a_1,\dots,a_n)<(b_1,\dots,b_n)\iff\begin{cases}a_1<b_1\\\vdots\\a_{n-1}<b_{n-1}&\text{si }a_1=b_1,\dots,a_{n-2}=b_{n-2}\\a_n<b_n&\text{si }a_1=b_1,\dots,a_{n-1}=b_{n-1}\end{cases}$$
- dans certains cas, on préfèrera un ordre plus brutal, mais partiel :
  $$(a_1,\dots,a_n)\leq(b_1,\dots,b_n)\iff\begin{cases}a_1\leq b_1\\\vdots\\a_n\leq b_n\end{cases}$$

  Pourquoi choisir cet ordre plutôt que l'ordre lexicographique ? L'intérêt se présente lorsqu'il est nécessaire de préserver la compatibilité entre l'ordre et d'autres opérations. Le meilleur exemple est [$\mathbb C\simeq\R^2$](https://fr.wikipedia.org/wiki/Corps_ordonné#Corps_totalement_ordonné) : le munir de l'ordre lexicographique lui fait perdre la compatibilité avec $+$ et $\times$. Le problème avec cet ordre est qu'il est partiel, et qu'on ne peut a priori pas dire qui est plus grand entre $1-i$ et $-1+i$.

### Bon ordre

Les ordres stricts se prêtent mieux à la démonstration des propriétés qui vont suivre : nous les utiliserons donc à partir de maintenant, sauf mention du contraire, et ils seront notés génériquement $<$, leur ordre large associé $\leq$.

#### Définition

$<$ est un bon ordre lorsque toute partie non vide $\mathcal A\subseteq A$ admet un minimum.

#### Totalité des bons ordres

Si $<$ est un bon ordre, alors $\leq$ est un ordre total.

##### Preuve

Soit $(a,b)\in A^2$. Alors $\{a,b\}\subseteq A$ donc cette partie admet un plus petit élément. Par symétrie, prenons $a$ : cela signifie donc que $a\leq b$, et l'ordre est bien total.

#### Suites strictement décroissantes dans un bon ordre

Si $<$ est un bon ordre, alors il n'existe aucune suite strictement décroissante de $A$.

##### Preuve

Soit $(x_n)_{n\in\N}\in A^\N$ une suite strictement décroissante. Alors $\{x_n\}_{n\in\N}\subseteq A$ et admet donc un plus petit élément, que l'on note $x_{n_0}$. Mais alors $x_{n_0+1}<x_{n_0}$, ce qui contredit sa minimalité : c'est absurde.

#### Somme de bons ordres

On définit $A+B=(\{0\}\times A)\cup(\{1\}\times B)$ (c'est l'ensemble des éléments du type somme de $A$ et $B$, une notion de la théorie des [types algébriques](https://fr.wikipedia.org/wiki/Type_algébrique_de_données#Type_somme)).

Si $A$ et $B$ sont bien ordonnés, alors $A+B$, muni de l'ordre lexicographique est bien ordonné.

_En pratique, on préfèrera définir $A+B=(A\times \{0\})\cup(B\times \{1\})$ pour être compatible avec [l'exponentiation](#puissance-de-bons-ordres). Il faudra donc prendre l'ordre lexicographique inverse._

##### Preuve

Soit $P\subseteq A+B$ non vide. On note $P_0=\{a,(0,a)\in P\}\subseteq A$ et $P_1=\{b,(1,b)\in P\}\subseteq B$.

Par définition, $P=(\{0\}\times P_0)\cup(\{1\}\times P_1)\neq\empty$ donc $P_0\neq\empty$ ou $P_1\neq\empty$. Si $P_0\neq\empty$, alors si $a_0$ est son plus petit élément, $(0,a_0)$ minore $P$. Sinon, on fait de même avec $b_1\in P_1$, et $(1,b_1)$ minore $P$. Dans tous les cas, $P$ admet un plus petit élément, et $A+B$ est bien ordonné.

#### Produit cartésien de bons ordres

Si $A$ et $B$ sont bien ordonnés, alors $A\times B$ muni de l'ordre lexicographique est encore bien ordonné

##### Preuve

Soit $P\subseteq A\times B$ _(attention ! $P$ peut ne pas s'écrire $\mathcal A\times\mathcal B$ avec $\mathcal A\subseteq A$ et $\mathcal B\subseteq B$, on sait juste que $P$ est un ensemble de couples de $A\times B$. Exemple : $P=\{(0,0),(1,1)\}$, qui est de cardinal $2$, s'il s'écrivait $\mathcal A\times\mathcal B$, alors $\#\mathcal A\times\#\mathcal B=2$, et sans perte de généralité, $\mathcal B$ est un singleton (cardinal $1$) qui contient $0$ et $1$, ce qui est impossible)_. Supposons que $P$ n'est pas vide et montrons qu'il admet un plus petit élément.

On considère $A_P=\{a,\exists b\in B,(a,b)\in P\}\subseteq A$ : par bon ordre, cette partie étant non vide (par définition de $P$), elle admet un plus petit élément $a_0\in A_P$, et on définit de même $B_{a_0}=\{b,(a_0,b)\in P\}\subseteq B$. Encore une fois, c'est une partie non vide de $B$, bien ordonné, donc qui admet un plus petit élément $b_0$.

Soit $(a,b)\in P$. Alors, par définition, $a_0\leq a$ et si $a=a_0$, alors $b\in B_{a_0}$ donc $b_0\leq b$ : on en déduit donc que $(a_0,b_0)\leq(a,b)$, i.e. c'est le minimum de $P$. On vient de montrer le bon ordre de $A\times B$.

#### Puissance de bons ordres

On définit $A^{(B)}$ comme les familles finies d'éléments de $A$ indexées par $B$. En d'autres termes, si $(a_b)_{b\in B}\in A^{(B)}$, $\#\{a_b\neq0\}_{b\in B}<+\infty$ (la définition de $0$ dépendant du contexte dans le cadre général).

Soit $A$ bien ordonné, dont on note $0$ son minimum. Lorsque $B$ est bien ordonné, on munit $A^{(B)}$ de l'ordre suivant :
$$(a_b)_{b\in B}<(\tilde a_b)_{b\in B}\iff \exists b_0\in B,\quad\begin{cases}a_{b_0}<\tilde a_{b_0}\\a_b=\tilde a_b\quad (\forall b_0<b)\end{cases}$$

Muni de cet ordre, $A^{(B)}$ est bien ordonné.

##### Preuve

###### $<$ est un ordre strict

- Pour tout $b\in B$, $a_b=a_b$, donc il n'existe aucun $b_0\in B$ tel que $a_{b_0}<a_{b_0}$ : c'est l'antiréflexivité.
- On considère $a<\tilde a$ et $\tilde a<\tilde{\tilde a}$. Soient $b_0\in B$ et $b_1\in B$ tels que :
  $$a_{b_0}<\tilde a_{b_0}\quad\text{et}\quad\tilde a_{b_1}<\tilde{\tilde a}_{b_1}$$
  $$\forall b_0<b,\quad a_b=\tilde a_b$$
  $$\forall b_1<b,\quad\tilde a_b=\tilde{\tilde a}_b$$

Puisque $<$ est un bon ordre, $\leq$ est un ordre total (sur $B$), et sans perte de généralité, on suppose que $b_0\leq b_1$. Si $b_0=b_1$, il n'y a plus rien à prouver : $a<\tilde{\tilde a}$. Sinon $a_{b_1}=\tilde a_{b_1}<\tilde{\tilde a}_{b_1}$ et pour tout $b_1<b$, $a_b=\tilde a_b=\tilde{\tilde a}_b$. On a bien montré que $a<\tilde{\tilde a}$.

###### $<$ est un bon ordre

Soit $P\subseteq A^{(B)}$ non vide. On définit $B_P=\{b,a_b\neq0,\forall b<\tilde b,a_{\tilde b}=0\}_{a\in P}$ (l'ensemble des derniers indices pour lequel chaque suite de $P$ est non nulle) : $P$ étant non vide, $B_P$ non plus, et étant une partie de $B$, bien ordonné, $B_P$ admet un plus petit élément $b_0$. On pose alors $A_{b_0}=\{a_{b_0},a_{b_0}\neq0\}_{a\in P}\subseteq A$ qui est une partie non vide par définition de $b_0$ elle admet donc un plus petit élément, qui est réalisé par une suite $a^0$.

Soit $a\in P$. Par définition, il existe $b_0\leq b$ tel que $a_{\tilde b}=0$ pour tout $b<\tilde b$. Si $b=b_0$, alors $a^0_{b_0}\leq a_{b_0}$ par définition de $a_0$ et $a^0_{\tilde b}=0=a_{\tilde b}$, donc $a^0\leq a$. Sinon $b_0<b$, donc $a^0_b=0<a_b$ (par définition de $a^0$) et on a toujours $a^0_{\tilde b}=0=a_{\tilde b}$, donc $a^0\leq a$. Dans tous les cas, on a bien un plus petit élément de $P$ donc $A^{(B)}$ est bien ordonné.

#### Récurrence transfinie

L'intérêt essentiel des ordinaux est de pouvoir étendre la notion de récurrence sur $\N$ à des ensembles bien ordonnés (au même titre que $\N$). En d'autres termes, la propriété essentielle rendant le principe de récurrence efficace est le bon fondement de l'ensemble sur lequel on indice. La propriété de récurrence transfinie est la suivante :

Étant donné $P$ un prédicat sur $A$ tel que :
$$\forall x\in A,\quad[\forall y\in A,\quad y<x\implies P(y)]\implies P(x)$$

Alors $P(x)$ est vrai pour tout $x\in A$.

##### Preuve

Soit $x\in A$. On considère $F=\{x,\neg P(x)\}$ : si $F\neq\empty$, alors étant une partie de $A$ non vide, $F$ admet un minimum $x$. Par définition :
$$\forall y<x,\quad P(y)$$

Or, par propriété de récurrence transfinie, cela entraîne $P(x)$, mais donc $x\notin F$ : $F=\empty$, en d'autres termes $P(x)$ est vraie pour tout $x\in A$.

#### Unicité des ordinaux

Si $E$ et $F$ sont bien ordonnés, alors il existe au plus une bijection croissante $f:E\longrightarrow F$, i.e. $x<y\implies f(x)<f(y)$ (pour les ordres respectifs sur $E$ et $F$).

##### Lemme : Réciproque d'une bijection croissante

Montrons tout d'abord que la réciproque d'une bijection croissante est croissante : soient $a=f(x)<b=f(y)$ dans $F$ (on peut toujours écrire $a$ et $b$ de cette manière car $f$ est une bijection). Puisque $E$ et $F$ sont bien ordonnés, l'ordre est total, et par contraposition de la définition de la croissance d'une fonction :
$$f(x)\geq f(y)\implies x\geq y$$

En remplaçant $a=f(x)$ et $b=f(y)$ par les expressions réciproques, i.e. $x=f^{-1}(a)$ et $y=f^{-1}(b)$, on obtient donc :
$$b\leq a\implies f^{-1}(b)\leq f^{-1}(a)$$

Puisque $a\neq b$, $x\neq y$, et toutes les inégalités sont strictes :
$$b<a\implies f^{-1}(b)<f^{-1}(a)$$

##### Preuve

Supposons qu'il existe $f$ et $g$ deux bijections croissantes de $E$ dans $F$. On va montrer par récurrence transfinie que $f=g$ : $P(x)$ correspond à l'assertion $f(x)\leq g(x)$. Soit $x\in E$, supposons que pour tout $y<x$, $P(y)$, i.e. $f(y)\leq g(y)$.

On en déduit donc que, à $y<x$ fixé, $g(y)<g(x)$ et donc $f(y)\leq g(y)<g(x)$, donc $y<f^{-1}(g(x))$.

Si $f^{-1}(g(x))<x$, alors on peut appliquer $P\left[f^{-1}(g(x))\right]$ par hypothèse, i.e. $f\left[f^{-1}(g(x))\right]\leq g\left[f^{-1}(g(x))\right]$, soit encore $g(x)\leq g\circ f^{-1}\circ g(x)$. En appliquant alors la bijection réciproque de $g$ :
$$x\leq f^{-1}(g(x))\iff f(x)\leq g(x)$$
Ceci contredit l'hypothèse $f^{-1}(g(x))<x\iff g(x)<f(x)$, soit $f(x)\leq g(x)$.

On en déduit donc que $f\leq g$, et par symétrie des rôles de $f$ et $g$, $f=g$.

## Ordinaux

Ces propriétés essentielles établies, et en particulier "l'unicité" des ordinaux, qui seront vus, à une bijection croissante près, comme des ensembles bien ordonnés, nous pouvons nous atteler à prouver des propriétés usuelles sur les ordinaux : sans encore parler d'arithmétique, on s'attend à retrouver les propriétés élémentaires sur les cardinaux ($+$, $\times$, exponentiation, ordre total…).

### Définition

On dit qu'un ensemble $\alpha$ est un ordinal lorsque :

- transitivité : $\forall x\in \alpha,\quad\forall y\in x,\quad y\in \alpha$

  De manière équivalente : $\forall x\in\alpha,\quad x\subseteq\alpha$

- $\in$ est un bon ordre sur $\alpha$

### Quelques exemples

$\empty$ est un ordinal. En effet, la transitivité est évidente pour $\empty$ (quantification sur l'ensemble vide), et la seule partie de $\empty$ est vide, donc $\in$ est bien un bon ordre.

$\{\empty,\{\empty\}\}$ est un ordinal. En effet, la transitivité est évidente (disjonction de cas sur chaque élément) et $\in$ est bien un bon ordre, car pour toute partie, il existe toujours un minimum :

| $P$                     | $\min(P)$    |
| ----------------------- | ------------ |
| $\empty$                | non défini   |
| $\{\empty\}$            | $\empty$     |
| $\{\{\empty\}\}$        | $\{\empty\}$ |
| $\{\empty,\{\empty\}\}$ | $\empty$     |

### Propriétés

#### Les éléments d'un ordinal sont des ordinaux

Si $\beta\in\alpha$ et que $\alpha$ est un ordinal, alors $\beta$ est un ordinal.

##### Preuve

###### Transitivité

Soient $x\in\beta$ et $y\in x$. Par hypothèse, $y\in x\in\alpha$ (transitivité sur $\alpha$), donc $y\in\alpha$. Or, $\alpha$ est bien ordonné par $\in$ et :

- $y\in\alpha$
- $x\in\alpha$
- $\beta\in\alpha$
- $y\in x\in\beta$

Ceci entraîne donc que $y\in\beta$ car $\in$ est une relation d'ordre (transitive) sur $\alpha$.

_ATTENTION : il est nécessaire de bien faire ces vérifications d'appartenance à $\alpha$, car une série d'appartenance en série, même si $\in$ est une "relation d'ordre", n'est pas automatiquement réduite par transitivité : rien n'indique que l'on est dans le bon ensemble sur lequel comparer. Pour donner un contre-exemple, on peut prendre $\alpha=\{\{\{0\}\}\}$, $y=0$, $x=\{0\}$, $\beta=\{\{0\}\}$ : on a bien $y\in x\in\beta\in\alpha$, mais on n'a pas $y\in\alpha$ ! Pourtant $\in$ est une bien relation d'ordre strict sur $\alpha$ (même un bon ordre) car $\alpha$ n'a qu'un seul élément…_

###### Bon ordre

Il s'agit de vérifier que $(\beta,\in)$ est bien ordonné. Ceci est immédiat par transitivité de $\alpha$ car $\beta\subseteq\alpha$ donc $\in$ est un bon ordre par simple restriction.

<!-- #### Ordinaux et segments initiaux -->

#### Ordre large sur les ordinaux

L'ordre large associé à $\in$ est $\subseteq$ sur les ordinaux.

##### L'ordre large est inclus dans $\subseteq$

Soient $\alpha$ et $\beta$ deux ordinaux tels que $\beta=\alpha$ ou $\beta\in\alpha$. Si $\beta=\alpha$, on a de manière évidente que $\beta\subseteq\alpha$. Sinon $\beta\in\alpha$, et par transitivité de $\alpha$, $\beta\subseteq\alpha$.

##### $\subseteq$ est inclus dans l'ordre large

Réciproquement, si $\beta\subseteq\alpha$ et $\beta\neq\alpha$, alors il s'agit de montrer que $\beta\in\alpha$. Par hypothèse, $\alpha\backslash\beta\neq\empty$ et $\alpha$ est bien ordonné, donc on peut prendre son plus petit élément $\gamma\in\alpha\backslash\beta$. $\gamma$ est un ordinal (c'est un élément de $\alpha$, ordinal) et $\gamma\subseteq\alpha$ par transitivité de $\alpha$. L'idée est de montrer que $\gamma=\beta$ car alors $\gamma=\beta\in\alpha$.

###### $\gamma\subseteq\beta$

Soit $x\in\gamma\subseteq\alpha$ : si $x\notin\beta$, i.e. $x\in\alpha\backslash\beta$, alors, sur $\alpha$ muni de la relation d'ordre $\in$, $x\in\gamma$. Or, $\gamma$ est supposé être le minimum de $\alpha\backslash\beta$ : c'est impossible. Donc $x\in\beta$. En d'autres termes, $\gamma\subseteq\beta$.

###### $\beta\subseteq\gamma$

On prend $x\in\beta$ et on s'intéresse à $\{x,\gamma\}\subseteq\alpha$. Si $x=\gamma$, alors $\gamma\in\beta$. Sauf que $\gamma\in\alpha\backslash\beta$ : c'est absurde. Si $\gamma\in x$, comme $x$ est un ordinal (c'est un élément de $\beta$), $x\subseteq\beta$ et donc $\gamma\in x\subseteq\beta$ et $\gamma\in\beta$ ce qui est encore absurde. Donc $x\in\gamma$ et $\beta\subseteq\gamma$.

<!-- #### Plus petit ordinal -->
<!---->
<!-- Si $\alpha\neq\empty$, alors $\empty\in\alpha$. _On verra par la suite que $\in$ est un ordre total sur la classe des ordinaux._ -->
<!---->
<!-- ##### Preuve -->
<!---->
<!-- On considère $\min\alpha\in\alpha$ par transitivité. Si $\min\alpha\neq\empty$, alors on peut prendre un élément $x\in\min\alpha$, mais alors par transitivité, $x\in\alpha$ : ceci contredit la minimalité de $x$, à moins que $x=\min\alpha$. Or ceci est exclu car $\in$ est un bon ordre, a fortiori un ordre strict. -->

#### Antiréflexivité de $\in$ sur les ordinaux

Si $\alpha$ est un ordinal, alors $\alpha\notin\alpha$.

##### Preuve

Supposons par l'absurde que $\alpha\in\alpha$. Alors, $\in$ étant un ordre strict sur $\alpha$, pour tout $x\in\alpha$, $x\notin x$. En particulier, pour $x=\alpha$, $\alpha\notin\alpha$, ce qui est absurde et conclut.

#### Successeur

On pose $\alpha^+=\alpha\cup\{\alpha\}$ (où $\alpha$ est un ordinal). Par construction, $\alpha\in\alpha^+$. Alors :

1. $\alpha^+$ est un ordinal
1. pour tout ordinal $\beta$ tel que $\alpha\in\beta$, $\alpha^+\subseteq\beta$.
1. $\alpha^+$ est le successeur de $\alpha$, au sens où si $\alpha\in\beta\subseteq\alpha^+$, alors $\beta=\alpha^+$. En d'autres termes, il n'existe aucun ordinal strictement compris entre $\alpha$ et $\alpha^+$.

##### $\alpha^+$ est un ordinal

###### $\alpha^+$ transitif

Si $x\in\alpha^+$, alors $x\in\alpha$ donc $x\subseteq\alpha$ (transitivité de $\alpha$) ou $x\in\{\alpha\}$, i.e. $x=\alpha$. Dans tous les cas, $x\subseteq\alpha\subseteq\alpha^+$.

###### $\in$ est un ordre

- antiréflexivité : si $x\in\alpha^+$, soit $x=\alpha$, ou alors $x\in\alpha$, mais [tout élément d'un ordinal est un ordinal](#les-éléments-dun-ordinal-sont-des-ordinaux) , donc $x$ est un ordinal dans tous les cas. De là, par [antiréflexivité de $\in$ sur les ordinaux](#antiréflexivité-de-in-sur-les-ordinaux), $x\notin x$.
- transitivité : Si $(x,y,z)\in(\alpha^+)^3$ avec $x\in y$ et $y\in z$. On rappelle que cela signifie en particulier que $x$, $y$ et $z$ sont tous des ordinaux (d'après le point précédent), on résume les différents cas possibles ($x\in\alpha$ ou $x=\alpha$) dans le tableau suivant, où $\in$ symbolise le premier cas, et $=$ désigne le second (s'il n'y a rien dans la case, le raisonnement est valide indépendamment du cas):

| $x$   | $y$   | $z$   | conclusion                                                                                                                            |
| ----- | ----- | ----- | ------------------------------------------------------------------------------------------------------------------------------------- |
| $\in$ | $\in$ | $\in$ | c'est une conséquence de la transitivité de $\in$ sur $\alpha$                                                                        |
| $\in$ | $\in$ | $=$   | on a immédiatement $x\in z=\alpha$                                                                                                    |
| $\in$ | $=$   | $\in$ | $y=\alpha\in z\in\alpha$ entraîne $\alpha\subseteq z\subseteq\alpha$ donc $z=\alpha$, mais alors $\alpha\in\alpha$ ce qui est absurde |
| $=$   | $\in$ |       | $x=\alpha\in y\in\alpha$ entraîne $\alpha\subseteq y\subseteq\alpha$ donc $y=\alpha$, mais alors $\alpha\in\alpha$ ce qui est absurde |
| $\in$ | $=$   | $=$   | on a $\alpha=y\in z=\alpha$, ce qui est absurde                                                                                       |
| $=$   | $=$   |       | on a $\alpha=x\in y=\alpha$, ce qui est absurde                                                                                       |

_Remarquons qu'on a bien énuméré tous les cas, qui sont au nombre de $2^3=8$._

On a donc montré que pour les cas non triviaux, il y a bien transitivité de $\in$ sur $\alpha^+$.

###### Bon ordre

Si $A\subseteq\alpha^+$ non vide, on distingue deux cas :

- $\alpha\notin A$ : dans ce cas, $A\subseteq\alpha$ et $A$ admet donc un plus petit élément pour $\in$ par bon ordre de $\alpha$
- $\alpha\in A$ : si $A\backslash\alpha=\empty$, $\alpha$ est bien le plus petit élément de $A$, sinon on prend le plus petit élément $x$ de $A\backslash\alpha$ : [la preuve de la transitivité](#alpha-transitif) donne immédiatement que $x\subseteq\alpha$, et donc $x$ est bien le plus petit élément de $A$ (puisque $\subseteq$ est un ordre large).

##### Passage à l'ordre large

Si $\alpha\in\beta$, alors si $x\in\alpha^+$, soit $x=\alpha$ et donc $x\in\beta$, sinon $x\in\alpha\subseteq\beta$ (par transitivité). En résumé, on a bien montré que $\alpha^+\subseteq\beta$.

##### $\alpha^+$ est le successeur de $\alpha$

Par la propriété précédente, si $\alpha\in\beta\subseteq\alpha^+$, alors $\alpha^+\subseteq\beta$ donc $\beta=\alpha^+$.

#### Totalité de $\in$

Si $\alpha$ et $\beta$ sont deux ordinaux, alors ils sont comparables. En d'autres termes, on se trouve dans (exactement) l'un des cas suivants :
$$\alpha\in\beta\qquad\alpha=\beta\qquad\alpha\ni\beta$$

##### Preuve

On suppose par que $\alpha$ et $\beta$ ne sont pas comparables, i.e. on a $\alpha\notin\beta$, $\alpha\notni\beta$ et $\alpha\neq\beta$. On s'intéresse alors à $\gamma=\alpha\cap\beta\subseteq\alpha$. Naturellement, si $\gamma=\alpha$, alors $\alpha\subseteq\beta$, ce qui est exclu, donc $\gamma\in\alpha$. Par un raisonnement analogue, $\gamma\in\beta$, mais cela se traduit par $\gamma\in\alpha\cap\beta=\gamma$. Or ceci est absurde car $\gamma\in\alpha$ qui est muni de l'ordre strict $\in$.

En résumé, $\alpha$ et $\beta$ sont comparables.

#### Bon ordre des ensembles d'ordinaux

Soit $A$ un ensemble d'ordinaux. Alors $(A,\in)$ est bien ordonné.

##### Preuve

Il est tout d'abord évident que $\in$ est un ordre sur $A$ puisque $\in$ est total sur la classe des ordinaux. Il reste donc à montrer que c'ste bon ordre. Pour cela, on considère $\beta=\bigcap\limits_{\alpha\in A}\alpha$ qui est inférieur à l'ensemble des éléments de $A$ (qu'on suppose évidemment non vide, il n'y a rien à montrer si $A=\empty$). Il s'agit de montrer que $\beta\in A$ : supposons par l'absurde que ce n'est pas le cas, ainsi on en déduit que pour tout $\alpha\in A$, $\beta\in\alpha$ (car $\beta\subseteq\alpha$ par définition). Ceci se réécrit précisément comme $\beta\in\bigcap\limits_{\alpha\in A}\alpha=\beta$. Or $\beta\in\alpha_0\in A$ (pour un $\alpha_0$ quelconque) donc $\beta$ est un ordinal et cette conclusion est absurde. Donc $\beta\in A$ est bien un minorant de $A$.

Remarquons que cette preuve est suffisante : si on prend une partie non vide de $A$, il s'agit encore d'un ensemble d'ordinaux et le résultat précédent s'applique.

#### Majorant d'un ensemble d'ordinaux

Si $A$ est un ensemble d'ordinaux, alors $\bigcup\limits_{\alpha\in A}\alpha$ est un ordinal.

##### Preuve

###### Transitivité

Si $x\in\bigcup\limits_{\alpha\in A}\alpha$, alors il existe $\alpha\in A$ tel que $x\in\alpha$ : par transitivité de $\alpha$, $x\subseteq\alpha\subseteq\bigcup\limits_{\alpha\in A}\alpha$, i.e. $x\subseteq\bigcup\limits_{\alpha\in A}\alpha$.

###### Bon ordre

$\bigcup\limits_{\alpha\in A}\alpha$ est un ensemble d'ordinaux (car c'est une réunion d'ordinaux, qui sont des [ensembles d'ordinaux](#les-éléments-dun-ordinal-sont-des-ordinaux)) et la propriété précédente garantit qu'il est donc bien ordonné.

### Opérations élémentaires sur les ordinaux

L'ensemble des propriétés élémentaires (et attendues) sur les ordinaux étant démontrées, nous allons désormais utiliser les notations usuelles pour les ordres sur les ordinaux : $<$ pour $\in$ et $\leq$ pour $\subseteq$.

Nous allons montrer quelques propriétés générales sur les ordinaux, qui sont très analogues à celles sur les entiers naturels. Nous rappelons que les opérations élémentaires ($+$, $\times$ et exponentiation) sont bien définies pour les ensembles bien ordonnés, et a fortiori pour les ordinaux.

#### Définition : ordinaux limites

$\alpha$ est dit ordinal limite lorsqu'il s'agit d'un ordinal qui ne le successeur d'aucun autre.

##### Exemple

Étant donné $\N$, construit par exemple dans l'axiomatique de Peano ou dans le modèle ZF[C], on pose $\overline0=\empty$ et $\overline{n+1}=\overline n^+$. Remarquons au passage que cette construction est saine car $\#\overline n=n$ !

Par suite, le premier ordinal limite est $\omega=\bigcup\limits_{n\in\N}\overline n$.

#### Successeur naturel

Si $\alpha$ est un ordinal, alors $\alpha^+=\alpha+\overline1$.

#### Éléments neutres et absorbants

Si $\alpha$ est un ordinal, alors :

1. $\overline0+\alpha=\alpha+\overline0=\alpha$
1. $\overline1\times\alpha=\alpha\times\overline1=\alpha$.
1. $\overline0\times\alpha=\alpha\times\overline0=\overline0$.
1. si $\alpha\neq\overline0$, alors $\overline0^\alpha=\overline0$
1. $\overline0^\overline0=\overline1$ (convention)
1. $\alpha^{\overline0}=\overline1$
1. $\alpha^{\overline1}=\alpha$

#### Distributivités

Si $\alpha$, $\beta$ et $\gamma$ sont des ordinaux, alors :

1. $\alpha(\beta+\gamma)=\alpha\times\beta+\alpha\times\gamma$
1. $\alpha^{\beta+\gamma}=\alpha^\beta\times\alpha^\gamma$
1. $(\alpha^\beta)^\gamma=\alpha^{\beta\gamma}$

**ATTENTION** : contrairement à l'arithmétique usuelle, on n'a pas la distributivité à droite de $\times$ sur $+$

#### Les opérations sont compatibles avec l'ordre

Si $\alpha$, $\beta$ et $\gamma$ sont des ordinaux, alors :

1. si $\alpha<\beta$, alors $\alpha+\gamma<\beta+\gamma$
1. si $\alpha\neq\overline0$ et que $\beta<\gamma$, alors $\alpha\beta<\beta\gamma$
1. si $\alpha>\overline1$ et que $\beta<\gamma$, alors $\alpha^\beta<\alpha^\gamma$
