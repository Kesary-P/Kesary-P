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

### CSS : du code au résultat

<table>
<tr>
<th>Extrait réel de <code>styles.less</code></th>
<th>Résultat mobile</th>
</tr>
<tr>
<td valign="top"><pre><code>@media (max-width: @tablet) {
  .hero {
    width: min(calc(100% - 32px), 680px);
    grid-template-columns: 1fr;
    padding: 22px 16px 16px;
    border-radius: 24px;

    &gt; img:nth-child(2) {
      order: 3;
      width: 100%;
      border-radius: 20px;
    }
  }
}</code></pre></td>
<td valign="top"><img src="https://raw.githubusercontent.com/Kesary-P/echappees-voyage/main/docs/maquettes/accueil-mobile.png" alt="Mise en page mobile obtenue avec CSS et les media queries" width="360"></td>
</tr>
</table>

La media query détecte un écran plus étroit. La grille passe alors à une seule colonne, les espacements diminuent et l’image prend toute la largeur disponible. La structure HTML reste identique : seules les règles CSS transforment la présentation.

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

### JavaScript : du code à l’interaction

<table>
<tr>
<th>Extrait réel de <code>script.js</code></th>
<th>Résultat après le clic</th>
</tr>
<tr>
<td valign="top"><pre><code>const dialog = document.querySelector(
  '#planner-dialog'
);

document
  .querySelectorAll('[data-open-planner]')
  .forEach((button) =&gt;
    button.addEventListener('click', () =&gt;
      dialog.showModal()
    )
  );

dialog
  .querySelector(':scope &gt; button:first-child')
  .addEventListener('click', () =&gt; dialog.close());</code></pre></td>
<td valign="top"><img src="https://raw.githubusercontent.com/Kesary-P/echappees-voyage/main/docs/maquettes/javascript-formulaire-itineraire.png" alt="Formulaire d’itinéraire ouvert avec JavaScript" width="520"></td>
</tr>
</table>

Le script sélectionne la fenêtre modale, écoute le clic sur les boutons « Préparer mon voyage », puis appelle `showModal()`. Un second gestionnaire permet de refermer la fenêtre avec `close()`, sans recharger la page.

## GitHub et mise en ligne

Le projet est versionné avec Git. GitHub Actions publie automatiquement la branche principale sur GitHub Pages après chaque mise à jour validée.

Ce processus montre un cycle complet : **concevoir → développer → vérifier → documenter → versionner → déployer**.

## Technologies

`HTML5` · `CSS3` · `LESS` · `JavaScript` · `Responsive design` · `Git` · `GitHub Actions` · `GitHub Pages`
