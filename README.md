# Global Dominion — 2035 V1

Prototype de jeu de plateau stratégique, 2 à 6 joueurs. Carte Natural Earth 1:110m (domaine public), 176 entités hors Antarctique, frontières historiques indicatives, noms anglais. Les valeurs de jeu sont fictives. Aucun téléchargement de carte nécessaire.

## GitHub Pages
1. Créer un dépôt GitHub, décompresser le ZIP et déposer son contenu à la racine (index.html doit être à la racine).
2. Settings > Pages > Deploy from a branch > main > / (root) > Save.
3. Ouvrir l'adresse Pages indiquée. Le mode local fonctionne sans serveur. Pour tester sur ordinateur : `python -m http.server 8000` puis ouvrir http://localhost:8000.

## Multijoueur distant (prototype entre amis)
1. Créer un projet Supabase. Dans SQL Editor, exécuter supabase.sql.
2. Copier l'URL du projet et sa clé publique anon (legacy JWT) dans config.js. Ne jamais utiliser la clé service_role.
3. Publier les modifications sur GitHub. Le créateur choisit le nombre de joueurs puis Créer salon. Les autres entrent le code et cliquent Rejoindre, chacun dans son navigateur. Attendre que tous aient rejoint avant de jouer.
4. La partie est synchronisée toutes les 1,5 secondes. Le jeton de siège reste dans la session de l'onglet ; conserver celui-ci. Pas de récupération de compte.

## Règles
Trois actions par tour. Recruter, fortifier, déplacer ou attaquer un voisin. Les déplacements et attaques engagent environ la moitié des unités ; la force est pondérée par type d'unité. Les revenus arrivent au début du tour suivant de la faction. Victoire par conquête totale. Les liens maritimes sont des connexions de plateau simplifiées. Zoom +/−, glisser pour déplacer la carte.

## Limites
Le serveur contrôle le siège actif et la révision mais ne valide pas toutes les règles : un client modifié peut tricher. Pas de protection anti-abus, de comptes, de matchmaking, de diplomatie, de marine ni de reprise après fermeture d'onglet. Les salons persistent en base et doivent être nettoyés manuellement. Ne pas utiliser comme service public compétitif. Le SQL et le jeu distant nécessitent un test réel après configuration ; aucun projet Supabase n'a été créé ici. Les figurines sont des symboles SVG originaux stylisés, pas des modèles photoréalistes.
