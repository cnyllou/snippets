# Lock the password
```bash
usermod -L testuser
passwd -l testuser
```
# Unlock the password
```bash
usermod -U testuser
passwd -u testuser
```

# Changing the shell
```bash
usermod -s /sbin/nologin [username]
```

# Verify if the account is locked or disabled.
```bash
passwd --status root
> root *LK* 2017-07-19 0 45 7 -1 (Password set, SHA512 crypt.)
```

# User del
```bash
userdel userName
userdel [options] userName
userdel -r userName
```
[link 1](https://www.thegeekdiary.com/unix-linux-how-to-lock-or-disable-an-user-account/)
[link 2](https://www.learnitguide.net/2016/08/how-to-lock-and-unlock-user-account-linux.html)
