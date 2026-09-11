# Privacy Policy — Wasp

**Effective date:** 11 September 2026  
**Application:** Wasp, a Discord bot for the /r/AndroidDev Discord server  
**Operator:** the volunteer moderation team of the /r/AndroidDev Discord server

Wasp is a moderation bot installed on the /r/AndroidDev Discord server. It is not a public product for other Discord servers. This policy describes how Wasp handles Discord data in that server.

## What Wasp does

Wasp has two features:

1. **Honeypot / `/sting`.** If someone posts in a designated trap channel, or a moderator runs `/sting` on a member, Wasp DMs that user, kicks them from the server (does not ban), and deletes their recent messages in text channels. That path is triggered by posting in the trap channel, or by a moderator choosing a member — not by analyzing the wording of the honeypot message.
2. **Rule 6 screening.** For users with a small number of messages in the server (default: five or fewer), Wasp reads the text of new messages and asks the Google Gemini API whether the message appears to solicit, trade, or buy Google Play testers in a way that would break server rule 6. If the Google Gemini API flags a possible violation, Wasp posts a review in a staff-only channel. **A human moderator must confirm** (warn and delete, or dismiss). Wasp never auto-moderates from the model output.

## Data Wasp processes

Depending on the feature, Wasp may process:

- Discord user ID, username, and mention
- Channel / thread IDs and names
- Message IDs and jump links
- Message text, and short reply-thread context, for rule-6 classification only
- A count of how many messages that author has in the server (used only to decide whether to run rule 6)
- The Google Gemini API’s structured result (whether it thinks rule 6 was violated, confidence, category, short rationale)
- Moderator identity and optional staff notes when a flag is resolved
- Kick / delete success or failure, for staff logs

Wasp does **not** process presence (online status, activity, or platform). It does **not** listen for member join, leave, or member-update events. It does **not** keep a full member list.

## Where data goes

**No bot-operated database.** Wasp is stateless. It does not write user or message data to disk, a database, or object storage on the machines that run the bot. Action state lives in Discord button IDs and Discord embeds.

**On Discord (staff channels in the same server):**

- Rule-6 flags (including a short excerpt of the message and the Google Gemini API’s rationale) go to the moderation queue
- Moderator decisions, excerpts, and honeypot / `/sting` results go to the logs channel
- Public honeypot / `/sting` warning embeds do not quote the user’s message text
- Rule-6 warning DMs explain the rule; they do not quote the original message

**Off Discord (rule 6 only):**

When a message is eligible for rule-6 screening, Wasp sends the message text (and reply-thread context, if any) to the **Google Gemini API** for a one-shot classification.

Under the paid Google Gemini API terms, Google does not use those prompts or responses to train or improve its products. Google may keep limited safety logs for a short period, as described in [Google’s Gemini API additional terms](https://ai.google.dev/gemini-api/terms).

Google is used as a **service provider** for inference. Wasp does not build, train, or fine-tune any machine-learning model on Discord data.

If the Google Gemini API is not enabled, rule-6 screening does not run. Honeypot and `/sting` still run.

## Retention

- Wasp itself retains nothing after the request finishes.
- Copies that appear in Discord staff channels remain until moderators delete those messages, subject to Discord’s own retention.
- Google’s paid-API safety logging follows Google’s terms, not a store we control.

## Children

The bot is only used in a Discord server. Discord’s terms require users to meet Discord’s minimum age. Wasp is not directed at children.

## Changes

We will update this page when Wasp’s data practices change. The effective date at the top is the date of the current version. You do not need to accept or re-agree to updates.

## Contact

Moderators of the [/r/AndroidDev Discord community](https://discord.gg/D2cNrqX).
