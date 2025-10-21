# Guide d'Harmonisation des Styles

## Vue d'ensemble

Ce guide documente le système de style harmonisé créé pour le site e-commerce. Une feuille de style globale `styles.css` a été créée avec une palette de couleurs unifiée, la police Poppins, et des composants standardisés.

## 🎨 Palette de Couleurs

### Couleurs Principales
- **Bleu foncé (Principal)**: `#1e3a8a` - Utilisé pour les titres, header, boutons primaires
- **Orange (Secondaire)**: `#f97316` - Utilisé pour les accents, boutons secondaires, prix
- **Gris clair (Fond)**: `#f1f5f9` - Fond de page
- **Blanc (Cartes)**: `#ffffff` - Fond des cartes et composants
- **Texte principal**: `#1e293b`
- **Texte secondaire**: `#64748b`
- **Bordures**: `#e2e8f0`

### Variables CSS
```css
:root {
  --color-primary: #1e3a8a;
  --color-secondary: #f97316;
  --color-light-bg: #f1f5f9;
  --color-white: #ffffff;
  --color-text: #1e293b;
  --color-text-muted: #64748b;
  --color-border: #e2e8f0;
}
```

## 🔤 Typographie

### Police
- **Famille**: Poppins (Google Fonts)
- **Poids**: 300 (Light), 400 (Regular), 600 (Semi-Bold), 700 (Bold)
- Import: `@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap');`

### Tailles de Titres
```css
h1 { font-size: 2.5rem; }      /* 40px */
h2 { font-size: 2rem; }        /* 32px */
h3 { font-size: 1.5rem; }      /* 24px */
h4 { font-size: 1.25rem; }     /* 20px */
h5 { font-size: 1.125rem; }    /* 18px */
h6 { font-size: 1rem; }        /* 16px */
```

## 📦 Composants Standardisés

### Cards (Produits, Catégories, Blog)
```html
<div class="card">
  <img src="image.jpg" class="card-image" alt="Description">
  <div class="card-content">
    <h3 class="card-title">Titre</h3>
    <p class="card-text">Description...</p>
    <div class="card-footer">
      <a href="#" class="btn btn-primary">Action</a>
    </div>
  </div>
</div>
```

### Boutons
```html
<!-- Bouton primaire (bleu) -->
<button class="btn btn-primary">Acheter</button>

<!-- Bouton secondaire (orange) -->
<button class="btn btn-secondary">Ajouter au panier</button>

<!-- Bouton outline -->
<button class="btn btn-outline">Voir plus</button>
```

### Grilles de Produits
```html
<div class="products-grid">
  <!-- Les cards s'adaptent automatiquement -->
  <div class="card">...</div>
  <div class="card">...</div>
  <div class="card">...</div>
</div>
```

## 📝 Intégration dans les Pages HTML

### Étape 1: Lier le fichier styles.css
Ajoutez cette ligne dans la section `<head>` de chaque page HTML:

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Votre Page</title>
  
  <!-- Feuille de style globale harmonisée -->
  <link rel="stylesheet" href="/styles.css">
  
  <!-- OU pour les sous-dossiers: -->
  <link rel="stylesheet" href="../styles.css">
</head>
```

### Étape 2: Chemins relatifs selon la structure

- **index.html** (racine): `<link rel="stylesheet" href="styles.css">`
- **categories/categorie1.html**: `<link rel="stylesheet" href="../styles.css">`
- **produits/produit1.html**: `<link rel="stylesheet" href="../styles.css">`
- **blog/index.html**: `<link rel="stylesheet" href="../styles.css">`
- **blog/article1.html**: `<link rel="stylesheet" href="../styles.css">`

## 🎨 Structure HTML Recommandée

### Template de Base
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Page Title</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <!-- Header -->
  <header>
    <nav>
      <div class="container">
        <a href="/" class="nav-brand">Boutique</a>
        <ul class="nav-links">
          <li><a href="/" class="nav-link">Accueil</a></li>
          <li><a href="/categories/" class="nav-link">Catégories</a></li>
          <li><a href="/produits/" class="nav-link">Produits</a></li>
          <li><a href="/blog/" class="nav-link">Blog</a></li>
        </ul>
      </div>
    </nav>
  </header>

  <!-- Contenu principal -->
  <main>
    <div class="container section">
      <h1>Titre de la page</h1>
      
      <!-- Grille de produits -->
      <div class="products-grid">
        <div class="card">
          <img src="image.jpg" class="card-image" alt="Produit">
          <div class="card-content">
            <h3 class="card-title">Nom du produit</h3>
            <p class="card-text">Description du produit</p>
            <div class="product-price">29,99 €</div>
            <div class="card-footer">
              <button class="btn btn-primary">Ajouter au panier</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>

  <!-- Footer -->
  <footer>
    <div class="container">
      <div class="footer-content">
        <div>
          <h3>À propos</h3>
          <p>Informations sur la boutique</p>
        </div>
        <div>
          <h3>Liens rapides</h3>
          <ul>
            <li><a href="#">Mentions légales</a></li>
            <li><a href="#">CGV</a></li>
            <li><a href="#">Contact</a></li>
          </ul>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2025 Boutique E-commerce. Tous droits réservés.</p>
      </div>
    </div>
  </footer>
</body>
</html>
```

## 📱 Responsive Design

Le système de style est entièrement responsive avec 3 breakpoints:

- **Mobile**: < 480px (1 colonne)
- **Tablet**: 480px - 768px (2 colonnes)
- **Desktop**: > 768px (3-4 colonnes)

Les grilles s'adaptent automatiquement:
```css
.products-grid,
.categories-grid,
.blog-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: var(--spacing-md);
}
```

## ✅ Checklist d'Harmonisation

Pour harmoniser une page existante:

1. ☐ Ajouter `<link rel="stylesheet" href="styles.css">` dans le `<head>`
2. ☐ Remplacer les styles inline par les classes standard
3. ☐ Utiliser `.card` pour tous les composants produits/catégories/blog
4. ☐ Remplacer les boutons par `.btn .btn-primary` ou `.btn-secondary`
5. ☐ Utiliser `.container` pour le contenu centré
6. ☐ Utiliser `.section` pour l'espacement vertical
7. ☐ Appliquer `.products-grid` / `.categories-grid` / `.blog-grid` pour les listes
8. ☐ Vérifier le responsive sur mobile/tablet/desktop

## 🛠️ Classes Utilitaires

```css
.text-center     /* Centrer le texte */
.text-muted      /* Texte secondaire */
.mb-sm, .mb-md, .mb-lg   /* Marges en bas */
.mt-sm, .mt-md, .mt-lg   /* Marges en haut */
```

## 📝 Exemple: Page Produit

```html
<div class="container section">
  <h1>Nos Produits</h1>
  <p class="text-muted mb-lg">Découvrez notre sélection</p>
  
  <div class="products-grid">
    <div class="card">
      <img src="produit1.jpg" class="card-image" alt="Produit 1">
      <div class="card-content">
        <span class="badge badge-new">Nouveau</span>
        <h3 class="card-title">Sneakers Alpha</h3>
        <p class="card-text">Chaussures confortables et élégantes</p>
        <div class="product-price">
          69,90 €
          <span class="product-price-old">89,90 €</span>
        </div>
        <div class="card-footer">
          <button class="btn btn-primary">Ajouter au panier</button>
        </div>
      </div>
    </div>
    <!-- Répéter pour d'autres produits -->
  </div>
</div>
```

## 🌟 Résumé des Avantages

✅ **Cohérence visuelle**: Toutes les pages utilisent la même palette et typographie
✅ **Maintenabilité**: Un seul fichier CSS à modifier pour tout le site
✅ **Performance**: Moins de code dupliqué, fichier CSS mis en cache
✅ **Responsive**: S'adapte automatiquement à tous les écrans
✅ **Accessibilité**: Focus states, contrastes appropriés

## 📄 Prochaines Étapes

1. Ajouter le lien vers `styles.css` dans chaque fichier HTML:
   - `index.html`
   - `categories/categorie1.html`
   - `produits/produit1.html`
   - `blog/index.html`
   - `blog/article1.html`

2. Remplacer les styles inline par les classes standard

3. Tester le responsive design sur différentes tailles d'écran

4. Valider la cohérence visuelle entre toutes les pages

---

**Fichier créé**: `styles.css` (dans la racine du projet)
**Date**: 2025
**Objectif**: Harmoniser l'apparence de toutes les pages du site e-commerce
