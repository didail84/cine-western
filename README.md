# Ciné Western

Ciné Western sert à explorer et gérer les films western : un catalogue de plusieurs milliers de titres (films, séries, téléfilms), une fiche par titre avec affiche, résumé, distribution, musique et bande-annonce, et ta propre collection (vus / à voir, notes, prêts, journal des séances, listes et sagas, quiz, statistiques).

- **Gratuit et open source** (licence MIT), sans publicité ni compte à créer.
- **Hors ligne** pour le catalogue et ta collection ; Internet sert seulement pour les affiches, résumés et liens.
- **Tes données restent sur ton ordinateur.**
- **Scanner** les codes-barres de tes DVD et Blu-ray avec la caméra de l'ordinateur.
- **Synchroniser** ta collection entre ton Mac et ton PC (dossier iCloud Drive, OneDrive, Google Drive ou Dropbox) et avec ta page Claude.

## Installer

Va dans **[Releases](https://github.com/didail84/cine-western/releases/latest)** et télécharge le fichier qui correspond à ton ordinateur :

| Ordinateur | Fichier |
|---|---|
| Windows 10 ou 11 | `CineWestern-x.y.z-win-x64.exe` |
| Mac Intel (jusqu'à 2020) | `CineWestern-x.y.z-mac-x64.dmg` |
| Mac Apple Silicon (M1, M2, M3, M4…) | `CineWestern-x.y.z-mac-arm64.dmg` |

macOS 12 (Monterey) ou plus récent est nécessaire.

### Windows
1. Double-clique sur le fichier `.exe`.
2. Si Windows affiche « Windows a protégé votre ordinateur » : clique sur **Informations complémentaires**, puis **Exécuter quand même**. Ce message apparaît parce que l'appli n'est pas signée par un certificat payant ; elle n'est pas dangereuse pour autant.
3. Suis l'installation. Un raccourci « Ciné Western » est créé sur le Bureau et dans le menu Démarrer.

### Mac
1. Ouvre le fichier `.dmg` et fais glisser **Ciné Western** dans le dossier **Applications**.
2. La première fois, dans Applications, fais **clic droit (ou Ctrl + clic) › Ouvrir**, puis **Ouvrir** dans la fenêtre qui s'affiche.
3. Si macOS refuse quand même (« l'app est endommagée ») : ouvre le Terminal et tape
   `xattr -cr "/Applications/Ciné Western.app"`, puis relance l'appli.

### Mises à jour
Au démarrage, l'appli regarde s'il existe une nouvelle version sur cette page et te propose de la télécharger. Ta collection est conservée.

### Récupérer une collection existante
Si tu utilisais déjà Ciné Western (ancienne version installée ou page Claude) : dans l'ancienne version, **Réglages › Exporter une sauvegarde**, puis dans la nouvelle, **Réglages › Restaurer une sauvegarde**.

## Synchroniser ton Mac, ton PC et ta page Claude

Dans **Réglages › Synchronisation** :
- **Entre deux ordinateurs** : choisis sur chacun le même dossier synchronisé (iCloud Drive, OneDrive, Google Drive ou Dropbox). L'appli y range le fichier `CineWestern-synchro.json`.
- **Avec ta page Claude** : colle l'adresse de ta propre page Ciné Western sur claude.ai, puis connecte-toi une fois dans la fenêtre « Ouvrir la fenêtre de la page ».

## Pour les curieux et les développeurs

L'appli est une page web (`app/index.html`) emballée avec [Electron](https://www.electronjs.org).

```bash
npm install          # une seule fois
npm start            # lancer l'appli
npm run dist:win     # fabriquer l'installateur Windows
npm run dist:mac     # fabriquer l'installateur Mac (sur un Mac)
```

Les installateurs officiels sont fabriqués automatiquement par GitHub Actions (`.github/workflows/release.yml`) à chaque nouvelle étiquette de version :

```bash
npm version patch    # 1.0.0 → 1.0.1
git push --follow-tags
```

Electron est figé en version 43 : c'est la dernière qui fonctionne encore sur macOS 12.

## Licence

Code sous licence MIT — voir [LICENSE](LICENSE). Données du catalogue et bibliothèques tierces : voir [NOTICE.md](NOTICE.md).
