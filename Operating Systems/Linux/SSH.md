SSH, known as Secure Shell protocol, manages and accesses the remote systems by using an encrypted connection between the users and remote machine. In Linux systems, SSH is the most common method to connect to your servers or machines remotely and make the connection more secure through dual-key encryption remotely.

When the first-time connection is established, the client stores the host keys of the host. The host key is an encrypted key that is used to verify the machine’s identity.

## **known_hosts**
The known_hosts File is a client file containing all remotely connected known hosts, and the ssh client uses this file. This file authenticates for the client to the server they are connecting to. The known_hosts file contains the host public key for all known hosts.

### **Location**: ‘/etc/ssh/known_hosts’ and ‘.ssh/known_hosts’

## SSH Keys
By default, SSH searches for `id_rsa`, `id_cdsa`, `id_ecdsa_sk`, `id_ed25519`, `id_ed25519_sk`, and `id_dsa` files. The keys do not have to be named like this, you can name it `mykey` just as well, or even place it in a different directory. However, if you do either of those, then you need to explicitly reference the key in the ssh command like so:

```
ssh user@server -i /path/to/mykey

```

If a command does not accept `-i`, e.g. `sshfs`, use the `IdentityFile` option:

```
sshfs -o IdentityFile=/path/to/mykey user@host:/path/on/remote /mountpoint

```

### How It Works
When generating a key, you'll get two files: `id_rsa` (private key) and `id_rsa.pub` (public key). As their names suggest, the private key should be kept secret and the public key can be published to the public.

Public-key authentication works with a public and a private key. Both the client and the server have their own keys. When installing `openssh-server` the server public and private keys are generated automatically. For the client, you'll have to do that on your own.

When you (client) connect with a server, public keys are exchanged. You'll receive the servers one, and the server yours. The first time you receive the server public key, you'll be asked to accept it. If this public key changes over a time, you'll be warned because a possible MITM (Man in the middle) attack is going on, intercepting the traffic between the client and the server.

The server checks whether you are allowed to connect (defined in `/etc/ssh/sshd_config`) and if your public key is listed in the `~/.ssh/authorized_keys` file. Possible reasons why the public key is denied:

-   `/etc/ssh/sshd_config`:
-   `AllowUsers` or `AllowGroups` is specified, but your server user is not listed in the groups or users list (default not defined, placing no restriction on the users or groups from logging in).
-   `DenyUsers` or `DenyGroups` is specified and you're in the users or groups list.
-   You're trying to login as root, but `PermitRootLogin` is set to `No` (default `yes`).
-   `PubkeyAuthentication` is set to `No` (default `yes`).
-   `AuthorizedKeysFile` is set to a different location, and the public keys are not added to that file (default `.ssh/authorized_keys`, relative to home dir)
-   `~/.ssh/authorized_keys`: your public key is not added in this file (note that this file is read as root user)

### Using multiple keys
It's not uncommon to use multiple keys. Instead of running `ssh user@host -i /path/to/identity_file`, you can use a configuration file, `~/.ssh/config`.

Common settings are the IdentityFile (the keys) and port. The next configuration will check "id_dsa" and "bender" only when connecting with `ssh youruser@yourhost`:

```
Host yourhost
   IdentityFile ~/.ssh/id_dsa
   IdentityFile ~/.ssh/bender

```

If you omit `Host yourhost`, the settings will apply to all SSH connections. Other options can also be specified for this host match, like `User youruser`, `Port 2222`, etc. This would allow you to connect with the shorthand `ssh yourhost` instead of `ssh -p2222 youruser@yourhost -i ~/.ssh/id_dsa -i ~/.ssh/bender`.

### **Generate an SSH Key Pair**
1.  Open a new Terminal window.
2.  Type ssh-keygen -b 4096 -t rsa.
3.  You will be prompted to enter a filename. By default, your keys will be saved as id_rsa and id_rsa.pub. ...
4.  When prompted, enter a passphrase.
5.  This will created a hidden directory called . ssh that contains both your public (id_rsa.