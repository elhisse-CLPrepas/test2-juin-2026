# Guide technique - Workspace et gestion des workflows

## 1. Rôle de ce guide

Ce guide explique comment retrouver le workspace local, comprendre l'organisation de l'atelier `Dossier-challenge-100j6 N°04` et gérer les workflows de travail dans le cadre du challenge.

Il sert de repère technique pour les membres du groupe, les encadrants et les contributeurs.

## 2. Chemin du workspace local

Le workspace local est le dossier racine ouvert dans VS Code.

Dans cet atelier, le workspace principal est :

```txt
C:\DEV\TEST2 JUIN 2026
```

Le dossier du challenge se trouve à l'intérieur :

```txt
C:\DEV\TEST2 JUIN 2026\Dossier-challenge-100j6 N°04
```

## 3. Comment vérifier le workspace dans VS Code

Pour vérifier que l'on travaille au bon endroit :

1. Ouvrir VS Code.
2. Regarder l'explorateur de fichiers à gauche.
3. Vérifier que le dossier racine affiché correspond à `TEST2 JUIN 2026`.
4. Vérifier que le dossier `Dossier-challenge-100j6 N°04` apparaît dans l'arborescence.

Dans le terminal intégré de VS Code, utiliser :

```powershell
Get-Location
```

Le résultat doit indiquer :

```txt
C:\DEV\TEST2 JUIN 2026
```

## 4. Comment ouvrir le bon dossier

Depuis VS Code :

1. Menu `File`.
2. Choisir `Open Folder`.
3. Sélectionner :

```txt
C:\DEV\TEST2 JUIN 2026
```

Ne pas ouvrir uniquement un sous-dossier si l'on veut gérer Git pour tout le projet.

## 5. Structure de l'atelier challenge

Le dossier challenge est organisé ainsi :

```txt
Dossier-challenge-100j6 N°04/
  00-cadrage/
  01-prompts/
  02-documents/
  03-supports-visuels/
  04-page-web/
  05-workflows/
  06-portfolio-preuves/
```

Chaque dossier a un rôle précis.

## 6. Rôle des dossiers

### 00-cadrage

Contient les documents de départ :

- fiche candidat ;
- objectif personnel ;
- premiers livrables.

### 01-prompts

Contient les prompts utilisés pendant le challenge.

Exemples :

- prompts de recherche ;
- prompts de génération ;
- prompts de correction ;
- prompts d'analyse.

### 02-documents

Contient les documents de travail.

Exemples :

- notes ;
- comptes rendus ;
- brouillons ;
- synthèses.

### 03-supports-visuels

Contient les images, captures, visuels, schémas et supports graphiques.

### 04-page-web

Contient les éléments liés à une page web ou à une publication numérique.

Exemples :

- HTML ;
- CSS ;
- JavaScript ;
- maquettes ;
- contenus préparés pour publication.

### 05-workflows

Contient les guides, procédures et méthodes de travail.

Ce dossier explique comment travailler.

### 06-portfolio-preuves

Contient les preuves de progression.

Exemples :

- captures d'écran ;
- liens ;
- exports ;
- livrables validés ;
- traces de réalisation.

## 7. Workflow de base pour un membre

Un membre suit généralement ce cycle :

```txt
1. Ouvrir le workspace
2. Vérifier la branche
3. Créer ou modifier un fichier
4. Relire le changement
5. Faire un commit
6. Pousser vers GitHub
7. Créer une Pull Request si nécessaire
8. Ajouter une preuve dans le portfolio
```

## 8. Vérifier l'état du projet

Dans le terminal :

```powershell
git status
```

Cette commande indique :

- la branche active ;
- les fichiers modifiés ;
- les fichiers non suivis ;
- l'état de synchronisation avec GitHub.

## 9. Vérifier la branche active

```powershell
git branch --show-current
```

Exemple attendu :

```txt
main
```

Pour un membre, on recommande une branche personnelle :

```txt
travail-nom-prenom
```

## 10. Créer une branche de travail

```powershell
git checkout -b travail-nom-prenom
```

Exemple :

```powershell
git checkout -b travail-amina
```

La branche permet de travailler sans modifier directement la version principale.

## 11. Ajouter un fichier au bon endroit

Avant de créer un fichier, choisir le bon dossier.

Exemples :

```txt
Un prompt -> 01-prompts
Une note -> 02-documents
Une image -> 03-supports-visuels
Une page web -> 04-page-web
Une méthode -> 05-workflows
Une preuve -> 06-portfolio-preuves
```

## 12. Préparer et enregistrer un changement

Après modification :

```powershell
git status
git add .
git commit -m "Ajouter guide workflow workspace"
```

Le message de commit doit expliquer l'action.

## 13. Envoyer le travail vers GitHub

```powershell
git push
```

Si la branche est nouvelle :

```powershell
git push -u origin travail-nom-prenom
```

## 14. Workflow recommandé pour le groupe

Le groupe peut utiliser cette méthode :

```txt
main = version stable
travail-nom-prenom = espace personnel
Pull Request = demande de validation
06-portfolio-preuves = preuves de travail
```

Chaque membre :

1. travaille dans sa branche ;
2. range ses fichiers dans les bons dossiers ;
3. fait des commits réguliers ;
4. pousse sur GitHub ;
5. ouvre une Pull Request ;
6. documente ses preuves.

## 15. Gestion des preuves

Chaque contribution importante doit produire une preuve.

Exemples de preuves :

- capture d'écran d'un résultat ;
- lien GitHub vers un commit ;
- lien vers une Pull Request ;
- fichier exporté ;
- document final ;
- note de synthèse.

Nom recommandé :

```txt
preuve-jour-001-nom-prenom.md
preuve-jour-002-nom-prenom.png
```

## 16. Bonnes pratiques de nommage

Utiliser des noms simples :

```txt
guide-workflow.md
fiche-amina.md
preuve-jour-001.png
prompt-generation-page-web.md
```

Éviter :

```txt
Mon fichier final!!!.docx
copie version 2 nouveau final.md
test ok.md
```

## 17. Contrôle avant validation

Avant de valider un travail :

```powershell
git status
git diff
```

Vérifier :

- le bon dossier ;
- le bon nom de fichier ;
- l'absence de fichier temporaire ;
- la clarté du contenu ;
- la présence d'une preuve si nécessaire.

## 18. Gestion des conflits

Un conflit arrive lorsque deux personnes modifient la même partie d'un fichier.

Pour les éviter :

- ne pas modifier directement `main` ;
- créer une branche par membre ;
- éviter de travailler à plusieurs sur le même fichier ;
- synchroniser régulièrement ;
- faire des Pull Requests courtes.

## 19. Checklist quotidienne

Avant de commencer :

- ouvrir le bon workspace ;
- vérifier la branche active ;
- récupérer les dernières modifications ;
- choisir le dossier de travail.

Pendant le travail :

- sauvegarder régulièrement ;
- faire des commits clairs ;
- ranger les fichiers au bon endroit.

Avant de terminer :

- vérifier `git status` ;
- pousser vers GitHub ;
- créer ou mettre à jour la preuve ;
- signaler la Pull Request si elle existe.

## 20. Commandes utiles

```powershell
Get-Location
git status
git branch --show-current
git pull
git checkout -b travail-nom-prenom
git add .
git commit -m "Message clair"
git push
git log --oneline -5
```

## 21. Conclusion

Le workspace est l'espace local où le projet est ouvert.

Le dossier `Dossier-challenge-100j6 N°04` est l'atelier de production du challenge.

Les workflows servent à organiser le passage entre idée, production, validation et preuve.

Une bonne gestion repose sur quatre réflexes :

- travailler dans le bon dossier ;
- utiliser une branche adaptée ;
- faire des commits clairs ;
- produire des preuves visibles.
