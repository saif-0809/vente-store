# VENTE — boutique en bois

Site vitrine/catalogue trilingue (français, arabe RTL, anglais), panier et commande WhatsApp, avec une interface d'administration de démonstration.

## Important avant publication
1. Dans `app.js`, remplacez `216XXXXXXXX` par le numéro WhatsApp de la boutique au format international, sans `+`, espace ou zéro initial (exemple de format : `216XXXXXXXX`).
2. Le code administrateur `1234` est uniquement une démonstration. Changez-le au minimum dans `app.js`.
3. **Sécurité / persistance :** cette version stocke les produits et le panier dans le `localStorage` du navigateur. Les modifications de l'administrateur ne sont visibles que sur ce navigateur/appareil. Le code PIN est côté client et ne constitue PAS une authentification sécurisée. Ne l'utilisez pas pour gérer un vrai commerce avec des données sensibles. Pour une boutique réellement administrable depuis plusieurs appareils, connectez une base de données et une authentification (par exemple Supabase).
4. Les images de démonstration proviennent d'Unsplash et nécessitent une connexion Internet. Remplacez-les par vos propres photos de produits.

## Tester en local
Ouvrez `index.html` dans un navigateur. Pour un meilleur résultat, utilisez un petit serveur local (par exemple l'extension Live Server de VS Code).

## Déploiement
### GitHub
- Créez un dépôt GitHub nommé `vente-store`.
- Téléversez les fichiers `index.html`, `style.css`, `app.js` et `README.md`.

### Hébergement
GitHub Pages ne doit pas être utilisé pour héberger gratuitement un site destiné à faciliter des transactions commerciales/e-commerce. Gardez GitHub comme dépôt de code et déployez le dépôt sur Netlify :
- Créez un compte sur https://www.netlify.com/
- Add new site → Import an existing project → GitHub.
- Sélectionnez `vente-store`, laissez le build command vide et le publish directory à `.`.
- Déployez. Netlify fournit un sous-domaine `*.netlify.app` gratuit selon les conditions et limites de son offre.

## Pour une vraie version de production
Configurer Supabase Auth + une table `products` avec politiques RLS d'administration, puis remplacer le stockage local par les opérations API Supabase. Ne rendez pas le panneau admin public avec un simple PIN JavaScript.
