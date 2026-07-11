# Carnet Japon 2026

Carnet de voyage & pêche pour le Japon (novembre 2026) — application web autonome, hors-ligne (PWA), une seule page.

## Contenu

```
index.html            l'application (tout est dedans : logique + icônes SVG)
manifest.webmanifest  métadonnées PWA (nom, couleurs, icônes)
sw.js                 service worker — cache hors-ligne
icon-192.png          icône 192×192
icon-512.png          icône 512×512
```

## Mise en ligne (GitHub Pages)

1. Créer un dépôt GitHub et y déposer ces fichiers **à la racine**.
2. Repo → **Settings → Pages** → *Source* : `Deploy from a branch`, branche `main`, dossier `/root`.
3. Ouvrir l'URL fournie (`https://<user>.github.io/<repo>/`).

Le service worker et le manifeste ne fonctionnent qu'en **HTTPS** (GitHub Pages en fournit un). Sur iOS/Android : ouvrir l'URL puis « Ajouter à l'écran d'accueil » pour l'installer comme une app plein écran, utilisable hors connexion.

## Données

Les saisies (checklists, prises, notes, budget…) sont stockées **localement** dans le navigateur (localStorage / IndexedDB), liées à l'URL. Elles ne sont pas synchronisées entre appareils. Utiliser le bouton **Sauvegarde** de l'app pour exporter/importer un fichier JSON.

## Local (sans serveur)

Ouvrir `index.html` en double-cliquant fonctionne pour tout sauf le mode hors-ligne PWA (qui exige HTTPS). Pour tester le service worker en local : `npx serve` puis ouvrir `http://localhost:3000`.
