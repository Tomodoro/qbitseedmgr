# qBittorrent Seeding Manager

Program to manage seeding options of multiple completed torrents at once

It is a very simple program that you can run manually or in an automated task schedule

Configurations are read from the file "qbitseedmgr.ini" and must follow the API Reference from qittorrent-api

More information at https://qbittorrent-api.readthedocs.io/en/latest/apidoc/torrents.html

## Usage
Clone the repo.

Enable the Web User Interface option from qBittorrent and check "Bypass authentication for clients on localhost"

If you want to use your credentials, just add them in qbitseedmgr.py in the following line:
```
client = qbittorrentapi.Client(host='localhost:8080', username='<your-username>', password='<your-password>')
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
