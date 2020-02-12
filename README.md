# ODTÜ Telegram Bot

This repository contains a tiny Telegram Bot that was developed to understand the Telegram Bot API, and Python web services. Currently under development.

## Installation

1. Get yourself a Bot account and a token at [Telegram Bots](https://core.telegram.org/bots).
2. Set up your environment and install dependencies.
3. Run `install.py` and enter your Telegram Bot Token.

## Usage

1. After installation, run `driver.py`
2. The bot should run smoothly.
3. If you want to make the bot verbose (and activate the debug mode), you should use the `--debug` flag.

## Running as a Service
The following guide explains how to run the bot as a service on Raspberry Pi (Raspbian), but it is applicable to any other Linux system as well.
1. Create a file at `/lib/systemd/system/telegram.service` with the following content:
```
[Unit]
Description=Telegram Bot
Wants=network-online.target
After=network-online.target

[Service]
Type=idle
ExecStart=/usr/bin/python3 /home/pi/telegram-bot/driver.py

[Install]
WantedBy=multi-user.target
```
Don't forget to change the line starting with `ExecStart` accordingly! The permissions of this file should be 644.

2. On a terminal window, enter the following commands;
```
sudo systemctl daemon-reload
sudo systemctl enable telegram.service
```
3. Reboot your system, and the bot should go live when the network connection is established.

## Dependencies

* Python 3
* Requests

## Bugs, Comments, Ideas?

Don't hesitate contacting me, or sending a pull request. They are always welcome.

Made in Ankara with 💙
