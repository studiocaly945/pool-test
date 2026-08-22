# Refonte du système de combat — Plan (mission CRITICAL)

## Constat

La demande initiale est :

> « Refonte majeure du système de combat du jeu avec impact sur plusieurs systèmes Unreal existants. »

État réel du dépôt `pool-test` au moment de cette mission : il ne contient que `README.md`.
Il n'existe ni projet Unreal Engine, ni code C++, ni Blueprint, ni système de combat,
ni aucun des « systèmes Unreal existants » mentionnés dans la demande.

Conséquence : il n'y a aucune cible concrète sur laquelle effectuer une refonte réelle.
Ce document ne contient donc pas de code Unreal, pas de C++, pas de Blueprint, pas de
fausse arborescence de projet — cela reviendrait à inventer une architecture qui n'existe pas.

## Informations manquantes avant toute exécution réelle

Avant qu'une vraie mission de refonte du combat puisse être exécutée, il faut préciser :

1. Quel projet Unreal Engine cibler (nom, dépôt, chemin) ?
2. Quel est le système de combat actuel (fichiers/modules concernés) ?
3. Implémentation en C++, en Blueprint, ou les deux ?
4. Quels systèmes annexes sont réellement impactés (IA ennemie, animation, réseau/multijoueur,
   UI de combat, sauvegarde, son) ?
5. Quelle version du moteur Unreal est utilisée ?
6. Quel est l'objectif de gameplay recherché par la refonte (ce qui ne fonctionne pas
   dans le système actuel, ou ce qui doit changer) ?

## Squelette de plan type pour une future vraie refonte

Une fois ces informations connues, une refonte de cette ampleur suivrait ce déroulé :

1. **Audit de l'existant** — lister les classes, Blueprints et systèmes réellement
   présents dans le projet cible, et leurs dépendances mutuelles.
2. **Conception** — définir la nouvelle architecture du combat et son impact précis
   sur chaque système annexe identifié.
3. **Implémentation isolée par module** — modifier un système à la fois, sur des
   branches dédiées, en limitant les changements simultanés.
4. **Intégration progressive** — reconnecter les modules modifiés au reste du jeu
   par étapes vérifiables.
5. **Tests de non-régression** — valider que les systèmes annexes (IA, animation,
   réseau, UI, sauvegarde) continuent de fonctionner après chaque étape.
6. **Plan de retour arrière** — pouvoir revenir à l'état précédent à chaque étape
   en cas de régression détectée.

## Recommandation

Avant de lancer une exécution réelle de cette mission, il est nécessaire de répondre
en mode ASK aux questions listées ci-dessus. Sans cela, toute mission CRITICAL sur ce
sujet restera au stade de planification.
