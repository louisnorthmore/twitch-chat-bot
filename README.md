[![Build Status](https://dev.azure.com/asottile/asottile/_apis/build/status/anthonywritescode.twitch-chat-bot?branchName=master)](https://dev.azure.com/asottile/asottile/_build/latest?definitionId=55&branchName=master)

twitch-chat-bot
===============

A hackety chat bot I wrote for my twitch stream.  I wanted to learn asyncio
and this felt like a decent project to dive in on.

## setup

1. Set up a configuration file

   ```json
   {
     "username": "...",
     "channel": "...",
     "oauth_token": "...",
     "client_id": "..."
   }
   ```

   - `username`: the username of the bot account
   - `channel`: the irc channel to connect to, for twitch this is the same as
     the streamer's channel name
   - `oauth_token`: follow the directions [here][docs-irc] to get a token
   - `client_id`: set up an application for your chat bot [here][app-setup]

1. Use python3.7 or newer and install `aiohttp`

   ```bash
   virtualenv venv -ppython3.7
   venv/bin/pip install aiohttp
   ```

1. Run! `venv/bin/python bot.py`

[docs-irc]: https://dev.twitch.tv/docs/irc/
[app-setup]: https://dev.twitch.tv/docs/authentication/#registration

## implemented commands

### `!help`

List all the currently supported commands

```
anthonywritescode: !help
anthonywritescodebot: possible commands: !help, !ohai, !uptime
```

### `!ohai`

Greet yo self

```
anthonywritescode: !ohai
anthonywritescodebot: ohai, anthonywritescode!
```

### `!uptime`

Show how long the stream has been running for

```
anthonywritescode: !uptime
anthonywritescodebot: streaming for: 3 hours, 57 minutes, 17 seconds
```

### `PING ...`

Replies `PONG` to whatever you say

```
anthonywritescode: PING
anthonywritescodebot: PONG
anthonywritescode: PING hello
anthonywritescodebot: PONG hello
```

### `!discord`

Show the discord url

```
anthonywritescode: !discord
anthonywritescodebot: We do have Discord, you are welcome to join: https://discord.gg/HxpQ3px
```

### `!followage [username]`

Show how long you or a user you specified have been following the channel

```
not_cool_user: !followage
anthonywritescodebot: not_cool_user is not a follower!

cool_user: !followage
anthonywritescodebot: cool_user has been following for 3 hours!

some_user: !followage another_user
anthonywritescodebot: another_user has been following for 5 years!
```

### `!joke`

Get a joke

```
anthonywritescode: !joke
anthonywritescodebot: The best thing about a Boolean is even if you are wrong, you are only off by a bit.
```
