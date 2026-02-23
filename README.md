# 💳 MonCompte — Application de suivi bancaire personnel

Application mobile installable sur iPhone et Android, hébergée gratuitement sur **GitHub Pages**.  
Données stockées localement sur votre téléphone — aucune connexion requise après installation.

---

## 📱 Fonctionnalités

- ✅ Suivi mensuel : crédits, débits, solde fin reporté automatiquement
- ✅ Budget par catégorie avec barre de progression
- ✅ Historique multi-années (+ bouton pour ajouter des années)
- ✅ Glisser gauche/droite pour changer de mois
- ✅ Export / Import JSON (sauvegarde)
- ✅ Mise à jour automatique via GitHub
- ✅ Fonctionne hors ligne (PWA)

---

## 🚀 Mise en place sur GitHub (5 minutes)

### Étape 1 — Créer un compte GitHub
Si vous n'en avez pas : https://github.com/signup

### Étape 2 — Créer un nouveau dépôt
1. Allez sur https://github.com/new
2. Nom du dépôt : `moncompte` (ou ce que vous voulez)
3. Visibilité : **Public** (obligatoire pour GitHub Pages gratuit)
4. Cliquez **Create repository**

### Étape 3 — Uploader les fichiers
Dans votre nouveau dépôt :
1. Cliquez **Add file → Upload files**
2. Déposez **tous les fichiers** de ce dossier :
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - Le dossier `icons/` (avec toutes les icônes)
3. Cliquez **Commit changes**

### Étape 4 — Activer GitHub Pages
1. Allez dans **Settings** (onglet en haut du dépôt)
2. Menu gauche : **Pages**
3. Source : **Deploy from a branch**
4. Branch : **main** → dossier **(root)**
5. Cliquez **Save**

⏳ Attendez 1-2 minutes, puis votre app est disponible à :
```
https://VOTRE_NOM_GITHUB.github.io/moncompte/
```

### Étape 5 — Installer sur votre téléphone

**iPhone (Safari uniquement) :**
1. Ouvrez l'URL ci-dessus dans Safari
2. Appuyez sur le bouton Partager 📤
3. → « Sur l'écran d'accueil »
4. → Ajouter
5. L'icône MonCompte apparaît sur votre écran d'accueil 🎉

**Android (Chrome) :**
1. Ouvrez l'URL dans Chrome
2. Bandeau « Ajouter à l'écran d'accueil » → Installer
3. Ou : menu ⋮ → « Installer l'application »

---

## 🔄 Mettre à jour l'application

### Méthode simple (sur GitHub.com)
1. Allez dans votre dépôt sur GitHub
2. Cliquez sur le fichier à modifier (`index.html` pour l'app, `sw.js` pour la version)
3. Cliquez sur ✏️ (crayon) pour éditer
4. Faites vos modifications
5. Cliquez **Commit changes**
6. ⚡ GitHub Pages se met à jour automatiquement en ~1 minute

### ⚠️ Important : incrémenter la version
À chaque mise à jour, modifiez dans `sw.js` :
```javascript
const VERSION = '1.0.1';  // changer à chaque update
```
Et dans `index.html` :
```javascript
const APP_VERSION = '1.0.1';
```
Cela force le rechargement de l'app sur les téléphones déjà installés.

### Méthode avancée (Git en ligne de commande)
```bash
git clone https://github.com/VOTRE_NOM/moncompte.git
cd moncompte
# ... faites vos modifications ...
git add .
git commit -m "Mise à jour v1.0.1"
git push
```

---

## 🗂️ Structure des fichiers
```
moncompte/
├── index.html      ← Application principale (toute la logique)
├── manifest.json   ← Configuration PWA (nom, icônes, couleurs)
├── sw.js           ← Service Worker (cache offline + mises à jour)
├── README.md       ← Ce fichier
└── icons/
    ├── icon-72.png
    ├── icon-96.png
    ├── icon-128.png
    ├── icon-144.png
    ├── icon-152.png
    ├── icon-192.png
    ├── icon-384.png
    └── icon-512.png
```

---

## 💾 Données & confidentialité

- Toutes les données sont stockées dans le `localStorage` de votre navigateur
- **Aucune donnée n'est envoyée sur internet**
- Exportez régulièrement vos données (Réglages → Exporter) pour éviter toute perte
- En cas de changement de téléphone : exportez, réinstallez l'app, importez

---

## ❓ Questions fréquentes

**Mes données disparaissent si j'efface le cache ?**  
Oui. Exportez régulièrement vos données depuis l'onglet Réglages.

**Puis-je utiliser l'app sans installer GitHub ?**  
Oui, ouvrez simplement `index.html` dans Safari ou Chrome sur votre téléphone. Mais les mises à jour seront manuelles.

**L'app fonctionne-t-elle sans internet ?**  
Oui, une fois installée, elle fonctionne complètement hors ligne.

---

## 📝 Licence
Usage personnel libre.
