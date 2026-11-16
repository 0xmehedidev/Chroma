# Chroma — Détecteur de couleurs / Color detector

[🇫🇷 Français](#-français) · [🇬🇧 English](#-english)

---

## 🇫🇷 Français

**Chroma** est une application web mobile qui identifie les codes couleurs des objets réels. Prends un objet en photo ou importe une image, touche la zone qui t'intéresse : Chroma affiche instantanément la couleur dans tous les formats utiles, ainsi que les références Pantone et RAL les plus proches.

### Fonctionnalités

- **Photo ou import** : ouverture directe de l'appareil photo arrière, ou import depuis la galerie (glisser-déposer et collage pris en charge sur ordinateur).
- **Pipette de précision** : loupe de zoom sous le doigt, mesure sur 1 px ou moyenne sur une zone de 5×5 ou 11×11 pixels pour lisser le bruit de l'appareil photo.
- **Codes numériques** : HEX, RGB, HSL, HSV, CMJN et décimal, copiables d'un geste.
- **Nom de la couleur** : nom français le plus proche (Bordeaux, Vert sauge, Bleu pétrole…).
- **Correspondances nuanciers** :
  - **Pantone Coated (PMS)** : 1 341 teintes, pour l'impression, le packaging et les goodies ;
  - **Pantone TCX** : 2 800 teintes, pour le textile, les vêtements et la déco ;
  - **RAL Classic** : 215 teintes, pour la peinture, le métal, le plastique et l'architecture.

  Chaque correspondance affiche la référence la plus proche, deux alternatives et un indice de fiabilité basé sur l'écart colorimétrique ΔE2000 (Excellent < 2, Bon < 5, Approximatif < 10, Éloigné au-delà).
- **Couleurs dominantes** : extraction automatique de la palette principale de l'image (k-means), avec la part de chaque couleur.
- **Mes couleurs** : historique des couleurs enregistrées, stocké localement sur l'appareil.

### Utilisation

1. Ouvre le site sur ton téléphone.
2. Appuie sur **Prendre une photo** ou **Importer une image**.
3. Touche ou glisse sur l'image pour viser la couleur.
4. Touche un code ou une référence pour la copier, ou **Copier tout** pour récupérer l'ensemble.

### Limites

- La couleur mesurée dépend de l'éclairage, de la balance des blancs et de l'appareil photo. Pour des valeurs fidèles, photographie l'objet à la lumière du jour, sans flash.
- Les références Pantone et RAL proviennent de tables d'équivalences publiques, et non des données officielles Pantone (sous licence). Elles indiquent la teinte la plus proche : valide toujours avec un nuancier physique ou un colorimètre avant une production.
- Le CMJN est une conversion mathématique simple, sans profil ICC. Pour un fichier d'impression, reconvertis la couleur dans ton logiciel de PAO avec le profil de ton imprimeur.

### Technique

- Un seul fichier HTML autonome (`chroma.html`) : HTML, CSS et JavaScript natifs, sans framework ni serveur.
- Aucune donnée n'est envoyée : les images sont analysées directement dans le navigateur.
- Le fichier `_redirects` fait servir `chroma.html` à l'adresse racine du site sur Netlify.

### Déploiement sur Netlify

1. Mets `chroma.html`, `README.md` et `_redirects` dans un même dossier.
2. Glisse ce dossier sur [app.netlify.com/drop](https://app.netlify.com/drop), ou, pour un site existant, dans l'onglet **Deploys**.

---

## 🇬🇧 English

**Chroma** is a mobile web app that identifies the color codes of real-world objects. Take a photo of an object or upload an image, tap the area you're interested in: Chroma instantly shows the color in every useful format, along with the closest Pantone and RAL references.

### Features

- **Photo or upload**: opens the rear camera directly, or imports from the gallery (drag-and-drop and paste supported on desktop).
- **Precision picker**: zoom loupe under your finger, sampling a single pixel or averaging a 5×5 or 11×11 area to smooth out camera noise.
- **Digital codes**: HEX, RGB, HSL, HSV, CMYK and decimal, copied with a single tap.
- **Color name**: closest French color name (Bordeaux, Vert sauge, Bleu pétrole…).
- **Color system matching**:
  - **Pantone Coated (PMS)**: 1,341 shades, for print, packaging and promotional items;
  - **Pantone TCX**: 2,800 shades, for textiles, apparel and home decor;
  - **RAL Classic**: 215 shades, for paint, metal, plastic and architecture.

  Each match shows the closest reference, two alternatives and a reliability score based on the ΔE2000 color difference (Excellent < 2, Good < 5, Approximate < 10, Far beyond that).
- **Dominant colors**: automatic extraction of the image's main palette (k-means), with each color's share.
- **My colors**: history of saved colors, stored locally on the device.

### How to use

1. Open the site on your phone.
2. Tap **Prendre une photo** (take a photo) or **Importer une image** (upload an image).
3. Tap or drag over the image to target a color.
4. Tap a code or reference to copy it, or **Copier tout** (copy all) to get everything.

### Limitations

- The measured color depends on lighting, white balance and the camera. For accurate values, photograph the object in daylight, without flash.
- Pantone and RAL references come from public equivalence tables, not official Pantone data (which is licensed). They indicate the closest shade: always check against a physical swatch book or a colorimeter before production.
- CMYK is a simple mathematical conversion, without an ICC profile. For print files, convert the color again in your desktop publishing software using your printer's profile.

### Technical details

- A single self-contained HTML file (`chroma.html`): plain HTML, CSS and JavaScript, no framework, no server.
- No data is sent anywhere: images are analyzed directly in the browser.
- The `_redirects` file makes Netlify serve `chroma.html` at the site's root URL.

### Deploying to Netlify

1. Put `chroma.html`, `README.md` and `_redirects` in the same folder.
2. Drag that folder onto [app.netlify.com/drop](https://app.netlify.com/drop), or, for an existing site, into the **Deploys** tab.

---

## Sources des données / Data sources

- RAL Classic : npm package [`ral-colors`](https://www.npmjs.com/package/ral-colors) (MIT)
- Pantone Coated : [Pantoner](https://github.com/jpederson/Pantoner) (MIT)
- Pantone TCX : npm package [`pantone-tcx`](https://www.npmjs.com/package/pantone-tcx) (ISC)

Pantone® et RAL® sont des marques déposées de leurs propriétaires respectifs. Chroma n'est affilié à aucune de ces sociétés.
Pantone® and RAL® are registered trademarks of their respective owners. Chroma is not affiliated with either company.
