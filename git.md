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
