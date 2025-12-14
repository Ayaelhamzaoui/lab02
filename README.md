# Lab 2 : Git et bonnes pratiques MLOps

## Introduction

Dans un contexte MLOps, le développement d’un modèle de Machine Learning ne se limite pas à l’entraînement. Il implique également une **gestion rigoureuse du code**, des **versions**, des **expérimentations**, ainsi que des **mécanismes de contrôle et de retour arrière**.

Ce lab a pour objectif de mettre en pratique l’utilisation de **Git** dans un projet MLOps réel, en simulant des situations concrètes rencontrées en équipe : modifications concurrentes, branches de fonctionnalités, conflits, annulation de changements et réécriture de l’historique.

Le projet utilisé est `mlops-lab-01`, qui représente un **mini-système MLOps** intégrant pipeline d’entraînement, registry de modèles, API de prédiction, monitoring et rollback.

---

## Objectifs du lab

- Comprendre le rôle de **Git dans un projet MLOps**
- Maîtriser les commandes Git essentielles dans un contexte réel
- Gérer des **branches de fonctionnalités**
- Comprendre et résoudre des **conflits de merge**
- Utiliser `stash`, `reset`, `revert` et `rebase`
- Faire la différence entre **prototype** et **système prêt pour la production**
- Adopter une logique de **traçabilité, gouvernance et reproductibilité**

---

## Étapes réalisées

### Étape 1 : Initialiser Git dans mlops-lab-01
- Initialisation du dépôt avec `git init`
- Création du fichier `.gitignore`
- Vérification de l’état du dépôt avec `git status`

### Étape 2 : Premier commit du projet MLOps
- Ajout des dossiers principaux (`src`, `data`, `registry`, `.gitignore`)
- Premier commit :
feat(project): initial mlops lab structure

markdown
Copier le code

### Étape 3 : Observer une modification avec git diff
- Modification de `monitor_drift.py` (`z_threshold`)
- Observation avec `git diff` et `git diff --staged`
- Commit de la modification

### Étape 4 : Créer une branche de fonctionnalité liée au lab
- Création de la branche `feature/api-request-id`
- Amélioration de la gestion du `request_id` dans `src/api.py`
- Commit de la fonctionnalité
- Retour sur la branche principale

### Étape 5 : Fusionner la branche feature dans la branche principale
- Fusion avec `git merge`
- Vérification de l’historique

### Étape 6 : Créer et résoudre un conflit de merge
- Modification simultanée de `gate_f1` dans `train.py`
- Résolution manuelle du conflit
- Commit de résolution

### Étape 7 : Utiliser git stash
- Mise de côté de modifications non prêtes avec `git stash`
- Récupération avec `git stash apply` ou `git stash pop`

### Étape 8 : Tester git reset sur un fichier d’expérimentation
- Création de plusieurs commits dans `experiments/reset_test.txt`
- Test de `git reset --soft`, `git reset` (mixed) et `git reset --hard`

### Étape 9 : Annuler un commit avec git revert
- Ajout volontaire d’un mauvais changement dans `api.py`
- Annulation propre avec `git revert HEAD`

### Étape 10 : Rebase d’une branche feature sur la branche principale
- Création d’une branche feature et ajout de commits
- Rebase sur la branche principale
- Vérification de l’historique linéaire

---

## Conclusion

Ce lab démontre que le Machine Learning en production ne se résume pas à entraîner un modèle.  
Un **système MLOps fiable** repose sur :

- une gestion rigoureuse du code
- un versionnement clair
- une traçabilité complète
- des mécanismes de contrôle (gate, rollback)
- une collaboration structurée via Git

Grâce à ce lab, l’étudiant comprend la différence fondamentale entre :
- un **prototype de data scientist**
- un **système prêt pour la production**

Ce travail constitue une base solide pour aborder des pratiques avancées telles que 
