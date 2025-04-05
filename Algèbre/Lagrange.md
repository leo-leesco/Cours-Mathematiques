# Théorème de <span style="font-variant:small-caps;">Lagrange</span>

Nous allons ici présenter un résultat très intéressant à la fois par son utilité et par les outils qu'il amène à développer : le théorème de <span style="font-variant:small-caps;">Lagrange</span>. Ce sera l'occasion d'illustrer les constructions abstraites par quotient de la partie précédente.

La motivation générale repose sur la recherche du nombre d'itérations pour lequel l'élément étudié donne l'identité. Pour cela, on peut étudier l'ordre de l'élément en question, mais cette approche n'est pas efficace au premier abord : plutôt que de calculer une à une les itérées d'un élément (en temps linéaire), on préfèrera connaître immédiatement l'exposant et appliquer l'algorithme d'exponentiation rapide (en temps logarithmique).

Ceci sera notamment utile pour déterminer l'inverse d'un élément dans $\Z/n\Z$ par exemple. Ensuite, pour déterminer l'ordre exact de l'élément, on pourra calculer les diviseurs (ou les facteurs premiers) de l'exposant en question (qui se trouve être le cardinal du groupe) et calculer toujours par exponentiation rapide l'itérée.

## Définition : Groupe

$(G,\times)$, noté $G$ lorsqu'il n'y a pas ambiguïté, est un groupe lorsque :

* $\times$ est une loi de composition interne associative
* il existe un élément neutre noté $1$
* tout élément possède un inverse pour cette loi

## Définition : Sous-groupe engendré

Si $A\subseteq G$, $\langle A\rangle$, le sous-groupe engendré par $A$, est défini par :
$$\langle A\rangle=\bigcap\limits_{\substack{I\text{ groupe}\\ B\subseteq I}}I$$

C'est également l'ensemble des multiplications possibles d'éléments de $A$ et de $A^{-1}$ (les inverses des éléments de $A$).

## Définition : Ordre

On définit l'ordre de $a$, qu'on notera ici $\omega(a)$, par :

$$\begin{aligned}
\omega(a)&=\#\langle a\rangle\\
&=\#\{a^k\}_{k\in\Z}\in\overline\N=\N\cup\{+\infty\}
\end{aligned}$$

## Proposition : Description d'un sous-groupe monogène

Si $\omega(a)<+\infty$, alors $\langle a\rangle=\{a^k\}_{0\leq k<\omega(a)}$. En particulier, $a^{\omega(a)}=1$.

Sinon, $a^k\neq a^j$ pour tout $k\neq j$ et $\langle a\rangle=\{a^k\}_{k\in\Z}$.

### Démonstration

Commençons par le cas $\omega(a)=+\infty$. S'il existait $k<j$ tel que $a^k=a^j$, alors $a^{j-k}=1$ et alors $(a^n)_{n\in\Z}$ est $j-k$ périodique donc à support fini, ce qui contredit $\omega(a)=+\infty$. Ceci donne le second point.

Supposons maintenant $\omega(a)<+\infty$ : on considère $1,a,\dots,a^{\omega(a)-1}$. Supposons que parmi ces éléments, deux soient égaux, par exemple $a^k=a^j$ avec $0\leq k<j<\omega(a)$. Alors $a^{j-k}=1$ et de nouveau cela entraîne que $(a^n)_{n\in\N}$ est $j-k<\omega(a)$ périodique et cela contredit $\omega(a)=\#\langle a\rangle$. Ces éléments sont donc distincts deux à deux et puisqu'ils sont au nombre de $\omega(a)$, on a décrit $\langle a\rangle$.

Finalement, on sait que $a^{\omega(a)}=a^k$ avec $0\leq k<\omega(a)$. Donc $a^{\omega(a)-k}=1$ et $0<\omega(a)-k\leq\omega(a)$ : ceci n'est possible que pour $\omega(a)-k=\omega(a)$ par la description des élements de $\langle a\rangle$ donc $k=0$ c'est-à-dire $a^{\omega(a)}=1$.

\
Nous avons maintenant à notre disposition tous les outils pour énoncer et démontrer le théorème de <span style='font-variant:small-caps;'>Lagrange</span>. Notons que ce théorème possède trois formes, la première étant extrêmement précise et généralisable, la dernière plus simple et très utile dans le cadre de l'arithmétique.

## Théorème de <span style='font-variant:small-caps;'>Lagrange</span>

Si $H\subseteq G$ sont des groupes, alors $\#G=\#(G/H)\#H$ (cette formule reste vraie dans le cas où ces groupes sont infinis).

En particulier $\#H$ divise $\#G$.

Finalement, si $\#G<+\infty$, alors :
$$\forall x\in G,\quad x^{\#G}=1$$

### Démonstration

On va quotienter $G$ par $H$ ($H$ n'est pas nécessairement distingué). Étant donné que ce quotient est sous-tendu par une relation d'équivalence, la partition induite permet d'écrire :
$$G=\bigsqcup_{\overline x\in G/H}\overline x=\bigsqcup_{\overline x\in G/H}xH$$

En passant aux cardinaux, $\#G=\sum\limits_{\overline x\in G/H}\#xH$. Or $\begin{array}{rcl}H&\longrightarrow&xH\\h&\longmapsto&xh\end{array}$ est une bijection donc $\#xH=\#H$ et on conclut donc par $\#G=\sum\limits_{\overline x\in G/H}\#H=\#(G/H)\#H$.

Pour le troisième point, il suffit de prendre $H=\langle a\rangle$ et de remarquer que $a^{\#G}=1^{\#(G/H)}=1$.
