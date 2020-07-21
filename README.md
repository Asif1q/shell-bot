# shell-bot
This is a fully functional shellrunner [Telegram bot][]. You tell it a
command, it executes it and posts the live output. You can send input to the
command by replying to the output messages.

# How to Deploy on Heroku
- Must follow this guide for automatic installing these useful softwares
```
rclone
folderclone
ffmpeg
youtube-dl
streamlink
aria2c
megatools
ngrok
qbittorrent-nox
rar & unrar
p7zip (support almost every archive type except rar)
```
- Import this repo (do not fork, otherwise you will not be able to make it private)
> First go to https://github.com/new and fill **shell-bot** in **Repository name** field.
> Then check **Private** (important)
> Then click on **Create Repository**
> Go to down and click on **Import code** and paste this :
```
https://github.com/magneto261290/shell-bot
```
> Click on **Begin Import**
> Wait for importing to be finished
- After importing has been done, go to your repo and edit README.md and config.json files
- got to end of READMe.md file and replace `your_repo_url` with you shell-bot's repo URL and save file.
- Now in config.json file, fill your Bot Token and Owner ID
- now go to .config/rclone folder and put your rclone config file (for rclone)
- go to accounts folder and upload your service accounts json file (for folderclone)
Now its been all done, Now simply open your repo and click on **Deploy to Heroku** button.

# READMe of official shell-bot
It's a fairly complex example, because it actually appears to the
command as a terminal, interprets escape sequences and **it will
update messages if their lines get touched**. This means interactive
programs such as wget should work naturally, you should see the
status bar update.

The bot also allows files to be uploaded or downloaded, and also
has a simple text editor available for convenience.

Here's an example of the bot running `git` to clone a repository:

![Basic tasks](http://i.imgur.com/Xxtoe4G.png)

Here's an example of the bot running alsamixer:

![Alsamixer with keypad](http://i.imgur.com/j8aXFLd.png)

This bot demonstrates a great part of [Botgram][]'s API.

**Note:** Due to the tight integration, running this bot on Windows is
currently *not* supported.

## Install

First install [node-pty dependencies](https://github.com/Microsoft/node-pty#dependencies). For example, if you're in Ubuntu/Debian:

~~~
sudo apt install -y make python build-essential
~~~

If you're using fedora instead:
```
sudo dnf install -y python
sudo dnf group install -y "C Development Tools and Libraries" 
```

Before using this, you should have obtained an auth token for your bot,
and know your personal user's numeric ID. If you don't know what this
means, check out the [blog post][] for a full step-by-step guide.

~~~
git clone https://github.com/botgram/shell-bot.git && cd shell-bot
npm install
~~~

To start the bot:

~~~
node server
~~~

The first time you run it, it will ask you some questions and create
the configuration file automatically: `config.json`. You can also
write it manually, see `config.example.json`.

When started it will print a `Bot ready.` message when it's up and running.
For convenience, you might want to talk to the BotFather and set the
command list to the contents of `commands.txt`.

## Authorization

When first started, the bot will just accept messages coming from your user.
This is for security reasons: you don't want arbitrary people to issue
commands to your computer!

If you want to allow another user to use the bot, use `/token` and give
that user the resulting link. If you want to use this bot on a group,
`/token` will give you a message to forward into the group.

## Proxy server

shell-bot obeys the `https_proxy` or `all_proxy` environment variable
to use a proxy, and supports HTTP/HTTPS/SOCKS4/SOCKS4A/SOCKS5 proxies.
Examples:

~~~ bash
export https_proxy="http://168.63.76.32:3128"
node server

export https_proxy="socks://127.0.0.1:9050"
node server
~~~

**Warning:** For SOCKS proxies, you need to use an IP address (not a DNS hostname).



[Telegram bot]: https://core.telegram.org/bots
[Botgram]: https://botgram.js.org
[blog post]: https://alba.sh/blog/telegram-shell-bot/

```
Deploy to heroku
```
**Click this button to deploy to heroku**
[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=your_repo_url)
