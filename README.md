# Gestion d'une liste de tâches

## Description

Cette application Vue.js permet de gérer une liste de tâches.

L'utilisateur peut :

* Ajouter une tâche
* Marquer une tâche comme terminée
* Supprimer une tâche
* Consulter le nombre de tâches non terminées

## Installation

Installer les dépendances avec :

```bash
npm install
```

## Lancer le projet

Pour lancer l'application en mode développement :

```bash
npm run dev
```

## Fonctionnalités

* Ajouter une nouvelle tâche
* Empêcher l'ajout d'une tâche vide
* Marquer une tâche comme terminée
* Afficher les tâches terminées avec un texte barré
* Supprimer une tâche
* Afficher automatiquement le nombre de tâches non terminées
* Afficher un message lorsque la liste est vide

## Technologies utilisées

* Vue.js 3
* Vite
* JavaScript
* HTML
* CSS
## Concepts utilisés

* **ref** : permet de créer une donnée réactive dans Vue.js.
* **v-model** : permet de lier un champ de formulaire à une donnée.
* **v-for** : permet d'afficher chaque élément d'un tableau.
* **:key** : permet d'identifier chaque élément de manière unique dans `v-for`.
* **computed** : permet de calculer une valeur automatiquement à partir de données réactives.
* **@submit.prevent** : permet de gérer la soumission du formulaire sans recharger la page.
* **@click** : permet d'exécuter une fonction lorsqu'un élément est cliqué.
