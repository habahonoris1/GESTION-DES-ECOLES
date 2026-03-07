# ÉcoleApp — Gestion Scolaire

Application web de gestion scolaire moderne. Fonctionne entièrement côté client (HTML + JS + localStorage).

---

## 🚀 Déploiement Netlify

### Option 1 — Drag & Drop (le plus rapide)
1. Allez sur [app.netlify.com](https://app.netlify.com)
2. Connectez-vous / créez un compte gratuit
3. Glissez-déposez ce dossier sur la zone **"Deploy manually"**
4. Votre app est en ligne en 30 secondes ✅

### Option 2 — CLI Netlify
```bash
npm install -g netlify-cli
netlify login
netlify deploy --prod --dir .
```

---

## 🔥 Déploiement Google Firebase Hosting

### Prérequis
```bash
npm install -g firebase-tools
firebase login
```

### Étapes
```bash
# 1. Initialisez (si premier déploiement)
firebase init hosting
#   → choisissez "Use an existing project" ou créez-en un nouveau
#   → "public directory" : .  (point = dossier courant)
#   → "single-page app" : yes
#   → "overwrite index.html" : NO

# 2. Déployez
firebase deploy
```

L'URL sera du type : `https://VOTRE-PROJET.web.app`

---

## 📁 Structure des fichiers

```
├── index.html       ← Application principale (tout-en-un)
├── manifest.json    ← PWA manifest (icône, nom, thème)
├── netlify.toml     ← Config Netlify (redirects + headers)
├── firebase.json    ← Config Firebase Hosting
├── .firebaserc      ← Projet Firebase par défaut
└── README.md        ← Ce fichier
```

---

## ✅ Corrections apportées (v19)

- **Bug `CURRENT_USER`** → corrigé en `curUser` dans la page Paramètres (le générateur de licences Admin s'affiche maintenant correctement)
- **Création d'école** → `MESSAGES` et `EMPLOI_DU_TEMPS` correctement réinitialisés pour chaque nouvelle école (les données de l'école précédente ne fuient plus)
- **Compteurs** → `nextMsgId` et `nextEdtId` inclus dans le snapshot de création d'école
- **Image de fond** → le fond par défaut reste affiché après création d'une nouvelle école sans image personnalisée ; `dbLoad()` réinitialise correctement à `[]` si absent
- **PWA** → balises meta mobile complètes (Apple, Android), `manifest.json`, theme-color
- **SPA routing** → redirections configurées pour Netlify et Firebase (toutes les URLs pointent vers `index.html`)
