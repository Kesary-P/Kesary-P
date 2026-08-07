# Site statique : Échappées

[← Développement web](developpement-web.md) · [Voir le site](https://kesary-p.github.io/echappees-voyage/) · [Voir le code](https://github.com/Kesary-P/echappees-voyage)

## Objectif

Échappées est un carnet de voyage interactif composé d’une page d’accueil, d’une page Contact et d’une page consacrée à Lisbonne. Le projet montre le passage de la conception responsive à l’intégration, puis au déploiement public.

## Captures de l’interface

### Accueil

| Desktop — 1440 × 1080 | Mobile — 390 × 844 |
| --- | --- |
| ![Accueil Échappées sur desktop](https://raw.githubusercontent.com/Kesary-P/echappees-voyage/main/docs/maquettes/accueil-desktop.png) | ![Accueil Échappées sur mobile](https://raw.githubusercontent.com/Kesary-P/echappees-voyage/main/docs/maquettes/accueil-mobile.png) |

### Contact

| Desktop — 1440 × 1080 | Mobile — 390 × 844 |
| --- | --- |
| ![Page Contact sur desktop](https://raw.githubusercontent.com/Kesary-P/echappees-voyage/main/docs/maquettes/contact-desktop.png) | ![Page Contact sur mobile](https://raw.githubusercontent.com/Kesary-P/echappees-voyage/main/docs/maquettes/contact-mobile.png) |

### Lisbonne Solaire

| Desktop — 1440 × 1080 | Mobile — 390 × 844 |
| --- | --- |
| ![Page Lisbonne Solaire sur desktop](https://raw.githubusercontent.com/Kesary-P/echappees-voyage/main/docs/maquettes/lisbonne-desktop.png) | ![Page Lisbonne Solaire sur mobile](https://raw.githubusercontent.com/Kesary-P/echappees-voyage/main/docs/maquettes/lisbonne-mobile.png) |

## HTML5 : structurer le contenu

Le HTML organise chaque page avec des éléments sémantiques comme `header`, `nav`, `main`, `section`, `article`, `form` et `footer`. Cette structure rend le contenu plus compréhensible pour le navigateur, les technologies d’assistance et les moteurs de recherche.

J’ai également utilisé des libellés de formulaire, des textes alternatifs pour les images et des attributs ARIA lorsque le comportement interactif le nécessite.

## CSS3 et LESS : construire l’interface

Le CSS traduit l’identité visuelle de la maquette : couleurs, typographies, espacements, cartes, boutons et hiérarchie des contenus.

Les principales techniques utilisées sont :

- Flexbox et CSS Grid pour organiser les composants ;
- media queries pour adapter la navigation et la mise en page aux petits écrans ;
- variables et règles LESS pour centraliser les choix graphiques et faciliter la maintenance ;
- états visuels pour les boutons, liens, favoris et éléments sélectionnés ;
- dimensions fluides, espacements cohérents et images adaptées à leur conteneur.

L’objectif n’est pas seulement d’obtenir un rendu esthétique : la feuille de styles doit rester lisible, réutilisable et prévisible sur desktop comme sur mobile.

### Capture — résultat du CSS responsive

![Mise en page mobile obtenue avec CSS et les media queries](https://raw.githubusercontent.com/Kesary-P/echappees-voyage/main/docs/maquettes/accueil-mobile.png)

Sur cette capture, le CSS adapte la largeur des blocs, empile les contenus, réduit la navigation et conserve des zones tactiles suffisamment grandes. La même page HTML est utilisée : ce sont les règles CSS et les media queries qui transforment sa présentation.

### Ce que les captures permettent d’observer

- **Desktop** : navigation horizontale, contenu réparti en colonnes et espace visuel plus généreux ;
- **Mobile** : menu réduit, sections empilées et boutons dimensionnés pour une utilisation tactile ;
- **Cohérence** : mêmes couleurs, typographies, arrondis et niveaux d’information sur les deux formats ;
- **Responsive design** : la composition change sans dupliquer le contenu HTML.

## JavaScript : ajouter les interactions

JavaScript est utilisé côté navigateur pour gérer :

- l’ouverture et la fermeture du menu mobile ;
- le filtrage des destinations ;
- les favoris ;
- le choix aléatoire d’une destination ;
- l’ouverture et la validation du formulaire d’itinéraire.

Ces fonctionnalités démontrent la manipulation du DOM, la gestion des événements et la mise à jour de l’interface selon les actions de l’utilisateur.

### Capture — interaction JavaScript

![Formulaire d’itinéraire ouvert avec JavaScript](https://raw.githubusercontent.com/Kesary-P/echappees-voyage/main/docs/maquettes/javascript-formulaire-itineraire.png)

Le clic sur « Préparer mon voyage » déclenche JavaScript, qui ouvre cette fenêtre modale. Le script gère aussi sa fermeture, les champs du formulaire, la validation et le message de confirmation sans charger une nouvelle page.

## GitHub et mise en ligne

Le projet est versionné avec Git. GitHub Actions publie automatiquement la branche principale sur GitHub Pages après chaque mise à jour validée.

Ce processus montre un cycle complet : **concevoir → développer → vérifier → documenter → versionner → déployer**.

## Technologies

`HTML5` · `CSS3` · `LESS` · `JavaScript` · `Responsive design` · `Git` · `GitHub Actions` · `GitHub Pages`
