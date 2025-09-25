# Git & Github training

## Git setup

1. download git from the link <a href="https://git-scm.com/downloads">https://git-scm.com/downloads</a>
2. Configure username and email
```shell
git config --global user.name
git config --global user.email
```

## Creating repository

1. Create repository with 
```shell
git init  
```
2. create a `.gitignore` file
3. create your first file
4. commit the changes
```shell
git add text.txt
git commit -m 'first commit'
```
5. Push changes to remote repository
```shell
git branch -M main
git remote add origin https://github.com/FirasMosbahi/git-tutorial.git
git push -u origin main
```