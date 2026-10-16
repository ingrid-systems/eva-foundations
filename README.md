# EVA Foundations

Deze repo is de plugin-marketplace voor EVA Foundations van Ingrid Staal. Ook EVA HQ-klanten voegen deze marketplace toe. Je voegt de marketplace één keer toe, daarna installeer je de plugin en komen updates automatisch mee.

| Plugin | Wat het is |
|---|---|
| `eva-assistants` | De assistenten van het EVA-systeem. Nu: de MailBlue Assistant, die MailBlue (ActiveCampaign) voor je bedient via de koppelingen en zijn eigen structuurbestand `About Me/Systeem/mailblue.md` bijhoudt. |
| `eva-system` | Gereedschap voor je eigen systeem in Cowork. Nu: `project-opzet`, de skill waarmee je Systeembeheerder een klus of een medewerker inricht: de werkmap, de functieomschrijving als paste-blok en de CLAUDE.md met vakregels. |

## Installeren (Claude chat, Claude Desktop, Cowork)

1. Open **Customize** in de linker sidebar en ga naar de tab **Plugins**.
2. Klik bij **Personal plugins** op de "+" en kies **Add marketplace**.
3. Kies **Add from a repository** en plak: `https://github.com/ingrid-systems/eva-foundations`
4. Klik op **Install** bij de plugin die je nodig hebt (`eva-assistants`, `eva-system`). Elke plugin installeer je apart; updates komen daarna vanzelf mee.

In Cowork open je eerst de Cowork-tab en daarna Customize.

## Installeren (Claude Code)

```
/plugin marketplace add ingrid-systems/eva-foundations
/plugin install eva-assistants@ingrid-staal-eva-foundations
/plugin install eva-system@ingrid-staal-eva-foundations
```

## Gebruiken

De MailBlue Assistant werkt pas als `About Me/Systeem/mailblue.md` bestaat. Dat structuurbestand maak je met de prompt uit de les "Je MailBlue Manager installeren"; de assistent leest het bij elke opdracht en werkt het zelf bij. Een assistent heeft geen werkmap: hij voert uit in MailBlue en past alleen zijn eigen structuurbestand aan.

De project-opzet skill gebruik je in het project van je Systeembeheerder, met je complete AI Library gekoppeld. Vraag "neem de [rol] aan" of "zet een nieuw project op"; de skill leest je Cowork-werkwijze en de Rolprofielen uit `Operations/Administratie/Resources/` en levert de functieomschrijving als paste-blok.

## Een update publiceren

1. Pas het SKILL.md-bestand aan in `plugins/<plugin>/skills/<skill-naam>/`.
2. Hoog het versienummer op in **twee** bestanden, met dezelfde waarde:
   - `plugins/<plugin>/.claude-plugin/plugin.json`
   - `.claude-plugin/marketplace.json` (het `version`-veld bij de plugin-entry)
3. Commit en push.

Iedereen die de marketplace heeft toegevoegd, krijgt de nieuwe versie zonder iets te downloaden of opnieuw te uploaden.
