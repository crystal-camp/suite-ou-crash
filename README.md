# Suite ou Crash ?

Jeu multijoueur statique pour GitHub Pages. Aucun compte, aucune base de données, aucun stockage permanent.

## Important : comment le multijoueur fonctionne

GitHub Pages ne peut servir que des fichiers statiques : deux navigateurs ne peuvent pas se découvrir tout seuls. Cette version utilise **PeerJS/WebRTC** : les joueurs communiquent directement entre leurs navigateurs, et le service public de signalisation PeerJS sert uniquement à établir la connexion. Les réponses et scores ne sont pas enregistrés dans une base de données par ce projet.

Conséquences :
- l'hôte est le serveur de la partie ;
- si l'hôte ferme ou actualise son onglet, la partie est perdue ;
- Internet est nécessaire ;
- certains réseaux très restrictifs peuvent bloquer WebRTC ;
- pour un usage public massif, il faudra à terme héberger son propre serveur de signalisation/relay ou ajouter un backend.

## Tester sur PC

Ne double-clique pas simplement sur `index.html` si ton navigateur bloque certaines fonctions réseau en `file://`.

Dans le dossier du jeu :

```bash
python -m http.server 8000
```

Puis ouvre `http://localhost:8000` dans le navigateur. Pour simuler plusieurs joueurs, ouvre plusieurs navigateurs/appareils. Le vrai test multijoueur est plus fiable une fois le site publié en HTTPS sur GitHub Pages.

## Mettre sur GitHub Pages

1. Crée un dépôt GitHub.
2. Envoie tous les fichiers de ce dossier à la racine du dépôt.
3. Dans GitHub : **Settings → Pages**.
4. Source : **Deploy from a branch**.
5. Branche : `main`, dossier `/ (root)`.
6. Ouvre l'adresse GitHub Pages fournie.

## Contenu

- 620 amorces d'histoires.
- 180 aides anti-page-blanche indépendantes des amorces.
- 90 contraintes Panique indépendantes.
- avatars emoji générés localement.
- codes de salon à 6 caractères.
- 3 à 10 manches ; 45 à 120 secondes d'écriture.
- réponses anonymes pendant le vote, identité révélée aux résultats.
- scores et classement final.

Les banques de textes sont dans `data.js` et peuvent être modifiées sans toucher au moteur du jeu.
