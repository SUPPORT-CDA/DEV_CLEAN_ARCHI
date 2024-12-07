# Cookify - Gestionnaire de Recettes Culinaires avec Planificateur de Menus

<img src="../images/logo.png" width="200" />

## 1. Contexte

**Cookify** est une application web permettant de gérer des recettes culinaires et de planifier des menus hebdomadaires à partir des recettes créées. Elle permet aux utilisateurs de :
- Créer, consulter, modifier et supprimer des recettes.
- Organiser les recettes dans un planning hebdomadaire.

## 2. Objectifs pédagogiques

Ce projet a pour objectif de :
1. **Maîtriser les concepts de base d'une application en React** : gestion des composants, de l'état et des props.
2. **Interagir avec une API RESTful** pour réaliser des opérations CRUD (Créer, Lire, Modifier, Supprimer).
3. **Intégrer une spécificité métier** : la planification des menus hebdomadaires.
4. **Appliquer les bonnes pratiques de développement** : séparation des composants, documentation, tests basiques, et déploiement.

## 3. Fonctionnalités attendues

### 3.1 Gestion des recettes (CRUD)

1. **Créer une recette** :  
   - Nom de la recette, liste des ingrédients et instructions.
   
2. **Consulter une recette** :  
   - Affichage détaillé de la recette sélectionnée.

3. **Modifier une recette** :  
   - Modification des champs d’une recette existante.

4. **Supprimer une recette** :  
   - Suppression d’une recette de la base de données.

### 3.2 Planification des menus

1. **Ajouter une recette à un jour de la semaine** :  
   - L'utilisateur peut attribuer une recette à un jour spécifique (ex. "Lundi : Tarte aux pommes").

2. **Consulter le menu hebdomadaire** :  
   - Affichage du menu complet de la semaine.

3. **Modifier ou supprimer un plat du menu** :  
   - Gestion des plats dans le planning.

## 4. Schéma des données

Le schéma de données est fourni. Il représente les **Recettes** et **Menus**, ainsi que leurs relations (OneToMany, ManyToMany).

### 4.1 Exemple de structure des données

#### Recette
```json
{
  "id": 1,
  "nom": "Tarte aux pommes",
  "ingrédients": [
    "200g de farine",
    "3 pommes",
    "100g de sucre"
  ],
  "instructions": "Mélanger la farine et le sucre, ajouter les pommes..."
}
```

#### Menu
```json
{
  "id": 1,
  "jour": "Lundi",
  "recipeId": 1
}
```

---

## 5. Architecture

### 5.1 Composants principaux

- **`App`** : Composant racine qui gère la navigation et les pages principales.
- **`RecipeList`** : Affiche la liste des recettes avec des options CRUD.
- **`RecipeForm`** : Formulaire pour ajouter ou modifier une recette.
- **`WeeklyPlanner`** : Planificateur pour afficher et gérer le menu hebdomadaire.
- **`MenuItem`** : Composant représentant une recette dans le menu d'un jour spécifique.

### 5.2 Gestion de l'état

L'état est géré localement avec **useState** et via **RTK Query** pour interagir avec l'API.

---

## 6. API RESTful fournie

Les **endpoints** suivants sont disponibles pour interagir avec les recettes et les menus :

1. **Recettes** (`/recipes`):
   - **GET /recipes** : Récupérer toutes les recettes.
   - **GET /recipes/:id** : Récupérer une recette par son ID.
   - **POST /recipes** : Créer une nouvelle recette.
   - **PUT /recipes/:id** : Modifier une recette existante.
   - **DELETE /recipes/:id** : Supprimer une recette.

2. **Menus** (`/menus`):
   - **GET /menus** : Récupérer le menu hebdomadaire.
   - **POST /menus** : Ajouter une recette à un jour spécifique (ex. `{ day: "Lundi", recipeId: 1 }`).
   - **DELETE /menus/:id** : Supprimer une recette du menu.

---

## 7. Installation et déploiement

### 7.1 Prérequis

- **Node.js** (version 18 ou supérieure)
- **npm** ou **yarn** pour gérer les dépendances

### 7.2 Étapes pour exécuter le projet

1. Clonez le dépôt :
   ```bash
   git clone https://github.com/votre-projet/cookify.git
   cd cookify
   ```

2. Installez les dépendances :
   ```bash
   npm install
   ```

3. Lancez l'application en local :
   ```bash
   npm start
   ```

### 7.3 Déploiement

Déployez l’application frontend sur **Vercel** ou **Netlify** et l'API backend sur **Render** ou un autre service de votre choix.

---

## 8. Tests et validation

### 8.1 Tests effectués

- Tests manuels pour valider les fonctionnalités principales (CRUD recettes, gestion des menus).
  
### 8.2 Limites

- Pas de tests unitaires automatisés.
- La sécurité avancée et l'intégration continue ne sont pas implémentées.

---

## 9. Auteur(s)

Projet réalisé par : **[Nom des étudiants]**

---

### **Instructions supplémentaires :**

1. Remplissez ce template avec les détails de votre projet.
2. Assurez-vous de documenter chaque section de manière claire et complète.
3. Testez toutes les fonctionnalités pour garantir qu'elles fonctionnent comme prévu avant le déploiement.

---

### **Livrables attendus :**

1. **README complet**  
2. **Code source** du frontend (React) et du backend (API Express).  
3. **Application déployée** accessible via une plateforme publique.

---

### **Conseils** :

- Faites attention à l'ergonomie de l'interface utilisateur et à la gestion des erreurs.
- Assurez-vous que l'API fonctionne correctement avec des données réelles.
- Prenez le temps de tester l'application avec plusieurs scénarios utilisateurs.
