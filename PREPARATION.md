# Preparation

## Install git
Check for the presence of `git` on your local machine by running 
```bash
git --version
```
in a terminal session. If it is not installed on your system install it (see e.g. [here](https://swcarpentry.github.io/git-novice/#installing-git)).

In order to properly configure `git` behavior, you should use the `git config` command.
A simple working configuration to add your name and email to your commits is achieved by running:
```bash
git config --local user.name "Your Name"
git config --local user.email your_email@example.com
```
which will write the following to a `.git/config` file
```
[user]
        name = Your Name
        email = your_email@example.com
```
Note: These options are local to the current repository and override the system-wide and global ones. 
You can pass `--global` instead of `--local` to effectively write the options to the `~/.gitconfig` file.
At any point you can run
```bash
git config --list
```
to list all the config options active for the current repository.

There are a lot of additional options available that you might want to configure (e.g. git editor, gpg signing key, etc...). Check out [here](https://git-scm.com/book/ms/v2/Customizing-Git-Git-Configuration) for a good reference on those.

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
