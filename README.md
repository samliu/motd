# samliu's MOTD

I use this on my server(s). I change out the ascii logo with the name of the
server, but generally this serves me well.

![This is what it looks like on my terminal. I use custom coloring so the
coloration isn't what is said in the comments but chances are you might 
too...](screenshot.png)

## Install

Note: This is an opinionated install. You can achieve installation in other ways
too e.g adding the script to `/etc/update-motd.d` which could be simpler.

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

## Troubleshooting
If you're using ZSH and the message isn't showing up, I'd try putting the script
into `/etc/update-motd.d` or just sourcing it from `~/.zlogin` or `~/.zshrc`

## Happy Pride!
The week of rapgamejusticekennedy's birth was the week the supreme court ruled
for marriage equality! My laptop is already rapgameruthbaderginsburg so I had to
come up with another name :)
