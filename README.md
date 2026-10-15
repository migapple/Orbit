# Orbit — Apple Watch (SwiftUI natif, FR/EN)

Jeu d'arcade pour Apple Watch : la Digital Crown fait tourner un anneau à 4 couleurs,
il faut placer le segment de la même couleur sous chaque balle avant qu'elle touche l'anneau.

## Fichiers
- `OrbitApp.swift` : point d'entrée (@main), palette encre/or, écran racine
- `L10n.swift` : textes FR/EN, langue de la montre par défaut, drapeau pour basculer (mémorisé)
- `OrbitGame.swift` : logique (rotation, balles, score, vies, difficulté, record, haptiques)
- `RingView.swift` : dessin de l'anneau, du moyeu et des balles (Canvas)
- `GameView.swift` : écran de jeu, Couronne, pause, fin de partie
- `MenuView.swift` : accueil avec anneau animé, record, bouton Jouer

## Installation dans Xcode
1. File > New > Project > watchOS > App, cocher **Watch-only App**, SwiftUI, watchOS 10 minimum.
2. Product Name : `Orbit`, bundle ID suggéré : `com.michel.garlandat.orbit` (Team 1017896729).
3. Supprimer le `ContentView.swift` et le fichier `...App.swift` générés.
4. Glisser les 6 fichiers `.swift` dans la cible Watch App (Target Membership cochée).
5. Lancer sur le simulateur (la molette de la souris simule la Couronne) ou via TestFlight comme Crown Drop.

## Règles
- Couronne : tourner l'anneau
- Bonne couleur : +1 point ; mauvaise couleur : -1 vie (3 vies)
- Vitesse croissante, 2 balles à partir de 12 points, 3 à partir de 30
- Appui long : pause (aussi automatique quand on baisse le poignet)
- Drapeau : FR/EN sur l'accueil et la pause

## Réglage
`degreesPerCrownUnit` dans `GameView.swift` (6 par défaut) règle la sensibilité de la Couronne.
