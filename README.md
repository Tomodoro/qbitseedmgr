# qBittorrent Seeding Manager

Program to manage seeding options of multiple completed torrents at once

It is a very simple program that you can run manually or in an automated task schedule

Configurations are read from the file "qbitseedmgr.ini" and must follow the API Reference from qittorrent-api

More information at https://qbittorrent-api.readthedocs.io/en/latest/apidoc/torrents.html

## Usage
Clone the repo.

Enable the Web User Interface option from qBittorrent and check "Bypass authentication for clients on localhost"

If qBittorrent is running on another machine, check "Bypass authentication for clients in whitelisted IP subnets" and add the machine's IP

Currently there is no support for credentials (working on it), you you will have to edit the following line inside "qbitseedmgr.py":
```
client = qbittorrentapi.Client(host=config["Client"]["host"], username='<your-username>', password='<your-password>')
```

To start managing your torrents run:
```
python qbitseedmgr.py set-tiers
```

If you only want to seed torrents with few seeds, then run:
```
python qbitseedmgr.py not-popular
```

You can also use both commands in any order:
```
python qbitseedmgr.py set-tiers not-popular
```

Managed torrents are paused once they reach the ratio limit, to automatically resume them:
```
python qbitseedmgr.py tier-active
```

To avoid overriding not-popular, run in the following order:
```
python qbitseedmgr.py tier-active not-popular
```

To see the help text just run:
```
python qbitseedmgr.py
```

## Prerequisites
Python 3<br>
pip packages: qbittorrent-api
```
pip3 install --user qbittorrent-api
```
