# Construction incrémentale

Comme le tableau précédent le montre, l'algèbre part de structures volontairement très peu restrictives et élabore graduellement à partir de celles-ci. Cette approche permet notamment de donner des résultats aux hypothèses minimales. Cependant, il est bon de noter que la plupart des résultats deviennent rapidement triviaux ou inintéressants dans les cadres élaborés : dans la pratique, les résultats établis pour — par exemple — un groupe fini sera intéressant dans ce cas et rarement en-dehors.

## Construction par quotient

Une autre technique très employée pour construire des ensembles aux bonnes propriétés est d'employer des relations d'équivalence pour construire des ensembles quotient qui ajoutent aux propriétés de l'ensemble de départ des propriétés additionnelles intéressantes.

L'exemple le plus classique de cette démarche est la chaîne de construction :
$$\emptyset\longrightarrow\N\underset{\text{quotient}}\longrightarrow\Z\underset{\text{quotient}}\longrightarrow\Q\longrightarrow\R\longrightarrow\C$$

Ces constructions reposent sur la notion de relation d'équivalence et permettent d'étendre de manière triviale les opérations que les structures précédentes possèdent tout en garantissant des propriétés supplémentaires. Donnons ici les définitions fondamentales qu'on illustrera dans le paragraphe suivant :

## Définition : Relation d'équivalence

Sur un ensemble $E$ quelconque, on dit que $\sim$ est une relation d'équivalence lorsqu'elle satisfait les trois propriétés suivantes :
$$\begin{aligned}
\forall x\in E&,&\ x\sim x&&\quad\text{(Réflexivité)}\\
\forall(x,y)\in E^2&,&\ x\sim y&\implies y\sim x&\quad\text{(Symétrie)}\\
\forall(x,y,z)\in E^3&,&\ (x\sim y)\wedge (y\sim z)&\implies x\sim z&\quad\text{(Transitivité)}
\end{aligned}$$

## Définition : Classe d'équivalence

Pour tout $x\in E$, on notera $\overline x=\{y\in E,\ y\sim x\}$ la classe d'équivalence de $x$. En particulier, $\overline x=\overline y\iff x\sim y$.

## Définition : Ensemble quotient

L'ensemble des classes d'équivalence pour $\sim$ est noté $E/{\sim}=\{\overline x\}_{x\in E}$

## Théorème : Équivalence entre relation d'équivalence et partition

Étant donné une partition $(P_i)_{i\in I}$ de $E$, on peut lui associer la relation d'équivalence $x\sim y\iff\exists i\in I,\ (x\in P_i)\wedge(y\in P_i)$.

Réciproquement, $E/{\sim}$ est une partition de $E$.

### Démonstration

Commençons par le second point afin de rappeler la définition d'une partition : il s'agit de montrer que $E/{\sim}$ est une partition, c'est-à-dire que $\bigsqcup\limits_{x\in E/{\sim}}\overline x=E$ et que $\overline x\cap\overline y\neq\emptyset\implies\overline x=\overline y$.
D'emblée $E/{\sim}$ recouvre bien $E$ tout entier par réflexivité et la seconde propriété (qualifiée de disjonctive) s'obtient en remarquant qu'il existe $z\in\overline x\cap\overline y\neq\emptyset$ et par définition $x\sim z$ et $y\sim z$ donc par transitivité et symétrie $x\sim y$ d'où $\overline x=\overline y$.

Pour le premier point, il suffit de vérifier que $\sim$ ainsi définie est bien une relation d'équivalence :

* pour tout $x\in E$, $(P_i)_{i\in I}$ étant une partition, il existe donc $i\in I$ tel que $x\in P_i$ et donc $x\sim x$.
* la symétrie est évidente car $(x\in P_i)\wedge(y\in P_i)\iff(y\in P_i)\wedge(x\in P_i)$.
* Si $(x\in P_i)\wedge(y\in P_i)$ et $(y\in P_j)\wedge(z\in P_j)$, alors $y\in P_i\cap P_j\neq\emptyset$ ce qui n'arrive que lorsque $i=j$ par définition d'une partition et donc $(x\in P_i)\wedge(z\in P_j)$ : c'est la transitivité.

Nous disposons maintenant des outils fondamentaux pour construire nos premiers ensembles, qu'ils soient concrets ou abstraits !

## Construction concrète de $\Z$ et $\Q$ à partir de $\N$

Pour rappel, $\N$, l'ensemble des entiers naturels, est défini par les propriétés suivantes :

* $0\in\N$
* $n\in\N\implies n+1\in\N$

Pour construire $\Z$, il faut se demander comment construire, à partir d'entiers positifs, un nombre négatif. La première idée est de prendre l'opposé, cependant prendre une telle définition est parfaitement tautologique. En revanche, on peut également penser qu'il s'agit de la soustraction de $0$ par $n$, le nombre en question, et même de $k$ par $n+k$. De manière générale, un entier relatif peut donc être encodé par $a-b$ pour $(a,b)\in\N^2$. Cette idée nous conduit à la relation d'équivalence $\sim$ sur $\N^2$, où les classes seront les entiers relatifs :
$$(a,b)\sim(x,y)\iff a+y=b+x$$

Pourquoi une telle définition ? Notons tout d'abord que, lorsqu'on aura défini $\Z$, que cette définition équivaudra précisément à $a-b=x-y$ : c'est le raisonnement précédent. Cette construction permet en fait de s'affranchir des problèmes de définition dûs à la soustraction qui n'est pas encore définie de manière générale (ou pas du tout en fonction de la construction de $\N$ choisie).

On peut aisément vérifier qu'il s'agit bien d'une relation d'équivalence. Dans ces conditions, on définit alors $\Z=\N^2/{\sim}$.

Pour construire $\Q$, on procède de la même manière sur $\Z\times\N^*$ en posant :
$$(a,b)\equiv(x,y)\iff ay=bx$$

L'intérêt de ces deux constructions est que $\Z$ est un anneau car $(\Z,+)$ est un groupe et $\Q$ est un corps ! Finalement, ces constructions permettent également un plongement de $\N$ dans $\Z$ puis dans $\Q$.

## Constructions abstraites

Finalement, il est possible de proposer des quotients correspondants à des situations-type. Ce sont ces constructions qui motivent d'ailleurs l'introduction de certaines notions nécessaires pour préserver les propriétés de l'ensemble initiale dans l'ensemble quotient. Parmi les plus célèbres :

* les sous-groupes distingués pour que $G/H$ soit bien un groupe avec la multiplication induite par celle de $G$
* les idéaux pour que $A/I$ soit un anneau
* les idéaux maximaux pour que $A/M$ soit un corps

### Quotient par une structure

Il faut tout d'abord commencer par donner un sens à l'écriture $A/B$ qui n'a pour l'instant été définie que sous la forme $A/{\sim}$. La raison d'être de cette notation est essentiellement que $\sim$ est systématiquement de la même forme et ne dépend en fait que de $B$ :

#### Définition : Quotient par un sous-groupe

Si $H\subseteq G$ sont des groupes, on définit $G/H$ comme la partition résultant de la relation d'équivalence :
$$x\sim y\iff x^{-1}y\in H$$

##### Démonstration

Il s'agit de montrer que $\sim$ est bien une relation d'équivalence. C'est bien le cas :

* Réflexivité : $x\sim x\iff x^{-1}x=1\in H$ car $H$ est unifère
* Symétrie : $x^{-1}y\in H\iff\left(x^{-1}y\right)^{-1}=y^{-1}x\in H$ car $H$ est stable par inverse.
* Transitivité : si $x^{-1}y\in H$ et $y^{-1}z\in H$ alors $x^{-1}yy^{-1}z=x^{-1}z\in H$ car la loi de $H$ est interne et associative.

\
On souhaite maintenant préserver la structure (groupe ou anneau) *a minima* en munissant l'ensemble quotient d'une loi naturelle. Du point de vue des notations, la loi naturelle est $\overline{xy}=\overline x\ \overline y$ est c'est en effet la définition que nous allons prendre. Pour cela, nous allons tout d'abord décrire $\overline x$ et donner une condition nécessaire et suffisante pour que la loi soit bien définie.

#### Description des classes d'équivalence

$$\overline x=xH=\{xh\}_{h\in H}$$

##### Démonstration

$$\begin{aligned}
y\in\overline x&\iff y\sim x\\
&\iff x^{-1}y\in H\\
&\iff\exists h\in H,\quad x^{-1}y=h\iff y=xh\\
&\iff y\in xH
\end{aligned}$$

#### Condition nécessaire et suffisante pour que $G/H$ soit un groupe

$$\begin{aligned}
G/H\text{ groupe}&\iff H\text{ distingué}\\
&\iff\forall g\in G,\quad gHg^{-1}=H\\
&\iff\forall g\in G,\quad gH=Hg
\end{aligned}$$

##### Démonstration

On souhaite que la multiplication naturelle sur $G/H$ soit bien définie. En d'autres termes, cela signifie que $\overline{xy}$ ne dépend que des classes de $x$ et $y$ et non des représentants $x$ et $y$. Écrivons tout d'abord la définition de la multiplication :
$$\begin{aligned}
\overline{xy}&=\overline x\ \overline y\\
\iff xyH&=xHyH\\
\iff yH&= HyH
\end{aligned}$$

Il s'agit donc de montrer que $yh_0=h_1yh_2$ pour tout $h\in H$ soit encore $h_0h_2^{-1}=y^{-1}h_1y$. Quitte à changer de notation, cela s'écrit :
$$h=y^{-1}\tilde hy$$

C'est précisément la définition d'un sous-groupe distingué.

Remarquons au passage que cette propriété est triviale dans un groupe commutatif !

### Idéal d'un anneau

On souhaite maintenant construire un anneau par quotient : $A/I$. On a vu qu'il était nécessaire que $I$ soit un sous-groupe distingué pour $+$ ce qui est acquis car cette loi est commutative par hypothèse.

On veut en revanche définir une multiplication. Pour cela, il faut à nouveau que la multiplication naturelle de classes soit indépendante du choix des représentants. D'après le paragraphe précédent, il faut donc que $I$ soit également "distingué" pour $\times$. Or la définition telle quelle fait intervenir des inverses d'éléments qui ne sont *a priori* pas définis dans un anneau. En utilisant la seconde définition, on voit qu'il faut en fait que $I$ soit globalement commutatif, c'est-à-dire $aI=Ia$ pour tout $a\in A$.

<!-- à vérifier -->

Pour s'approcher du cadre de l'arithmétique, on impose en fait la condition plus forte $aI=Ia=I$ : cette définition permet entre autres de simplifier les preuves et de donner une condition intrinsèque pour qu'un ensemble soit un idéal.

#### Définition : Idéal

Si $A$ est un anneau, $I$ est un idéal lorsque c'est un sous-groupe additif de $A$ et est stable par produit par tout élément de $A$.

\
On souhaite maintenant que $A/M$ soit un corps, c'est-à-dire que tout élément admette un inverse pour $\times$.

#### Définition : Idéal maximal

On dit que $M$ est un idéal maximal lorsque le seul idéal contenant $M$ strictement est $A$ (en particulier $M\neq A$).

#### Théorème

$A/M$ est un corps $ssi$ $M$ est maximal.

##### Démonstration

Supposons que $M$ est maximal et soit $\overline a\in A/M\backslash\{\overline 0\}$. On considère $\langle a,M\rangle$ l'idéal engendré par $M\cup\{a\}$ : c'est un idéal contenant strictement $M$ (car il contient $a\notin M$ car $\overline a\neq\overline0$) dont il vaut $A$ et contient en particulier $1$ qui s'écrit sous la forme $ka+m$ où $m\in M$. Modulo $M$, cela donne $\overline k\overline a=\overline1$ donc $\overline k=\overline a^{-1}$ (on ici identifié $k\in\Z$ à $k1\in\Z1$)

Réciproquement, si $A/M$ est un corps, on considère $I$ un idéal contenant strictement $M$ : il existe donc $a\in I\backslash M$ et par hypothèse $\overline a\neq\overline0$ donc $\overline a$ admet un inverse dans $A/M$ qu'on note $\overline b$. Ceci s'écrit exactement $\overline a\overline b=\overline1$ et donc il existe $m\in M$ tel que $ab+m=1$. Or $ab\in I$ et donc $ab+m=1\in I$. Par suite, pour tout $x\in A$, $1x=x\in I$ et donc $I=A$.
