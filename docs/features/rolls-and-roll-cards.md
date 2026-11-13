---
title: Rolls and roll cards
parent: Features
nav_order: 1
---

# Rolls and roll cards

**Tier:** Free, with some parts in Basic and PRO (listed below).

When someone rolls on D&D Beyond in your connected campaign, the roll appears in two places in Owlbear Rodeo:

- The **roll list** in the Gamelog window. It keeps the latest 50 rolls and fades its edges while more cards are hidden past them.
- A **card in a corner of the map**, for everyone in the room. It shows up to four cards at a time and fades out by itself.

{% include screenshot.html src="roll-list.png" alt="The Gamelog roll list with several roll cards" %}

{% include screenshot.html src="map-cards.png" alt="Roll cards in the corner of the map" %}

## What you get

| What | Tier |
| --- | --- |
| Rolls from the D&D Beyond website in the roll list and on the map | Free |
| Pending ("rolling…") cards, kept and dropped dice, roll breakdown | Free |
| D&D Beyond roll privacy (to DM / self stay private) | Free |
| Players see the roll history, keep rolls after a reload | Free |
| Card themes, character avatars on cards | Basic |
| Monster rolls | PRO |
| Rolls from the D&D Beyond mobile app | PRO |
| Rolls made with the Avrae Discord bot (experimental, off by default) | PRO |

Without the PRO items, those rolls simply do not arrive. See [Tiers]({{ '/tiers.html' | relative_url }}).

## What a card shows

- Who rolled and what: the character name and the action, for example "Scimitar" or "Dexterity Save".
- Each roll with its type (check, save, attack, damage, healing, initiative), the formula, the dice and the total. With advantage or disadvantage the dropped die is struck through in the dice list, so in `1d20+5 [17, 4]` the 4 is crossed out.
- A tag for advantage, disadvantage, critical hit or fumble, as D&D Beyond decided them. A natural 20 or 1 colours the whole card.
- The roller's D&D Beyond avatar (Basic).

## Pending cards (Free)

While a roll is still being made, the roll list shows a pending card: "Rolling 1d20+5…". When the roll is done, the same card fills in with the result and the dice. The map shows only finished rolls.

{% include screenshot.html src="pending-card.png" alt="A pending card in the roll list" %}

## Who sees a roll (Free)

D&D Beyond lets a roll go to everyone, to the DM only, or to the roller only. Gamelog respects that:

- **Public** rolls reach everyone in the room.
- Rolls **to the DM** and rolls **to self** stay in the roll list of the GM whose browser relays D&D Beyond, marked **to GM** or **private**. They never go to the players.

{% include screenshot.html src="private-roll-card.png" alt="A roll card tagged to GM in the GM's roll list" %}

{: .note }
Owlbear Rodeo has no private channel between players, so a private roll cannot be sent to selected people. That is why other GMs and the player who rolled do not see these rolls in Owlbear Rodeo; they see them on D&D Beyond.

Monster rolls and the Discord relay follow the same rule: only public rolls are shared.

## Settings

**Settings → Rolls & cards.** These settings apply to the whole room.

### Roll cards (Free)

| Setting | What it does | Default |
| --- | --- | --- |
| Roll cards on the map | Show new rolls as cards in a corner of every player's map | On |
| Roll card fade out | How long a card stays: 6, 12 or 24 seconds, or until dismissed | 12 s |
| Roll card corner | Bottom right, bottom left, top right or top left. Pick another corner when an extension like Dice+ covers the cards | Bottom right |
| Offset from the side, from the top or bottom | Pixels to move the cards away from the edge, for example to sit next to another extension's cards | 0 |

{% include screenshot.html src="roll-cards-settings.png" alt="Settings, Rolls and cards page, Roll cards section" %}

Each card has a **✕** to dismiss it, and **Clear all** appears when more than one card is shown.

### Roll history (Free)

| Setting | What it does | Default |
| --- | --- | --- |
| Players see the roll history | Off: players get no earlier rolls when they join and their Gamelog window shrinks to a note. Live cards still appear | On |
| Dim other cards on hover | Hovering a card in the roll list dims the others, so it stands out | On |
| Keep rolls after a reload | Every browser saves the rolls of this room, so the list is not empty when the room is reopened. Switching it off deletes the saved rolls everywhere | On |
| Clear the roll history | Empties the roll list, the saved rolls and the map cards in every browser that is in the room now. Cannot be undone | |

{% include screenshot.html src="roll-history-settings.png" alt="Settings, Rolls and cards page, Roll history section" %}

The roll list has two buttons for the GM: **Clear** empties it for the whole room, and **Recap** adds a session recap, see [Statistics]({{ '/features/statistics.html' | relative_url }}#session-recap-pro).

## Monster rolls (PRO)

Rolls made for monsters in D&D Beyond also show up. Only public monster rolls reach the players.

## Rolls from the D&D Beyond mobile app (PRO)

Rolls made on the D&D Beyond website are free. Rolls made in the D&D Beyond mobile app (the one on your phone or tablet, including its dice roller) need PRO. Without PRO they simply do not arrive.

## Good to know

- Only one GM browser relays rolls at a time, and rolls arrive only while it has the room open. See [Only one GM relays]({{ '/troubleshooting.html' | relative_url }}#relaying-gm).
- Rolls land on the right token only when characters are linked, see [Character linking]({{ '/features/character-linking.html' | relative_url }}).
- Missing membership items are listed for the GM under **Not in your membership** on the Rolls & cards page. Players never see it.
