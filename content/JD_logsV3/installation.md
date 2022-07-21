---
title: "Installation"
weight: 45
---

### Installation

1. Download the latest version from github: https://github.com/prefech/JD_logsV3 (Click the clone button and then download to zip.)
2. Put the JD_logsV3 folder in the server resource directory
    - Make sure to rename the folder to **JD_logsV3**.
3. Get yourself the bot token(s) and add them in the `config/config.json`
    - Not sure how to get a bot token? [How to get a bot token.](https://forum.prefech.com/d/12-how-to-get-a-discord-bot-token)
    - The bots need to have the following intents enabled:
        - Presence Intent
        - Server Members Intent
        - Message Content Intent
4. Add this to your server.cfg
```
ensure JD_logsV3
```
5. Start the resource once and let it build.
6. Go to your discord where you invited the bot (*The one where you want your new main logs to be.*) and use the command `!jdlogs setup`.
    - Make sure the first bot (*The one with the token at `1`*) has permissions to send messages, create channels and create webhooks.
    - All other bots just need permission to send messages in the channels.
7. Restart your server and you will see the logs on your discord.

{{% notice info%}}
If you have any issues installing after this you can make a ticket on our discord and we're happy to help: https://discord.gg/prefech
{{% /notice %}}

{{% notice info%}}
Guess what.
You can look at a video for installation [here](https://www.youtube.com/watch?v=IUNx97XVonk)
{{% /notice %}}
