# Durabilité des tests

## Définition

Un test durable est un test qui n'a pas besoin
d'être ré-écrit suite à un refactoring.
Il respecte le principe de responsabilité unique
(SRP) dans le sens où il n'a qu'une raison de
changer : un changement de spécification.

## Dette technique

Les tests durables sont essentiels pour conserver
une base de code agile. 

Par définition, ils facilitent les refactorings et
réduisent le coût de la dette technique.

Le développement de nouvelles fonctionnalités est
aussi fluidifié puisqu'il ne devrait pas impacter
les tests existants.

## Tests end to end

Les tests end to end sont durables. 
Comme ils n'intéragissent qu'avec les entrées/sorties
du système, ils ne dépendent pas de l'implémentation.
A l'extrême, un changement d'architecture aussi radical
que migrer d'un monolithe vers des microservices
ne nécessite pas de ré-écriture.

## Tests unitaires

