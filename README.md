# EVA Foundations

Deze repo is de plugin-marketplace voor EVA Foundations van Ingrid Staal. Ook EVA HQ-klanten voegen deze marketplace toe. Je voegt de marketplace één keer toe, daarna installeer je de plugin en komen updates automatisch mee.

| Plugin | Wat het is |
|---|---|
| `eva-assistants` | De assistenten van het EVA-systeem. Nu: de MailBlue Assistant, die MailBlue (ActiveCampaign) voor je bedient via de koppelingen en zijn eigen structuurbestand `About Me/Systeem/mailblue.md` bijhoudt. |

## Installeren (Claude chat, Claude Desktop, Cowork)

1. Open **Customize** in de linker sidebar en ga naar de tab **Plugins**.
2. Klik bij **Personal plugins** op de "+" en kies **Add marketplace**.
3. Kies **Add from a repository** en plak: `https://github.com/ingrid-systems/eva-foundations`
4. Klik op **Install** bij `eva-assistants`.

In Cowork open je eerst de Cowork-tab en daarna Customize.

## Installeren (Claude Code)

```
/plugin marketplace add ingrid-systems/eva-foundations
/plugin install eva-assistants@ingrid-staal-eva-foundations
```

## Gebruiken

De MailBlue Assistant werkt pas als `About Me/Systeem/mailblue.md` bestaat. Dat structuurbestand maak je met de prompt uit de les "Je MailBlue Manager installeren"; de assistent leest het bij elke opdracht en werkt het zelf bij. Een assistent heeft geen werkmap: hij voert uit in MailBlue en past alleen zijn eigen structuurbestand aan.

## Een update publiceren

1. Pas het SKILL.md-bestand aan in `plugins/eva-assistants/skills/<skill-naam>/`.
2. Hoog het versienummer op in **twee** bestanden, met dezelfde waarde:
   - `plugins/eva-assistants/.claude-plugin/plugin.json`
   - `.claude-plugin/marketplace.json` (het `version`-veld bij de plugin-entry)
3. Commit en push.

Iedereen die de marketplace heeft toegevoegd, krijgt de nieuwe versie zonder iets te downloaden of opnieuw te uploaden.
