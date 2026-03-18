# 🐹 Crazy Hamster

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-orange.svg)](https://creativecommons.org/licenses/by-nc/4.0/)
[![Status](https://img.shields.io/badge/Status-Stable-green)]()
[![Platform](https://img.shields.io/badge/Platform-Web-lightgrey)]()

**Crazy Hamster** est une mini-suite d'applications web légères et ludiques centrées sur l'univers d'un hamster intrépide. Ce projet combine un jeu de labyrinthe procédural et un outil de relaxation (Timer Zen), développé sans frameworks pour une performance maximale.

---

## 🚀 Aperçu des Fonctionnalités

### 1. 🏁 Le Labyrinthe (Hampter Maze)
Un jeu de réflexion où vous guidez un hamster à travers un dédale généré aléatoirement à chaque session.
* **Génération Procédurale** : Utilise un algorithme de "Backtracking" pour créer des labyrinthes uniques.
* **Contrôles Hybrides** : Jouable au clavier (flèches) ou via des contrôles tactiles optimisés pour mobile.
* **Expérience Fluide** : Blocage strict du zoom et des gestes natifs pour une immersion totale sur iOS et Android.

### 2. ⏱️ Timer Zen (Hamster Zen Timer)
Un minuteur visuel de 4 minutes conçu pour la pause ou la méditation.
* **Animation Fluide** : Un hamster galope sur une roue de litière rotative.
* **Feedback Visuel** : L'animation s'arrête automatiquement à la fin du décompte de 240 secondes.
* **Esthétique Apaisante** : Palette de couleurs douces pour réduire la fatigue visuelle.

---

## 🧠 Focus Technique : L'Algorithme de Génération

Le labyrinthe est généré dynamiquement à l'aide d'un algorithme de **Backtracking récursif** (exploration en profondeur).

### Le concept de "Marche Aléatoire"
1. **Initialisation** : La grille commence comme un bloc plein de murs (valeur `1`).
2. **Exploration** : L'algorithme choisit une direction aléatoire, vérifie si la case à deux unités est libre, puis "casse" le mur intermédiaire.
3. **Récursion & Backtrack** : Le processus se répète jusqu'à ce que tous les chemins soient explorés, garantissant un **chemin unique** vers la sortie.

```javascript
function walk(x, y) {
    maze[y][x] = 0; 
    let dirs = [[0, -2], [0, 2], [-2, 0], [2, 0]].sort(() => Math.random() - 0.5);
    for (let [dx, dy] of dirs) {
        let nx = x + dx, ny = y + dy;
        if (nx > 0 && nx < cols && ny > 0 && ny < rows && maze[ny][nx] === 1) {
            maze[y + dy / 2][x + dx / 2] = 0; 
            walk(nx, ny); 
        }
    }
}
```

---

## 📱 Optimisations Mobile & UX

Une attention particulière a été portée à l'utilisation sur smartphones (écosystème Apple et Android) :
* **`touch-action: none`** : Désactive les gestes de navigation par défaut du navigateur.
* **Anti-Zoom** : Un script intercepte les doubles-taps pour stabiliser l'affichage.
* **Événements Pointer** : Utilisation de `onpointerdown` pour éliminer la latence tactile.
* **Viewport Cover** : Intégration parfaite sur les écrans à encoche via `viewport-fit=cover`.

---

## ⚙️ Personnalisation

Le code est modulaire pour permettre des ajustements rapides :
* **Difficulté** : Modifiez `TILE_SIZE`, `COLS` ou `ROWS` dans `jeu.html`.
* **Durée du Timer** : Modifiez `--timer-duration` (CSS) et `setTimeout` (JS) dans `timer.html`.

---

## 📁 Structure du Projet

```text
crazy-hamster/
├── index.html        # Menu principal (Hub)
├── jeu.html          # Application du Labyrinthe
├── timer.html        # Application du Timer Zen
└── README.md         # Documentation
```

---

## 📄 Licence

Ce projet est sous licence **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)**.
* ✅ **Autorisé** : Utilisation personnelle, partage et modification pour usage privé.
* ❌ **Interdit** : Toute forme de vente ou d'utilisation commerciale du code ou du matériel.

---

**Développé par @nycote99**
