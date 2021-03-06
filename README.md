Page is a small program to report to you the status of WeeChat by
connecting to it via the relay protocol

Right now it connects, subscribes (`sync`s) to all buffers, and sends notifications of highlights and private messages.

How do?
=======

```sh
git clone git://github.com/mythmon/page.git
cd page
virtualenv .
. bin/activate
pip install -r requirements.txt
vim config.json
PYTHONPATH=. python page/client.py
```

config.json
-----------

```json
{
  "host": "example.com",
  "port": 7001,
  "password": "secrets",
  "command": "notify-send %m",
  "heartbeat": false
}
```

`command` is `notify-send %m` by default. You can replace this with whatever command you want it to run when you receive a message. `%m` is replaced with the message that was received.

`heartbeat` will send a ping every minute to test the connection. It defaults to `false`
