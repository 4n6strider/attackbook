# Linux Tracks







#### Log files

`/etc/syslog.conf`

In this file you can read all the logs that syslog log.

On linux systems a lot of logs are stored in:

```text
/var/logs
```

For example:

```text
/var/log/messages
```

Here you have failed and successful login attempts. SSH, SUDO, and much more.

```text
/var/log/auth.log
```

#### Apache

```text
/var/log/apache2/access.log
/var/log/apache2/error.log
```

Remove your own ip like this

```text
grep -v '<src-ip-address>' /path/to/access_log > a && mv a /path/to/access_log
```

What it does is simply to copy all lines except the lines that contain your IP-address. And then move them, and them move them back again.

```text
grep -v <entry-to-remove> <logfile> > /tmp/a ; mv /tmp/a <logfile> ; rm -f /tmp/a
```

#### UTMP and WTMP

These logs are not stored in plaintext but instead as binaries. Which makes it a bit harder to clear.

```text
who
```

```text
last
```

```text
lastlog
```

#### Command history

All your commands are also stored.

```text
echo $HISTFILE
echo $HISTSIZE
```

You can set your file-size like this to zero, to avoid storing commands.

```text
export HISTSIZE=0
```

If you set it when you get shell you won't have to worry about cleaning up the history.

### Shred files

Shredding files lets you remove files in a more secure way.

```text
shred -zu filename
```

