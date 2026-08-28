# Codex SWTOR — site statique

Petit site d'aide-mémoire SWTOR (gearing 80, opérations, optimisation), prêt à héberger sur **GitHub Pages**.

## Contenu du dossier

| Fichier | Rôle |
|---|---|
| `index.html` | Page d'accueil (portail). **Doit garder ce nom** : c'est la page servie par défaut. |
| `gearing-80.html` | Codex du Gearing 80 |
| `swtorops.html` | Codex des Opérations |
| `fiches-optimisation-7.7.html` | Codex de l'Optimisation (v7.7) |

Chaque page est autonome (CSS + JS à l'intérieur). Aucune installation, aucun outil de build : ce sont de simples fichiers HTML.

## Ce qui a été adapté par rapport aux fichiers d'origine

1. `accueil.html` renommé en **`index.html`** (page servie à la racine par GitHub Pages).
2. **Tous les liens internes corrigés** et alignés sur les noms de fichiers (ils étaient incohérents : `gearing-80.html` vs `gearing80.html`, etc. → 404 sur un serveur Linux).
3. Ajout dans chaque page d'un `<!DOCTYPE html>`, `<meta charset="utf-8">` et `<meta name="viewport">` (encodage correct des accents + affichage mobile correct).

---

## Mise en ligne — méthode simple (interface web GitHub)

1. Va sur https://github.com et connecte-toi (crée un compte si besoin).
2. Clique sur **New repository**. Donne-lui un nom, par ex. `codex-swtor`. Laisse-le en **Public**. Clique **Create repository**.
3. Sur la page du dépôt vide, clique **uploading an existing file** (ou **Add file → Upload files**).
4. Glisse-dépose **les 4 fichiers `.html`** (le `README.md` est optionnel) directement à la racine, puis **Commit changes**.
5. Va dans **Settings** (onglet du dépôt) → menu de gauche **Pages**.
6. Sous **Build and deployment → Source**, choisis **Deploy from a branch**.
7. Branche : **`main`**, dossier : **`/ (root)`**. Clique **Save**.
8. Attends ~1 minute. Recharge la page : GitHub affiche l'URL du site, du type :

   ```
   https://TON-PSEUDO.github.io/codex-swtor/
   ```

C'est en ligne. La page d'accueil (`index.html`) s'ouvre automatiquement, et les liens vers les autres codex fonctionnent.

## Mettre à jour plus tard

Pour modifier une page : dans le dépôt, ouvre le fichier → icône crayon (**Edit**) → modifie → **Commit**. Le site se met à jour tout seul en ~1 minute. Pour ajouter la future page « Optimisation 8.0 », dépose simplement le nouveau fichier et ajoute son lien dans `index.html`.

## Notes

- Les noms de fichiers sur GitHub Pages sont **sensibles à la casse** : garde tout en minuscules et ne renomme pas `index.html`.
- Le mode clair/sombre et les cases à cocher (routine quotidienne/hebdo) sont mémorisés dans le navigateur de chaque visiteur — ça fonctionne tel quel.
- Les polices Google se chargent en HTTPS, donc sans souci sur GitHub Pages.
