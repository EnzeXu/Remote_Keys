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

Locate your public SSH key
```shell
enze@ENZE .ssh % ls ~/.ssh/id*  
/Users/enze/.ssh/id_rsa		/Users/enze/.ssh/id_rsa.pub
```

Copy it to remote server (You may need to type you log-in password here)
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

~/.ssh/id_rsa.pub | ssh user@hostname "cat >> ~/.ssh/authorized_keys"

---