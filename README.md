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

### Link SSH Key to GitHub

Below are the steps to add your newly created SSH key to your GitHub account. Photos are from Google Chrome on mobile, if you decide to do these steps on desktop for some reason then it will look different.

1. Open browser to https://github.com
	- If not already logged into GitHub, do so now
2. Click your profile icon in the top right of the webpage
    - <img src="./images/step-1.png" width="100" align="middle" alt="Image walkthrough of above step">
3. Click "Settings" on the menu that pops down
    - <img src="./images/step-2.png" width="100" align="middle" alt="Image walkthrough of above step">
4. Click "SSH & GPG keys" on this new menu
   - <img src="./images/step-3.png" width="100" align="middle" alt="Image walkthrough of above step">
5. Scroll down until you see "New SSH key" in a green button and click it
	- <img src="./images/step-4.png" width="100" align="middle" alt="Image walkthrough of above step">
6. Scroll down to enter title and key of the New SSH key that you previously made
	- For title, I usually go with `<username-on-computer>@<computer-name>`
	- Since Acode runs in sandboxed root in an app, I just put `acode@<phone-name>`
7. Once the title is in and the key is copied over, click the green "Add SSH key" button at the bottom of the page
	- <img src="./images/step-5.png" width="100" align="middle" alt="Image walkthrough of above step">

