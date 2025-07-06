<div align="center">
  <h1>EventSurge</h1>
  <p>A powerful, flexible, and modern event management plugin for Minecraft servers</p>
</div>

---

## 🚀 What's New in 2.1.0
- **Double progress bug fixed**: No more double counting or duplicate listeners
- **Global & Community Event Sync**: Server-wide progress and rewards, with new global event types
- **Full Multi-Language Support**: Built-in English, Spanish, Indonesian, French, and German (see below)
- **Improved GUI**: Better event info, status, and creation tools
- **Debug Mode Toggle**: Enable detailed logging for troubleshooting
- **More Config Options**: Fine-tune event, GUI, and reward settings

---

## 🌍 Multi-Language Support
EventSurge now supports:
- **English** (en)
- **Spanish** (es)
- **Indonesian** (id)
- **French** (fr)
- **German** (de)

**How to change language:**
1. Use the command: /es lang <lang>  |  Example: /es lang es
2. Make sure the language file exists in the folder: /plugins/EventSurge/lang/

You can also customize any message by editing the language files in `lang/`.

---

## Features
- **Multiple Event Types**: Mining, Killing, Fishing, Crafting, Placing, and Custom events
- **Custom Event Builder**: Create any event in-game (in-chat, with GUI trigger)
- **Real-time Progress Tracking**: Visual bars, auto-completion, player-specific and community progress
- **Reward System**: Money (Vault), command, and display rewards, with broadcast announcements
- **Community & Global Events**: Server-wide progress and rewards
- **User-friendly & Flexible**: Simple config, tab completion, GUI manager, player history, debug mode, multi-language
- **Performance & Quality**: Async operations, detailed logging, error handling, supports all modern Minecraft versions

---

## 🏁 Quick Start
```yaml
# config.yml (snippet)
debug: false
language: "en"
broadcast-prefix: "&6[EventSurge] &f"
prefix-settings:
  use-prefix-by-default: true
  show-prefix-in-rewards: true
  show-prefix-in-descriptions: false
allow-multiple-events: true
# ... more options below
```

```yaml
# events.yml (snippet)
events:
  diamond_miner:
    type: mine
    target: DIAMOND_ORE
    amount: 10
    title: "💎 Diamond Miner"
    description: "Mine 10 diamond ores to prove your mining skills!"
    broadcast: true
    use-prefix: true
    duration-minutes: 30
    allow-multiple: false
    reward:
      command: "give %player% netherite_ingot 2"
      display: "2x Netherite Ingot"
      money: 1000

  mixed_mining:
    type: custom
    target: mine
    title: "🏔️ Mixed Mining Challenge"
    description: "Mine different types of valuable ores!"
    broadcast: true
    use-prefix: true
    duration-minutes: 120
    allow-multiple: true
    objectives:
      DIAMOND_ORE: 5
      EMERALD_ORE: 10
      GOLD_ORE: 20
    reward:
      command: "give %player% netherite_block 1"
      display: "1x Netherite Block"
      money: 2000

  community_mining:
    type: custom
    target: mine
    title: "🏆 Community Mining Challenge"
    description: "Work together to mine massive amounts of resources!"
    broadcast: true
    use-prefix: true
    duration-minutes: 180
    allow-multiple: true
    objectives:
      DIAMOND_ORE: 100
      EMERALD_ORE: 200
      GOLD_ORE: 500
    reward:
      command: "give %player% netherite_ingot 10"
      display: "10x Netherite Ingot"
      money: 5000
```

---

## 🕹️ Commands
| Command | Description | Permission |
|---------|-------------|------------|
| `/eventsurge info` | Show all active event info | eventsurge.participate |
| `/eventsurge progress` | Check your progress for all events | eventsurge.participate |
| `/eventsurge history` | View your event history | eventsurge.participate |
| `/eventsurge gui` | Open event selection GUI | eventsurge.admin |
| `/eventsurge start <event>` | Start an event | eventsurge.admin |
| `/eventsurge stop` | Stop all active events | eventsurge.admin |
| `/eventsurge stop <event>` | Stop a specific event | eventsurge.admin |
| `/eventsurge reload` | Reload configuration and languages | eventsurge.admin |
| `/eventsurge active` | List all active events | eventsurge.participate |

---

## 🛠️ Configuration
<details>
<summary>Click to view config.yml</summary>

```yaml
# EventSurge Configuration

debug: false
language: "en"
broadcast-prefix: "&6[EventSurge] &f"
prefix-settings:
  use-prefix-by-default: true
  show-prefix-in-rewards: true
  show-prefix-in-descriptions: false
messages:
  no-permission: "&cYou don't have permission to use this command!"
  event-start: "&aEvent has started: %event%"
  event-stop: "&cEvent has been stopped: %event%"
  event-complete: "&a%player% has completed the %event% event!"
  progress: "&7Progress: &e%current%&7/&e%target% &7%type%"
  event-reminder: "&7Event in progress: &e%event% &7- %description%"
  reward-announcement: "&a%player% has received &e%reward% &afor completing &6%event%! &7🎁"
  time-remaining: "&e%event% &7has &e%time% &7minutes remaining!"
  event-expired: "&cEvent &e%event% &chas expired!"
announce-sound: "ENTITY_EXPERIENCE_ORB_PICKUP"
reminder-sound: "BLOCK_NOTE_BLOCK_PLING"
auto-start: true
interval-seconds: 1800
announcement-interval: 300
allow-multiple-events: true
gui:
  title: "&8Event Manager"
  rows: 3
custom-events:
  max-duration: 1440
  max-objectives: 10
  allow-money-rewards: true
  allow-command-rewards: true
multiple-events:
  enabled: true
  max-concurrent: 5
  show-all-active: true
debug-settings:
  log-event-registration: true
  log-progress-updates: true
  log-reward-execution: true
  log-permission-checks: true
  log-configuration-loading: true
```
</details>

<details>
<summary>Click to view events.yml</summary>

```yaml
# Example events
events:
  diamond_miner:
    type: mine
    target: DIAMOND_ORE
    amount: 10
    title: "💎 Diamond Miner"
    description: "Mine 10 diamond ores to prove your mining skills!"
    broadcast: true
    use-prefix: true
    duration-minutes: 30
    allow-multiple: false
    reward:
      command: "give %player% netherite_ingot 2"
      display: "2x Netherite Ingot"
      money: 1000

  mixed_mining:
    type: custom
    target: mine
    title: "🏔️ Mixed Mining Challenge"
    description: "Mine different types of valuable ores!"
    broadcast: true
    use-prefix: true
    duration-minutes: 120
    allow-multiple: true
    objectives:
      DIAMOND_ORE: 5
      EMERALD_ORE: 10
      GOLD_ORE: 20
    reward:
      command: "give %player% netherite_block 1"
      display: "1x Netherite Block"
      money: 2000

  community_mining:
    type: custom
    target: mine
    title: "🏆 Community Mining Challenge"
    description: "Work together to mine massive amounts of resources!"
    broadcast: true
    use-prefix: true
    duration-minutes: 180
    allow-multiple: true
    objectives:
      DIAMOND_ORE: 100
      EMERALD_ORE: 200
      GOLD_ORE: 500
    reward:
      command: "give %player% netherite_ingot 10"
      display: "10x Netherite Ingot"
      money: 5000
```
</details>

---

## 🧩 API Usage
```java
// Get the plugin instance
EventSurge plugin = EventSurge.getInstance();

// Create a custom event (see CustomEventBuilder for full options)
AbstractEventType customEvent = new CustomEvent(
    "custom_event",
    "Custom Event",
    true,
    "Description",
    rewardConfig,
    10,
    0,
    true,
    false,
    objectivesMap,
    "place",
    materialTargets,
    entityTargets
);

// Register the event
plugin.getEventManager().registerEvent(customEvent);
```

---

## 🔄 Migration Guide (from 2.0.x or 1.x)
- **Update your config.yml and events.yml** to include new options (see above)
- **Set `allow-multiple-events: true`** in config.yml to enable multiple concurrent events
- **Use the new custom event builder** for flexible event creation
- **Vault is required for money rewards**
- **Multi-language:** Set your language in config.yml
- See `roadmap.md` for full changelog and future plans

---

## ❓ Need Help?
- [Documentation & Roadmap](./roadmap.md)
- Example configs included in the plugin jar
- Open an issue for support
- Use `/eventsurge reload` to reload config

---

<div align="center">
  <b>EventSurge &copy; 2025</b>
</div> 
