# Arithmétique

## Cadre général

### Définition : Anneau

$A$ est un anneau lorsque $(A,+)$ est un groupe commutatif de neutre noté $0$ et $(A,\times)$ est un monoïde de neutre noté $1$.

Il faut retenir qu'on a :

* $0$ et $1$ dans $A$
* $a+b\in A$
* $-a\in A$
* $ab\in A$

Les anneaux sont le cadre naturel de l'arithmétique : ils sont en fait une structure qui est très similaire à celle de $\Z$ et on va chercher à étendre les notions de divisibilité.

#### Exemple : $\Z$ et $n\Z$

* $(\Z,+,\times)$ est l'anneau de base dont on s'inspirera
* $n\Z$ (pour $n\in\N$) est presque un anneau :
  * $0\in n\Z$
  * $0\in n\Z$
  * $a-b\in n\Z$ et $ab\in n\Z$ (en fait $n^2\Z\subseteq n\Z$)
  * &#x26a0;&#xfe0f; mais on n'a pas $1\in n\Z$ (dès que $n\neq1$)
  
  En fait $n\Z$ est un idéal et on construira par quotient les anneaux modulaires $\Z/n\Z$ grâce aux bonnes propriétés des idéaux !

### Définition : Idéal

$I$ est un idéal à gauche (respectivement à droite) de $A$ lorsque :

* $I$ est un sous-groupe (additif) de $A$
* $\forall a\in A,\quad\forall x\in I,\quad ax\in I$ (respectivement $xa\in I$)

On parle d'idéal sans plus de précision lorsqu'il s'agit d'un idéal à droite et à gauche.

Pour revenir à $n\Z$, on a vu que $n\Z$ est bien un sous-groupe additif et il suffit donc de vérifier le second point : dire que $x\in n\Z$, c'est dire que $n\mid x$ et donc pour tout $a\in\Z$, $n\mid ax$ i.e. $ax\in n\Z$.

### Définition : Idéal engendré par une partie

Si $B\subseteq A$ est un ensemble quelconque, l'idéal engendré par $B$, noté $\langle B\rangle$, possède deux définitions équivalentes :

* $\langle B\rangle=\bigcap\limits_{\substack{I\text{ idéal}\\ B\subseteq I}}I$
* l'ensemble des combinaisons linéaires (finies) d'éléments de $B$ : $\langle B\rangle=\left\{\sum\limits_{k=1}^na_kx_k\alpha_k,\ n\in\N,\ ((a_k,\alpha_k),x_k)_{1\leq k\leq n}\in(A^2\times B)^n\right\}$

### Motivation pour introduire une telle structure

Petit point d'histoire : c'est <span style="font-variant:small-caps;">Abel</span> qui a introduit la notion d'idéal en étudiant les problèmes de commutativité. Il pensait en particulier que les idéaux permettaient une description complète des groupes (ce qui n'était pas en réalité le cas, il fallut introduire préalablement la notion de groupe simple).

#### Approche ensembliste de la divisibilité

On remarque d'emblée que la notion de divisibilité ($a\mid b\iff b=aq\in aA$) rejoint précisément celle d'un idéal particulier, l'idéal engendré par un unique élément : $\langle a\rangle=aA$.

Notons au passage que cela permet de définir (dans les anneaux principaux) les notions de PGCD et PPCM par des biais ensemblistes :

* $(a\vee b)A=aA\cap bA$
* $(a\wedge b)A=aA+bA$

Naturellement, cette construction permet très aisément de définir le PGCD et le PPCM pour des familles finies et même quelconques d'éléments !

Le cadre pour ces définitions est celui des anneaux principaux, qui résume le fait qu'on peut bien écrire les idéaux $aA\cap bA$ et $aA+bA$ sous la forme $xA$.

### Définition : Anneau principal

On dit que $A$ est principal lorsque tous ses idéaux sont principaux, c'est-à-dire monogène ou encore engendrés par un seul élément.

Ils sont donc de la forme $I=\langle a\rangle=aA$.

### Théorème : $\Z$ est principal

#### Démonstration

Soit $I$ un idéal de $\Z$. Si $I=\{0\}$, alors $I=0A$ est bien principal.

Sinon, en remarquant que $I$ est nécessairement symétrique par rapport à $0$ (car c'est un groupe additif), on pose $n=\min I\cap\N^*$. En écrivant la division euclidienne de tout $k\in I$ par $n$, $k=qn+a$ avec $0\leq a<n$. Or $a=k-qn\in I$ : par minimalité de $n$, $a=0$ et on a bien $k\in n\Z$.

## $\Z/n\Z$

On définit par quotient $\Z/n\Z$ : il s'agit de l'ensemble de l'ensemble des restes des entiers par la division euclidienne par $n$.

### Notation : Congruence

La relation de congruence modulo $n$, qui est la relation d'équivalence sur $\Z$ modulo $n\Z$, est notée par :
$$\overline a=\overline b\iff n\mid a-b\iff a\equiv b\;[n]$$

### Définition : Groupe des inversibles

Si $A$ est un anneau, on note $A^\times=\{a\in A,\ \exists b\in A,\ ab=1\}$ l'ensemble des inversibles de $A$.

C'est un groupe.

#### Démonstration

* $A^\times\neq\emptyset$ car $1\in A$ est inversible.
* si $(a,b)\in A^\times$, alors $ab$ est d'inverse $b^{-1}a^{-1}$.
* si $a\in A^\times$, alors $a^{-1}$ est l'inverse de $a$.

### Théorème : description des inversibles de $\Z/n\Z$

$$\overline a\in(\Z/n\Z)^\times\iff a\wedge n=1$$

#### Démonstration

$$\begin{aligned}
&&\overline a&\in(\Z/n\Z)^\times\\
\iff&&\overline b&=\overline a^{-1}\\
\\
\iff&&\overline a\overline b=\overline{ab}&=\overline 1\\
\\
\iff&&\exists k\in\Z,\quad ab+nk&=1\\
\\
\underset{\text{Bézout}}\iff&& a\wedge n&=1
\end{aligned}$$

### Théorème : Condition nécessaire et suffisante pour que $\Z/n\Z$ soit un corps

$$\begin{aligned}
\Z/n\Z\text{ corps}&\iff n\text{ premier}\\
&\iff\Z/n\Z\text{ intègre}
\end{aligned}$$

### Définition : Indicatrice d'<span style='font-variant:small-caps;'>Euler</span>

### Théorème d'<span style='font-variant:small-caps;'>Euler-Fermat</span>

### Théorème chinois
