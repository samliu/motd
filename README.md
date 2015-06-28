# samliu's MOTD

I use this on my server(s). I change out the ascii logo with the name of the
server, but generally this serves me well.

![This is what it looks like on my terminal. I use custom coloring so the
coloration isn't what is said in the comments but chances are you might 
too...](screenshot.png)

## Install

1. Copy `dynmotd` to `/usr/local/bin`
2. `chmod +x /usr/local/bin/dynmotd`
3. Disable `/etc/motd` by modifying `/etc/ssh/sshd_config` -- set the following:
```
PrintMotd no
```
4. Restart sshd (try `/etc/init.d/sshd restart` or `service sshd restart`)
5. Modify PAM to prevent `/etc/motd` after a successful login by commenting out
   lines like this from `/etc/pam.d/login`:
```
#session    optional    pam_motd.so
```
6. Append the following to end of `/etc/profile`
```
/usr/local/bin/dynmotd
```
