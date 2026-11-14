---
title: Discord
parent: Features
nav_order: 6
---

# Discord

**Tier:** PRO.

Gamelog can post the public rolls of your table to a Discord channel, as the character, with the dice. It can also post the session recap, see [Statistics]({{ '/features/statistics.html' | relative_url }}#session-recap-pro).

| What | Tier |
| --- | --- |
| Discord relay of public rolls | PRO |
| Session recap to Discord | PRO |

Only public rolls are posted. Rolls that stay private on D&D Beyond (to DM or to self) are never posted, and the server checks that again before it posts.

{% include screenshot.html src="discord-message.png" alt="A relayed roll in a Discord channel" %}

## Set it up

Do this in the browser of the GM who relays D&D Beyond rolls.

1. In Discord, open the channel's settings, then **Integrations → Webhooks → New Webhook**.
2. Click **Copy Webhook URL**.
3. In Owlbear Rodeo, open **Settings → Integrations → Discord**, paste the URL and click **Connect**. A test message appears in the channel.

{% include screenshot.html src="discord-config-1.png" alt="Settings, Integrations page, Discord section before the webhook is connected" %}

{% include screenshot.html src="discord-config-2.png" alt="The Discord section once the webhook is connected" %}

The channel gets a welcome message once the webhook is connected.

{% include screenshot.html src="discord-welcome-message.png" alt="The welcome message of DDB Gamelog in the Discord channel" %}

{: .note }
A webhook URL lets anyone post to your channel. Do not share it and do not show it in screenshots. Gamelog stores it encrypted on the Gamelog server and never shows it again, not even to players.

## Switch it off and on

The **Integrations** section lists Discord with a switch. While it is off, rolls are not posted, but the webhook stays connected; switch it on to resume. **Disconnect** removes the webhook. To use another channel, disconnect and connect the new webhook.

## If something is off

| The page says | What it means |
| --- | --- |
| Set up from the relaying GM's browser | Open the settings in the browser of the GM who relays rolls |
| Discord needs Gamelog PRO | The membership does not include it |
| Temporarily disabled by the server | Posting is paused on the Gamelog server for a while, usually because of a problem on Discord's side. It comes back on its own |
| Membership unknown (not connected) | Connect to Gamelog in this browser first |

If you delete the webhook in Discord, rolls are no longer posted. Connect a new webhook.
