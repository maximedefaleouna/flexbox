# Guide Complet et Pratique de CSS Flexbox

Depot pedagogique et aide-memoire interactif pour comprendre et maitriser le modele de mise en page Flexbox (Flexible Box Layout) en CSS. Ce projet rassemble les concepts theoriques essentiels ainsi que des exemples visuels concrets classes par proprietes.

---

## Les Fondations de Flexbox

Le modele Flexbox repose sur deux elements fondamentaux :
- **Le conteneur flex (Parent)** : L'element auquel on applique `display: flex` ou `display: inline-flex`.
- **Les elements flex (Enfants)** : Les enfants directs du conteneur qui se positionnent selon les regles flex.

### Les Deux Axes

Tout le comportement de Flexbox est determine par deux axes orthogonaux :
- **Axe principal (Main Axis)** : Par defaut horizontal, oriente de gauche a droite (peut etre modifie avec `flex-direction`).
- **Axe transversal (Cross Axis)** : Perpendiculaire a l'axe principal, oriente par defaut de haut en bas.

---

## Proprietes du Conteneur (Flex Container)

### 1. display
Active le contexte flex pour tous les enfants directs.
- `display: flex` : Cree un conteneur de niveau bloc.
- `display: inline-flex` : Cree un conteneur flex en ligne.

### 2. flex-direction
Definit l'axe principal et la direction des elements.
- `row` (valeur par defaut) : De gauche a droite.
- `row-reverse` : De droite a gauche.
- `column` : De haut en bas (axe principal devient vertical).
- `column-reverse` : De bas en haut.

### 3. flex-wrap
Controle si les elements doivent passer a la ligne lorsque l'espace est insuffisant.
- `nowrap` (par defaut) : Tous les elements restent sur une seule ligne (reduction de taille automatique).
- `wrap` : Les elements passent sur plusieurs lignes si necessaire.
- `wrap-reverse` : Les elements passent a la ligne dans le sens inverse.

### 4. flex-flow
Raccourci combinant `flex-direction` et `flex-wrap`.
- Exemple : `flex-flow: row wrap;`

### 5. justify-content
Gere la repartition et l'alignement des elements le long de l'axe principal.
- `flex-start` (par defaut) : Elements regroupes au debut.
- `flex-end` : Elements regroupes a la fin.
- `center` : Elements centres sur l'axe.
- `space-between` : Premier element au debut, dernier a la fin, espacement egal entre les elements.
- `space-around` : Espacement egal autour de chaque element.
- `space-evenly` : Espacement strictement identique entre tous les elements et les bordures.

### 6. align-items
Gere l'alignement des elements sur l'axe transversal (pour chaque ligne).
- `stretch` (par defaut) : Les elements s'etirent pour remplir la hauteur du conteneur.
- `flex-start` : Elements alignes en haut de l'axe transversal.
- `flex-end` : Elements alignes en bas de l'axe transversal.
- `center` : Elements centres sur l'axe transversal.
- `baseline` : Elements alignes sur leur ligne de base textuelle.

### 7. align-content
Gere l'alignement des lignes d'elements le long de l'axe transversal quand `flex-wrap: wrap` est actif.
- Valeurs disponibles : `stretch`, `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `space-evenly`.

---

## Proprietes des Elements Enfants (Flex Items)

### 1. order
Modifie l'ordre d'affichage visuel sans toucher au HTML (valeur par defaut : 0).

### 2. flex-grow
Definit la capacite d'un element a grandir pour occuper l'espace restant (valeur par defaut : 0).

### 3. flex-shrink
Definit la capacite d'un element a retrecir si l'espace est insuffisant (valeur par defaut : 1).

### 4. flex-basis
Definit la taille de depart d'un element avant la distribution de l'espace restant (ex : `200px`, `auto`).

### 5. flex (Raccourci)
Combine `flex-grow`, `flex-shrink` et `flex-basis`.
- Exemple courant : `flex: 1;` (equivaut a `flex: 1 1 0;`).

### 6. align-self
Permet a un element specifique de surcharger la regle `align-items` definie sur son conteneur parent.

---

## Exemples et Cas d'Usage Incontournables

### Centrage Parfait (Horizontal et Vertical)
Le probleme historique du centrage en CSS resolu en trois lignes :

```css
.parent {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
```

### Barre de Navigation Responsive
Positionner le logo a gauche et les liens d'action a droite :

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
}
```

### Grille de Cartes Flexibles avec Retour a la Ligne
```css
.card-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.card {
  flex: 1 1 300px; /* Largeur de base 300px, s'etire ou se retrecit si necessaire */
}
```

---

## Utilisation des Exemples Pratiques du Projet

Ce projet contient des démonstrations HTML et CSS indépendantes pour chaque propriété majeure dans le sous-dossier `container/`.

Pour tester un exemple :
1. Cloner le depot localement :
   ```bash
   git clone https://github.com/maximedefaleouna/flexbox.git
   cd flexbox
   ```
2. Ouvrir le fichier `index.html` du dossier de votre choix dans un navigateur (par exemple `container/justify-content/index.html`) pour observer le comportement des boites.
3. Modifier les proprietes CSS dans le fichier `style.css` correspondant pour tester l'impact visuel en direct.

---

## Auteur

**Maxime DEFALEOUNA**
- Profil GitHub : [@maximedefaleouna](https://github.com/maximedefaleouna)
- Portfolio : [https://maximedefa.netlify.app](https://maximedefa.netlify.app)
