# BMS ToolBox — Releases

Dépôt de distribution de **BMS ToolBox**, une application Windows destinée aux outils de diagnostic, de documentation et d'organisation pour les installations de Gestion Technique du Bâtiment (GTB/BMS).

> **État du projet :** développement actif. Ce dépôt contient les versions compilées et les fichiers nécessaires aux mises à jour. Le code source de l'application est conservé séparément.

## BMS ToolBox

BMS ToolBox regroupe plusieurs outils dans une seule application :

- **Sites** — centralisation des installations, accès, utilisateurs, notes et dossiers de projet ;
- **Ressources** — classement et recherche de fichiers de ressources ;
- **Modbus RTU** — découverte des esclaves et lecture/diagnostic de registres ;
- **BACnet** — découverte d'équipements et d'objets via BACnet/IP ou MS/TP ;
- **Documentations** — import, classement et recherche dans les documents techniques de l'utilisateur ;
- **À propos** — informations sur l'application, son périmètre et les règles d'utilisation.

Les fonctions de communication intégrées sont destinées au **diagnostic et à la lecture**. Elles n'effectuent pas d'écriture automatique sur les équipements.

## Télécharger une version

Les versions sont disponibles dans la section **Releases** du dépôt :

**[Ouvrir la dernière version publiée](https://github.com/3dd1e/BMSToolBox-Releases/releases/latest)**

Pour une version Windows x64, télécharger le fichier :

```text
BMSToolBox-vX.Y.Z-win-x64.zip
```

Chaque publication contient également :

```text
SHA256SUMS.txt
```

Ce fichier permet de vérifier l'intégrité de l'archive téléchargée.

## Installation

1. Télécharger l'archive ZIP de la version souhaitée.
2. Extraire son contenu dans un dossier dédié, par exemple `C:\BMS ToolBox`.
3. Lancer `BMSToolBox.exe`.
4. Lors du premier démarrage, créer le mot de passe principal demandé par l'application.

La version distribuée est **autonome (self-contained)** : l'installation séparée du runtime .NET n'est pas nécessaire pour utiliser le binaire publié.

## Mise à jour

BMS ToolBox intègre un mécanisme de mise à jour capable de :

- détecter une version plus récente ;
- télécharger l'archive publiée ;
- vérifier son empreinte SHA-256 ;
- fermer l'application ;
- remplacer les fichiers applicatifs ;
- redémarrer BMS ToolBox.

Les données locales de l'utilisateur ne sont pas incluses dans les archives de release et doivent rester conservées lors d'une mise à jour, notamment les dossiers :

```text
Data
SecureData
```

> Lorsque ce dépôt est privé, la consultation anonyme des Releases n'est pas possible. Le mécanisme de mise à jour automatique est donc principalement utilisé lorsque le dépôt de distribution est accessible à l'application.

## Vérifier manuellement le SHA-256

Sous PowerShell :

```powershell
Get-FileHash .\BMSToolBox-vX.Y.Z-win-x64.zip -Algorithm SHA256
```

Comparer la valeur obtenue avec celle indiquée dans `SHA256SUMS.txt` de la même release.

## Données et sécurité

Les informations sensibles associées aux **Sites** sont stockées localement dans le coffre sécurisé de BMS ToolBox. Les fichiers de release ne contiennent aucune donnée utilisateur, aucun mot de passe et aucun coffre local.

Avant une mise à jour importante ou un déplacement de l'installation, il est recommandé de sauvegarder le dossier complet de BMS ToolBox, en particulier `Data` et `SecureData`.

## Application indépendante

BMS ToolBox est un projet indépendant. Il n'est affilié à aucun fabricant et ne redistribue ni firmware, ni logiciel constructeur, ni documentation constructeur.

Les documentations techniques utilisées par l'application sont celles importées par l'utilisateur.

## Contenu de ce dépôt

Ce dépôt est volontairement limité aux éléments de distribution :

```text
Releases
├── BMSToolBox-vX.Y.Z-win-x64.zip
└── SHA256SUMS.txt
```

Les sources, outils de développement et données locales ne sont pas publiés dans ce dépôt.
