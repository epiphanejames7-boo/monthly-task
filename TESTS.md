# Vérifications effectuées

## Générateur de planning
Le module `src/planner.ts` a été compilé séparément avec TypeScript strict puis exécuté sur un scénario comportant deux objectifs de priorités différentes.

Vérifications réussies :
- des séances sont générées pour les objectifs fournis ;
- aucun jour non sélectionné n'est utilisé ;
- aucune séance ne dépasse la durée maximale configurée ;
- la charge journalière ne dépasse pas la capacité quotidienne ;
- la somme des durées planifiées correspond à la charge estimée.

## Limite de validation
Le build complet Vite/React n'a pas pu être exécuté dans l'environnement de travail, car les dépendances npm ne sont pas disponibles et l'accès au registre npm a expiré. Le build complet devra être vérifié après `npm install` dans l'environnement de développement.
