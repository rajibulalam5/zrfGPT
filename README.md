# zrfGPT
Example Discord bot written in Python that uses the OpenAI API to have conversations with the `text-davinci-003` model, and the moderations API to filter the messages.


<h1 align="center">
  <br>
  <a href="https://github.com/Cog-Creators/Red-DiscordBot/tree/V3/develop"><img src="https://imgur.com/pY1WUFX.png" alt="Red - Discord Bot"></a>
  <br>
  Red Discord Bot
  <br>
</h1>

# Please read!


**For any problems running this specific bot:** [Discord Project Post](https://discord.com/channels/974519864045756446/1055336272543092757)

**For general OpenAI API problems or questions:** [Discord API Discussions](https://discord.com/channels/974519864045756446/1037561178286739466)

**For bugs in the template code:** create an Issue

**For feature requests:** this repo is not accepting feature requests, you can discuss potential features in [Discord Project Post](https://discord.com/channels/974519864045756446/1055336272543092757)

**For PRs:** only bug fix PRs wil be accepted. If you are implementing a new feature, please fork this repo.

Thank you!

---
# GPT Discord Bot

Example Discord bot written in Python that uses the [chat completions API](https://platform.openai.com/docs/api-reference/chat/create) to have conversations with the `gpt-3.5-turbo` model, and the [moderations API](https://beta.openai.com/docs/api-reference/moderations) to filter the messages.

This bot uses the [OpenAI Python Library](https://github.com/openai/openai-python) and [discord.py](https://discordpy.readthedocs.io/).


# Features

- `/chat` starts a public thread, with a `message` argument which is the first user message passed to the bot. You can optionally also adjust the `temperature` and `max_tokens` parameters.
- The model will generate a reply for every user message in any threads started with `/chat`
- The entire thread will be passed to the model for each request, so the model will remember previous messages in the thread
- when the context limit is reached, or a max message count is reached in the thread, bot will close the thread
- you can customize the bot instructions by modifying `config.yaml`
- you can change the model, the default value is `gpt-3.5-turbo`

# Optional configuration

1. If you want moderation messages, create and copy the channel id for each server that you want the moderation messages to send to in `SERVER_TO_MODERATION_CHANNEL`. This should be of the format: `server_id:channel_id,server_id_2:channel_id_2`
1. If you want to change the personality of the bot, go to `src/config.yaml` and edit the instructions
1. If you want to change the moderation settings for which messages get flagged or blocked, edit the values in `src/constants.py`. A higher value means less chance of it triggering, with 1.0 being no moderation at all for that category.

# FAQ

> Why isn't my bot responding to commands?

Ensure that the channels your bots have access to allow the bot to have these permissions.
- Send Messages
- Send Messages in Threads
- Create Public Threads
- Manage Messages (only for moderation to delete blocked messages)
- Manage Threads
- Read Message History
- Use Application Commands
