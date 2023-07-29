# Some Custom Steps

x11vnc

```bash
x11vnc -storepasswd
```

ssh key

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

gpg key

`export GPG_TTY=$(tty)`

```bash
gpg --full-generate-key
gpg -K --keyid-format=long
gpg --armor --export <key>
git config --global user.signingkey <key>
git config --global commit.gpgsign true
```
