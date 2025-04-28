# Preparation

## Install git
Check for the presence of `git` on your local machine by running 
```bash
git --version
```
in a terminal session. If it is not installed on your system install it (see e.g. [here](https://swcarpentry.github.io/git-novice/#installing-git)).

## Set up your GitHub account
[Sign up](https://github.com/signup) for a GitHub account if you don't have one.

Also, make sure you have MFA enabled. See [here](https://swcarpentry.github.io/git-novice/#creating-a-github-account) for a quick way to do that.

## Generating an SSH Key Pair

> These instructions are for both macOS and Linux systems.

Generate an SSH key pair using one of the following methods:

### Using Ed25519 (Recommended)
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

### Using RSA
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

When prompted, you can accept the default location or specify a custom path:
```
Enter file in which to save the key (/home/your_username/.ssh/id_ed25519):
```
You will also be asked to enter a passphrase for an extra layer of security. If you choose to create it (recommended) make sure to keep that take that down.

After generation, verify your keys exist:
```bash
ls ~/.ssh/
# Should show id_ed25519 and id_ed25519.pub (or your chosen path)
```

## Adding the Key to the SSH Agent

### Start the SSH Agent
```bash
eval "$(ssh-agent -s)"
```
Note: On macOS, the SSH agent typically starts automatically at login.

### Add Your Private Key to the Agent
```bash
ssh-add ~/.ssh/id_ed25519
```


## Add the SSH public key to Github

Once the keys have been correctly generated as described [above](#generating-an-ssh-key-pair) copy the output of the following command
```bash
cat ~/.ssh/id_ed25519.pub
```
and add it to your account on GitHub by following the guide from GitHub official [docs](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account).
