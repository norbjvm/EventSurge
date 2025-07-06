# EventSurge v2.0.0 Documentation

**Plugin Version:** v2.0.0

## Example Screenshots

### 1. Event Progress & Reward Notification
Shows event progress (e.g., placing DIRT blocks) and money reward notification after event completion.
![Event Progress & Reward]

![2025-07-06_08 23 10](https://github.com/user-attachments/assets/3f3327af-130b-4275-a800-3e2e74b2f0cb)

### 2. Event Completion, Multiple Rewards, & Info
Example of event completion messages, item rewards, and active event info displayed in chat.
![Event Completion & Info]

![2025-07-06_09 21 56](https://github.com/user-attachments/assets/71c6a271-5dd2-4be2-9020-af2fb2f01eac)

### 3. Multiple Active Events Display
Display of `/es info` showing several active events at once, with description, target, and reward for each.
![Multiple Active Events]

![2025-07-06_09 39 06](https://github.com/user-attachments/assets/6bcdd7ee-9b96-4afd-b42a-3e4b23140ba4)


### 4. Custom Event GUI
GUI for creating custom events, highlighting main features: multiple objectives, time limits, money rewards, custom commands.
![Custom Event GUI]

![2025-07-06_09 20 48](https://github.com/user-attachments/assets/f203e175-ff9e-47d0-ba9b-75840e150dd0)
---
## Overview
EventSurge is a powerful, flexible event management plugin for Minecraft servers. It allows you to create, manage, and reward players for participating in a variety of server events, with real-time progress tracking, custom objectives, and a user-friendly GUI.

---

## What's New in 2.0.0
- **Custom Event Builder (NEW!)** – Create your own events in-game with a chat wizard and GUI trigger.
- **Block Placing Events** – Now fully supports events where players compete by placing blocks.
- **Multiple Objectives** – Each event can have several missions/goals at once.
- **Time Limits** – Set a timer/duration for any event.
- **Money & Command Rewards** – Vault support, money prizes, and custom command rewards.
- **Community Events** – Server-wide progress and rewards for everyone.
- **Multiple Events** – Run several events at the same time (configurable).
- **Improved GUI** – Select, create, and manage events directly from the GUI.
- **Enhanced progress/info commands** – View info and progress for all active events.
- **Player event history & achievement tracking.**
- **Debug mode for admins** – detailed logging for easier troubleshooting.
- **Improved error handling, validation, and performance.**

---

## Event Types
- **Mine**: Break specific blocks.
- **Kill**: Kill specific entities.
- **Fish**: Catch fish.
- **Craft**: Craft items.
- **Place**: Place specific blocks.
- **Custom**: Use the builder to create any combination of objectives.

---

## Custom Event Builder
- Access via `/eventsurge gui` and click "Create Custom Event".
- Follow the chat prompts to set:
  - Title, description, type (mine, kill, place, etc), duration, prefix, objectives, rewards, etc.
- Supports multiple objectives, time limits, money/command rewards, and more.
- Event starts immediately after creation.

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

---

## Rewards
- **Money**: Requires Vault. Set `money: <amount>` in reward section.
- **Command**: Run any command as reward. Use `command: "<command>"`.
- **Display**: Custom display name for the reward.
- **Multiple rewards**: Supported via custom event builder.

---

## Player History & Achievements
- Players can view their event participation history and achievements via `/eventsurge history`.
- Achievements are tracked per player and per event type.

---

## Debug Mode
- Enable debug mode in `config.yml` for detailed logging.
- Useful for troubleshooting and reporting issues.

---

## Migration Guide
- Update your `config.yml` and `events.yml` to include new options (see above).
- Use the new custom event builder for flexible event creation.
- Set `allow-multiple-events: true` in `config.yml` to enable multiple concurrent events.
- Vault is required for money rewards.
- See `roadmap.md` for full changelog and future plans.

---

## FAQ
**Q: How do I create a custom event?**  
A: Use `/eventsurge gui` and follow the prompts for "Create Custom Event".

**Q: How do I give money as a reward?**  
A: Add `money: <amount>` in the reward section and make sure Vault is installed.

**Q: Can I run multiple events at once?**  
A: Yes! Set `allow-multiple-events: true` in `config.yml`.

**Q: Where can I get support?**  
A: Open an issue on GitHub.

---

EventSurge © 2025 
