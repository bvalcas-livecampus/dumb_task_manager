# 1. Manual Tests

## 1.1 UI Tests

| Elements testés      | Observations | Bug | Piste d'améliorations |
| -------------------- | ------------ | --- | --------------------- |
| home page (/) (non connecté)        | couleurs très flashy | [ ] | couleurs plus armonieuses |
| home page (/) (non connecté)        | button pour accéder à la page login | [ ] | redirection automatique |
| home page (/) (connecté)            | button pour accéder à la page tasks | [ ] | redirection automatique |
| login page (/login)  | couleurs très flashy | [ ] | couleurs plus armonieuses |
| login page (/login)  | tentative de connexion **user** `admin` **password** `admin` et attente infinie de l'application | [x] | le serveur back doit envoyer un retour d'erreur au front |
| register page (/register)  | couleurs très flashy | [ ] | couleurs plus armonieuses |
| register page (/register)  | mot de passe non caché par défaut | [x] | ajouter l'attribut qui permet de cacher le mot de passe |
| register page (/register)  | aucun message de confirmation | [ ] | eventuellement ajouter un message de confirmation ou d'erreur pour la création d'un compte |
| tasks page (/tasks)  | couleurs très flashy | [ ] | couleurs plus armonieuses |
| tasks page (/tasks) (connecté)            | button pour accéder à la page tasks | [ ] | redirection automatique |
| tasks page (/tasks) (non connecté)        | si nous essayons d'ajouter une tâche, nous sommes redirigés vers une page sans style qui affiche "Unauthorized" | [x] | le serveur back doit envoyer un retour d'erreur au front |
| tasks page (/tasks) (connecté userId = 5)            | L'ajout et la suppression de tâches fonctionne correctement | [ ] | Petit message de confirmation pourrait être sympathique |
| tasks page (/tasks) (connecté userId = 5)            | La selection de la checkbox qui permet d'indiquer que la tâche est terminée ne change rien visuellement | [ ] | La tâche doit avoir une information visuelle ou du texte qui indique que la tâche est terminée |
| dashboard admin (/admin) | Le panneau d'administration permet de lister les utilisateurs et de les supprimer facilement | [ ] | Amélioration du design |
| dashboard admin (/admin) | La suppression d'un utilisateur redirige vers une page d'erreur sans style | [x] | Amélioration du design | Gestion correcte des erreurs

## 1.2 Pen Tests

| Type d'attaque       | Emplacement | Description | Brèche de sécurité | Criticité | Piste d'amélioration |
| -------------------- | ----------- | ------------ | ------------ | ------------ | --------------------- |
| Usurpation d'identité | /tasks?userId=1 | Le changement de la valeur du userId dans le lien permet de se faire passer pour un autre utilisateur | [x] | Critique | Implémenter un système de sessions sécurisé et vérifier l'identité de l'utilisateur à chaque requête |
| Privilège d'accès | /admin | L'accès à la page admin est possible pour n'importe qui | [x] | Critique | Vérifier les droits d'accès à la page admin |
| Possibilité de supprimer tous les utilisateurs | /admin | L'utilisateur peut supprimer tous les utilisateurs | [x] | Critique | Vérifier les droits d'accès à la page admin |
| XSS (Cross-Site Scripting) | /tasks (champ title, description) | L'utilisateur peut injecter du code html dans le titre ou la description d'une tâche | [ ] | Basse | L'injection est correctement gérée |
| XSS (Cross-Site Scripting) | /admin (user.username) | L'utilisateur peut injecter du code html dans le username | [ ] | Basse | L'injection est correctement gérée |
| Brut force | /login | Le mot de passe administrateur est trop simple | [x] | Critique | Vérifier la force du mot de passe administrateur |
| Cryptographique | /login | Les mots de passe sont stockés en clair dans la base de données | [x] | Critique | Utiliser un algorithme de hashage pour stocker les mots de passe |
| Journalisations | all | Pas de journalisations sur toutes les routes | [ ] | Critique | Ajouter la journalisation pour toutes les routes exposées |
| Journalisations | middleware authenticate | le password est affiché en clair dans les logs | [x] | Moyenne | Ne pas logger le password |
| Variable globale | / | Une variable globale est utilisé pour le userId | [x] | Moyenne | Restreindre le scope de la variable |
| Variable globale | /user/register | Une variable globale est utilisé pour le password | [x] | Moyenne | Restreindre le scope de la variable |
| Variable globale | /remove | Une variable globale est utilisé pour taskId et userId | [x] | Moyenne | Restreindre le scope des variables |
| Variable globale | /tasks | Une variable globale est utilisé pour userId | [x] | Moyenne | Restreindre le scope de la variable |
| Exposition de routes non utilisées | PUT /tasks:id | La route PUT /tasks:id n'est pas utilisée | [x] | Moyenne | Supprimer la route |
| Crash de l'application | PUT /tasks:id | La route PUT /tasks:id fait planter l'application | [x] | Critique | Mettre en place des tests fonctionnels |

## 1.3 Usage

### Qualité de l'architecture

Les dossiers sont correctement structurés.

- Routes
- Models
- Config
- Public
- Views

Pistes d'amélioration:

- Ajouter un dossier pour les middlewares
- Ajouter un dossier pour les tests unitaires

### Qualité du code

- Les variables globales sont nombreuses
- La journalisation n'est pas systématique
- Le middleware `authenticate` est déclaré dans **routes/tasks.js**
- Les cas d'erreurs ne sont pas tous gérés
- L'échappement des variables est correctement géré
- Les parties d'API et de front pourraient être séparé

Pistes d'amélioration:

- Déplacer le middleware authenticate dans le dossier middleware
- Ajouter un middleware pour la journalisation sur toutes les routes
- Modifier toutes les variables ~~`var`~~ par `let` ou `const`
- Mettre un linter ou un vérificateur de code qui permet d'alerter en cas de détection de variables globales

### Qualité et couverture des tests

- La couverture des tests est inexistante

Pistes d'amélioration:

- Mettre en place des tests unitaires
- Mettre en place des tests fonctionnels

### Conclusion avec les pistes d'amélioration et de sécurisation

- Améliorer la qualité visuelle de l'application
- Une mise en place d'une politique de hiérarchisation des fichiers est nécessaire
- Une mise en place de politique de journalisation est nécessaire
- Les variables globales sont nombreuses et doivent être limitées
- Les tests sont faibles et doivent être mis en place
- Mise en place d'un système de cookies pour sécuriser l'application
- Les mots de passe sont stockés en clair dans la base de données et doivent être hashés
- Une politique de mot de passe fort est nécessaire
- L'application doit pouvoir tout le temps répondre
- Une gestion des erreurs plus performante est nécessaire


## 1.4 Documentation commune