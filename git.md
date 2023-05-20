## Github authentication - [docs](https://docs.github.com/en/authentication)

List existing keys 
```
ls -al ~/.ssh
```

Generate a key
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

Copy the key and add it to your Github account
```
pbcopy < ~/.ssh/id_ed25519.pub
```

Test your SSH connection
```
ssh -T git@github.com
```

Add SSH key to ssh-agent
```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
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
