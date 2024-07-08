# Durabilité des tests

## Introduction

* *Etant donnée* une application mobile
* *En tant qu'* utilisateur
* *Lorsque* je l'utilise
* *Alors* je ne sais pas si :
  * elle est native ou web
  * les données sont en local ou à distance
  * les services sont exécutés par le mobile, un serveur monolithique, des microservices...

Il en découle que tout test manipulant l'application à la manière d'un utilisateur
est indépendant de comment elle fonctionne.

L'architecture pourrait être fondamentalement modifiée sans avoir à le modifier.

Un tel test est *durable*.

## Définition

La *durabilité* d'un test mesure sa capacité à perdurer malgré les refactorings
et les nouvelles fonctionnalités.

La *durabilité* est optimale lorsque seule une modification de la fonctionnalité
testée provoque une modification de ses tests.

En ce sens, un test durable doit respecter SRP (Single Responsability Principle).

Dans les faits, cet optimum est rarement atteint.

La *durabilité* peut être améliorée en jouant sur 2 axes :
* limiter les raisons de modifier un test
* faciliter ses modifications

## Avantages

Avoir des tests durables offre de nombreux avantages :
dévaluation de la dette technique, meilleure vélocité, facilitation du test first.

### Dévaluation de la dette technique

Les tests non durables sont un frein au refactoring.

Ils échouent ou ne compilent plus dès que l'implémentation est modifiée.

La manière la plus souvent adoptée est alors de les effacer, d'effectuer
le refactoring puis d'écrire de nouveaux tests.

Cette ré-écriture est non seulement une perte de temps mais aussi une
perte de qualité. Le soin apporté aux tests après un refactoring n'est
pas le même que lors de la première implémentation. Non seulement le
développeur n'a plus les connaissances qu'il avait mais en plus le temps
alloué est réduit.

Un chef de projet n'acceptera pas d'investir plus que le strict minimum
pour un refactoring qui n'apporte pas un gain immédiat.

Au contraire, les tests durables accélèrent le refactoring.

Non seulement il n'y a pas besoin de les ré-écrire mais ils garantissent
la non régression. 
La pratique du RAT (Refactoring Aided by Tests) devient possible:

Faire un petit refactoring, Exécuter la non régression et Recommencer.