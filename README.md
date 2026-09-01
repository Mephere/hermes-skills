# Hermes — bibliotheque de skills

Skills au format `SKILL.md` pour l'agent Hermes. Chaque skill est un dossier autonome :
un `SKILL.md` avec son en-tete YAML, et les gabarits dont il a besoin dans `assets/`.

## Installation

Une seule commande, a coller dans le terminal.

```bash
mkdir -p ~/.claude/skills && curl -fsSL https://github.com/Mephere/hermes-skills/archive/refs/heads/main.tar.gz | tar -xz --strip-components=2 -C ~/.claude/skills hermes-skills-main/skills/rediger-un-email-professionnel-clair-et-court
```

Le skill est alors disponible dans `~/.claude/skills/rediger-un-email-professionnel-clair-et-court/`.

### Installer toute la bibliotheque

```bash
mkdir -p ~/.claude/skills && curl -fsSL https://github.com/Mephere/hermes-skills/archive/refs/heads/main.tar.gz | tar -xz --strip-components=2 -C ~/.claude/skills hermes-skills-main/skills
```

### Variante avec git

```bash
git clone --depth 1 https://github.com/Mephere/hermes-skills.git ~/hermes-skills && cp -r ~/hermes-skills/skills/* ~/.claude/skills/
```

### Verifier

```bash
ls ~/.claude/skills/
```

### Desinstaller

```bash
rm -rf ~/.claude/skills/rediger-un-email-professionnel-clair-et-court
```

## Repertoire d'installation

`~/.claude/skills/` est le chemin par defaut. Adapter la commande si Hermes lit ses
skills ailleurs, par exemple `~/.hermes/skills/` : remplacer les deux occurrences du
chemin dans la commande.

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
