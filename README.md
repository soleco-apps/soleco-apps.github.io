# Soleco Apps — portail

Page statique (GitHub Pages) : **écran de connexion Soleco** + lanceur des
web-apps Apps Script + administration des comptes.

- URL : https://soleco-apps.github.io/  ·  `noindex`
- Contenu : `index.html` (tout), `site.webmanifest`, `assets/` (icônes)

## Fonctionnement

- Connexion via les RPC Supabase `connexion` / `session_valide` / … (comptes
  `app_utilisateurs`, `APPLICATION = 'PORTAIL'`). Seule la **clé publiable**
  Supabase est dans le code — publique par nature, aucun secret.
- Les tuiles « participant à la session » (`app_applications` avec une URL)
  s'ouvrent via un **jeton de relais** (`jeton_relais` → `…/exec?h=<code 60 s>`) :
  connecté d'un clic, sans ressaisir le mot de passe.
- Les autres outils (GMAO, Overview) sont de simples liens.
- Administration (rôle `admin`) : comptes (validation, rôle/niveau, applis,
  reset…) et applications (libellé, URL, ouvert par défaut).

## Modifier

- URL / libellé d'une app : depuis la page (Administration → Applications).
- « Autres outils » (liens simples) : éditer `index.html`.
- `git push` sur `main` republie (GitHub Pages).
