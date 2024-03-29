[![Build Status](https://travis-ci.com/Jimmy2027/NORBY.svg?branch=main)](https://travis-ci.com/Jimmy2027/NORBY)
[![Documentation Status](https://readthedocs.org/projects/norby/badge/?version=latest)](https://norby.readthedocs.io/en/latest/?badge=latest)

# NORBY
Get notified via a telegram bot when your bash command finished via the command line or from any python code.

# Usage
```console
user@host $ norby "echo hi"
executing command echo hi
hi

user@host $ norby ./broken_workflow.sh
your job got killed with: some_error
```
````python
from norby import send_msg
results = run_very_long_workflow()
send_msg(f'Very long workflow finished. The results are: {results}.')
````

# Installation
### Via portage:
The package is available via the [Chymeric Overlay](https://github.com/TheChymera/overlay):
```
emerge norby
```
### Via pip:
```
pip install norby
```
# Setup:
- Install `norby` 
- Create bot in telegram by messaging `BotFather` with `/newbot` to receive the bot ID
- write `/start` to new bot to start it
- write something to new bot and go to `https://api.telegram.org/bot<token>/getUpdates` to get the chat_id
- fill token and chat_id in the `norby_config.ini`
- move the config to `~/.config/norby_config.ini`
