# Contribution Guidelines

The AvaIre Agent is [API.AI](https://api.ai/) agent that [AvaIre](https://github.com/AvaIre/AvaIre) uses for handling AI requests, if you'd like to contribute to the AI please follow the guidelines so there is some consistency within the agent.

## Guidelines

 - **Intents**
    - Intent names should clearly describe what the intent is **OR** be the action name.
    - Intents must **NOT** have an event attached to it.
    - All intents must have an action attached to it.
        - All actions must be **ALL** lowercase.
        - Actions must contain at least one dot, for example `smalltalk.hello` or `request.cat`.
    - All text responses must be in English.
        - Swear words are allowed for comedic effect, just don't use them needlessly.
 - **Entities**
    - Entity names should clearly describe what the entity is.
    - Entity names should be all lowercase.
    - Entity values and synonyms can contain both upper and lowercase letters.

### Smalltalk Actions

Smalltalk actions have a special role within Ava, any AI action that starts with `smalltalk.` will have the text response associated with the intent formated for placeholders and sent back to the user directly, this means that any smalltalk action **MUST** include at least one text response.

#### Smalltalk Action Placeholders

| Placeholder       | Description      |
| ----------------- |:---------------- |
| %user% |  Will be replaced with the user's username that triggered the AI intent. |
| %nick% |  Will be replaced with the user's nickname that triggered the AI intent, if the user doesn't have a nickname the user's username will be used instead. |

### Custom Actions

Creating new custom actions can be awesome, however, custom actions need to be implemented in Avas AI intent handler for them to work properly, if you're creating a new custom action you should also write the Intent handler in Ava to support it. You can find Avas intent handler list at [`/app/services/ai/Intents.js`](https://github.com/AvaIre/AvaIre/blob/master/app/services/ai/Intents.js) while the actual intent handlers are located in [`/app/services/ai/intents`](https://github.com/AvaIre/AvaIre/tree/master/app/services/ai/intents) and has to extend the `IntentHandler` class, a simple intent handler that just says sends back the text responses from the intent in an info-embedded element would look like the following.

```javascript
/** @ignore */
const IntentHandler = require('./IntentHandler');

/**
 * Describe your custom intent here so the documentation stays up
 * to date and other developers can easily understand what it
 * does without having to look at the code.
 *
 * @extends {IntentHandler}
 */
class CustomIntent extends IntentHandler {

    /**
     * This is invoked by the service provider when the AI
     * returns a matching response action for the intent.
     */
    handle() {
        return app.envoyer.sendInfo(this.getMessage(), this.response.result.fulfillment.speech);
    }
}

module.exports = CustomIntent;

```