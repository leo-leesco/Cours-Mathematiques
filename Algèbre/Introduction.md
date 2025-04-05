# Introduction

On pourrait décrire la motivation générale de l'algèbre en une idée : abstraire les structures de la construction proposée pour les objets. En d'autres termes, l'algèbre est fondamentalement complémentaire de la doctrine constructiviste en ce qu'elle produit des résultats forts d'existence sans donner de construction dans la majorité des cas.

Les arguments employés sont élégants et puissants : on a souvent recours à des arguments de cardinalité et de dénombrement par exemple, mais également aux ensembles quotients qui sont omniprésents dans la théorie.

Étonnamment, cette théorie abstraite produit des résultats très intéressants du point de vue de l'arithmétique. Parmi les exemples d'application les plus remarquables, la cryptographie et en particulier l'algorithme RSA ou encore l'emploi des courbes elliptiques reposent justement sur ces résultats forts d'existence dont on ne connaît pas de bonne preuve constructive : affirmer qu'il existe une solution sans l'exhiber est l'une des bases essentielles des preuves sans information (ou _zero-knowledge proof_) qui garantissent la sécurité des échanges informatiques.

\
Ce cours prend le parti de la linéarité, c'est-à-dire d'introduire assez formellement les notions de sorte à en disposer pour que, dès que la pensée est assez mûre, aucune notion n'ait à être introduite _a posteriori_.

Cette approche est ambitieuse car elle est par nature plus abstraite mais elle est aussi plus satisfaisante car elle n'occulte aucun point et ne laisse pas le lecteur laissé à lui-même devant une notion pas encore introduite ou devant un flou théorique qu'on résoudra plus tard. Au besoin, on admettra certains résultats qui seront démontrés plus tard avec le souci de ne pas faire de cercle vicieux logique.

## Plan du cours

1. [Construction de structures](Constructions.md)
	1. [Définitions fondamentales](#structures-étudiées-et-construction-de-la-pensée-algébrique)
	1. [Construction par quotient](Constructions.md#construction-par-quotient)
		1. [Construction de $\Z$ et $\Q$](Constructions.md#construction-concrète-de-et-à-partir-de)
		1. [Constructions abstraites](Constructions.md#constructions-abstraites)
1. [Théorème de <span style='font-variant:small-caps;'>Lagrange</span>](Lagrange.md)
1. [Arithmétique](Arithmétique.md)
	1. $\Z/n\Z$
		1. Propriétés fondamentales
		1. Théorème d'<span style='font-variant:small-caps;'>Euler-Fermat</span>
		1. $\Z/p\Z$
	1. Arithmétique polynomiale
<!-- 1. Questions de caractéristique -->
<!-- 1. Théorie de Galois -->

## Structures étudiées et construction de la pensée algébrique

Le sujet d'étude principal de l'algèbre est celui des structures abstraites, qu'on résume par le tableau suivant :

| Structure | Forme usuelle | Description | Élément neutre
| --------- | ------------- | ----------- | --------------
| Monoïde | $(M,*)$ | $*$  est associative | $e$
| Groupe | $(G,\times)$ | Monoïde inversible | $1$
| Groupe abélien | $(G,+)$ | $+$ est commutative | $0$
| Anneau | $(A,+,\times)$ | $(A,+)$ groupe abélien | $0$
||| $(A,\times)$ monoïde | $1$
||| distributivité de $+$ sur $\times$
| Corps | $(K,+,\times)$ | Anneau où $(K^*,\times)$ groupe abélien | $0$ et $1$
| Espace vectoriel | $(E,+,\cdot)$ | $(E,+)$ groupe abélien | $0$
||| $\lambda\cdot x$ avec $\lambda\in K$ corps et $x\in E$ | $1$
| Algèbre | $(A,+,\cdot,\times)$ | $(A,+,\cdot)$ espace vectoriel
||| $(A,+,\times)$ anneau

L'algèbre traite plus volontiers des structures jusqu'aux anneaux qui sont riches malgré leurs hypothèses faibles. L'étude des corps finis fait également partie du champ d'étude de l'algèbre.

Les trois dernières structures sont usuellement rattachées au domaine de l'analyse ce qui justifie les hypothèses considérablement plus fortes faites sur ces objets : dans la pratique, contrairement à l'algèbre, on considèrera que le corps de base est $\R$ (ou $\C$ quoique cela revienne pratiquement au même du point de vue algébrique).
