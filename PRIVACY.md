# Privacy Policy

**Effective date:** 2 October 2026

This Privacy Policy explains how **SR-Results-Bot** (the "Bot"), operated by the GitHub account **ToddWatkinsDev** ("we," "us," or "our"), collects, uses, stores, and shares information when you use the Bot or participate in a server, regatta, race, signup, or results workflow using the Bot. The account name does not identify the operator's legal person or entity.

This Policy describes how information is processed when you use the Bot. It should be read together with the [Terms of Service](TOS.md).

## 1. Information We Collect

The Bot processes information needed to operate its player, signup, regatta, race, and results features. This includes Discord user IDs and usernames, SailRanks IDs, game/player names and country codes, Discord server IDs, configuration IDs, regatta and signup details, race positions, and timestamps.

### Persistent CSV records

The Bot writes CSV files under `SAILRANKS_DATA_DIR` (which defaults to `data/`):

- `profiles.csv` contains Discord user IDs and names, SailRanks IDs, game names, and country codes.
- `signups.csv` contains Discord user IDs and names, regatta IDs, SailRanks IDs, game names, and country codes.
- `current_race.csv` contains the active regatta ID and name, start time, reminder status, and signup message ID.
- `result_audit.csv` contains the timestamp, regatta ID, race number, finishing position, Discord ID, SailRanks ID, game name, and Discord ID of the person who submitted the results.
- `approved_guilds.csv` contains Discord server IDs and approval status.

### Logs and configuration

The Bot writes logs to its configured Python logging output, which is the terminal by default. In the current deployment, logs are console-only and are not saved after the process ends. Logs can include successful interaction details (user, Discord ID, server ID, and action); profile save/removal details (Discord and SailRanks IDs); SailRanks action details (player ID, name, country, or regatta ID); and error details, exception causes or codes, and command inputs. Logs may include the SailRanks login username. The standard login-success log does not intentionally include the configured password hash. In dry-run mode, logs include the SailRanks write payload that would have been sent, which may contain player or result data. Bot and SailRanks credentials may be present in deployment configuration; do not share them in support requests.

During SailRanks requests, the HTTP session may hold a temporary authentication cookie in memory. The Bot uses aiohttp's default in-memory cookie jar, does not save the cookie to a file, and does not explicitly log it. The session is closed on shutdown and the in-memory cookie is lost when the process exits. This does not rule out separate host-level mechanisms such as memory dumps or swap.

The Bot also processes information through Discord interactions and API requests, including information supplied in command options. Do not submit passwords, payment details, government identification, health information, or other sensitive personal information through Bot commands.

## 2. How We Use Information

We use collected information to:

- create, link, and maintain player records;
- process signups and participation in regattas, races, or events;
- record, display, verify, and correct race results;
- identify who submitted a result or changed a record;
- associate players with SailRanks and in-game names;
- send relevant Bot notifications and provide support;
- configure channels, roles, and permissions for a Discord server;
- prevent spam, fraud, abuse, and unauthorized access;
- troubleshoot errors and improve reliability using operational logs; and
- comply with legal obligations or respond to lawful requests.

We do not use the information listed in this policy to sell personal profiles or for targeted advertising.

Our preliminary assessment is that legitimate interests may provide a lawful basis for the following activities, subject to confirming the purposes, necessity, safeguards, and balancing of interests:

- The operator's interests in maintaining player links, operating signup and results workflows, approving servers, and securing and troubleshooting the Bot.
- Event organizers' interests in managing signups, operating regattas, and maintaining results. An organizer may determine the purposes and means of some event-related processing and may act as a separate controller.

A contract may be a lawful basis only where the person whose data is processed is a party to the relevant agreement and the processing is necessary to perform it. A legal obligation applies only where a specific legal requirement requires the processing or retention. The legal bases and the parties' data-protection roles remain subject to confirmation.

## 3. Where Information Is Visible

Information submitted through Discord may be visible to members of the relevant server, moderators, event organizers, and others with access to the relevant channels or result records. Race results and player records may also appear in leaderboards, event summaries, exports, and other Bot outputs.

Server owners and administrators control many of the channels, roles, permissions, and workflows in which the Bot operates. They are responsible for configuring their server appropriately and for giving their members any additional notices required by applicable law.

The operator determines how the Bot's player-linking, signup, results, and audit features are designed and operated. Server and event organizers choose event-specific settings, including which regatta to run, who may use officer commands, and where results are posted. Each party therefore makes decisions about some processing. Each is responsible for the processing purposes it determines. Where the operator and an organizer jointly determine the purposes and essential means of particular processing, they may have joint-controller responsibilities. The precise roles depend on the parties' actual arrangements and have not been legally assessed; the operator does not act solely on organizers' instructions.

## 4. Sharing and Service Providers

The Bot displays information through Discord, including signup cards, standings, reminders, and command replies. The information shown can include names, positions, SailRanks IDs, and race data. Visibility depends on whether a reply or channel post is public or ephemeral and on the server's channel permissions.

We may share information with:

- Discord servers and event organizers using the Bot;
- SailRanks, when a feature requires sending relevant player, signup, or result information to that service;
- Discord, as necessary to operate the Bot and its commands; and
- public authorities or other parties where required by law, or where reasonably necessary to investigate abuse or protect the rights, safety, and property of users, the Bot, Discord communities, or others.

We do not sell personal information or share it with third parties for their independent marketing purposes. The Bot runs on a server managed by the operator in England. Persistent records are stored in local CSV files under `SAILRANKS_DATA_DIR` (default: `data/`). The operator states that they are the only person with access to the server, files, and logs, and that no backups are currently made. The Bot writes logs to the process console by default. The Bot is not configured to send information to a separate analytics or advertising service.

## 5. Retention and Deletion

The Bot does not automatically expire stored records:

- **Profiles:** A profile remains in `profiles.csv` until an officer uses `/unlink` for that member or the file is manually edited or deleted.
- **Signups:** A signup remains in `signups.csv` until the user withdraws, an officer unlinks the member, a new `/race` is set, `/end` is run, or the file is manually edited or deleted.
- **Active race:** The record in `current_race.csv` remains until `/end` clears it, another `/race` replaces it, or the file is manually edited or deleted. It persists when the Bot restarts.
- **Result audit:** Each results submission is appended to `result_audit.csv`. Entries are retained indefinitely unless the file is manually edited or deleted; the Bot has no normal command for deleting historical entries.
- **Server approval:** Server approval status is recorded in `approved_guilds.csv`. The Bot has no automatic expiry process for these records.
- **Logs:** The Bot writes logs to the process console and does not configure a log file or rotation. In the current deployment, console output is not saved after the process ends.

No backups are currently made. Removing the Bot from a server does not itself delete existing CSV records, exported records, or information held by server administrators, event organizers, Discord, or SailRanks. It also does not remove historical result-audit entries. For a privacy request, contact the operator privately on Discord at **Jerseytbw** (user ID **422045346902966272**). Do not post Discord IDs, player details, or other personal information in public [GitHub Issues](https://github.com/ToddWatkinsDev/SR-Results-Bot/issues) or public Discord support channels.

## 6. Security

The operator states that they are the only person with access to the server, CSV files, and logs; that no backups are currently made; and that Bot and SailRanks credentials are stored outside the public repository with access restricted to them. The Bot uses an in-memory HTTP cookie jar for temporary SailRanks authentication. It does not save or explicitly log the cookie, and the cookie is lost when the process exits. This does not rule out host-level mechanisms such as memory dumps or swap. Other server access controls have not been confirmed. No online service or storage system is completely secure. Do not submit sensitive information through Bot commands or forms.

## 7. International Processing

The Bot's server is located in England. SailRanks' terms state that its website is hosted by OVH in France. Bot requests to SailRanks are therefore likely handled by that service, but this does not establish where Bot-submitted information is stored, copied, or logged, or where SailRanks keeps backups. Discord may also process information in other locations under its own arrangements. The relevant processing locations and any applicable international-transfer safeguards have not been confirmed with the providers.

## 8. Your Rights

Depending on where you live, you may have rights to request access to, correction of, deletion of, or a copy of your personal information, or to object to or restrict certain processing. Under UK data-protection law, you may also have rights relating to automated decision-making and data portability, subject to applicable exceptions. You may complain to the [UK Information Commissioner's Office (ICO)](https://ico.org.uk/make-a-complaint/) if you believe your information has been handled unlawfully.

To make a rights request, send a private Discord message to **Jerseytbw** (user ID **422045346902966272**). Do not submit requests or personal information through public GitHub Issues or public Discord support channels.

## 9. Children's Privacy

[Discord's current Terms](https://discord.com/terms) require users to be at least 13 and to meet any higher minimum age required by the laws in their country. The Bot is intended for users who meet Discord's minimum age in their country, including eligible teenagers. The Bot does not verify users' ages, and we do not knowingly collect personal information in violation of applicable age requirements. For a privacy concern involving a child, send a private Discord message to **Jerseytbw** (user ID **422045346902966272**); do not post personal details in public channels.

## 10. Third-Party Services

The Bot depends on Discord and sends relevant player, signup, or result information to SailRanks when a feature requires it. Discord and SailRanks have their own privacy policies and terms. The Bot is not configured to send information to another service provider. This Policy does not describe how Discord or SailRanks independently collect or use information.

## 11. Changes to This Policy

We may update this Privacy Policy when our data practices or legal obligations change. We will post the updated version at [https://github.com/ToddWatkinsDev/SR-Results-Bot/blob/main/PRIVACY.md](https://github.com/ToddWatkinsDev/SR-Results-Bot/blob/main/PRIVACY.md) and update the effective date.

## 12. Contact

For privacy questions, access or deletion requests, corrections, or complaints, contact:

**Operator account:** ToddWatkinsDev. The legal person or entity behind the account has not been identified here.

**General support, help, maintenance schedules, and known issues:** [SR-Results-Bot Discord support server](https://discord.gg/gTb7cMbAXk). Do not share personal information in public support channels.

**Privacy, deletion, and legal requests:** Send a private Discord message to **Jerseytbw** (user ID **422045346902966272**). Do not submit these requests or personal information through public GitHub Issues or public Discord channels.

**Privacy policy URL:** [https://github.com/ToddWatkinsDev/SR-Results-Bot/blob/main/PRIVACY.md](https://github.com/ToddWatkinsDev/SR-Results-Bot/blob/main/PRIVACY.md)
