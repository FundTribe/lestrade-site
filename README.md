# L'Estrade — mise en ligne du site

Site statique (une page + mentions légales + CGV). Aucun serveur, aucune base de données : il s'héberge gratuitement sur GitHub Pages.

## Contenu du dossier

| Fichier | Rôle |
|---|---|
| `index.html` | La page de vente |
| `mentions-legales.html`, `cgv.html` | Pages légales (à compléter, zones surlignées en jaune) |
| `favicon.svg` | Icône d'onglet |
| `robots.txt`, `sitemap.xml` | Référencement |
| `CNAME` | Nom de domaine (à modifier si vous n'utilisez pas `www.lestrade.fr`) |
| `.nojekyll` | Indique à GitHub de servir les fichiers tels quels |

## Étape 1 — Mettre en ligne sur GitHub Pages (10 min)

1. Connectez-vous sur github.com → bouton **New repository**.
2. Nom : `lestrade-site` (ou autre). Laissez **Public** (obligatoire pour Pages gratuit). Cochez « Add a README »… ou non, peu importe. **Create repository**.
3. Dans le dépôt : **Add file → Upload files**. Glissez tous les fichiers de ce dossier (y compris `.nojekyll` et `CNAME` ; si votre explorateur cache les fichiers commençant par un point, activez l'affichage des fichiers cachés). **Commit changes**.
4. **Settings → Pages** (menu de gauche). Sous *Build and deployment* : Source = **Deploy from a branch**, Branch = **main** / **/ (root)**. **Save**.
5. Attendez 1 à 2 minutes, rechargez la page Settings → Pages : l'adresse `https://VOTRE-PSEUDO.github.io/lestrade-site/` apparaît. Le site est en ligne.

> Si vous n'avez pas encore de nom de domaine, **supprimez le fichier `CNAME`** avant l'upload, sinon GitHub cherchera un domaine qui n'existe pas encore.

Pour mettre à jour le site ensuite : ouvrez le fichier sur GitHub → icône crayon → modifiez → **Commit**. Le site se met à jour tout seul en une minute.

## Étape 2 — Recevoir les demandes d'appel (Formspree, 5 min)

1. Créez un compte gratuit sur [formspree.io](https://formspree.io) (50 envois/mois offerts).
2. **New form** → nommez-le « Appel découverte », e-mail de réception : le vôtre.
3. Formspree affiche une adresse du type `https://formspree.io/f/xabcdefg`. Copiez l'identifiant (`xabcdefg`).
4. Dans `index.html`, remplacez `VOTRE_ID` dans la ligne `action="https://formspree.io/f/VOTRE_ID"` par cet identifiant.
5. Testez le formulaire sur le site : le premier envoi vous demande de confirmer votre e-mail.

## Étape 3 — Nom de domaine (optionnel, ~10 €/an)

1. Achetez le domaine chez un registrar français (OVH, Gandi, Ionos). Vérifiez d'abord la disponibilité de la marque sur [data.inpi.fr](https://data.inpi.fr).
2. Dans la zone DNS du registrar, ajoutez :

   | Type | Nom | Valeur |
   |---|---|---|
   | A | `@` | `185.199.108.153` |
   | A | `@` | `185.199.109.153` |
   | A | `@` | `185.199.110.153` |
   | A | `@` | `185.199.111.153` |
   | CNAME | `www` | `VOTRE-PSEUDO.github.io` |

3. Sur GitHub : **Settings → Pages → Custom domain** : saisissez `www.lestrade.fr` → **Save**. Attendez la vérification DNS (quelques minutes à quelques heures), puis cochez **Enforce HTTPS**.
4. Adaptez le fichier `CNAME` et les adresses `https://www.lestrade.fr/` dans `index.html`, `sitemap.xml` et `robots.txt` si le domaine est différent.

## Étape 4 — Réservations (Calendly, 5 min)

1. Compte gratuit sur [calendly.com](https://calendly.com) → créez un événement « Appel découverte — 20 min », lieu : Google Meet ou Zoom.
2. Copiez le lien (ex. `https://calendly.com/lestrade/decouverte`).
3. Dans `index.html`, vous pouvez remplacer les liens `href="#contact"` des boutons « Réserver un appel découverte » par ce lien Calendly, en ajoutant `target="_blank"`. Ou gardez le formulaire et mettez le lien Calendly dans votre réponse par e-mail.

## Étape 5 — Paiements (Stripe Payment Links, 15 min)

1. Compte sur [stripe.com](https://stripe.com) (vérification d'identité + IBAN, 1 à 2 jours).
2. **Catalogue de produits** → créez « Séance de coaching 1 h — 120 € », « Pack 5 séances — 550 € », « Atelier journée — 190 € ».
3. **Liens de paiement** → un lien par produit. Aucun code.
4. Dans `index.html`, mettez ces liens sur les boutons « Commencer » et « Demander le programme » (ou envoyez-les après l'appel découverte, ce qui convertit souvent mieux pour du coaching).

Frais : 1,5 % + 0,25 € par paiement carte européenne.

## Étape 6 — Avant de communiquer

- [ ] Compléter les zones jaunes de `mentions-legales.html` et `cgv.html` (obligatoire).
- [ ] Remplacer les 3 témoignages d'exemple par de vrais témoignages (ou les retirer).
- [ ] Remplacer les chiffres « 12 ans / 400+ / 30 » par les vôtres.
- [ ] Ajouter votre photo : mettez `portrait.jpg` dans le dossier et remplacez le bloc `<div class="portrait">…</div>` par `<img class="portrait" src="portrait.jpg" alt="Votre nom, coach de prise de parole">`.
- [ ] Créer une image de partage `og.png` (1200×630 px, Canva) pour les aperçus sur LinkedIn/WhatsApp.
- [ ] Ajouter le site à [Google Search Console](https://search.google.com/search-console) et soumettre `sitemap.xml`.
- [ ] Créer une fiche [Google Business Profile](https://business.google.com) « Coach en prise de parole » — c'est souvent la première source de clients locaux.

## Aller plus loin

- **Analytics sans cookies** : [Plausible](https://plausible.io) (payant) ou [Umami](https://umami.is) — pas de bandeau cookies nécessaire.
- **Qualiopi** : indispensable pour être financé par les OPCO ; comptez 1 500–3 000 € et 3 à 6 mois. Rentable dès que vous vendez des formations en entreprise.
- **Blog / SEO** : une page par question que vos clients tapent sur Google (« gérer le trac en réunion », « préparer un casting »). Chaque page = un nouveau fichier HTML dans le dépôt.
