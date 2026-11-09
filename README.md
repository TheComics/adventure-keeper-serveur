# Adventure Keeper Serveur

Le serveur de **session en direct** d'[Adventure Keeper](https://adv-keeper.web.app),
à faire tourner sur l'ordinateur du MJ.

Pendant la séance, les jetons, les PV et le combat bougent en continu chez
tous les joueurs, et la brume se lève pendant que le MJ la peint. Les joueurs
n'ont rien à installer : ils jouent dans leur navigateur, comme d'habitude.

> Ce dépôt ne contient que les **installeurs** (onglet
> [Releases](https://github.com/TheComics/adventure-keeper-serveur/releases)).
> Le code de l'application est dans le dépôt principal d'Adventure Keeper.

## Télécharger

Le plus simple : la page **[adv-keeper.web.app/serveur](https://adv-keeper.web.app/serveur)**
propose la version de votre système.

Ou directement, la dernière version :

| Système               | Fichier                                                                                                                                                                         |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Windows               | [Adventure-Keeper-Serveur-windows-x64-setup.exe](https://github.com/TheComics/adventure-keeper-serveur/releases/latest/download/Adventure-Keeper-Serveur-windows-x64-setup.exe) |
| macOS (Apple Silicon) | [Adventure-Keeper-Serveur-macos-arm64.dmg](https://github.com/TheComics/adventure-keeper-serveur/releases/latest/download/Adventure-Keeper-Serveur-macos-arm64.dmg)             |
| macOS (Intel)         | [Adventure-Keeper-Serveur-macos-x64.dmg](https://github.com/TheComics/adventure-keeper-serveur/releases/latest/download/Adventure-Keeper-Serveur-macos-x64.dmg)                 |
| Linux (AppImage)      | [Adventure-Keeper-Serveur-linux-x64.AppImage](https://github.com/TheComics/adventure-keeper-serveur/releases/latest/download/Adventure-Keeper-Serveur-linux-x64.AppImage)       |
| Linux (.deb)          | [Adventure-Keeper-Serveur-linux-x64.deb](https://github.com/TheComics/adventure-keeper-serveur/releases/latest/download/Adventure-Keeper-Serveur-linux-x64.deb)                 |

Chaque version publie aussi un fichier `SHA256SUMS.txt`, pour vérifier un
téléchargement.

## Première ouverture

L'application n'est pas encore signée : le système demande une confirmation
la première fois.

- **Windows** : « Informations complémentaires », puis « Exécuter quand même ».
- **macOS** : ouvrez l'application une fois, puis Réglages Système →
  Confidentialité et sécurité → « Ouvrir quand même ».
- **Linux** : rendez l'AppImage exécutable (clic droit → Propriétés, ou
  `chmod +x`), ou installez le `.deb`.

## Lancer une séance

1. Ouvrez **Adventure Keeper Serveur** : la fenêtre affiche « Serveur prêt »
   et une adresse en `https://…`.
2. Sur Adventure Keeper, ouvrez l'aventure, puis le **bouton serveur** à côté
   de « Démarrer la session » : « Chercher » trouve l'adresse sur cet
   ordinateur (sinon, collez-la avec « Copier »).
3. **Démarrez la session.**

Gardez la fenêtre ouverte et l'ordinateur connecté à Internet jusqu'à la fin
de la séance : la fermer arrête le serveur. Rien n'est perdu pour autant : la
table attend qu'il revienne, et « Terminer la session » enregistre tout dans
Adventure Keeper.

## Comment ça marche

- L'application fait tourner le serveur temps réel d'Adventure Keeper sur
  votre ordinateur, et lui ouvre une adresse publique en `https` grâce à un
  **tunnel Cloudflare** gratuit (sans compte, sans réglage de la box). Une
  nouvelle adresse est donnée à chaque lancement : rien à retenir.
- Seuls les comptes Adventure Keeper qui font partie de la table entrent dans
  la séance : le serveur vérifie l'identité de chacun, et la clé de la
  session.
- Les séances en cours sont gardées sur votre disque, dans le dossier de
  données de l'application ; celles qu'on n'a pas touchées depuis 60 jours
  sont effacées.
