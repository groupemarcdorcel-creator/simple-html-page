# simple-html-page

Un set de templates HTML harmonisés pour un mini site e-commerce (accessibles, réutilisables).

---
## Blocs harmonisés à réutiliser dans TOUTES les pages

Pour garantir l’uniformité graphique, l’accessibilité et la maintenabilité, tous les fichiers HTML doivent réutiliser les trois blocs suivants depuis `template-harmonized.html`:

1) Header / Nav
- Rôle: navigation principale, identique sur toutes les pages
- ARIA: `role="navigation"` et `aria-label="Navigation principale"`
- Contenu variable minimal (URLs) mais structure et classes inchangées

2) Fil d’Ariane (Breadcrumb)
- Rôle: situer l’utilisateur dans l’arborescence
- ARIA: `<nav aria-label="Fil d’Ariane">` + `<ol>`
- Même structure; n’adapter que les éléments de la liste selon la page

3) Footer
- Rôle: informations globales, liens utilitaires, newsletter
- Identique sur toutes les pages, mêmes classes et hiérarchie

Copier/coller ces blocs tels quels pour chaque page, puis modifier uniquement les textes et URLs nécessaires. Conserver les classes, rôles ARIA et ordre des éléments.

---
## Templates disponibles dans `template-harmonized.html`

Le fichier contient 3 templates prêts à l’emploi. Pour créer une page, dupliquez le fichier et conservez uniquement le `<main>` du template visé (supprimez les autres), tout en gardant les blocs communs Header, Breadcrumb et Footer.

- Template Home (`#home-template`)
  - Sections: Hero, Produits en vedette (cartes produits harmonisées), Catégories (cartes catégories), Blog (optionnel)
  - Objectif: présentation générale, mise en avant

- Template Catégorie (`#category-template`)
  - À activer en remplaçant le H1 par le nom de la catégorie et en mettant à jour le breadcrumb: Accueil > Catégories > Nom Catégorie
  - Grille de produits: réutilise la même carte `.product-card` que la Home
  - Inclut un toolbar tri/pagination (markup prêt)

- Template Produit (`#product-template`)
  - Breadcrumb: Accueil > Catégories > Nom Catégorie > Nom Produit
  - Layout: galerie, infos produit, buy-box, points forts et onglets détails/caractéristiques/livraison

Chaque composant (cartes, boutons, badges, grilles) utilise les mêmes classes afin de garantir l’harmonie visuelle via `styles.css`.

---
## Bonnes pratiques (à respecter)

- Sémantique: conserver `header`, `nav`, `main`, `section`, `footer`, etc.
- Accessibilité: aria-labels, roles, ordre logique, textes alternatifs pour les images
- Performances: attribut `loading="lazy"` sur les images non critiques
- Uniformité: ne pas renommer les classes harmonisées; n’ajouter que des classes utilitaires si nécessaire

---
## Fichiers clés

- `template-harmonized.html`: source de vérité pour les blocs Header/Breadcrumb/Footer et les 3 templates (Home/Catégorie/Produit). Contient des commentaires expliquant l’usage et les zones à personnaliser.
- `styles.css`: style global harmonisé, support des composants (.card, .grid, .btn, .badge, etc.).
- `index.html`, `categories/…`, `produits/…`: doivent réutiliser les blocs et patrons issus de `template-harmonized.html`.

---
## Liens de test public
- Accueil: https://groupemarcdorcel-creator.github.io/simple-html-page/
- Catégorie 1: https://groupemarcdorcel-creator.github.io/simple-html-page/categories/categorie1.html
- Produit 1: https://groupemarcdorcel-creator.github.io/simple-html-page/produits/produit1.html
- Blog: https://groupemarcdorcel-creator.github.io/simple-html-page/blog/index.html
- Premier article: https://groupemarcdorcel-creator.github.io/simple-html-page/blog/article1.html
- Template harmonisé: https://groupemarcdorcel-creator.github.io/simple-html-page/template-harmonized.html

---
## Changelog
- Harmonisation: ajout blocs Header/Nav, Breadcrumb, Footer + templates Home/Catégorie/Produit + consignes d’utilisation
