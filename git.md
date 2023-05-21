## Github authentication - [docs](https://docs.github.com/en/authentication)

### General steps

1. List existing keys 
```
ls -al ~/.ssh
```

2. Generate a key

Use either `ed25519` or `rsa`:
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

3. Copy the key and add it to your Github account
```
pbcopy < ~/.ssh/id_ed25519.pub
```

4. Test your SSH connection
```
ssh -T git@github.com
```

5. Clone your repo using SSH
```
git clone git@github.com:omkarscode/notebook.git
```

### Add SSH key to ssh-agent

The ssh-add command is used to add your private key to the SSH agent, which is a program that runs in the background and manages your SSH keys. By adding your private key to the agent, you can avoid typing your passphrase every time you establish an SSH connection or perform an action that requires authentication.

On Linux:
```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/[your-private-key]
```

On older versions of MacOS:
```
ssh-add -K ~/.ssh/[your-private-key]
```

On newer versions of MacOS (12.0 Monterey):
```
ssh-add --apple-use-keychain ~/.ssh/[your-private-key]
```


## Creating a new repository

```
echo "# notebook" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:omkarscode/notebook.git
git push -u origin main
```

## Pushing an existing repository

```
git remote add origin git@github.com:omkarscode/notebook.git
git branch -M main
git push -u origin main
```

## Basic commit and push process

```
git add .
git commit -m "add a new great feature"
git push
```

## Remove staged file or files

```
git rm --cached <file>
git rm -r --cached .
```

## Adding hidden files to .gitignore

```
echo ".*" >> .gitignore
```
