SSH Remote Keys
===========================
This document is used to show the detailed description of SSH Remote Keys Tuition.

---

# (1) Mac/Linux User

Start
```shell
enze@ENZE ~ % cd ~/.ssh
enze@ENZE .ssh % ssh-keygen
```

Choose a file path to save
```shell
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/enze/.ssh/id_rsa): /Users/enze/.ssh/id_rsa
```

You may leave `passphrase` empty
```shell
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/enze/.ssh/id_rsa
Your public key has been saved in /Users/enze/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:oPgzBj+ipULt4u8xzy2rm/7ECUy0/roo+mZ8DhmEChs enze@ENZE.dhcp.wfu.edu
The key's randomart image is:
+---[RSA 3072]----+
|   .             |
| .. .            |
|E .o  .          |
|o++. . .         |
|o =+.   S        |
| . B+ .          |
|..*oB=           |
|o===X=.          |
|O**%*=o.         |
+----[SHA256]-----+
```

[//]: # (Locate your public SSH key)

[//]: # (```shell)

[//]: # (enze@ENZE .ssh % ls ~/.ssh/id*  )

[//]: # (/Users/enze/.ssh/id_rsa		/Users/enze/.ssh/id_rsa.pub)

[//]: # (```)

Copy it to remote server (You need to type you server's log-in password here)
```shell
enze@ENZE .ssh % ssh-copy-id user@remote-host
```

Try to log in using key to test
```shell
enze@ENZE .ssh % ssh -i /Users/enze/.ssh/id_rsa user@remote-host
```

Add your key to local saves that you don't need to type "-i xxxxx" again
```shell
enze@ENZE .ssh % ssh-add /Users/enze/.ssh/id_rsa
```

---

# (2) Windows User
Start
```shell
enze@ENZE .ssh % ssh-keygen
```

Choose a file path to save
```shell
Generating public/private rsa key pair.
Enter file in which to save the key (C:\Users\enze/.ssh/id_rsa):
```

You may leave `passphrase` empty
```shell
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in C:\Users\enze/.ssh/id_rsa.
Your public key has been saved in C:\Users\enze/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:A+VqUFHSxr8Td6+tLKogTqyJqHxsFRacEHLZrYVv7VY enze@ENZEXUD44D
The key's randomart image is:
+---[RSA 3072]----+
| . +* B=o        |
|  o. B *+        |
|    . *.o.       |
|     = = .oE. .  |
|    . = S .+ . . |
|   . o   +o     .|
|  . = . .  .   o |
|o. O . .    ... .|
|=.= .   .... .o. |
+----[SHA256]-----+
```
Copy it to remote server (You need to type you server's log-in password here)
```shell
enze@ENZE cat ~/.ssh/id_rsa.pub | ssh user@hostname "cat >> ~/.ssh/authorized_keys"
```


PS C:\Users\enze> ssh exu03@bg1.cs.wm.edu
FQDN:  bg1.cs.wm.edu (128.239.2.100)

If you have any problems or questions please visit http://support.cs.wm.edu
   or email cs-support@wm.edu to open a support ticket - Thank you
Last login: Tue Feb 13 01:22:46 2024 from 70.160.198.18
exu03@bg1:~$

PS C:\Users\enze>
---
