# Examples

Screenshots of the /r/AndroidDev Discord bots using message content in the server. Each folder is one bot.

## Wasp

Wasp reads message text from newer members and, when the Google Gemini API suggests a possible [rule 6](../privacy/wasp.md) (Play tester solicitation) issue, posts a staff review with an excerpt of that text. A moderator decides whether to warn or dismiss. Wasp does not act on the model output by itself.

See [wasp-message-content/](wasp-message-content/).

## Bee

Bee reads jobs-channel posts so staff can review them before they are visible. The review embed includes the submission text. A public fallback ping used when DMs are closed does not include the post body.

See [bee-message-content/](bee-message-content/).

## Mosquito

Mosquito reads message text in allowed channels to match joke keywords and to notice @mentions. It does not send that text to third parties.

See [mosquito-message-content/](mosquito-message-content/).
