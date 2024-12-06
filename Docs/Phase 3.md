# Post Mortem

## Gestion de projet

- Comment s'est déroulée la planification initiale du projet ?
```
La planification initiale du projet s'est déroulée de manière structurée et efficace. Dès le départ, nous avions des objectifs clairs et bien définis :

- Sécurisation complète de l'application
- Amélioration de la fonctionnalité globale
- Correction des bugs et vulnérabilités existants
- Mise en place d'une suite de tests complète
  - Tests unitaires avec Jest
  - Tests end-to-end avec Cypress
  - Tests fonctionnels avec Jest
  
- Implémentation d'un pipeline CI/CD avec GitHub Actions
  - Vérification automatique du code à chaque PR
  - Exécution des tests


Cette clarté dans les objectifs nous a permis d'établir une feuille de route précise et de prioriser les tâches essentielles. La phase de planification a inclus une analyse approfondie des besoins en sécurité et des fonctionnalités à améliorer, ce qui a grandement facilité l'exécution du projet par la suite.
```

- Les délais ont-ils été respectés ? Pourquoi/Pourquoi pas ?

```
Les délais fixés pour ce projet ont été respectés avec succès. En tant qu'équipe de deux personnes, plusieurs facteurs clés ont contribué à cette réussite :

- Une coordination efficace et une répartition claire des tâches
- Des points de synchronisation réguliers
- Une bonne gestion de notre emploi du temps

Notre petite taille d'équipe a facilité la communication et les prises de décision rapides, nous permettant d'atteindre nos objectifs dans les temps malgré nos obligations académiques.
```

- La répartition des tâches était-elle efficace ?
```
La répartition des tâches a été efficace, nous avons su nous partager les tâches en fonction de nos compétences et de nos disponibilités. Plus précisément :

- Répartition des tâches de sécurisation entre les deux membres de l'équipe
- Attribution des tâches de développement selon nos points forts respectifs
- Flexibilité dans la répartition pour s'adapter aux contraintes de temps
- Support mutuel sur les tâches complexes nécessitant une collaboration
- Revue croisée du code pour assurer la qualité
```

- Quels outils de gestion de projet ont été utilisés ? Étaient-ils adaptés ?
```
Nous avons utilisé GitHub pour la gestion de projet, il s'est avéré adapté à nos besoins. GitHub nous a permis de suivre l'avancement du projet, de partager du code facilement et de gérer les tâches grâce à des issues et des pull requests. En parallèle, nous avons utilisé Discord pour la communication orale et le partage d'écran, ce qui a grandement facilité notre collaboration à distance.
```

## Aspects techniques

- Quels ont été les principaux défis techniques rencontrés ?
```
Les principaux défis techniques rencontrés ont été :

- Mise en place d'une suite de tests complète
- Implémentation d'un pipeline CI/CD
```

- Les choix technologiques étaient-ils appropriés ?
```
Les choix technologiques ont été appropriés, nous avons su nous adapter aux technologies demandées et nous sommes satisfaits de nos choix.
```

- La qualité du code est-elle satisfaisante ?
```
La qualité du code est satisfaisante, nous avons su nous organiser pour écrire un code propre et maintenable.
```

- Que pourrait-on améliorer dans l'architecture du projet ?

```
L'architecture du projet pourrait être améliorée sur plusieurs aspects :

- Ajout d'un linter pour maintenir une cohérence dans le style de code et détecter les problèmes potentiels avant le déploiement
- Exécution de tests end-to-end (e2e) lors des pull requests pour valider le bon fonctionnement de l'application dans son ensemble
- Renforcement de la validation automatique du code avec des hooks pre-commit
```

## Collaboration et communication

- Comment s'est déroulée la communication au sein de l'équipe ?
```
La communication au sein de l'équipe s'est déroulée de manière efficace, nous avons su nous comprendre et nous supporter mutuellement.
```

- Le processus de revue de code était-il efficace ?
```
Le processus de revue de code était efficace, nous avons su nous respecter et nous comprendre.
```

- Y a-t-il eu des conflits ? Comment ont-ils été résolus ?
```
Il n'y a eu aucun conflit, nous avons su nous comprendre et appréhender nos points de vue divergent.
```

## Apprentissages

- Quelles sont les principales leçons apprises ?
```
- La gestion de projet
- La gestion de code
- La gestion de la sécurité
- La gestion de la documentation
- La gestion des tests unitaires et d'intégration
- L'importance de la couverture de tests pour la qualité du code
- L'automatisation des tests dans le pipeline CI/CD
- L'importance de la normalisation des branches et des commits pour maintenir un historique Git propre et compréhensible
- L'utilisation de conventions de nommage cohérentes (feat/, fix/, docs/, etc.) pour les branches
- La rédaction de messages de commit clairs et descriptifs
- La mise en place de workflows GitHub Actions pour automatiser les vérifications
```

- Quelles compétences ont été acquises ou renforcées ?
```
- La gestion de la sécurité
- La gestion de la documentation
- La gestion des tests unitaires et d'intégration
- L'utilisation de GitHub pour la gestion de projet
- La création de conventions de commit pour maintenir un historique clair
- La mise en place d'un pipeline CI/CD
```

- Qu'est-ce qui aurait pu être fait différemment ?

```
Nous n'avons pas identifié d'éléments majeurs qui auraient pu être faits différemment. Le projet s'est déroulé de manière fluide et efficace grâce à une bonne organisation et communication au sein de l'équipe.
```

## Points positifs et négatifs

- Quels ont été les plus grands succès du projet ?

```
- La mise en place d'une documentation complète et structurée
- L'établissement de normes de développement claires et cohérentes
- L'automatisation réussie des tests et des vérifications via GitHub Actions
- La normalisation des processus de développement par des conventions (nommage des branches, messages de commit, etc.)
- L'amélioration significative de la qualité du code grâce aux tests automatisés
- La création d'un environnement de développement plus efficace et maintenable
- La mise en place d'un pipeline CI/CD fonctionnel
- L'adoption réussie des bonnes pratiques de développement par toute l'équipe
```
- Quels ont été les principaux obstacles ?
```
Nous n'avons pas rencontré d'obstacles majeurs durant ce projet. L'équipe a su travailler efficacement et surmonter les petits défis techniques qui se sont présentés.
```

- Quelles sont les opportunités d'amélioration pour les projets futurs ?

```
Nous n'avons pas identifié d'opportunités d'amélioration majeures pour les projets futurs. Le projet s'est déroulé de manière fluide et efficace grâce à une bonne organisation et communication au sein de l'équipe.
```

# Technical Doc

Vous pouvez trouver la documentation technique dans le fichier suivant :

https://github.com/tunsay/dumb_task_manager/blob/main/docs/Phase_3_doc_technique_lisez_moi.md