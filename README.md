# Les royaumes de ashenfall - Ressourcepack officiel ![Minecraft](https://img.shields.io/badge/Minecraft-1.21.1-62b47a?logo=minecraft&logoColor=white)

> Resource pack Minecraft pour le serveur **Les royaumes de ashenfall** : icônes de grades et d'indicateurs affichés dans le chat, le TAB et les scoreboards.

<img width="600" height="292" alt="image" src="https://github.com/user-attachments/assets/dbca7573-b1b6-4b9a-bcdc-72b9cc07946d" />

## Aperçu

Ce pack remplace des caractères Unicode spécifiques par des images, grâce à une police bitmap (`default.json`). Il permet d'afficher des icônes personnalisées dans le texte, sans mod côté client.

## Contenu

### Grades

| Image | Fichier | Code Unicode |
|---|---|---|
| <img width="928" height="176" alt="image" src="https://github.com/user-attachments/assets/2baf2bcd-c181-41d0-8d5d-afa30d525c04" /> | `fondateur.png` | `\u20b7` |
| <img width="1152" height="176" alt="image" src="https://github.com/user-attachments/assets/15f378cd-6127-4ce7-a294-3012a6582f07" /> | `gardien.png` | `\u20b5` |
| <img width="1264" height="176" alt="image" src="https://github.com/user-attachments/assets/01f9db42-a348-4138-8b61-c62acbcfbabc" /> | `apprenti.png` | `\u0e3f` |
| <img width="1264" height="176" alt="image" src="https://github.com/user-attachments/assets/d3444e83-2730-4b20-8fe6-51728a902333" /> | `voyageur.png` | `\u20a5` |

### Indicateurs

| Image | Fichier | Code Unicode |
|---|---|---|
| <img width="448" height="176" alt="image" src="https://github.com/user-attachments/assets/03f39626-e427-4605-94fa-c18f6a3cb52e" /> | `afk.png` | `\u20be` |
| <img width="448" height="176" alt="image" src="https://github.com/user-attachments/assets/5f1fe615-e851-4933-bebf-06919452c0ed" /> | `tpa.png` | `\u20c0` |
| <img width="560" height="176" alt="image" src="https://github.com/user-attachments/assets/20cda1f9-a7e6-462a-a9a3-3cf69e319ba8" /> | `vote.png` | `\u20b1` |
| <img width="688" height="176" alt="image" src="https://github.com/user-attachments/assets/2db9380a-f2ba-41f7-af12-1f39674068c3" /> | `homes.png` | `\u20ab` |

## Installation

### Joueurs

1. Télécharge le dernier `.zip` dans l'onglet [Releases](https://github.com/ashenfall-craft/ressource_pack/releases).
2. Place-le dans le dossier `resourcepacks` de ton Minecraft (`.minecraft/resourcepacks`).
3. En jeu : **Options → Packs de ressources**, puis active le pack.

> Si le serveur envoie le pack automatiquement, tu n'as rien à faire : accepte simplement le téléchargement à la connexion.

### Administrateurs

Le pack peut être envoyé aux joueurs de deux façons :

- via `resource-pack` et `resource-pack-sha1` dans `server.properties` ;
- via un plugin qui héberge et envoie le pack (par exemple [ImageEmojis](https://modrinth.com/plugin/image-emojis), avec l'option `mergeWithServerResourcePack`).

## Utilisation

Chaque image est associée à un caractère Unicode. Pour l'afficher, il suffit d'utiliser ce caractère dans un texte.

**Dans un JSON text component** (`tellraw`, titres, etc.) :

```
/tellraw @a {"text":"\u20b7 Pseudo"}
```

**Dans la config d'un plugin** (TAB, plugin de chat, scoreboard…) : colle directement le caractère correspondant en UTF-8, ou utilise le format accepté par le plugin.

> Les images de police sont teintées par la couleur du texte. Place un code couleur blanc (`&f` ou `#FFFFFF`) avant le caractère pour garder les couleurs d'origine.

## Structure

```
.
├── pack.mcmeta
├── pack.png
└── assets
    └── minecraft
        ├── font
        │   └── default.json
        └── textures
            └── font
                ├── fondateur.png
                ├── gardien.png
                ├── apprenti.png
                ├── dirigeant.png
                ├── voyageur.png
                ├── afk.png
                ├── tpa.png
                ├── vote.png
                └── homes.png
```

## Ajouter une image

1. Place ton image `.png` dans `assets/minecraft/textures/font/`.
2. Ajoute un provider dans `assets/minecraft/font/default.json` :

```json
{
  "type": "bitmap",
  "file": "minecraft:font/mon_image.png",
  "height": 10,
  "ascent": 8,
  "chars": ["\ue000"]
}
```

3. Utilise un caractère libre de la **zone privée Unicode** (`\ue000` à `\uf8ff`), car aucune vraie police ne l'utilise, et ne réutilise pas un code déjà attribué.

## Caractères déjà présents

| Nom | Caractère | Code Unicode | Point de code |
|---|---|---|---|
| fondateur | ₷ | `\u20b7` | U+20B7 |
| gardien | ₵ | `\u20b5` | U+20B5 |
| apprenti | ฿ | `\u0e3f` | U+0E3F |
| dirigeant | ₼ | `\u20bc` | U+20BC |
| voyageur | ₥ | `\u20a5` | U+20A5 |
| afk | ₾ | `\u20be` | U+20BE |
| tpa | ⃀ | `\u20c0` | U+20C0 |
| vote | ₱ | `\u20b1` | U+20B1 |
| homes | ₫ | `\u20ab` | U+20AB |

## Compatibilité

- **Version de Minecraft :** 1.21.1 (`pack_format` : 34)
- **Java Edition uniquement** (la police bitmap n'est pas garantie sur Bedrock).

## Contribuer

Les suggestions et corrections sont les bienvenues : ouvre une [issue](https://github.com/ashenfall-craft/ressource_pack/issues) ou une pull request.

## Crédits

- Création du pack : **neophitt**
- Serveur : **Les royaumes de Ashenfall**
