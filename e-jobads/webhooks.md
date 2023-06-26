# 🪝 Webhooks

**Follow this simple steps to setup your webhooks.**

* Goto Webhook.lua and open it in visual studio code or in any other editor of your choice

**Setting up a webhook on discord:**

1.  **Open the Discord Channel Settings**

    Navigate to the channel for which you want to create a webhook. Click the gear icon next to the channel's name to open the Channel Settings.
2.  **Create the Webhook**

    In the Channel Settings, click on the 'Integrations' tab. From there, click on the 'Webhooks' button, then the 'New Webhook' button. This will take you to the setup page.

    Here you can customize your webhook. You can change the name, choose an avatar, and select the channel where the webhook will post.
3.  **Save and Copy the Webhook URL**

    After customizing, click 'Copy Webhook URL'. This is the URL you will use to post messages to your Discord channel programmatically. Make sure to keep this URL secret, as anyone with the URL can post to your Discord channel.

    Once you're done, click the 'Save' button.

[_<mark style="background-color:red;">**DISCLAIMER AND WARNING: NEVER EVER SHARE ANY OF YOUR WEBHOOKS AND DONT SHOW THEM TO ANYONE. THIS MAY CAUSE MAJOR TROUBLE IF SOMEONE HAS THEM. WEBHOOKS ARE SAFE AS LONG AS YOU KEEP THEM FOR YOURSELF AND PEOPLE YOU TRUST.**</mark>_](#user-content-fn-1)[^1]

**Adding your webhook to the Webhook. lua:**

{% code title="Webhook.lua" lineNumbers="true" %}
```lua
Webhook = {}

Webhook.Ads = "https://discordapp.com/api/webhooks/" -- add your webhook here
Webhook.Servername = "EvolvedStudios" -- add your servername here
```
{% endcode %}

Congratulations! Youve setted up an own webhook. For safety purpose make the channel only visible for admins or staff members.

[^1]: 
