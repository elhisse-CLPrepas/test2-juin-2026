# Guide pédagogique avancé - Comprendre et organiser le travail collaboratif avec GitHub et VS Code

## 1. Rôle du document

Ce document sert de guide source pédagogique pour apprendre le travail collectif autour d'un dossier partagé.

Il explique comment plusieurs membres d'un groupe peuvent travailler chacun à leur façon, tout en gardant un espace commun organisé, vérifiable et synchronisé.

Le guide s'appuie sur les principes de Git, GitHub et Visual Studio Code.

## 2. Résumé simple

Pour lire ou télécharger un dépôt GitHub public, un compte GitHub n'est pas obligatoire.

Pour modifier un dépôt, envoyer des fichiers, créer une branche, faire un commit, ouvrir une Pull Request ou participer à une revue, un compte GitHub est obligatoire.

L'email peut servir d'identifiant pédagogique interne, mais il ne remplace pas le compte GitHub.

## 3. Les trois outils à comprendre

### Git

Git est l'outil qui enregistre l'historique du travail.

Il permet de savoir :

- qui a modifié quoi ;
- quand une modification a été faite ;
- pourquoi une modification a été enregistrée ;
- comment revenir à une version précédente ;
- comment travailler sur plusieurs versions grâce aux branches.

### GitHub

GitHub est la plateforme en ligne qui héberge le dépôt.

Il permet de :

- partager le projet avec un groupe ;
- gérer les accès ;
- créer des branches distantes ;
- ouvrir des Pull Requests ;
- discuter les changements ;
- relire et valider avant intégration ;
- conserver l'historique commun.

### VS Code

Visual Studio Code est l'éditeur utilisé pour travailler localement.

Il permet de :

- ouvrir le dossier du projet ;
- voir les fichiers modifiés ;
- préparer les changements ;
- faire des commits ;
- synchroniser avec GitHub ;
- changer de branche ;
- utiliser l'extension GitHub Pull Requests and Issues pour créer et relire des Pull Requests.

## 4. Compte GitHub, email et identité

### Le compte GitHub

Le compte GitHub sert à gérer l'accès réel au dépôt.

Chaque personne qui doit contribuer doit avoir son propre compte GitHub.

Il ne faut pas partager un seul compte entre plusieurs membres, car cela empêche de savoir clairement qui a fait quelle contribution.

### L'email

L'email peut être utilisé comme ID pédagogique.

Exemple :

```txt
Email-ID : amina.exemple@gmail.com
Compte GitHub : amina-dev
Branche : travail-amina
Rôle : contributrice
```

L'email peut apparaître dans une fiche candidat, un tableau de suivi ou un dossier participant.

### Configuration locale de Git

Chaque membre doit configurer son identité Git sur son ordinateur :

```bash
git config --global user.name "Nom Prenom"
git config --global user.email "nom.prenom@example.com"
```

Cette configuration aide à associer les commits à une personne.

## 5. Deux modèles de collaboration

GitHub distingue principalement deux manières de collaborer.

### Modèle 1 : dépôt partagé

Tous les membres autorisés travaillent dans le même dépôt.

Ce modèle est adapté à un groupe fermé, comme une classe, une équipe ou un challenge encadré.

Fonctionnement recommandé :

1. Le responsable garde la branche `main` comme version officielle.
2. Chaque membre crée sa propre branche.
3. Chaque membre pousse son travail sur GitHub.
4. Chaque membre ouvre une Pull Request.
5. Le responsable ou les pairs relisent.
6. Les changements validés sont fusionnés dans `main`.

### Modèle 2 : fork et Pull Request

Chaque membre copie le dépôt dans son propre compte GitHub avec un fork.

Ce modèle est adapté à un groupe ouvert, avec des contributeurs externes ou des personnes qui ne doivent pas avoir accès direct au dépôt principal.

Fonctionnement recommandé :

1. Le membre crée un fork.
2. Il travaille dans son fork.
3. Il pousse ses changements dans son fork.
4. Il ouvre une Pull Request vers le dépôt principal.
5. Le responsable accepte ou demande des corrections.

## 6. Méthode recommandée pour un challenge pédagogique

Pour ton cas, le modèle le plus simple est le dépôt partagé avec une branche par membre.

Exemple :

```txt
main
travail-amina
travail-karim
travail-sara
```

La branche `main` représente la version officielle.

Les branches `travail-*` représentent les espaces de contribution.

Chaque membre peut travailler à sa façon dans sa branche, mais l'intégration finale se fait proprement par Pull Request.

## 7. Organisation possible des dossiers

Une organisation claire aide à éviter les conflits.

Exemple :

```txt
participants/
  amina-exemple-gmail-com/
    fiche-candidat.md
    livrable-01.md
    preuves/
  karim-exemple-gmail-com/
    fiche-candidat.md
    livrable-01.md
    preuves/
```

Conseil : éviter les caractères spéciaux dans les noms de dossiers participants.

Exemple recommandé :

```txt
amina-exemple-gmail-com
```

Exemple à éviter :

```txt
amina.exemple@gmail.com
```

Cela rend les chemins plus simples à utiliser dans Git, VS Code et les terminaux.

## 8. Cycle de travail avec Git en ligne de commande

### Première installation

Chaque membre clone le dépôt :

```bash
git clone https://github.com/elhisse-CLPrepas/test2-juin-2026.git
cd test2-juin-2026
```

### Créer sa branche

```bash
git checkout -b travail-nom-prenom
```

### Travailler et enregistrer

```bash
git status
git add .
git commit -m "Ajouter contribution de Nom Prenom"
```

### Envoyer vers GitHub

```bash
git push -u origin travail-nom-prenom
```

### Demander l'intégration

Le membre ouvre ensuite une Pull Request depuis GitHub.

## 9. Cycle de travail avec VS Code

VS Code permet de faire la plupart des opérations Git sans quitter l'éditeur.

### Ouvrir le dépôt

1. Ouvrir VS Code.
2. Ouvrir le dossier du projet.
3. Vérifier que l'icône Source Control apparaît dans la barre latérale.

VS Code détecte automatiquement un dossier qui contient un dépôt Git.

### Voir les modifications

Dans Source Control, VS Code affiche les fichiers modifiés.

Le membre peut relire les différences avant de faire un commit.

### Préparer les fichiers

Le membre peut cliquer sur `+` à côté d'un fichier pour le préparer.

Cela correspond à :

```bash
git add fichier.md
```

### Faire un commit

Dans la zone de message, écrire un message clair :

```txt
Ajouter fiche candidat Amina
```

Puis cliquer sur Commit.

### Synchroniser

Le bouton Sync permet de pousser et récupérer les changements.

Pour un apprentissage progressif, il est utile de comprendre que Sync combine souvent deux actions :

- récupérer les changements distants ;
- envoyer les commits locaux.

### Travailler avec GitHub dans VS Code

Avec l'extension GitHub Pull Requests and Issues, VS Code peut aussi servir à :

- se connecter à GitHub ;
- voir les Pull Requests ;
- créer une Pull Request ;
- demander une revue ;
- commenter une Pull Request ;
- relire les changements ;
- fusionner quand le travail est prêt.

## 10. Pull Request : rôle pédagogique

Une Pull Request n'est pas seulement une demande technique.

C'est un espace de discussion et de validation.

Elle permet de :

- expliquer ce qui a été fait ;
- montrer les différences entre deux branches ;
- demander une relecture ;
- recevoir des commentaires ;
- corriger avant validation ;
- garder une trace de la décision.

Modèle simple de description :

```md
## Objectif
Décrire le but de la contribution.

## Changements réalisés
- Ajout de ...
- Modification de ...

## Points à vérifier
- Orthographe
- Structure
- Cohérence avec le challenge
```

## 11. Revue de contribution

La revue sert à améliorer le travail avant de l'intégrer.

Un relecteur peut :

- commenter sans bloquer ;
- approuver ;
- demander des changements.

Règles pédagogiques :

- commenter le contenu, pas la personne ;
- expliquer clairement le problème ;
- proposer une amélioration ;
- valider quand les corrections sont faites ;
- garder une trace des décisions.

## 12. Gestion des conflits

Un conflit arrive lorsque deux personnes modifient la même partie d'un même fichier.

Pour réduire les conflits :

- une branche par membre ;
- un dossier personnel par membre ;
- des commits fréquents ;
- des Pull Requests courtes ;
- une synchronisation régulière ;
- éviter que plusieurs membres modifient le même fichier central en même temps.

Si un conflit apparaît, il faut décider quelle version garder ou comment combiner les deux versions.

VS Code aide à résoudre les conflits avec une interface visuelle.

## 13. Rôles dans le groupe

Un groupe peut fonctionner avec des rôles simples.

### Responsable du dépôt

Il gère :

- les accès GitHub ;
- la branche `main` ;
- les règles de contribution ;
- la validation finale.

### Contributeur

Il gère :

- sa branche ;
- ses fichiers ;
- ses commits ;
- sa Pull Request.

### Relecteur

Il gère :

- la relecture ;
- les commentaires ;
- les demandes de correction ;
- l'approbation.

## 14. Règles minimales pour le groupe

Voici une charte simple :

1. Ne pas travailler directement sur `main`.
2. Créer une branche par membre ou par tâche.
3. Faire des commits courts et clairs.
4. Ne pas supprimer le travail d'un autre membre.
5. Relire avant de fusionner.
6. Utiliser l'email comme ID pédagogique.
7. Utiliser le compte GitHub comme ID technique.
8. Synchroniser régulièrement.
9. Demander de l'aide dès qu'un conflit apparaît.
10. Documenter les décisions importantes.

## 15. Messages de commit recommandés

Un bon message de commit explique l'action.

Exemples :

```txt
Ajouter fiche candidat Amina
Corriger objectif personnel Karim
Créer dossier preuves Sara
Mettre à jour guide de collaboration
```

À éviter :

```txt
test
modif
ok
final
```

## 16. Niveau débutant, intermédiaire, avancé

### Débutant

Objectif :

- comprendre dépôt, fichier, commit ;
- modifier un fichier ;
- faire un commit ;
- pousser vers GitHub.

### Intermédiaire

Objectif :

- créer une branche ;
- ouvrir une Pull Request ;
- relire une contribution ;
- résoudre un conflit simple.

### Avancé

Objectif :

- organiser les accès ;
- protéger `main` ;
- définir une charte ;
- structurer les dossiers participants ;
- standardiser les Pull Requests.

## 17. Réponse directe aux questions fréquentes

### Est-ce obligatoire d'avoir un compte GitHub ?

Pour lire un dépôt public : non.

Pour contribuer au dépôt : oui.

### Une simple connexion par email suffit-elle ?

Non. GitHub utilise les comptes GitHub pour gérer les permissions.

### Peut-on utiliser les emails comme ID ?

Oui, pour l'organisation pédagogique.

Mais il faut associer chaque email à un compte GitHub.

### Peut-on travailler chacun à sa façon ?

Oui, si chacun travaille dans sa branche ou son dossier.

Mais l'intégration dans `main` doit suivre des règles communes.

## 18. Sources officielles consultées

Documentation GitHub :

- Getting started with collaborative development models : https://docs.github.com/github/collaborating-with-pull-requests/getting-started
- About pull requests : https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests
- Collaborating with pull requests : https://docs.github.com/en/pull-requests/collaborating-with-pull-requests
- About pull request reviews : https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/about-pull-request-reviews

Documentation VS Code :

- Source Control in VS Code : https://code.visualstudio.com/docs/sourcecontrol/overview
- Quickstart: use source control in VS Code : https://code.visualstudio.com/docs/sourcecontrol/quickstart
- Working with GitHub in VS Code : https://code.visualstudio.com/docs/sourcecontrol/github
- Git Branches and Worktrees in VS Code : https://code.visualstudio.com/docs/sourcecontrol/branches-worktrees

## 19. Conclusion

Le travail collaboratif devient clair lorsque chaque membre comprend son espace, son identité et son chemin de contribution.

Git enregistre l'historique.

GitHub organise le partage, les droits, les branches et les Pull Requests.

VS Code facilite le travail quotidien en montrant les modifications, les commits, les branches et les synchronisations.

Pour un groupe pédagogique, la formule la plus sûre est :

```txt
1 compte GitHub par membre
1 email comme ID pédagogique
1 branche par membre ou par tâche
1 Pull Request pour proposer les changements
1 validation avant fusion dans main
```

Cette méthode permet à chacun de travailler à sa façon sans désorganiser le projet commun.
