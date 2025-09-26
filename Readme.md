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

6. Setup branchs

```shell
git checkout -b staging
git push --set-upstream origin staging

git checkout -b dev
git push --set-upstream origin dev
```

## Create first merge via UI

1. Push to feature branch

```shell
git checkout dev
git checkout -b feature-1
echo 'text1' > text.txt
git add .
git commit -m 'first feature'
git push --set-upstream origin feature-1
```

2. Create pull request

3. Pull changes from dev branch

```shell
git checkout dev
git pull
```

## Create merge via shell

Push to feature branch

```shell
git checkout dev
git checkout -b feature-2
echo 'text2' > text.txt
git add .
git commit -m 'second feature'
git push --set-upstream origin feature-2
```

```shell
git pull origin dev
git merge feature-2
```

## Resolve merge conflicts

1. Create conflict:

```shell
git checkout dev
git checkout -b feature-3
echo 'text3' > text.txt
git add .
git commit -m 'third feature'
git push --set-upstream origin feature-3

git checkout dev
git checkout -b feature-4
echo 'text4' > text.txt
git add .
git commit -m 'fourt feature'
git push --set-upstream origin feature-4
```

2. Merge branch feature-3

3. Pull request branch feature-4

4. Resolve conflicts

```shell
git checkout feature-4
git pull origin dev

git status

git add .
git commit -m 'resolve conflicts'
git push
```

5. Merge branch feature-4

## Release to main

1. Create pull request from dev to staging and merge it

2. Create pull request from staging to main and merge it

3. Add tag

```shell
git tag -a v1.0 -m "First release"
git push origin v1.0
```

## make hotfix

1. Create hotfix

```shell
git checkout staging
git pull
git checkout -b H1-hotfix

echo 'text 10' > text.txt

git add .
git commit -m 'hotfix: change text.txt content'
git push --set-upstream origin H1-hotfix
```

2. Merge to staging

3. Merge staging into dev

4. Merge staging into main

## Revert changes

```shell
git revert {commit hash}
git push
```