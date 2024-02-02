# qBittorrent Seeding Manager

Program to manage seeding options of multiple completed torrents at once

It is a very simple program that you can run manually or in an automated task schedule

Configurations are read from the file "qbitseedmgr.ini" and must follow the API Reference from qittorrent-api

More information at https://qbittorrent-api.readthedocs.io/en/latest/apidoc/torrents.html

## Usage

Clone main branch (qBittorrent 4.6.3+):
```
git clone https://github.com/Tomodoro/qbitseedmgr.git
```

For older clients:
```
git clone -b legacy https://github.com/Tomodoro/qbitseedmgr.git
```

Fill the [Client] fields inside the configuration file, remember to toggle credentials for your use case.

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
