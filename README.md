# Boris is Peppa — Mini-jeu vidéo Web

> **Statut :** concept / prototype en développement  
> **Type :** mini-jeu vidéo Web  
> **Genre :** arcade / endless runner / action  
> **Référence de gameplay :** jeu Dinosaur de Google Chrome  
> **Technologies envisagées :** HTML, CSS, JavaScript  
> **Objectif :** transformer les assets graphiques déjà disponibles en un mini-jeu vidéo Web complet et jouable.

---

# 1. Vision du projet

**Boris is Peppa** est un **mini-jeu vidéo Web** jouable directement dans un navigateur.

Le gameplay s'inspire du fonctionnement du jeu **Dinosaur de Google Chrome** :

- le personnage avance automatiquement ;
- le joueur contrôle principalement ses déplacements et ses sauts ;
- des obstacles arrivent progressivement ;
- il faut les éviter ;
- la difficulté augmente avec le temps ;
- une collision dangereuse provoque un Game Over ;
- de nouvelles mécaniques apparaissent au fur et à mesure de la progression.

La différence essentielle est que **Boris is Peppa possède son propre univers, ses propres personnages, ses propres obstacles et son propre humour**.

---

# 2. Point essentiel : les assets graphiques sont déjà disponibles

Le projet **ne consiste pas à créer les éléments graphiques du jeu à partir de zéro**.

Une grande partie des éléments qui constituent visuellement le jeu existe déjà sous forme d'images, notamment en **PNG avec transparence**.

Les éléments déjà disponibles comprennent notamment :

- le personnage principal ;
- les différentes parties/personnages nécessaires au jeu ;
- les flaques ;
- les saucisses qui sont lancées ;
- le personnage du boucher ;
- le fond / décor principal ;
- différents éléments graphiques destinés à être intégrés dans le jeu.

Ces éléments doivent principalement être :

1. importés dans le projet ;
2. positionnés ;
3. redimensionnés si nécessaire ;
4. animés ;
5. utilisés pour les collisions ;
6. intégrés aux mécaniques du jeu.

## Ce qui reste principalement à créer

Le développement porte surtout sur :

- le **moteur du mini-jeu** ;
- les déplacements ;
- les sauts ;
- la gravité ;
- les collisions ;
- la génération des obstacles ;
- les projectiles ;
- les interactions ;
- les power-ups ;
- la progression ;
- les niveaux ;
- le système de score ;
- le Game Over ;
- les écrans du jeu ;
- la **GUI** ;
- éventuellement les effets et animations supplémentaires.

> **Principe directeur : les graphismes existent déjà ; le travail consiste principalement à les transformer en éléments interactifs d'un vrai mini-jeu vidéo Web.**

---

# 3. Concept général

Le joueur contrôle Boris.

Boris avance automatiquement dans un environnement qui défile.

Le joueur doit :

- sauter par-dessus les flaques ;
- éviter les obstacles ;
- éviter les saucisses lancées ;
- récupérer certains objets ;
- utiliser certaines capacités au bon moment ;
- progresser le plus loin possible ;
- éventuellement atteindre le boucher.

La boucle de gameplay est donc :

```text
Boris apparaît
     ↓
Début de la partie
     ↓
Course automatique
     ↓
Obstacles
     ↓
Saut / esquive
     ↓
Progression
     ↓
Vitesse qui augmente
     ↓
Nouvelles mécaniques
     ↓
Boucher / fin de niveau
     ↓
Victoire ou Game Over
```

---

# 4. Gameplay de base

Le premier gameplay doit rester extrêmement simple.

### Début

Boris est placé sur le sol devant le décor.

Lorsque le joueur lance la partie :

```text
START
 ↓
Boris commence à courir
 ↓
Les obstacles apparaissent
```

### Contrôle

Le contrôle principal est le **saut**.

Exemple :

- `Espace` → sauter ;
- clic / tap → sauter sur mobile.

Le personnage est ensuite soumis à une gravité normale :

```text
Sol
 ↓
Saut
 ↓
Montée
 ↓
Sommet
 ↓
Descente
 ↓
Atterrissage
```

---

# 5. Les flaques

Les flaques constituent le premier obstacle du jeu.

Le joueur doit sauter par-dessus.

### Collision

Si Boris touche une flaque :

```text
Collision
   ↓
Boris = mort
   ↓
Game Over
```

L'état de mort utilise l'asset de Boris associé aux flaques déjà préparé.

L'objectif est donc de pouvoir utiliser directement l'image existante pour représenter la conséquence de la collision.

### Variations futures

Les flaques pourront ensuite :

- être plus larges ;
- être rapprochées ;
- apparaître en séries ;
- être combinées avec d'autres obstacles ;
- nécessiter un power-up pour être franchies.

---

# 6. Les autres éléments déjà disponibles

Le projet dispose également d'autres assets qui pourront être intégrés au gameplay.

## Saucisses

Les saucisses sont des projectiles lancés dans la direction de Boris.

Elles peuvent devenir :

- des obstacles ;
- des projectiles ;
- des éléments d'une attaque ennemie ;
- des éléments de la séquence finale.

## Boucher

Le boucher est prévu comme personnage important de la fin du jeu.

Il pourra notamment lancer les saucisses vers Boris.

L'objectif à long terme est d'en faire un **boss ou adversaire final**.

## Fond

Le fond constitue déjà la base visuelle du monde du jeu.

Il n'est donc pas nécessaire de créer un environnement graphique complet : le travail consiste à faire défiler, positionner et exploiter correctement le décor existant.

---

# 7. Les saucisses comme projectiles

Une mécanique avancée consiste à faire lancer des saucisses au joueur.

Concept :

```text
Boucher
   ↓
Lance une saucisse
   ↓
Saucisse → → → Boris
```

Le joueur doit alors :

- sauter ;
- esquiver ;
- éventuellement utiliser un pouvoir ;
- continuer sa progression.

## Difficulté progressive

Au début :

- peu de projectiles ;
- vitesse faible ;
- trajectoires simples.

Plus tard :

- davantage de projectiles ;
- vitesse plus élevée ;
- intervalles plus courts ;
- patterns différents ;
- combinaison avec les flaques.

---

# 8. Le boucher et la fin du jeu

À long terme, le boucher doit pouvoir devenir l'objectif principal de la progression.

Une possibilité est :

```text
Course
 ↓
Obstacles
 ↓
Progression
 ↓
Zone du boucher
 ↓
Attaques de saucisses
 ↓
Phase finale
 ↓
Victoire
```

Le boucher pourrait lancer continuellement des saucisses.

Le joueur doit alors survivre et accomplir une mécanique permettant d'atteindre le boucher.

L'idée humoristique finale est que Boris puisse finalement **dévorer le boucher**, selon la forme exacte retenue pour la scène finale.

Cette partie est volontairement considérée comme une **fonctionnalité longue durée** : elle nécessite davantage de gameplay, d'animations et de level design.

---

# 9. Le drapeau britannique

Une mécanique spéciale envisagée est l'utilisation du **drapeau britannique comme cape**.

Le drapeau pourrait donner à Boris une capacité temporaire lui permettant de :

- planer ;
- voler ;
- rester plus longtemps dans les airs ;
- franchir certaines flaques ou séquences d'obstacles.

Concept :

```text
Boris récupère le drapeau
          ↓
Activation
          ↓
Cape
          ↓
Vol / planage temporaire
          ↓
Fin de la capacité
          ↓
Retour au sol
```

La capacité pourra être limitée par :

- une durée ;
- une jauge ;
- un nombre d'utilisations.

---

# 10. Les drapeaux européens

Une autre mécanique humoristique est l'utilisation de **drapeaux européens dans les flaques**.

Concept :

```text
Boris arrive devant une flaque
          ↓
Utilise / jette un drapeau européen
          ↓
Le drapeau tombe dans la flaque
          ↓
Boris peut passer
          ↓
Le drapeau ressort sale
```

Le gag repose sur l'humour autour du **Brexit** et de la relation Royaume-Uni / Union européenne.

Cette mécanique peut être essentiellement visuelle et humoristique.

Elle permet également d'introduire un principe de **power-up consommable**.

---

# 11. Système d'objets

Les objets spéciaux peuvent être intégrés progressivement.

| Objet | Fonction |
|---|---|
| Drapeau britannique | Vol / planage temporaire |
| Drapeau européen | Permet de franchir une flaque |
| Autres objets futurs | À définir |

Les objets doivent être facilement identifiables à l'écran.

---

# 12. Progression de la difficulté

Comme dans Chrome Dino, le jeu doit devenir progressivement plus rapide et plus difficile.

La progression peut modifier :

- la vitesse de Boris ;
- la vitesse du décor ;
- la fréquence d'apparition des obstacles ;
- la distance entre les obstacles ;
- la vitesse des saucisses ;
- la fréquence des projectiles ;
- les combinaisons d'obstacles.

Concept :

```text
Début
 ↓
Vitesse faible
 ↓
Flaques simples
 ↓
Vitesse moyenne
 ↓
Plus d'obstacles
 ↓
Saucisses
 ↓
Combinaisons
 ↓
Vitesse élevée
 ↓
Boucher
```

Toutes ces valeurs doivent idéalement être centralisées dans un système de difficulté facilement configurable.

---

# 13. Endless runner ou niveaux ?

Deux grandes architectures de gameplay sont possibles.

## Option A — Endless runner

Le jeu fonctionne comme Chrome Dino.

La partie continue jusqu'à ce que Boris meure.

Le score augmente avec la distance.

### Avantages

- simple à programmer ;
- très rapide à prototyper ;
- parfaitement adapté à un mini-jeu Web ;
- rejouabilité importante.

---

## Option B — Jeu par niveaux

Le jeu est divisé en plusieurs niveaux.

Exemple :

### Niveau 1 — Les flaques

Apprentissage du saut.

### Niveau 2 — Les obstacles

Introduction de nouveaux dangers.

### Niveau 3 — Les saucisses

Introduction des projectiles.

### Niveau 4 — Les drapeaux

Introduction des pouvoirs.

### Niveau 5 — Le boucher

Séquence finale / boss.

---

## Approche recommandée

Commencer par une **version endless runner très simple**, puis ajouter progressivement une structure en niveaux si le gameplay s'y prête.

Cela évite de développer immédiatement un système complexe alors que les mécaniques de base doivent d'abord être validées.

---

# 14. GUI

La **GUI est l'un des principaux éléments qui restent à concevoir**.

Elle devra être créée autour des assets déjà existants.

## Écran d'accueil

Possibilité :

```text
┌─────────────────────────────┐
│                             │
│       BORIS IS PEPPA        │
│                             │
│           BORIS             │
│                             │
│          [ JOUER ]          │
│                             │
└─────────────────────────────┘
```

## Interface pendant la partie

Afficher uniquement les informations utiles :

- score ;
- distance ;
- niveau ;
- power-up disponible ;
- jauge de capacité si nécessaire.

## Game Over

```text
GAME OVER

Score : XXXX
Record : XXXX

[ REJOUER ]
[ MENU ]
```

## Écran de victoire

Si le système de niveaux est retenu :

```text
NIVEAU TERMINÉ !

[ CONTINUER ]
```

Et éventuellement une séquence dédiée à la fin du jeu.

---

# 15. Score

Le score peut simplement dépendre de la distance parcourue.

```text
Score = distance
```

Des bonus pourront être ajoutés ultérieurement :

- temps de survie ;
- obstacles évités ;
- objets récupérés ;
- niveau terminé ;
- boss vaincu.

Le système de score doit être simple au départ.

---

# 16. Architecture technique

Le projet étant un mini-jeu vidéo Web, une première architecture peut être construite avec :

```text
HTML
CSS
JavaScript
```

Une structure possible :

```text
boris-is-peppa/
│
├── index.html
├── README.md
│
├── css/
│   └── style.css
│
├── js/
│   ├── game.js
│   ├── player.js
│   ├── obstacles.js
│   ├── projectiles.js
│   ├── items.js
│   ├── collision.js
│   ├── levels.js
│   └── ui.js
│
├── assets/
│   ├── characters/
│   ├── obstacles/
│   ├── projectiles/
│   ├── items/
│   ├── backgrounds/
│   └── audio/
│
└── docs/
    └── game-design.md
```

Cette structure est indicative.

---

# 17. Canvas ou éléments HTML ?

Deux solutions sont envisageables.

## Solution 1 — HTML / CSS / JavaScript

Les différents éléments sont représentés par des éléments HTML positionnés avec CSS.

### Avantages

- très rapide pour commencer ;
- simple à prototyper ;
- facile à modifier ;
- très adapté à une première expérimentation.

### Limites

Lorsque le nombre d'objets et d'animations augmente, la gestion peut devenir moins propre.

---

## Solution 2 — HTML Canvas

Le jeu est rendu dans un `<canvas>`.

### Avantages

- particulièrement adapté à un mini-jeu 2D ;
- gestion centralisée du rendu ;
- déplacement des sprites ;
- collisions ;
- animations ;
- objets multiples.

### Recommandation

Le plus important est de **faire un prototype jouable rapidement**.

L'architecture pourra ensuite être consolidée autour d'un Canvas si le nombre de mécaniques augmente.

---

# 18. Gestion des sprites

Les PNG transparents existants devront être utilisés comme sprites du jeu.

Chaque asset devra avoir des propriétés permettant de contrôler :

- position X ;
- position Y ;
- largeur ;
- hauteur ;
- vitesse ;
- état ;
- hitbox ;
- visibilité ;
- animation éventuelle.

Concept :

```text
Asset PNG
   ↓
Sprite
   ↓
Position
   ↓
Animation
   ↓
Collision
   ↓
Interaction
```

Il ne s'agit donc pas de recréer les personnages : il s'agit de **leur donner une logique de jeu**.

---

# 19. Système de collision

Les collisions sont une partie essentielle du moteur.

Exemple :

```text
Boris
┌──────────┐
│  hitbox  │
└──────────┘

Flaque
┌──────────────┐
│    hitbox    │
└──────────────┘
```

Si les deux zones se touchent :

```text
collision = true
       ↓
Boris = dead
       ↓
Game Over
```

Pour les objets non mortels :

```text
collision
 ↓
effet appliqué
 ↓
objet modifié / supprimé
```

Les hitboxes peuvent être légèrement plus petites que les images afin d'obtenir un gameplay plus agréable.

---

# 20. Boucle de jeu

Le jeu doit fonctionner autour d'une boucle principale.

Concept :

```text
Game Loop
   ↓
Lire les entrées du joueur
   ↓
Mettre à jour Boris
   ↓
Mettre à jour les obstacles
   ↓
Mettre à jour les projectiles
   ↓
Mettre à jour les objets
   ↓
Calculer les collisions
   ↓
Mettre à jour le score
   ↓
Augmenter la difficulté
   ↓
Dessiner la scène
   ↓
Recommencer
```

Cette boucle constitue le cœur technique du mini-jeu.

---

# 21. Génération des obstacles

Les obstacles doivent pouvoir apparaître automatiquement.

Concept :

```text
Obstacle Manager
       ↓
Choisit un obstacle
       ↓
Choisit une position
       ↓
Définit sa vitesse
       ↓
Crée l'objet
       ↓
L'objet se déplace
       ↓
Hors écran → suppression
```

Cela évite d'avoir à placer manuellement chaque flaque dans le niveau.

---

# 22. Patterns d'obstacles

Des patterns pourront être créés pour générer des situations intéressantes.

Exemples :

```text
Flaque
```

ou :

```text
Flaque      Flaque
```

ou :

```text
Flaque
       Obstacle
               Flaque
```

ou :

```text
Flaque
        Saucisse
                Flaque
```

L'objectif est de générer des situations qui restent **réalisables**, même lorsque la vitesse augmente.

---

# 23. Gestion de la mort

Lorsqu'une collision mortelle est détectée :

```text
collision
   ↓
arrêt du gameplay
   ↓
état = DEAD
   ↓
sprite Boris mort
   ↓
petite animation éventuelle
   ↓
affichage Game Over
```

Le joueur doit ensuite pouvoir recommencer immédiatement.

---

# 24. Gestion des états du joueur

Boris peut avoir plusieurs états.

```text
IDLE
 ↓
RUNNING
 ↓
JUMPING
 ↓
FALLING
 ↓
RUNNING
```

Avec des transitions possibles :

```text
RUNNING → DEAD
JUMPING → DEAD
FALLING → DEAD
RUNNING → FLYING
FLYING → FALLING
```

Cette architecture facilitera l'ajout de mécaniques supplémentaires.

---

# 25. Assets et organisation des fichiers

Les assets existants doivent être classés proprement.

Exemple :

```text
assets/
│
├── characters/
│   ├── boris.png
│   ├── boris-dead.png
│   └── butcher.png
│
├── obstacles/
│   ├── puddle.png
│   └── ...
│
├── projectiles/
│   └── sausage.png
│
├── items/
│   ├── uk-flag.png
│   └── eu-flag.png
│
├── backgrounds/
│   └── background.png
│
└── audio/
    └── ...
```

Les noms exacts dépendront des fichiers réellement disponibles.

---

# 26. Ce qui doit être créé versus ce qui existe déjà

| Élément | État |
|---|---|
| Personnage principal | **Déjà disponible** |
| PNG transparents | **Déjà disponibles** |
| Flaques | **Déjà disponibles** |
| Saucisses | **Déjà disponibles** |
| Boucher | **Déjà disponible** |
| Fond / décor | **Déjà disponible** |
| Objets graphiques principaux | **Déjà disponibles** |
| Moteur de jeu | À programmer |
| Déplacement | À programmer |
| Saut | À programmer |
| Gravité | À programmer |
| Collisions | À programmer |
| Génération d'obstacles | À programmer |
| Projectiles | À programmer |
| Power-ups | À programmer |
| Progression | À programmer |
| Score | À programmer |
| Game Over | À programmer |
| GUI | **À créer** |
| Menus | **À créer** |
| Animations supplémentaires | À intégrer / programmer selon les assets |
| Audio | Optionnel / à ajouter plus tard |

---

# 27. MVP

Le MVP doit être extrêmement simple.

Il ne faut surtout pas commencer par le boucher, les niveaux ou les power-ups.

Le premier objectif est :

```text
Boris
  ↓
Course
  ↓
Saut
  ↓
Flaque
  ↓
Collision
  ↓
Mort
  ↓
Game Over
  ↓
Rejouer
```

### MVP fonctionnel

Le premier prototype doit permettre de :

- lancer une partie ;
- faire courir Boris ;
- faire sauter Boris ;
- faire défiler le décor ;
- faire apparaître des flaques ;
- détecter les collisions ;
- afficher Boris mort ;
- arrêter la partie ;
- afficher Game Over ;
- recommencer.

**Dès que cette version fonctionne, le projet est déjà un vrai mini-jeu vidéo Web.**

---

# 28. Roadmap de développement

## Phase 1 — Import des assets

- [ ] organiser les PNG ;
- [ ] intégrer le fond ;
- [ ] intégrer Boris ;
- [ ] intégrer les flaques ;
- [ ] intégrer les autres éléments déjà disponibles ;
- [ ] vérifier les dimensions et la transparence.

---

## Phase 2 — Premier prototype

- [ ] créer la page du jeu ;
- [ ] afficher le décor ;
- [ ] afficher Boris ;
- [ ] créer le sol ;
- [ ] créer la boucle de jeu ;
- [ ] créer la course ;
- [ ] créer le saut ;
- [ ] créer la gravité.

---

## Phase 3 — Première vraie mécanique

- [ ] faire apparaître les flaques ;
- [ ] déplacer les flaques vers Boris ;
- [ ] créer les hitboxes ;
- [ ] détecter les collisions ;
- [ ] afficher Boris mort ;
- [ ] créer le Game Over ;
- [ ] créer le bouton Rejouer.

**À ce stade : première version jouable.**

---

## Phase 4 — Gameplay

- [ ] score ;
- [ ] meilleur score ;
- [ ] vitesse progressive ;
- [ ] génération procédurale / aléatoire ;
- [ ] différents patterns d'obstacles ;
- [ ] équilibrage de la difficulté.

---

## Phase 5 — Saucisses

- [ ] intégrer le PNG de saucisse ;
- [ ] créer le système de projectile ;
- [ ] créer le lancement ;
- [ ] gérer la trajectoire ;
- [ ] gérer la collision ;
- [ ] créer différents patterns.

---

## Phase 6 — Power-ups

### Drapeau britannique

- [ ] intégration du PNG ;
- [ ] récupération ;
- [ ] activation ;
- [ ] mode cape ;
- [ ] vol / planage ;
- [ ] durée ;
- [ ] fin du pouvoir.

### Drapeaux européens

- [ ] intégration du PNG ;
- [ ] récupération ;
- [ ] utilisation dans une flaque ;
- [ ] suppression / transformation ;
- [ ] version sale du drapeau.

---

## Phase 7 — GUI

- [ ] écran d'accueil ;
- [ ] bouton Jouer ;
- [ ] affichage du score ;
- [ ] affichage du niveau ;
- [ ] indicateur de power-up ;
- [ ] écran Game Over ;
- [ ] bouton Rejouer ;
- [ ] écran de victoire ;
- [ ] éventuel écran de sélection de niveau.

---

## Phase 8 — Niveaux

- [ ] créer le système de niveaux ;
- [ ] définir les objectifs ;
- [ ] définir les obstacles de chaque niveau ;
- [ ] créer les transitions ;
- [ ] créer la progression.

---

## Phase 9 — Boucher / Boss

- [ ] intégrer le boucher ;
- [ ] créer son apparition ;
- [ ] créer ses animations ;
- [ ] créer le lancement de saucisses ;
- [ ] créer ses patterns d'attaque ;
- [ ] créer la phase finale ;
- [ ] créer la condition de victoire ;
- [ ] créer la séquence de fin.

---

## Phase 10 — Polish

- [ ] animations ;
- [ ] effets visuels ;
- [ ] sons ;
- [ ] musique éventuelle ;
- [ ] optimisation des PNG ;
- [ ] optimisation du code ;
- [ ] tests clavier ;
- [ ] tests mobile ;
- [ ] correction des bugs ;
- [ ] équilibrage final.

---

# 29. Version mobile

Comme le jeu est Web, une compatibilité mobile est intéressante.

Contrôles possibles :

```text
Tap → Saut
```

et éventuellement :

```text
Bouton tactile → Pouvoir
```

La GUI devra être responsive.

Le jeu devra prendre en compte :

- différentes résolutions ;
- écrans tactiles ;
- boutons suffisamment grands ;
- orientation portrait/paysage si nécessaire.

---

# 30. Performance

Le jeu doit rester léger.

Les principaux points à surveiller :

- taille des PNG ;
- nombre d'objets simultanés ;
- fréquence de génération ;
- suppression des objets hors écran ;
- nombre de calculs de collision ;
- efficacité de la Game Loop.

Les assets existants pourront être compressés/optimisés sans modifier leur apparence.

---

# 31. Audio

L'audio peut être ajouté après le gameplay.

Effets possibles :

- saut ;
- atterrissage ;
- collision ;
- flaque ;
- récupération d'un objet ;
- activation de la cape ;
- lancement d'une saucisse ;
- Game Over ;
- apparition du boucher ;
- victoire.

L'audio reste secondaire par rapport au gameplay.

---

# 32. GitHub

Le projet pourra être hébergé sur GitHub.

Le `README.md` devra présenter :

1. le nom du projet ;
2. une description ;
3. le concept ;
4. les fonctionnalités ;
5. les contrôles ;
6. les assets ;
7. la roadmap ;
8. l'installation ;
9. le lancement du jeu ;
10. éventuellement des captures d'écran ou GIFs.

Le présent document sert de **base complète de conception** et pourra ensuite être condensé pour devenir un README public plus lisible.

---

# 33. Méthode de développement

Le projet doit être construit **mécanique par mécanique**.

À chaque étape :

```text
Nouvelle fonctionnalité
        ↓
Développement
        ↓
Test
        ↓
Correction
        ↓
Intégration
        ↓
Commit Git
        ↓
Fonctionnalité suivante
```

Exemples de commits :

```text
feat: add game loop
feat: add player movement
feat: add jump physics
feat: add puddle obstacle
feat: add collision detection
feat: add game over
feat: add score system
feat: add sausage projectiles
feat: add UK flag power-up
feat: add EU flag mechanic
feat: add butcher boss
```

---

# 34. Philosophie du projet

Le projet ne doit pas chercher à devenir immédiatement un gros jeu vidéo.

Le but est de créer un **petit jeu Web fini, amusant et propre**.

La règle principale :

> **Ne pas développer une mécanique complexe avant d'avoir une version jouable.**

Ordre recommandé :

```text
Faire fonctionner
       ↓
Rendre amusant
       ↓
Ajouter du contenu
       ↓
Améliorer les animations
       ↓
Ajouter les effets
       ↓
Polir l'ensemble
```

---

# 35. Ce qui différencie Boris is Peppa de Chrome Dino

Chrome Dino est uniquement une **référence de structure de gameplay**.

Le projet ne cherche pas à reproduire son univers.

Le gameplay reprend notamment :

- course automatique ;
- obstacles ;
- saut ;
- progression de vitesse ;
- score ;
- Game Over.

Mais l'identité de **Boris is Peppa** repose sur les éléments déjà créés :

- Boris ;
- les flaques ;
- les saucisses ;
- le boucher ;
- les drapeaux ;
- le fond ;
- les situations absurdes ;
- l'humour autour du Brexit ;
- les interactions entre ces éléments.

---

# 36. Vision finale

À terme, le joueur doit pouvoir ouvrir une page Web et avoir immédiatement accès à un petit jeu complet.

Concept final :

```text
                BORIS IS PEPPA
                       │
                    [ JOUER ]
                       │
                       ▼
                 Boris court
                       │
                       ▼
                   Flaques
                       │
                 ┌─────┴─────┐
                 │           │
               Saut       Drapeau
                 │           │
                 ▼           ▼
              Continue     Vole
                 │
                 ▼
              Obstacles
                 │
                 ▼
              Saucisses
                 │
                 ▼
             Boucher
                 │
                 ▼
          Phase finale / Boss
                 │
          ┌──────┴──────┐
          ▼             ▼
       Victoire       Game Over
```

---

# 37. Objectif final du projet

Créer un **véritable mini-jeu vidéo Web**, directement jouable dans un navigateur, à partir des assets graphiques déjà disponibles.

Le projet doit principalement transformer ces éléments :

```text
PNG transparents
+
Fond existant
+
Personnages existants
+
Flaques existantes
+
Saucisses existantes
+
Boucher existant
```

en :

```text
          MINI-JEU VIDÉO WEB
                  │
        ┌─────────┴─────────┐
        │                   │
     Gameplay              GUI
        │                   │
  ┌─────┼─────┐        ┌────┼────┐
  │     │     │        │    │    │
 Saut  Obst. Score    Menu HUD Game Over
  │     │     │
  └─────┼─────┘
        │
    Progression
        │
   ┌────┴────┐
   │         │
Power-ups  Saucisses
   │         │
   └────┬────┘
        │
      Boucher
        │
      Fin
```

**L'objectif n'est donc pas de créer les graphismes du jeu : ils sont déjà largement disponibles. L'objectif est de programmer le jeu qui donne vie à ces graphismes.**

---

# 38. Résumé ultra-court

**Boris is Peppa** est un mini-jeu vidéo Web inspiré du Chrome Dino.

Boris court automatiquement et doit éviter des flaques et différents obstacles. Le jeu devient progressivement plus rapide. Des saucisses sont ensuite utilisées comme projectiles et le boucher peut devenir l'adversaire final.

Des power-ups humoristiques pourront être ajoutés :

- 🇬🇧 drapeau britannique → cape / vol ;
- 🇪🇺 drapeau européen → permet de franchir une flaque et ressort sale.

La majorité des assets graphiques existent déjà en **PNG transparents**, ainsi que le fond, les flaques, les saucisses et le boucher.

Le travail consiste donc principalement à programmer :

**le moteur du jeu, les déplacements, les collisions, les obstacles, les projectiles, les power-ups, la progression, les niveaux, le score, le Game Over et la GUI.**

Le premier objectif reste volontairement simple :

> **Boris court → Boris saute → Boris évite une flaque → Boris continue.**

Puis le jeu est enrichi progressivement jusqu'à devenir un mini-jeu Web complet.
