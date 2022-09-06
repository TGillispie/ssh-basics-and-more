# An SSH Presentation.
Some SSH resources for everyone.


## Quick Reference

- [Some Basic Questions](#some-basic-questions-about-open-ssh)
   - [What is OpenSSH](#what-is-openssh)
   - [Why Use OpenSSH](#why-use-openssh)
   - [What comes with OpenSSH](#what-comes-with-openssh)
   - [Where to get OpenSSH](#where-to-get-openssh)
- [How to use Open SSH](#how-to-use-open-ssh)
   - [What is Needed?](#what-is-needed-to-use-open-ssh)
   - [Connect with password](#how-to-connect-with-a-password)
   - [Connect with a key pair](#how-to-connect-with-a-key-pair)
- [What About Keys](#what-about-keys)
   - [Create a key pair](#create-a-key-pair)
   - [Distinguish Public vs. Private](#distinguish-between-private-and-public-keys)
   - [Send Public Key to Remote Device](#send-key-to-remote-server)
   - [Alternate Key Transfer Methods?](#alternate-method-copy-it-via-any-means-possible)
- [Profiles](#profiles-gettin-fancy)
- [Gotchas](#gotchas)
- [Advanced](#advanced-uses)
- [Resources](#resources)

</br>

## Some Basic Questions about Open SSH.

### What is OpenSSH?
 Open SSH is a secure connection protocol and program suite.
### Why use OpenSSH?
 SSH provides tools for connecting to a remote server to get data, put data, and run commands.
### What comes with OpenSSH?
 Several programs come with OpenSSH: ssh, scp, sftp, ssh-agent, ssh-keygen, and more.
### Where to get OpenSSH?
 Open SSH comes with most Operating Systems.  Git-bash and Bash emulators also provide Open SSH.

</br>

## How to use Open SSH.

### What is needed to use Open SSH?
1. One or more devices to connect to which are running an ssh service.
2. An installed version of Open SSH. (ssh, scp, etc.)
3. An account and permissions on a remote device.
4. ...and hopefully, a password or a public/private key pair.

### How to connect with a password.
``` ssh username@server-or-ip ```

### How to connect with a key pair.
``` ssh username@server-or-ip ```

### How to copy files to a remote server.
``` scp ./path/file.ext username@server-or-ip:/path/to/store ```

### Hot to run a command on a remote server.
``` ssh username@server-or-ip 'ls && who && pwd' ```

</br>

## What about keys?!
Keys provide passwordless access and are great for automation.  For added security, passwords can be added to ssh keys.  A public keys can be used on multiple servers.

After creating a key pair, put the public key into the ~/.ssh ([user]/.ssh) folder of any device to enable access.

### Create a key pair.
```ssh-keygen```

### Distinguish between Private and Public Keys.
Public keys have a .pub extension.

### Send key to remote server.
``` ssh-copy-id username@server-or-ip ```

### Alternate method: copy it via any means possible.
``` scp ~/.ssh/[key].pub username@server-or-ip:~/.ssh ```
... copy paste, ftp, ect.  It is a public key, its fine.

</br>

## Profiles, gettin' fancy.
SSH can be configured to automate and alias much of the reptitiveness in ssh commands.

</br>

## Gotchas
1. Authorized Keys errors can surface when connecting for the first time.  User interaction is required for initial connections to remote devices.
2. File permissions can cause troublesome difficulties.  The use of ssh-copy-id can mitigate many of those problems.
3. Transfering large quaitites of files over scp can bog down a network.  Tar and possibly compress large quantities of files before sending them accross the wrire.

</br>

## Advanced Uses
There are many advanced uses, from automationg to connection a local browser to a remote internet.

</br>

## Resources
1. [Developers and Maintainers of Open SSH: www.openssh.com](https://www.openssh.com/)
2. [SSH.com 3rd Party Vendor (Great Documentation)](https://www.ssh.com/academy/ssh/openssh)
3. [SSH Cheat Sheet. Search Google for them! This one is neat.](https://www.marcobehler.com/guides/ssh-cheat-sheet)

