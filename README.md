# Acode - Git/GitHub Setup

## Install Dependencies

Needed software to get everything running.

```bash
apk add git openssh-keygen openssh-client-common dropbear-ssh
```

## Setup SSH Key

This is needed to allow interaction between got and GitHub via ssh such as cloning or pushing repos

### Generate SSH Key

```bash
# First, setup an ssh key
# Follow instructions (password highly suggested)
ssh-keygen
```

Once complete, find your public key; we need it for the next step. The path to this will probably be `/root/.ssh/id_ed25519.pub` if you just followed the ssh-keygen output without changing anything. You can do the following command to output the key:
```bash
cat /root/.ssh/id_ed25519.pub
```

The output of that command will look like this:
```bash
ssh-ed25519 <random-string-of-characters> root@localhost
```

Make sure to copy it all.

> [!IMPORTANT]
> **Never** upload your private SSH key to a repository on accident or share it with anyone. It essentially acts as a login to your account.
> 
> If you do this, **immediately** revoke the key from your GitHub account.
