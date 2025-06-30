<div align="center">
  <h1>EventSurge</h1>
  <p>A lightweight and flexible event management plugin for Minecraft servers</p>
</div>

## Features
- **Multiple Event Types**
  - Mining events
  - Kill events
  - Fishing events
  - Crafting events
- **Real-time Progress Tracking**
  - Visual progress bars
  - Automatic completion detection
  - Player-specific progress
- **Reward System**
  - Automatic reward distribution
  - Customizable rewards
  - Broadcast announcements
- **User-friendly**
  - Simple configuration
  - Tab completion
  - Intuitive commands

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
```

## Commands
| Command | Description | Permission |
|---------|-------------|------------|
| `/eventsurge info` | Show current event info | eventsurge.participate |
| `/eventsurge progress` | Check your progress | eventsurge.participate |
| `/eventsurge history` | View your event history | eventsurge.participate |
| `/eventsurge start <event>` | Start an event | eventsurge.admin |
| `/eventsurge stop` | Stop current event | eventsurge.admin |
| `/eventsurge reload` | Reload configuration | eventsurge.admin |

## Configuration
<details>
<summary>Click to view config.yml</summary>

```yaml
# Basic plugin settings
broadcast-prefix: "&6[EventSurge] &f"

messages:
  event-start: "&aEvent has started: %event%"
  event-complete: "&a%player% has completed the %event% event!"
  reward-announcement: "&a%player% has received &e%reward%!"

auto-start: true
interval-seconds: 1800  # 30 minutes
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
```
</details>

## API Usage
```java
// Get the plugin instance
EventSurge plugin = EventSurge.getInstance();

// Create a custom event
AbstractEventType customEvent = new CustomEvent(
    "custom_event",
    "Custom Event",
    true,
    Material.DIAMOND,
    10,
    "Description",
    rewardConfig
);

// Register the event
plugin.getEventManager().registerEvent(customEvent);
```
