<div align="center">

# ⚔️ SimpleLogs 
**A Next-Generation Combat & Forensic Logging System for Modern SMPs**

[![Version](https://img.shields.io/badge/Version-1.0-blue.svg)](https://github.com/YounggamingDJ/SimpleLogs)
[![API](https://img.shields.io/badge/API-1.21.1+-green.svg)](https://papermc.io/)
[![Author](https://img.shields.io/badge/Author-YounggamingDJ-red.svg)](#)

*SimpleLogs is an extremely lightweight, high-performance combat logging and server forensics plugin. Designed specifically for Spigot & Paper environments, it prevents PvP unfairness while empowering admins with deep-tracking mechanics.*

</div>

---

## 🌟 Key Features

### ⚔️ **Advanced Combat Tagging**
- **Grace Period**: Configure a timer to prevent players from instantly being combat-tagged when they first join. Protects your community from spawn-killers!
- **Dynamic Action Options**: Decide exactly what happens when a player combat logs (`KILL`, `PUNISH`, or `BOTH`).
- **Loot Drop Support**: Support for dropping the escaping player's loot seamlessly—keeping PvP rewarding.
- **Audio/Visual Feedback**: ActionBars, configurable Bossbars, and custom combat-start sound cues (`ENTITY_ENDER_DRAGON_GROWL`).

### 💣 **Explosion Forensics (For Private SMPs)**
A unique, high-performance tracking system for finding "who blew up what" on your server!
- **Deep Tracking**: Monitors TNT ignitions, Bed (Nether/End) explosions, End Crystals, and Respawn Anchors.
- **Suspect Highlighting System**: Any player within a configurable radius of an explosion is flagged as a `SUSPECT`.
- **In-Memory Ring Buffers**: Uses O(1) complexity async processing—making it 100% lag-free.

### 📜 **Asynchronous Storage & History**
- **Zero-Lag File I/O**: File writing, reading, and parsing are entirely asynchronous.
- **In-Game Log Viewing**: Access a player's recent combat encounters or server-wide explosions without leaving the game.
- **Player Storage Modes**: Store logs globally or split them by `PER_PLAYER` cleanly.

### 🛡️ **Punishment & Restriction Engine**
- Block teleportation, spawn, or any unwanted commands dynamically (Whitelist & Blacklist support).
- Automatic configurable `Bans`, `Tempbans`, and `Warnings` natively built-in.

---

## 🛠️ Commands & Permissions

| Command | Permission | Description |
|---|---|---|
| `/sl` | - | Shows version and help menu |
| `/sl reload` | `simplelogs.reload` | Reloads the configuration variables |
| `/sl setmode <private/public>` | `OP` / `simplelogs.admin` | Switches between SMP (Explosions) and Public mode |
| `/sl history <player>` | `simplelogs.history` | Displays a player's latest combat logs |
| `/sl explosions` | `simplelogs.explosions` | View recent explosion forensics |
| *Bypass Restrictions* | `simplelogs.bypass` | Bypasses blacklisted commands while tagged |

---

## ⚙️ Configuration Setup

Our configuration is extensive, clear, and easy to modify without reloading the server. Customize exactly how long combat should last, what players see, where logs save, and how abusers are punished!

> [!TIP]
> **Performance Recommendation** 
> If you are running a massive public server with heavy player flow, setting `server-mode.type: PUBLIC` disables explosion tracking completely, preserving critical CPU ticks.

---

## 🚀 Built For Performance

As server developers, we know TPS drops kill servers. 
**SimpleLogs operates utilizing:**
- `ConcurrentHashMaps` & `HashSets` for near instantaneous `O(1)` memory lookup.
- `distanceSquared` math instead of standard `sqrt()` to eliminate heavy math operations.
- Dynamic Listener Lifecycle—Explosion trackers automatically completely unregister themselves if they aren't being used.

---

<div align="center">
  <sub>Developed with ❤️ by YounggamingDJ</sub>
</div>
