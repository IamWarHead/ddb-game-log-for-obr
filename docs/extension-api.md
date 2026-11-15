---
title: Extension API
parent: Integrations
nav_order: 1
---

# Extension API

For developers of other Owlbear Rodeo extensions: send your rolls to Gamelog, and they show up in its roll list and as roll cards on the map. Each card carries a **via** tag with your extension's name.

{: .note }
Rolls from other extensions are a **Gamelog PRO** feature. They only work when the GM who relays the room has a PRO membership and has switched on **Settings → Integrations → Other Owlbear extensions**. Players do not need PRO. Without PRO the switch is locked and Gamelog drops every roll sent to it.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## What the room needs

- Gamelog installed, and **Other Owlbear extensions** switched on by a GM whose membership includes PRO. The switch is off by default.
- For public rolls, a relaying GM in the room, that is, a GM connected to D&D Beyond in Gamelog. Without one, public rolls are dropped. Any player's extension can send public rolls.
- Hidden rolls show only in the history of the GM who made them and never leave that browser. A hidden roll sent from a player's browser is dropped.
- Discord, the statistics and the initiative tracker ignore these rolls. If your extension sets initiative, it does so itself.

## Sending a roll

Send the roll to the channel `com.ddbgamelog/api/roll` with `destination: "LOCAL"`. Only Gamelog in the roller's own browser tab reads the message, and Gamelog passes it on to the room. If Gamelog is not installed, nothing happens.

```ts
await OBR.broadcast.sendMessage("com.ddbgamelog/api/roll", payload, { destination: "LOCAL" });
```

Send each roll once, after its result is known. Gamelog ignores a `rollId` it has already seen.

## Payload schema (version 1)

```ts
interface GamelogRoll {
  /** API version. Messages with any other value are ignored. */
  v: 1;
  /** Your unique id for this roll, 1–64 characters, e.g. a UUID. */
  rollId: string;
  /** Your extension's name for the card's "via …" tag, 1–32 characters. */
  via: string;
  /** Who rolled. */
  entity: {
    /** Non-empty, e.g. the token or character id. */
    id: string;
    type: "character" | "monster" | "other";
    name: string;
    /** https only; other URLs are not shown. */
    avatarUrl?: string;
  };
  /** What was rolled, e.g. "Longsword", "Dexterity Save", "Initiative". At most 256 characters. */
  action: string;
  /** A hidden GM roll that stays in that GM's own history. Default false (public). */
  hidden?: boolean;
  /** 1–10 rolls, e.g. the attack and the damage of one attack. */
  rolls: {
    type: "check" | "save" | "attack" | "damage" | "heal" | "initiative" | "recharge" | "custom" | "other";
    kind: "normal" | "advantage" | "disadvantage" | "critical";
    /** Shown as is, e.g. "2d20kh1+4". */
    formula: string;
    total: number;
    /** The flat modifier, 0 if there is none. */
    constant: number;
    /** One entry per dice group of the formula. */
    dice: {
      /** Sides of the die, e.g. 20. */
      faces: number;
      /** How many dice of this group were rolled. */
      count: number;
      /** Every die rolled; `active: false` for dice that were dropped (advantage, disadvantage). */
      results: { value: number; active: boolean }[];
      /** For keep-highest / keep-lowest rolls. */
      keep?: { mode: "highest" | "lowest"; count: number };
    }[];
    /** A natural 20 or a natural 1 on the d20, otherwise null. */
    outcome: "critical" | "fumble" | null;
  }[];
}
```

Rules:

- The whole message must stay under **15 kB**.
- Malformed messages, messages that are too large and messages with another `v` are ignored without an answer.
- Unknown `type`, `kind` or `entity.type` values fall back to `"other"`, `"normal"` and `"other"`.
- `faces` is a positive whole number, `count` a whole number of 0 or more, and every `value` in `results` a whole number.

## Examples

All examples use `via: "My Dice Roller"`. Replace it with your extension's name.

### Attack and damage

One card with the attack roll and its damage.

```json
{
  "v": 1,
  "rollId": "a1b2c3",
  "via": "My Dice Roller",
  "entity": {
    "id": "token-7f3a",
    "type": "character",
    "name": "Mira Thornwood",
    "avatarUrl": "https://example.com/mira.png"
  },
  "action": "Longsword",
  "rolls": [
    {
      "type": "attack",
      "kind": "normal",
      "formula": "1d20+5",
      "total": 17,
      "constant": 5,
      "dice": [{ "faces": 20, "count": 1, "results": [{ "value": 12, "active": true }] }],
      "outcome": null
    },
    {
      "type": "damage",
      "kind": "normal",
      "formula": "1d8+3",
      "total": 8,
      "constant": 3,
      "dice": [{ "faces": 8, "count": 1, "results": [{ "value": 5, "active": true }] }],
      "outcome": null
    }
  ]
}
```

### Saving throw with advantage

Both d20s go into `results`; the dropped one has `active: false`, and `keep` says which one counts.

```json
{
  "v": 1,
  "rollId": "save-0042",
  "via": "My Dice Roller",
  "entity": { "id": "token-7f3a", "type": "character", "name": "Mira Thornwood" },
  "action": "Dexterity Save",
  "rolls": [
    {
      "type": "save",
      "kind": "advantage",
      "formula": "2d20kh1+2",
      "total": 17,
      "constant": 2,
      "dice": [
        {
          "faces": 20,
          "count": 2,
          "results": [
            { "value": 6, "active": false },
            { "value": 15, "active": true }
          ],
          "keep": { "mode": "highest", "count": 1 }
        }
      ],
      "outcome": null
    }
  ]
}
```

### Critical hit

A natural 20 sets `outcome: "critical"` on the attack. The damage of a critical hit has `kind: "critical"` and the doubled dice.

```json
{
  "v": 1,
  "rollId": "crit-0007",
  "via": "My Dice Roller",
  "entity": { "id": "token-9c1d", "type": "character", "name": "Brakka" },
  "action": "Greataxe",
  "rolls": [
    {
      "type": "attack",
      "kind": "normal",
      "formula": "1d20+6",
      "total": 26,
      "constant": 6,
      "dice": [{ "faces": 20, "count": 1, "results": [{ "value": 20, "active": true }] }],
      "outcome": "critical"
    },
    {
      "type": "damage",
      "kind": "critical",
      "formula": "2d12+4",
      "total": 19,
      "constant": 4,
      "dice": [
        {
          "faces": 12,
          "count": 2,
          "results": [
            { "value": 9, "active": true },
            { "value": 6, "active": true }
          ]
        }
      ],
      "outcome": null
    }
  ]
}
```

### Hidden GM roll with disadvantage

A monster's check that only the GM sees. The kept die is a natural 1, so `outcome` is `"fumble"`. Send it from the GM's browser; from a player's browser it is dropped.

```json
{
  "v": 1,
  "rollId": "gm-stealth-3",
  "via": "My Dice Roller",
  "entity": { "id": "token-goblin-2", "type": "monster", "name": "Goblin Boss" },
  "action": "Stealth",
  "hidden": true,
  "rolls": [
    {
      "type": "check",
      "kind": "disadvantage",
      "formula": "2d20kl1+2",
      "total": 3,
      "constant": 2,
      "dice": [
        {
          "faces": 20,
          "count": 2,
          "results": [
            { "value": 1, "active": true },
            { "value": 14, "active": false }
          ],
          "keep": { "mode": "lowest", "count": 1 }
        }
      ],
      "outcome": "fumble"
    }
  ]
}
```

### Healing

```json
{
  "v": 1,
  "rollId": "heal-0101",
  "via": "My Dice Roller",
  "entity": { "id": "token-4e2b", "type": "character", "name": "Brother Aldous" },
  "action": "Cure Wounds",
  "rolls": [
    {
      "type": "heal",
      "kind": "normal",
      "formula": "2d8+3",
      "total": 12,
      "constant": 3,
      "dice": [
        {
          "faces": 8,
          "count": 2,
          "results": [
            { "value": 4, "active": true },
            { "value": 5, "active": true }
          ]
        }
      ],
      "outcome": null
    }
  ]
}
```

### Several dice groups in one roll

Each group of the formula gets its own `dice` entry, here the weapon die and the smite dice.

```json
{
  "v": 1,
  "rollId": "smite-0002",
  "via": "My Dice Roller",
  "entity": { "id": "token-1a9f", "type": "character", "name": "Sir Caldor" },
  "action": "Longsword + Divine Smite",
  "rolls": [
    {
      "type": "damage",
      "kind": "normal",
      "formula": "1d8+2d8+3",
      "total": 20,
      "constant": 3,
      "dice": [
        { "faces": 8, "count": 1, "results": [{ "value": 7, "active": true }] },
        {
          "faces": 8,
          "count": 2,
          "results": [
            { "value": 4, "active": true },
            { "value": 6, "active": true }
          ]
        }
      ],
      "outcome": null
    }
  ]
}
```

### Custom roll without a character

For table rolls and anything else that is not a character or a monster, use `entity.type: "other"` and `type: "custom"`.

```json
{
  "v": 1,
  "rollId": "wild-0013",
  "via": "My Dice Roller",
  "entity": { "id": "table", "type": "other", "name": "Wild Magic Surge" },
  "action": "Wild Magic table",
  "rolls": [
    {
      "type": "custom",
      "kind": "normal",
      "formula": "1d100",
      "total": 63,
      "constant": 0,
      "dice": [{ "faces": 100, "count": 1, "results": [{ "value": 63, "active": true }] }],
      "outcome": null
    }
  ]
}
```

### Sending it from your extension

```ts
import OBR from "@owlbear-rodeo/sdk";

await OBR.broadcast.sendMessage(
  "com.ddbgamelog/api/roll",
  {
    v: 1,
    rollId: crypto.randomUUID(),
    via: "My Dice Roller",
    entity: { id: token.id, type: "character", name: token.name },
    action: "Longsword",
    rolls: [attackRoll, damageRoll],
  },
  { destination: "LOCAL" },
);
```

## Detecting Gamelog (optional)

Send anything to `com.ddbgamelog/api/ping` with `destination: "LOCAL"`. If Gamelog is installed, it answers on `com.ddbgamelog/api/pong`, also LOCAL:

```ts
{ v: 1, enabled: boolean, relay: boolean }
```

- `enabled`: a GM switched **Other Owlbear extensions** on and the relaying GM's membership includes PRO. Every browser in the room learns this from the relay, so a player's answer is right too. Until a relay has said so, for example in a room that never had one, it is `false`.
- `relay`: a relaying GM is in the room, so public rolls reach the room's history.

```ts
const off = OBR.broadcast.onMessage("com.ddbgamelog/api/pong", (event) => {
  off();
  const { enabled, relay } = event.data as { v: number; enabled: boolean; relay: boolean };
  // e.g. show a "Send rolls to Gamelog" switch only when enabled is true
});
await OBR.broadcast.sendMessage("com.ddbgamelog/api/ping", {}, { destination: "LOCAL" });
```

No answer within about a second means Gamelog is not installed.

Questions about the API? Ask on [Discord](https://discord.com/invite/HSTtrphyFg).
