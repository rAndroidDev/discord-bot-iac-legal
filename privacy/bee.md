# Privacy Policy — Bee

**Effective date:** 11 September 2026  
**Application:** Bee, a Discord bot for the /r/AndroidDev Discord server  
**Operator:** the volunteer moderation team of the /r/AndroidDev Discord server

Bee is the jobs-channel bot for the /r/AndroidDev Discord server. It is not a public product for other Discord servers. This policy describes how Bee handles Discord data in that server.

## What Bee does

When someone posts in the jobs channel, Bee deletes that message so it is not publicly visible, then runs a review workflow:

1. Optionally send the post text to the **Google Gemini API** to check channel rules and extract structured fields (title, company, location, and similar).
2. Post a **staff-only review** in the moderation queue (Approve / Reject / Edit).
3. DM the author an acknowledgment, and later an approval or rejection.
4. If approved, post a structured job listing in the jobs channel.

The Google Gemini API is advisory. A human moderator always decides. If the Google Gemini API is unavailable, staff review the post manually.

## Data Bee processes

- Discord user ID, username, avatar (for embed attribution), and mention
- Channel and message IDs, jump links
- The full text of the jobs-channel submission (and any later edit instructions from moderators)
- The Google Gemini API’s compliance label, confidence, issues, observations, rationale, and extracted fields
- Moderator identity and timestamps for approve / reject / edit
- Optional rejection reasons (written by staff)
- Optional “how did it go?” feedback if the author marks a post fulfilled or found
- Whether a DM could be delivered (not the post body) when a DM cannot be sent

Bee does **not** process presence. It does **not** listen for member join, leave, or member-update events.

## Where data goes

**No bot-operated database.** Bee is stateless. Review state lives in Discord embeds and button IDs, not in a database on the machines that run the bot.

**On Discord:**

- The original jobs-channel message is deleted immediately.
- Staff see the submission (or a long preview) and the Google Gemini API’s assessment in the moderation queue.
- Approved posts appear in the jobs channel as a structured embed (including a copy of the original message text in that embed).
- Acknowledgment, approval, and rejection DMs may include post text or extracted fields so the author can see what was decided.
- If DMs are closed, Bee pings the author in a fallback channel with a retry button. **That fallback message does not include the job post body.**

**Off Discord:**

When the Google Gemini API is enabled, Bee sends the submission text (and, for staff edits that use the Google Gemini API, the current field values plus the moderator’s instruction) to the **Google Gemini API**.

Under the paid Google Gemini API terms, Google does not use those prompts or responses to train or improve its products. Google may keep limited safety logs for a short period, as described in [Google’s Gemini API additional terms](https://ai.google.dev/gemini-api/terms).

Google is used as a **service provider** for inference. Bee does not train or fine-tune models on Discord data.

If the Google Gemini API is not enabled, Bee still intercepts jobs posts and sends them to staff for manual review.

## Retention

- Bee itself retains nothing after the request finishes.
- Review embeds, live job posts, DMs, and logs remain on Discord until staff or Discord remove them.
- Google’s paid-API safety logging follows Google’s terms.

## Children

The bot is only used in a Discord server. Discord’s terms require users to meet Discord’s minimum age. Bee is not directed at children.

## Changes

We will update this page when Bee’s data practices change. The effective date at the top is the date of the current version. You do not need to accept or re-agree to updates.

## Contact

Moderators of the [/r/AndroidDev Discord community](https://discord.gg/D2cNrqX).
