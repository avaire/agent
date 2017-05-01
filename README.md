# AvaIre Agent

AvaIre Agent is the [API.AI](https://api.ai/) agent that [AvaIre](https://github.com/AvaIre/AvaIre) uses for handling AI requests, it is a combination of a bunch of custom intents and entities as well as some pre-built AI integrations like `Small Talk`.

## Self Hosting

If you're self-hosting an old version of [AvaIre](https://github.com/AvaIre/AvaIre) and you wanna use the Agent, make sure that the intents in the Agent line up with the intent handlers in the version of [AvaIre](https://github.com/AvaIre/AvaIre) you're using, unresolved intent calls can cause exceptions or making the AI sketchy.


#### How to Import

 - First download the entire repository as a .zip file(or [click here](https://github.com/AvaIre/Agent/archive/master.zip))
 - Head over to your [API.AI](https://api.ai/) agent profile and open up the settings for the agent.
 - Click on the `Export and Import` tab and import the .zip file that you just downloaded.

## Testing the AI

You can easily test Avas AI by joining the **[AvaIre Central](https://discord.gg/gt2FWER)** support server and talking to her in one of the **#sandbox** channels,

#### Self Hosting Tests

You can test the AI by tagging AvaIre in any message as long as the AI module is enabled for the given channel, you can check the status of all modules for a given channel by using the [channel](http://avaire.senither.com/docs/commands#channel) admin command, you can also test the AI directly on [API.AIs](https://api.ai/) website by [clicking here](https://bot.api.ai/fef82466-de68-4e4a-8e24-9369a222cd0d) or following the link below.

https://bot.api.ai/fef82466-de68-4e4a-8e24-9369a222cd0d

> **Note:** Almost all of the custom intents for this agent are resolved client sided(in the bot itself), and therefore a lot of the responses from the website will be `[empty response]`, it is therefore recommended that you test it in Discord.