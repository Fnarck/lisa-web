# Relaxation thérapeutique Bergès — Site de Lisa Guillaud

Site one-page statique pour le cabinet libéral de Lisa Guillaud,  
praticienne en relaxation thérapeutique selon la méthode Bergès.

---

## 🔜 Next Steps (en attente)

### 1. Formulaire de contact — Formspree ⏳
**Bloqué sur** : réception de l'adresse email professionnelle de Lisa.

Une fois l'email dispo :
1. Créer un compte sur [formspree.io](https://formspree.io)
2. Créer un nouveau form → copier l'ID (ex: `xwkgabcd`)
3. Dans `index.html`, rechercher `FORMSPREE_ID` et remplacer par l'ID réel
4. Déployer : `npx vercel --prod --yes`

Le formulaire collecte : Prénom/Nom · Téléphone · Email · Message  
→ L'email de Lisa n'apparaît jamais dans le code source.

### 2. Infos de contact à intégrer
Dans le bloc **Schema.org JSON-LD** (`index.html`, lignes ~30-55) :
- `"telephone": ""` → à compléter
- `"email": ""` → à compléter (si Lisa accepte de l'exposer)

### 3. Photo professionnelle (optionnel)
Section `#parcours` — prévoir un `<img>` avec photo de Lisa si elle en dispose.

### 4. Thème par défaut
Valider avec Lisa son thème préféré parmi Blanc / Sauge / Lin  
→ Modifier `data-theme="blanc"` sur la balise `<html>` (ligne 2).

### 5. Domaine secondaire court (optionnel)
`lisaguillaud.com` reste disponible pour un usage oral / carte de visite.  
Peut pointer vers le même site Vercel en alias.

---

## 🌐 Accès

| Environnement | URL |
|---|---|
| **Production** | https://guillaud-relaxation-therapeutique.fr |
| **Alias Vercel** | https://lisa-web-gamma.vercel.app |
| **Local** | `npx serve . -l 4242` → http://localhost:4242 |

---

## 🗂️ Structure

```
Lisa-Web/
├── index.html       # Site complet (HTML + CSS + JS inline)
├── vercel.json      # Config Vercel (security headers)
└── README.md        # Ce fichier
```

**Architecture** : zéro dépendance, zéro build step — un seul fichier HTML auto-suffisant.

---

## 🎨 Design

- **Typographie** : Inter (Google Fonts) — corps et titres harmonisés
- **3 thèmes CSS** commutables via `data-theme` sur `<html>` :
  - `blanc` — fond blanc cassé, accents taupe
  - `sauge` — fond crème, accents vert sauge
  - `lin` — fond lin chaud, accents terre
- **Switcher** : 3 pastilles colorées dans la navigation → choix persisté via `localStorage`
- **Responsive** : menu hamburger mobile, animations `fadeUp` sur les sections

---

## 🔧 Déploiement

### Modifier et redéployer
```bash
# 1. Éditer index.html
# 2. Déployer
cd /Users/franck/.gemini/antigravity/scratch/Lisa-Web
npx vercel --prod --yes
```

### DNS (OVH)
Le domaine `guillaud-relaxation-therapeutique.fr` est géré chez OVH.  
Les enregistrements A pointent vers Vercel :

| Sous-domaine | Type | Cible |
|---|---|---|
| `@` | A | `76.76.21.21` |
| `www` | A | `76.76.21.21` |

### Compte Vercel
- **Org** : `fnarcks-projects`
- **Projet** : `lisa-web`
- **Dashboard** : https://vercel.com/fnarcks-projects/lisa-web

---

## 📋 Contenu — Sections

1. **Accueil** — Hero avec accroche et CTA prise de rendez-vous
2. **Parcours** — Formation et référence à la méthode Bergès
3. **La pratique** — Description de la relaxation thérapeutique
4. **Pour qui ?** — Publics cibles (adultes, enfants, adolescents)
5. **Professionnels de santé** — Section dédiée aux prescripteurs
6. **Localisation** — Cabinet à Saint-Jean-de-Moirans (Voiron / Grenoble)

---

## ✏️ Modifications fréquentes

| Besoin | Où dans `index.html` |
|---|---|
| Numéro de téléphone | Chercher `<!-- TEL -->` ou `href="tel:"` |
| Email de contact | Chercher `href="mailto:"` |
| Lien Doctolib/Calendly | Boutons CTA "Prendre rendez-vous" |
| Photo de Lisa | Section `#parcours`, balise `<img>` |
| Thème par défaut | Attribut `data-theme` sur `<html>` |
