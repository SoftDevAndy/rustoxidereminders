# rustoxidereminders
Oxide Plugin for Rust, Used to remind newer players of features for the first few days of their time on the server.

New players need a little extra help so this plugin was designed to pester them a little with some custom reminder messages for however many days you decide. This helps remind players about the many mods and commands on the server that they don't know about or utilize yet. Custom messages are easy to add and a configuration file is included.

**Reminders are sent to the player privately to keep the chat free of clutter!**

**The plugin tracks when players login so there is no micromanagement!**

## Configuring the plugin

The configuration file is found in

```
config/ChatReminders.json
```

Whenever you make a change to the plugin you will need to reload it using the following command.

```
oxide.reload ChatReminders 
```

The configuration file looks like this

```
{
  "ALLOW_REMINDERS": true,
  "COLOR_TAG" : "#F5D76E",
  "LOGINS_REQUIRED" : 3,
  "REMINDER_DAYS_PERIOD" : 3,
  "TAG" : "[REMINDER]"
}
```

**ALLOW_REMINDERS** lets you set if you wish to switch all reminders on or off using true or false.

**COLOR_TAG** is the hex value for the color tag that appears with the reminder message.

**LOGINS_REQUIRED** required is the integer for how many times a player must connect to the server before they stop recieving the messages in conjuction with....

**REMINDER_DAYS_PERIOD** is how many days (from the first time visted date) that the player will recieve reminders for.

**TAG** is the text to prepends any reminder sent to the user.

## Adding a reminder message

Reminders are added manually in the data file for the plugin found at.

```
The data/ChatReminder.json
```

The data file looks like the following. The format is very easy to follow

```
{
  "reminders": [
    {
      "reminderMessage": "<color=\"#89C4F4\">180s Message</color>",
      "remindTime": 180
    },
    {
      "reminderMessage": "<color=\"#89C4F4\">330s Message</color>",
      "remindTime": 330
    }
  ],
  "playersNewbs": [
    {
      "joinTime": "2017-02-18T23:59:36.1329739Z",
      "originaldisplayName": "Newbie",
      "userID": "xxxxxxxxxxxxxxxxxxx",
      "logins": 1
    }
  ],
  "playersVets": [
    {
      "joinTime": "2017-02-22T23:59:36.1329739Z",
      "originaldisplayName": "Vet User",
      "userID": "xxxxxxxxxxxxxxxxxxx",
      "logins": 5
    }
  ]
}
```

An example of the format, it's important to note that the time is in seconds! You don't want to pester then too much..

```
{
  "reminderMessage": "<color=\"#89C4F4\">180s Message</color>",
  "remindTime": 180
}
```
