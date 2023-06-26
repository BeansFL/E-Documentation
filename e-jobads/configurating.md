# 🛠 Configurating

**Follow this simple steps to configurate your script**

* Open your `config.lua to see what you can configure`

&#x20;  Configurating the framework:

* Change the value of this config to either esx or qbcore to chose your framework

{% code title="Config.lua" lineNumbers="true" %}
```lua
Config = {}

Config.Framework = "esx" -- set to esx or qbcore
```
{% endcode %}

Adding more jobs and the way the script handles the jobs:\


{% code title="Config.lua" lineNumbers="true" %}
```lua
Config.AllowedJobs = {
    ['police'] = {
        imageDict = "CHAR_CALL911", -- more on https://wiki.rage.mp/index.php?title=Notification_Pictures
        imageTexture = "CHAR_CALL911", -- more on https://wiki.rage.mp/index.php?title=Notification_Pictures
        notificationCooldown = 5000, -- set how long it should be displayed
        payment = {
            shouldCost = true, --here you can chose if the job should pay or not 
            price = 1000, 
        },
        webhookcolor = tonumber("3399FF", 16), -- more on https://www.color-hex.com/
    },
    ['ambulance'] = {
        imageDict = "WEB_DIGIFARM", -- more on https://wiki.rage.mp/index.php?title=Notification_Pictures
        imageTexture = "WEB_DIGIFARM", -- more on https://wiki.rage.mp/index.php?title=Notification_Pictures
        notificationCooldown = 5000, -- set how long it should be displayed
        payment = {
            shouldCost = false, --here you can chose if the job should pay or not
            price = 1000,
        },
        webhookcolor = tonumber("CC0000", 16), -- more on https://www.color-hex.com/
    },
    ['banker'] = {
        imageDict = "CHAR_BANK_MAZE", -- more on https://wiki.rage.mp/index.php?title=Notification_Pictures
        imageTexture = "CHAR_BANK_MAZE", -- more on https://wiki.rage.mp/index.php?title=Notification_Pictures
        notificationCooldown = 5000, -- set how long it should be displayed
        payment = {
            shouldCost = true, --here you can chose if the job should pay or not
            price = 1000, 
        },
        webhookcolor = tonumber("FFFF00", 16), -- more on https://www.color-hex.com/
    },
}
```
{% endcode %}

How to add more Jobs:

* Use this template to add more Jobs easily.
* Put them into your config.lua after the last job inserted.&#x20;

{% code title="Config.lua" lineNumbers="true" %}
```lua
    ['yourjob'] = {
        imageDict = "yourimgdict", -- more on https://wiki.rage.mp/index.php?title=Notification_Pictures
        imageTexture = "yourimgtext", -- more on https://wiki.rage.mp/index.php?title=Notification_Pictures
        notificationCooldown = 5000,
        payment = {
            shouldCost = true, -- here you can chose if the job should pay or not 
            price = yourprice, -- set your price here in numbers
        },
        webhookcolor = tonumber("your_color", 16), -- more on https://www.color-hex.com/
    },
```
{% endcode %}

Configurating the NPC and selecting if he should spawn or not

{% code title="Config.lua" lineNumbers="true" %}
```lua
Config.enablePed = true -- should a npc spawn?
Config.Location = { -- set the location
    {
        location = vector4(434.5182, -975.0252, 29.7119, 92.4269), -- put the spawncords
        pedmodel = "s_m_y_cop_01", -- ignore if enabledPed is set to false otherwise add your ped hash here
    }
}
```
{% endcode %}

Configurating the sounds

<pre class="language-lua" data-title="Config.lua" data-line-numbers><code class="lang-lua"><strong>Config.Sounds = {
</strong>    enableSound = true, -- set to false if you don't want to play a sound
    sounddic    = "HUD_MINI_GAME_SOUNDSET", -- more on https://altv.stuyk.com/docs/articles/tables/frontend-sounds.html
    soundname   = "5_SEC_WARNING", -- more on https://altv.stuyk.com/docs/articles/tables/frontend-sounds.html
    soundvolume = 1.0, -- set the volume of the sound max is 1.0
    soundpitch  = 0.1, -- set the pitch of the sound max is 1.0
}
</code></pre>

Translating the locales easily

* You can translate the locales easily by translating the things wich are in  `" "`

{% code title="Config.lua" lineNumbers="true" %}
```lua
Config.Locales = { -- this is the locale file, you can change the text here
    PressE = "~y~Press E to advertise for the ~b~", -- this is the text that will be displayed when you are near the ped
    exitBtnText = "Exit", -- this is the text that will be displayed on the exit button
    paymentBtnText = "Pay", -- this is the text that will be displayed on the payment button
    bankPaymentText = "Bank", -- this is the text that will be displayed on the bank payment button
    cashPaymentText = "Cash", -- this is the text that will be displayed on the cash payment button
    containerTitleText = "Announcements", -- this is the text that will be displayed on the container title
    containerDescriptionText = "Description...", -- this is the text that will be displayed on the container description
    containerTitlePlaceholder = "Title...", -- this is the text that will be displayed on the container title placeholder

}
```
{% endcode %}

Adding your own Notificationsystem

* Replace the existing notification calls (`ESX.ShowNotification(message)` for esx or `QBCore.Functions.Notify(message, "error")` for qbcore) with your own notification function. You would simply replace these lines with a call to your own function, passing in the `message` as an argument.&#x20;
* You can also remove `local message = "You do not have enough money!"` and inserting the text manually in your notification event. Example:  `ESX.ShowNotification(`"You do not have enough money!"`, 5000)`\


{% code title="Config.lua" lineNumbers="true" %}
```lua
function NotifyNotEnough()  -- this is a function to notify the player that he does not have enough money
    local message = "You do not have enough money!"
    if Config.Framework == "esx" then
        ESX.ShowNotification(message, 5000) -- set your own notification here for esx
    elseif Config.Framework == "qbcore" then
        QBCore.Functions.Notify(message, "error") -- set your own notification here for qbcore
    end
end
```
{% endcode %}
