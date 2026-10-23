# Pronostics 360 – mise en ligne et mises à jour

Contenu : `index.html` (l'application), `CLAUDE.md` (consignes que Claude lit pour mettre à jour le site).

## Mettre en ligne (une seule fois)
1. Crée un compte GitHub (gratuit) et un dépôt (« repository ») nommé `pronostics360`.
2. Envoie-y les trois fichiers de ce dossier (bouton « Add file » puis « Upload files »).
3. Sur Cloudflare Pages (ou Netlify), choisis « connecter un dépôt GitHub » et sélectionne `pronostics360`.
   Aucun réglage de compilation n'est nécessaire : le dossier racine contient directement `index.html`.
4. Tu obtiens une adresse publique. À chaque changement envoyé sur GitHub, le site se met à jour tout seul.

## Faire les mises à jour avec Claude
Ouvre ce dépôt dans Claude Code (application Claude Desktop, ou Claude Code sur le web/téléphone si ton abonnement
l'inclut : vérifie sur le site d'Anthropic). Claude lira `CLAUDE.md` tout seul. Exemples de demandes :
- « Mets à jour les matchs de la semaine pour tous les championnats. »
- « Ajoute les résultats d'hier au bilan. »
- « Retire le code de test et ajoute mon lien de paiement Orange Money : … »

Si tu préfères ne pas utiliser GitHub, remplace simplement `index.html` sur l'hébergeur (glisser-déposer)
après chaque nouvelle version produite dans la conversation Claude.
