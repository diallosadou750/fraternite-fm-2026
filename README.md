# 📻 Radio Fraternité FM Mamou — Site Web

## 🚀 MISE EN LIGNE EN 4 ÉTAPES (20 minutes)

---

### ÉTAPE 1 — Créer un compte GitHub (gratuit)
1. Allez sur **github.com** → "Sign up"
2. Choisissez un nom d'utilisateur (ex: `fraternitefm`)
3. Vérifiez votre email
4. Créez un **nouveau dépôt** (repository) :
   - Cliquez "New repository"
   - Nom : `fraternite-fm`
   - Visibilité : **Public** ✅
   - Cliquez "Create repository"
5. Uploadez **tous les fichiers** de ce dossier dans le dépôt
   (glissez-déposez les fichiers sur la page GitHub)

---

### ÉTAPE 2 — Déployer sur Netlify (gratuit)
1. Allez sur **netlify.com** → "Sign up with GitHub"
2. Cliquez "Add new site" → "Import an existing project"
3. Choisissez **GitHub** → sélectionnez votre dépôt `fraternite-fm`
4. Laissez tout par défaut → cliquez **"Deploy site"**
5. ✅ Votre site est en ligne en 2 minutes !
6. Notez votre URL (ex: `https://fraternite-fm.netlify.app`)

---

### ÉTAPE 3 — Configurer l'accès à l'éditeur (Decap CMS)

**3a. Créer une OAuth App GitHub**
1. Sur GitHub : Settings → Developer settings → OAuth Apps → "New OAuth App"
2. Remplissez :
   - Application name : `Fraternité FM CMS`
   - Homepage URL : `https://votre-site.netlify.app`
   - Authorization callback URL : `https://sveltia-cms-auth.netlify.app/callback`
3. Cliquez "Register application"
4. Notez le **Client ID** et générez un **Client Secret**

**3b. Mettre à jour le fichier config.yml**
- Ouvrez `admin/config.yml` sur GitHub
- Remplacez `VOTRE_USERNAME/fraternite-fm` par votre vrai pseudo GitHub et nom du dépôt
- Ex : `repo: fraternitefm/fraternite-fm`
- Sauvegardez → Netlify redéploie automatiquement

---

### ÉTAPE 4 — Accéder à l'éditeur d'articles
Allez sur : **`https://votre-site.netlify.app/admin/`**

Connectez-vous avec votre compte GitHub → vous avez accès à l'éditeur complet !

---

## ✏️ PUBLIER UN ARTICLE (quotidien)

1. Allez sur `votre-site.netlify.app/admin/`
2. Cliquez **"📰 Articles & Actualités"** → **"New Articles"**
3. Remplissez : Titre, Catégorie, Date, Icône, Résumé
4. Cliquez **"Publish"** (bouton en haut à droite)
5. ✅ L'article apparaît sur le site en 30 secondes !

### L'éditeur vous permet aussi de :
- **Modifier** les programmes radio (horaires, animateurs)
- **Mettre à jour** les fiches de l'équipe
- **Supprimer** les anciens articles
- **Programmer** des publications futures

---

## 📁 Structure du projet

```
fraternite-fm/
├── index.html              ← Page principale du site
├── admin/
│   ├── index.html          ← Interface Decap CMS
│   └── config.yml          ← ⚠️ Mettez votre username GitHub ici
├── css/
│   └── style.css           ← Design et styles
├── js/
│   └── app.js              ← Logique et affichage
├── _data/
│   ├── articles/           ← Vos articles (créés par le CMS)
│   │   ├── index.json
│   │   └── *.json
│   ├── programmes/         ← Grille des émissions
│   │   ├── index.json
│   │   └── *.json
│   └── equipe/             ← Fiches de l'équipe
│       ├── index.json
│       └── *.json
├── assets/
│   └── uploads/            ← Images uploadées via le CMS
├── netlify.toml            ← Configuration Netlify
└── README.md               ← Ce fichier
```

---

## 🔧 Infos techniques du site

| Élément | Valeur |
|---------|--------|
| Fréquence FM | 95.0 MHz |
| Stream audio | stream.zeno.fm/z951m76tyc9uv |
| Page Facebook | facebook.com/FraterniteFm95Mamou |
| Chaîne YouTube | youtube.com/channel/UCJIFBiOGN3o-gFMPqQhagPA |
| WhatsApp | +224 629 020 259 |
| CMS | Decap CMS (anciennement Netlify CMS) |

---

*Radio Fraternité FM Mamou — La voix de la Moyenne Guinée*
