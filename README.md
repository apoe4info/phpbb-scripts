# phpbb-scripts

Miscellaneous phpBB-related scripts. Currently there's only one. :-)

## email-notify-by-default

This is a perl script to turn email user notifications on without overwriting
prior user choices.

It's a companion of
[apoe4info/userdefaults](https://github.com/apoe4info/userdefaults), which
added the remaining four notification types to the excellent
[david63/userdefaults](https://github.com/david63/userdefaults) extension. The
extension sets the defaults for new users; the script sets the defaults for
existing users.

My cPanel-based hosting provider didn't have many perl packages installed, so I
ran this on a personal Ubuntu 20.04 server. I had to authorize my home IP
address using cPanel's *Remote MySQL* applet.

There were adventures installing the perl packages *DBI* and *DBD::mysql*.  I
wound up installing these Ubuntu packages ...

```
sudo apt install -y cpanminus libssl-dev zlib1g-dev mysql-server libmysqlclient-dev
```

... and at the end I had to force the DBD::mysql installation because it was
failing a single unimportant test

```
sudo cpanm install --force DBD::mysql
