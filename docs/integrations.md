---
title: Integrations
nav_order: 6
---

# Integrations

{: .warning }
Integrations with other extensions and services can break when either side updates. Please report problems, see [Feedback]({{ '/feedback.html' | relative_url }}).

Gamelog works with other Owlbear Rodeo extensions and with services outside it. An integration runs when your membership includes it **and** it is switched on. The switches are under **Settings → Integrations**, GM only.

{% include screenshot.html src="integrations.png" alt="Settings, Integrations page with the four integration switches" %}

| Integration | What it does with Gamelog | Tier |
| --- | --- | --- |
| [Initiative Tracker](#initiative-tracker) | Sets the initiative of linked tokens from D&D Beyond rolls | Free, experimental |
| [Stat Bubbles for D&D](#stat-bubbles-for-dd) | Hit points and armor class of linked tokens follow D&D Beyond | PRO |
| [Discord](#discord) | Public rolls and the session recap in a channel | PRO |
| [Avrae](#avrae-experimental) | Rolls made with the Avrae Discord bot appear in the room | PRO, experimental |
| [Other Owlbear extensions](#other-owlbear-extensions-experimental) | Rolls from extensions that support it join the roll list | Free, experimental |

The Overview page counts the integrations that run now and lists them.

## Initiative Tracker

**Needs:** the official Initiative Tracker extension.
**Tier:** Free. **Status:** experimental.

An initiative roll from D&D Beyond sets the linked token's initiative. See [Initiative]({{ '/features/initiative.html' | relative_url }}).

## Stat Bubbles for D&D

**Needs:** the [Stat Bubbles for D&D](https://extensions.owlbear.rodeo/bubble-tracker) extension and linked tokens.
**Tier:** PRO.

See [Live token stats]({{ '/features/live-token-stats.html' | relative_url }}).

## Discord

**Needs:** a Discord channel webhook.
**Tier:** PRO.

See [Discord]({{ '/features/discord.html' | relative_url }}).

## Avrae (experimental) {#avrae-experimental}

**Needs:** your table rolls with the [Avrae](https://avrae.io) Discord bot, and the characters are linked to D&D Beyond.
**Tier:** PRO. **Status:** experimental, **off by default**.

D&D Beyond shows the rolls made with Avrae in its game log. Gamelog can relay them too, so `!check persuasion`, `!save con` or `!roll 1d20+5` appear as cards in the room.

Switch it on under **Settings → Integrations → Avrae**.

{% include screenshot.html src="avrae-roll.png" alt="A roll made with Avrae shown as a card in the roll list" %}

Known limit: `!multiroll` does not reach D&D Beyond's game log, so Gamelog never sees it.

## Other Owlbear extensions (experimental) {#other-owlbear-extensions-experimental}

**Tier:** Free. **Status:** experimental, **off by default**.

Rolls made with other Owlbear Rodeo extensions that support it, for example 5e Tools Integration, join the roll list and the map cards. They carry a **via** tag with the extension's name, so you can tell them from D&D Beyond rolls.

Switch it on under **Settings → Integrations → Other Owlbear extensions**.

{% include screenshot.html src="extension-roll-card.png" alt="A roll card with a via tag from another extension" %}

- Public rolls need a relaying GM in the room, that is, a GM connected to D&D Beyond in Gamelog. Without one, public rolls are dropped. Any player's extension can send them.
- Hidden rolls show only in the history of the GM who made them. A hidden roll sent by a player is dropped.
- Discord, the statistics and the initiative tracker ignore these rolls.

Are you an extension developer and want to send rolls to Gamelog? Ask on [Discord](https://discord.com/invite/HSTtrphyFg).
