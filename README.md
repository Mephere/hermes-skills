# Hermes — bibliotheque de skills

Skills au format `SKILL.md` pour l'agent Hermes. Chaque skill est un dossier autonome :
un `SKILL.md` avec son en-tete YAML, et les gabarits dont il a besoin dans `assets/`.

## Installation

Une seule commande, a coller dans le terminal. Choisir la ligne correspondant a son
systeme.

### Windows (PowerShell)

Ouvrir PowerShell, pas l'invite de commandes classique.

```powershell
mkdir -Force "$HOME\.hermes\skills" | Out-Null; curl.exe -fsSL https://github.com/Mephere/hermes-skills/archive/refs/heads/main.tar.gz -o "$env:TEMP\hs.tgz"; tar -xzf "$env:TEMP\hs.tgz" -C "$HOME\.hermes\skills" --strip-components=2 hermes-skills-main/skills/rediger-un-email-professionnel-clair-et-court
```

### Mac et Linux

```bash
mkdir -p ~/.hermes/skills && curl -fsSL https://github.com/Mephere/hermes-skills/archive/refs/heads/main.tar.gz | tar -xz --strip-components=2 -C ~/.hermes/skills hermes-skills-main/skills/rediger-un-email-professionnel-clair-et-court
```

Le skill est alors disponible dans `~/.hermes/skills/rediger-un-email-professionnel-clair-et-court/`.

## Installer toute la bibliotheque

### Windows (PowerShell)

```powershell
mkdir -Force "$HOME\.hermes\skills" | Out-Null; curl.exe -fsSL https://github.com/Mephere/hermes-skills/archive/refs/heads/main.tar.gz -o "$env:TEMP\hs.tgz"; tar -xzf "$env:TEMP\hs.tgz" -C "$HOME\.hermes\skills" --strip-components=2 hermes-skills-main/skills
```

### Mac et Linux

```bash
mkdir -p ~/.hermes/skills && curl -fsSL https://github.com/Mephere/hermes-skills/archive/refs/heads/main.tar.gz | tar -xz --strip-components=2 -C ~/.hermes/skills hermes-skills-main/skills
```

## Verifier l'installation

### Windows (PowerShell)

```powershell
ls -Recurse "$HOME\.hermes\skills\rediger-un-email-professionnel-clair-et-court"
```

### Mac et Linux

```bash
ls -R ~/.hermes/skills/rediger-un-email-professionnel-clair-et-court
```

Le dossier doit contenir `SKILL.md` et un dossier `assets/` avec `modele-email.md`
et `formules-a-supprimer.md`.

## Desinstaller

### Windows (PowerShell)

```powershell
Remove-Item -Recurse -Force "$HOME\.hermes\skills\rediger-un-email-professionnel-clair-et-court"
```

### Mac et Linux

```bash
rm -rf ~/.hermes/skills/rediger-un-email-professionnel-clair-et-court
```

## Repertoire d'installation

`~/.hermes/skills/` sur Mac et Linux, `%USERPROFILE%\.hermes\skills\` sur Windows.
C'est le dossier ou Hermes va chercher ses skills au demarrage. Si votre installation
lit les skills ailleurs, remplacer ce chemin dans la commande.

Apres l'installation, redemarrer Hermes pour qu'il relise ses skills.

## En cas d'erreur

| Message | Cause | Solution |
|---|---|---|
| `La syntaxe de la commande n'est pas correcte` | Commande Mac lancee dans l'invite de commandes Windows | Utiliser PowerShell et la commande Windows |
| `404 Not Found` | Depot prive, ou nom de compte errone dans l'URL | Verifier que le depot est public |
| Le dossier est vide apres extraction | Le chemin apres `--strip-components=2` ne correspond pas a l'arborescence du depot | Verifier l'arborescence sur GitHub |
| `tar : command not found` | Windows anterieur a la version 10 build 17063 | Telecharger l'archive ZIP depuis GitHub et l'extraire a la main |

## Structure du depot

```
hermes-skills/
├── README.md
└── skills/
    └── rediger-un-email-professionnel-clair-et-court/
        ├── SKILL.md
        └── assets/
            ├── modele-email.md
            └── formules-a-supprimer.md
```

## Ajouter un skill

Un dossier par skill sous `skills/`, nomme comme le champ `name` de son en-tete YAML.
Le `SKILL.md` suit toujours la meme structure : en-tete YAML, puis les sections
Quand l'utiliser, Prerequis, Deroulement, Notions cles, Outils et systemes, Cas
courants, Format de sortie, Prompt d'activation.

## Licence

Apache-2.0.
