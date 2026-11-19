# saharahub — DESIGN.md (site web)

Direction : **startup tech, claire et confiante**. Fond blanc, beaucoup d'air, une seule couleur d'action (Bleu Data), l'orange réservé aux touches « Sahara », des sections sombres « Nuit » pour rythmer. Le motif signature est celui du logo : des **lignes de données qui s'affinent en montant** et les **demi-disques**.
Basé sur l'identité validée (logo « Data Dune · Dissolve ») — pas sur une comparaison de sites existants (outil UXKIN non connecté).

## Couleur
| Token | Valeur | Rôle |
|---|---|---|
| `--ink` | #0B1026 | texte principal, fonds des sections sombres |
| `--ink-2` | #2A3050 | titres secondaires |
| `--muted` | #4A5072 | texte secondaire (7,9:1 sur blanc) |
| `--line` | #E2E4EE | bordures, séparateurs |
| `--surface` | #F5F6FA | fonds de cartes et bandes claires |
| `--sand` | #FFF6EE | fond chaleureux ponctuel (section « Pourquoi nous ») |
| `--bg` | #FFFFFF | fond de page |
| `--primary` | #3B5BFF | boutons, liens, focus (5,1:1 sur blanc) |
| `--primary-hover` | #2C47E0 | survol des boutons |
| `--primary-on-dark` | #6E86FF | liens et accents sur `--ink` (5,8:1) |
| `--accent` | #FF7A30 | demi-disque, puces, petits accents graphiques — jamais du texte sur blanc |
| `--success` / `--warning` / `--error` | #12A150 / #E08600 / #D93A3F | états de formulaire |

Pas de mode sombre global : le site alterne sections claires et sections `--ink`. Pas de dégradé violet, pas de verre dépoli.

## Typographie
- **Latin** : titres **Poppins** 600/700 (la police du logo), texte **Inter** 400/500/600.
- **Arabe** : titres **Readex Pro** 500/700, texte **IBM Plex Sans Arabic** 400/500. (Janna LT demandée : police commerciale, non disponible librement — remplaçable si la licence est achetée.)
- Échelle (px / interligne) : 14/1.5 · 16/1.6 (corps) · 18/1.6 (intro) · 22/1.35 · 28/1.25 · 40/1.15 · 56/1.05 · 72/1.0 (h1 desktop). Mobile : h1 40.
- Lignes de 60 à 72 caractères ; arabe : interligne +0,15.

## Espacement et mise en page
- Échelle 8 px : 4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 96 · 128.
- Sections : 128 px haut/bas desktop, 72 px mobile. Contenu max 1200 px, marges 24 px mobile / 40 px desktop.
- Grille 12 colonnes desktop, 1 colonne < 768 px. Mise en page miroir automatique en arabe (`dir="rtl"`, propriétés logiques CSS).

## Forme et profondeur
- Rayons : 8 (champs, badges) · 14 (boutons, cartes) · 24 (grands panneaux, maquettes).
- Ombres : une seule, `0 12px 32px -12px rgb(11 16 38 / .18)`, pour les maquettes d'interface. Les cartes ont une bordure `--line`, pas d'ombre.

## Composants
- **Bouton primaire** : fond `--primary`, texte blanc, 48 px de haut, rayon 14 ; survol `--primary-hover` + 1 px vers le haut ; clic : retour à 0 ; focus : anneau 3 px `--primary` à 30 %, décalé de 2 px ; désactivé : 40 % d'opacité.
- **Bouton secondaire** : contour 1,5 px `--ink`, texte `--ink` ; sur fond sombre : contour et texte blancs.
- **Bouton discret** : texte `--primary` + flèche, soulignement qui se dessine au survol.
- **Liens** : `--primary`, soulignés au survol.
- **Champs** : 48 px, bordure `--line`, rayon 8, libellé visible au-dessus, erreur sous le champ en `--error`.
- **Cartes** : fond `--bg` ou `--surface`, bordure `--line`, rayon 14, lien entier qui se soulève de 2 px au survol.
- **Navigation** : barre fixe blanche, logo à gauche (à droite en arabe), liens, sélecteur FR · ع · EN, bouton primaire ; menu plein écran sur mobile.
- **Pied de page** : fond `--ink`, logo version sombre, coordonnées, liens, langues.

## Images et icônes
- Pas de photos d'équipe fictives. Visuels = maquettes d'interface en HTML (tableau de bord, jeu éducatif, plateforme), et captures réelles des projets dès que le client les fournit.
- Icônes : un seul jeu linéaire (trait 1,75 px, coins arrondis), couleur `--ink` ou `--primary`.
- Motif graphique : lignes horizontales qui s'affinent (comme le logo) en fond de hero et de séparateurs ; demi-disques orange en ponctuation.
- Animation : le logo du hero se dessine ligne par ligne au chargement ; survols discrets ; tout s'arrête avec `prefers-reduced-motion`.
