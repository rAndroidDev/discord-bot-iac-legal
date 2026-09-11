# Privacy Policy — Mosquito

**Effective date:** 11 September 2026  
**Application:** Mosquito, a Discord bot for the /r/AndroidDev Discord server  
**Operator:** the volunteer moderation team of the /r/AndroidDev Discord server

Mosquito is an April Fools joke bot for the /r/AndroidDev Discord server. It is not a public product for other Discord servers. It is typically enabled only around April 1.

## What Mosquito does

Mosquito reads message text in allowed channels so it can:

- reply when a message contains configured joke keywords (for example “bug”, “flutter”, “mosquito”)
- sometimes add a mosquito reaction or post “Bzzz”
- respond when it is @mentioned
- run slash commands `/buzz` and `/zap` (`/zap` temporarily suppresses the random reactions and “Bzzz” lines in that channel)

Staff can exclude channels entirely.

## Data Mosquito processes

- Discord user ID of the message author (only to ignore the bot’s own messages and to receive slash-command interactions)
- Channel ID (to honor exclusions and `/zap`)
- Message text, in memory, to test keyword matches and whether the bot was mentioned

Mosquito does **not** send message content to the Google Gemini API or any other third party. It does **not** process presence. It does **not** listen for member join, leave, or member-update events. It does **not** keep a database.

## Where data goes

Keyword checks happen in memory on the host and are discarded after the message is handled. Joke replies and reactions are ordinary Discord messages in the same channel. `/zap` keeps a short in-memory timer per channel (about 15 minutes) and does not store message text.

## Retention

Mosquito does not retain message content after handling the event. Channel messages it posted remain on Discord until deleted.

## Children

The bot is only used in a Discord server. Discord’s terms require users to meet Discord’s minimum age. Mosquito is not directed at children.

## Changes

We will update this page when Mosquito’s data practices change. The effective date at the top is the date of the current version. You do not need to accept or re-agree to updates.

## Contact

Moderators of the [/r/AndroidDev Discord community](https://discord.gg/D2cNrqX).
