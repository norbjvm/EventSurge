<div align="center">
  <h1>EventSurge</h1>
  <p>A powerful, flexible, and modern event management plugin for Minecraft servers</p>
</div>

---
Here’s an updated **README.md** draft for EventSurge v2.1.0, reflecting all the new features, fixes, and improvements—including auto-extracted events, multi-language support, and more.  
---

## 🚀 What's New in 2.1.0
- **Double Progress FIXED** – No more double progress bugs for global or per-player events; event listeners are guaranteed to be registered only once.
- **Global/Community Event Sync** – Global event progress is truly collective and rewards are only given to contributors.
- **Full Multi-Language Support** – All plugin messages (events, help, commands, etc.) are now fully translatable, including the `/eventsurge lang <lang>` command.
- **Built-in Language Files** – Comes with English, Spanish, Indonesian, French, and German language files out of the box!
- **Dynamic Help & Command Messages** – Help/command messages are loaded from language files and displayed in the selected language.
- **Modern GUI Layout** – The event GUI now shows only 3 main categories in the center, with sub-GUIs for each category.
- **More Example Events** – Many new example global and community events (mining, killing, fishing, crafting, placing, custom) included in `events.yml`, ready to use.
- **Debug Mode Toggle** – Debug logging can now be enabled/disabled via `config.yml` (`debug: true/false`).
- **Placeholder & Reload Improvements** – All message placeholders are consistent, and config/language reloads are truly runtime.
- **Event Without Reward** – Events without rewards are now loaded (with a warning), not skipped.
- **Improved Listener Management** – Event listeners are registered/unregistered correctly, preventing duplicate handlers.

---

## Features
- **Multiple Event Types**
  - Mining events
  - Kill events
  - Fishing events
  - Crafting events
  - Block placing events
  - Custom events (with builder)
- **Custom Event Builder**
  - Create any event in-game (in-chat, with GUI trigger)
  - Set type, objectives, time limit, rewards, and more
- **Real-time Progress Tracking**
  - Visual progress bars
  - Automatic completion detection
  - Player-specific progress
  - Multiple objectives per event
- **Reward System**
  - Automatic reward distribution
  - Money (Vault), command, and display rewards
  - Broadcast announcements
  - Community/server-wide rewards
- **User-friendly & Flexible**
  - Simple configuration (`config.yml`, `events.yml`)
  - Tab completion & intuitive commands
  - GUI event manager
  - Player event history
  - Debug mode for admins
  - Allow multiple events at once (configurable)
  - Optional message prefix
  - **Multi-language support** (EN, ES, ID, FR, DE)
- **Performance & Quality**
  - Async operations
  - Detailed logging & error handling
  - Supports all modern Minecraft versions

---

## Quick Start
```yaml
# Create your first event in events.yml
zombie_hunter:
  type: kill
  target: ZOMBIE
  amount: 20
  title: "Zombie Hunter"
  description: "Hunt down 20 zombies!"
  broadcast: true
  reward:
    command: "give %player% diamond 5"
    display: "5x Diamond"

# Example block placing event
beacon_builder:
  type: place
  target: BEACON
  amount: 3
  title: "Beacon Builder"
  description: "Place 3 beacons!"
  broadcast: true
  reward:
    money: 10000
    display: "$10000"
```

---

## Commands
| Command | Description | Permission |
|---------|-------------|------------|
| `/eventsurge info` | Show all active event info | eventsurge.participate |
| `/eventsurge progress` | Check your progress for all events | eventsurge.participate |
| `/eventsurge history` | View your event history | eventsurge.participate |
| `/eventsurge gui` | Open event selection GUI | eventsurge.admin |
| `/eventsurge start <event>` | Start an event | eventsurge.admin |
| `/eventsurge stop` | Stop all active events | eventsurge.admin |
| `/eventsurge reload` | Reload configuration | eventsurge.admin |
| `/eventsurge lang <lang>` | Change plugin language at runtime | eventsurge.admin |

---

## Custom Event Builder (In-Chat)
1. Open the GUI: `/eventsurge gui` and click "Create Custom Event"
2. Follow the chat prompts to set:
   - Title, description, type (mine, kill, place, etc), duration, prefix, objectives, rewards, etc.
3. Supports multiple objectives, time limits, money/command rewards, and more.
4. Event starts immediately after creation!

---

## Configuration
<details>
<summary>Click to view config.yml</summary>

```yaml
# Basic plugin settings
broadcast-prefix: "&6[EventSurge] &f"
debug: false

messages:
  event-start: "&aEvent has started: %event%"
  event-complete: "&a%player% has completed the %event% event!"
  reward-announcement: "&a%player% has received &e%reward%!"

allow-multiple-events: true  # Allow multiple events to run at the same time

# Language and auto-extract
language: "en"
```
</details>

<details>
<summary>Click to view events.yml</summary>

```yaml
# Example events
diamond_miner:
  type: mine
  target: DIAMOND_ORE
  amount: 10
  title: "Diamond Miner"
  description: "Mine 10 diamond ores!"
  broadcast: true
  reward:
    command: "give %player% netherite_ingot 2"
    display: "2x Netherite Ingot"

beacon_builder:
  type: place
  target: BEACON
  amount: 3
  title: "Beacon Builder"
  description: "Place 3 beacons!"
  broadcast: true
  reward:
    money: 10000
    display: "$10000"
```
</details>

---

## API Usage
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

## Migration Guide (from 1.x to 2.x)
- Update your config.yml and events.yml to include new options (see above).
- Use the new custom event builder for flexible event creation.
- Set `allow-multiple-events: true` in config.yml to enable multiple concurrent events.
- Vault is required for money rewards.
- See roadmap.md for full changelog and future plans.

---

## Need Help?
- [Documentation & Roadmap](./roadmap.md)
- Example configs included in the plugin jar
- Open an issue for support

---

<div align="center">
  <b>EventSurge &copy; 2025</b>
</div> 
