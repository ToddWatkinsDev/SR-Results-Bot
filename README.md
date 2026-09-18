# Basic Command List

This bot uses slash commands. The main ones are:

## Public / member commands

- `/srid` — link your Discord account to a SailRanks player
- `/signup` — sign up for the active regatta
- `/withdraw` — remove yourself from the active regatta
- `/whois` — look up a member's linked SailRanks account
- `/checkresults` — view current standings for a regatta

## Officer commands

- `/setup` — set the server's signup/results channels and officer role
- `/createsrid` — create and link a SailRanks player for a user
- `/unlink` — remove a user's SailRanks link
- `/race` — set the active regatta
- `/end` — clear the active regatta and signups
- `/results` — submit race results

---

# Setup Process

1. Put the bot token and SailRanks credentials in `.env`.
2. Start the bot.
3. In Discord, run `/setup`.
4. Choose:
   - the signup channel
   - the results channel
   - the officer channel (optional)
   - the officer role (optional)
5. Members run `/srid` to connect their SailRanks account.
6. An officer runs `/race` with the regatta ID.
7. Members use `/signup` to join the race.
8. When results are ready, an officer runs `/results`.
9. Use `/checkresults` to view standings.

---

# Simple example flow

```text
/setup
/srid sailranks_id:12345
/race regatta_id:67890
/signup
/results race_number:1
/checkresults
```

This is the shortest normal workflow for running a race with the bot.
