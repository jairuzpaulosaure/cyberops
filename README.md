# Bot Commands Reference by Access Level

This exhaustive list outlines every single bot command (96 total), categorized by required access level. Each tier inherits the commands from the tiers beneath it.

---

## 1. General Community
These commands are available to everyone in the server by default.

| Command | Inputs | Description |
|---|---|---|
| `/help` | None | Displays the interactive help menu |
| `/ping` | None | Checks the bot's current response latency |
| `/xp profile` | `[user]` | View your own or another user's XP, level, and rank |
| `/xp leaderboard` | None | Display the top 10 XP earners in the server |
| `/event profile` | `[user]` | Check your Event Points and participation tier |
| `/event leaderboard` | None | Display the top 10 most active event attendees |
| `/event raffle list` | None | View all currently active raffles |
| `/social thank` | `<user>` | Thank someone for their help (Awards them 10 XP) |
| `/quiz leaderboard` | None | View the top MLBB quiz scorers |

---

## 2. Server Boosters
These commands are exclusive to members actively boosting the server. The bot dynamically checks the user's booster tier based on their subscription length.

| Command | Inputs | Description |
|---|---|---|
| `/booster perks` | None | View your current booster tier and XP multipliers |
| `/booster list` | None | Display a list of all current server boosters |
| `/booster color` | None | Select an exclusive vanity color role |
| `/booster emblem` | None | Claim an exclusive emblem role (Requires Booster Tier 2+) |
| `/booster raffle` | None | Opt into the booster weekly raffle system |

---

## 3. Moderation Team
These commands require explicit moderation permissions in Discord (e.g., Kick/Ban/Manage Messages). Used strictly to enforce community guidelines.

| Command | Inputs | Description |
|---|---|---|
| `/warn` | `<user>`, `<reason>` | Issue a formal warning (Applies a 24-hour XP lock) |
| `/mute` | `<user>`, `<duration>`, `[reason]`| Timeout/mute a user for a specific duration |
| `/unmute` | `<user>` | Remove a timeout/mute early |
| `/restrict` | `<user>`, `<duration>`, `[reason]`| Revoke permissions to send images and embeds |
| `/unrestrict` | `<user>` | Restore image and embed permissions |
| `/kick` | `<user>`, `[reason]` | Kick a member from the server |
| `/ban` | `<user>`, `[duration]`, `[reason]`| Ban a user (Permanently wipes their economy/XP data) |
| `/unban` | `<user_id>` | Unban a user via their Discord ID |
| `/history` | `<user>` | View a user's complete moderation record |

---

## 4. Administration Team
These commands require the native "Administrator" permission. Admin commands span across full server configuration, economy management, analytics, testing, and event handling.

### Core Setup & Validation
| Command | Inputs | Description |
|---|---|---|
| `/setup view` | None | View all config states and bound channels/roles |
| `/setup channel` | `<type>`, `<channel>` | Map core system channels (e.g., bot, booster_chat) |
| `/setup role` | `<type>`, `<role>` | Map core system roles (e.g., helpers, moderators, msl) |
| `/setup vc` | `<channel>` | Bind specific voice channels internally |
| `/setup color-add` | `<role>` | Add a role to the booster color whitelist |
| `/setup color-remove`| `<role>` | Remove a role from the booster color whitelist |
| `/setup color-list` | None | View all allowable booster color roles |
| `/setup emblem-add` | `<role>` | Add a role to the booster emblem whitelist |
| `/setup emblem-remove`| `<role>` | Remove a role from the booster emblem whitelist |
| `/setup emblem-list` | None | View all allowable booster emblem roles |
| `/setup xp_roles` | `<tier>`, `<role>` | Map Discord roles to XP progression levels |
| `/setup sync_xp_roles`| None | Bulk-assign correct XP tier roles to all users |
| `/setup ep_roles` | `<sub-tier>`, `<role>`| Map Discord roles to Event Point tiers |
| `/setup peak_roles` | `<role>` | Map legacy peak rank roles |
| `/setup trigger_eos` | None | Force trigger End-of-Season routine (Reset EP / peak assignments) |
| `/setup quiz_channel`| `<channel>` | Designate where automated quizzes take place |
| `/setup wipe` | None | Hard factory reset of the bot database |
| `/social bind-badges`| `<role>` | Map dynamic Discord Roles to specific badge achievements |

### Automations & Settings
| Command | Inputs | Description |
|---|---|---|
| `/autorole` | None | Manually trigger auto-role assignment across the server |
| `/voice setup` | `<channel>` | Flag a voice channel to automatically duplicate when joined |
| `/voice remove` | `<channel>` | Strip automatic duplication rules from a channel |
| `/keyword add` | `<word>` | Add a keyword to the automated auto-moderator |
| `/keyword remove` | `<word>` | Remove a keyword from the auto-moderator |
| `/keyword list` | None | View all active restricted keywords |

### Economy (XP & EP) OVERRIDES
| Command | Inputs | Description |
|---|---|---|
| `/xp start/stop` | None | Toggle the global background XP gain system |
| `/xp status` | None | View whether XP gain is globally active |
| `/xp add` | `<user>`, `<amount>` | Force add XP to a specific user |
| `/xp set` | `<user>`, `<amount>` | Hard override a user's total XP value |
| `/xp reset` | `<user>` | Reset a specific user's XP to absolute zero |
| `/ep add` | `<user>`, `<amount>` | Force add Event Points to a specific user |
| `/ep set` | `<user>`, `<amount>` | Hard override a user's total EP value |
| `/ep reset` | `<user>` | Reset a single user's Event Points to zero |

### Events, Raffles & Quizzes
| Command | Inputs | Description |
|---|---|---|
| `/event kiosk` | `<channel>` | Deploy an RSVP/Check-in button for an active Voice Event |
| `/event status` | None | Generate a live dashboard of Event Health and Attendance |
| `/event cap-placement`| `<event>`, `<amount>`| Lock a rigid EP budget ceiling on competitive events |
| `/event placement` | `<user>`, `<event>` | Award competitive placement (deducts safely from budget) |
| `/event revoke` | `<payout_id>` | Erase a false EP payout record entirely |
| `/overflow add` | `<event>`, `<channel>`| Link an unlisted Voice Channel to active event tracking |
| `/overflow remove` | `<channel>` | Sever connection between overflow room and the event |
| `/event raffle create`| `<args>` | Deploy a customized raffle with parameters |
| `/event raffle draw` | `<raffle_id>` | Execute draw logic manually |
| `/event raffle cancel`| `<raffle_id>` | Terminate a scheduled event raffle |
| `/quiz start/stop` | None | Toggle the automated trivia engine |
| `/quiz status` | None | View next scheduled quiz info |
| `/quiz reload` | None | Hot-reload trivia questions bank |

### Verification & Moonton Student Leaders (MSL)
| Command | Inputs | Description |
|---|---|---|
| `/verify deploy` | `<channel>` | Post the interactive verification widget |
| `/verify status` | `<user>` | Check a user's backend MLBB database sync |
| `/verify whois` | `<uid>` | Reverse lookup Discord user by their MLBB UID |
| `/verify update` | `<user>` | Admin override to edit a user's MLBB validation |
| `/verify remove` | `<user>` | Unlink / strip verification from a participant |
| `/msl setup` | `<url>`, `<role>` | Connect Google Sheets to the MSL validation layer |
| `/msl refresh` | None | Force immediate cache refresh of the MSL spreadsheet |
| `/msl check` | `<user>` | Retroactively assign MSL roles to already-verified users |

### Tickets Management
| Command | Inputs | Description |
|---|---|---|
| `/ticket deploy` | `[channel]` | Post the interactive ticket creation hub |
| `/ticket config-category`| `<category>` | Designate category folder for active ticket spawns |
| `/ticket config-roles`| `<role>`, `<type>` | Bind staff hierarchies to ticket permission levels |
| `/ticket test` | None | Safely toggle diagnostic mode for tickets |
| `/ticket stats` | None | Export ticket rating and speed resolutions |

### Analytics & Tracking Data
| Command | Inputs | Description |
|---|---|---|
| `/analytics overview` | None | Generate a live 7-day community health summary |
| `/analytics retention`| None | Output the D1, D7, and D30 new member stickiness |
| `/analytics channels` | None | Query top 10 channels by message volume |
| `/analytics voice` | None | Query top 10 channels by voice traffic |
| `/analytics invites` | None | List leading invite links and referrers |
| `/analytics event` | `<event>` | Calculate RSVP-to-Attendance conversion percentage |
| `/analytics roles` | None | Graph opt-in role adoption percentages |
| `/analytics track_link`| `<link>`, `<desc>` | Generate an intercepted tracking button payload |
| `/analytics link_stats`| `<link_id>` | Chart interception clicks and traffic |
| `/analytics peak_hours`| None | Output activity heatmaps |
| `/setup analytics_regions` | `<roles...>` | Configure geographic/regional tracking |
| `/setup analytics_sentiment_channel`| `<channel>` | Log automated AI sentiment analysis |
| `/setup analytics_tracked_roles`| `<roles...>` | Assign key segment tracking tags |
| `/sentiment daily/weekly/monthly`| None | Generate deep qualitative AI community health summaries |

### Embed Configuration (Discohook Interop)
| Command | Inputs | Description |
|---|---|---|
| `/embed send` | `<channel>`, `<json>`| Deploy a standard Discohook sequence directly |
| `/embed edit` | `<link>` | Push live modifications to an existing dynamic embed |
| `/embed download` | `<msg_url>` | Extract JSON tree from live embeds |
| `/embed manage` | None | View, delay, or purge scheduled sequence embeds |
| `/embed logs` | `<channel>` | Map the internal history log for embed broadcasts |

### Testing & Developer Tools
| Command | Inputs | Description |
|---|---|---|
| `/test add-xp` | `<amount>` | Inject naked XP independently |
| `/test add-ep` | `<amount>` | Inject naked Event Points |
| `/test add-tokens` | `<amount>` | Inject raw currency values |
| `/test reset-user` | `<user>` | Wipe single target testing payload |
| `/test set-events` | `<amount>` | Modify user total attended metric |
| `/test set-streak` | `<days>` | Overwrite consecutive daily check-in sequence |
| `/test xp-debug` | None | Output verbose pipeline for XP scaling |
| `/test check-db` | None | Perform core schema validation checks |
| `/testrole` | None | Run assignment pipeline dry-run payload |
| `/auth admin` | `<pass>` | Internal auth command for admin permissions |
| `/auth logout` | None | Terminate active auth session |
