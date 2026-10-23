# Pronostics 360 – instructions pour Claude

Application web d'une seule page (`index.html`, sans dépendance externe) qui affiche des pronostics de football
pour les 5 grands championnats européens, la Ligue des champions et l'Europa League.
Langue de l'interface : français. Public : Burkina Faso / Afrique de l'Ouest francophone.
Le propriétaire ne code pas : fais les modifications toi-même et explique-les simplement.

## Où sont les données (dans `index.html`, balise `<script>`)
- `M` : quelques matchs « soignés » avec cotes de bookmakers (champs : lg, day, t, h, a, o, p, ou, bt, sc, cf, n, pr).
- `AU` : matchs des 5 championnats, une ligne = `[championnat, jour, heure GMT, domicile, extérieur, [p1, pX, p2]]`.
  Les probabilités viennent de SportRadar. Buts et scores sont calculés par le modèle de Poisson de la page.
- `UL` : matchs d'Europa League (probabilités du site Adalbet).
- Matchs de Ligue des champions : lignes écrites à la suite de `AU` (probabilités SportRadar, ou cote déduite via `mk2`).
- `FIN` : matchs terminés `[domicile, extérieur, buts dom., buts ext.]` pour le bilan « Mes pronostics terminés ».
- Les jours sont du texte (ex. `Sam. 24 oct`) et doivent exister dans `DN` ; l'année codée est 2026, mois d'octobre : à adapter en novembre.
- Les matchs dont le coup d'envoi date de plus de 2 h disparaissent tout seuls de l'affichage.

## Réglages (ligne `const PAY=...`)
- `PAY.om`, `PAY.card` : liens de paiement Orange Money et carte Visa (vides = « bientôt disponible »).
- `WA` : numéro WhatsApp pour la preuve de paiement. `CODES` : codes d'accès valables `DAYS` jours.
- `TRIAL` : jours d'essai gratuit (14). Prix affiché : 500 FCFA ou 1 $ par mois.
- À FAIRE AVANT LE LANCEMENT PUBLIC : retirer le code de test `ESSAI30`.

## Routine de mise à jour (à la demande du propriétaire)
1. Cherche les matchs des 7 prochains jours pour chaque championnat (outil de données sportives ou recherche web).
2. Ajoute les lignes manquantes ; mets les résultats des matchs joués dans `FIN`.
3. Ne JAMAIS inventer des cotes ou des probabilités : si aucune source fiable, n'ajoute pas le match et dis-le.
4. Indique la source de chaque donnée (champ `src` ou `n`). Les cotes anciennes doivent être signalées.
5. Mets à jour la date dans le bandeau « Mise à jour le … ».
6. Enregistre, envoie sur GitHub : l'hébergeur republie le site automatiquement.

## Règles à respecter
- Aucun résultat n'est garanti : garde les mentions « Jeu responsable » et « Réservé aux 18+ ».
- Pas de clés d'API ni de mots de passe dans `index.html` (le fichier est public).
- Garde le fichier autonome (pas de fichiers ou scripts externes).
- Apostrophes et guillemets typographiques (’ « ») dans les textes visibles.
- Les comptes et l'essai gratuit sont stockés sur l'appareil de chaque utilisateur (pas de serveur) : ne pas présenter cela comme une sécurité forte.
- Crédit à conserver en bas de page : « Développé par W-edge · WhatsApp +226 78097713 ».
