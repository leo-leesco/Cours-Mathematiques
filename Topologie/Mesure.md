# Théorie de la mesure et intégration de Lebesgue

<!--toc:start-->

- [Théorie de la mesure et intégration de Lebesgue](#théorie-de-la-mesure-et-intégration-de-lebesgue)
  - [Mesure](#mesure)
    - [Définition](#définition)
  - [On dit que $\mu$ est une mesure lorsque : -](#on-dit-que-mu-est-une-mesure-lorsque)
  <!--toc:end-->

Les mathématiques regorgent de paradoxes fascinants, et bien souvent ceux-ci trouvent leur origine dans le concept d'infini : les résultats sont paradoxaux parce qu'ils défient notre compréhension _finie_ du monde.

Le sujet qui va nous intéresser ici est la notion de mesure. Grâce à cette notion, différentes branches des mathématiques s'ouvrent soudainement, les plus marquantes étant les probabilités et la théorie de l'intégration. De manière surprenante peut-être, on ne s'attend pas à avoir besoin d'une théorie différente de celle de Riemann, qui est raisonnablement bien fondée et aisément compréhensible. Pourtant, de nombreuses intégrales sont incalculables avec sa méthode alors que l'intuition nous suggère le contraire.

## Mesure

### Définition

Soit $A$ un ensemble. On dit que $\mu:A\to\overline\R_+$ est une mesure lorsque :

- $\mu(\empty)=0$
- $\sigma$-additivité : si $(E_n)_{n\in\N}$ sont (une famille de parties de $A$ dénombrable) deux à deux disjoints, alors :
  $$\mu\left(\bigsqcup_{n\in\N}E_n\right)=\sum_{n\in\N}\mu(E_n)$$

Notons plusieurs choses :

- rien n'impose que $\mu$ soit défini sur l'ensemble des parties de $A$. Nous verrons certains "paradoxes" qui justifient que $\mu$ est bien une fonction, et non une application
- la mesure d'un ensemble est positive, mais pas nécessairement finie. C'est en fait tout à fait ce à quoi on s'attend en général : quelle est la taille de $[1,+\infty[$ ? L'intégration suggère bien une taille infinie, là où $[1,2]$ est de taille finie (égale à $1$).
