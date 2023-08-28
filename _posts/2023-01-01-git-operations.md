---
title: '[Etc] git-operations'
excerpt: Commonly used git commands

categories:
    - Etc

tag:
    - Git

last_modified_at: 2023-01-01T00:00:00+09:00
toc: true
---

## Frequently used git commands

__Check current status__
git status

__Check the full log__
git log

__Create a git repository__
git init

__Clone and download a repository__
git clone [https: ~~~~ ]

__Add code to a repository__
git add
git add *

__Include all changes to a file in a commit at once__
git add -A

__Create a commit__
git commit -m "message"

__Upload changes to the remote server (push)__
git push origin master

__Pull changes from the remote repository to the current directory (pull)__
git pull

__Compare the changed contents before merging__
git diff [branch name] [other branch name]

## Git Config settings

__Check the full config list__
git config --list

__How to set git config__
git config --global user.name "Hong Gildong"
git config --global user.email "name@naver.com"

__Remove git config__
git config --unset user.name
git config --unset user.email

__Remove git config (for name and email set as global options)__
git config --unset --global user.name
git config --unset --global user.email

## Git creation, branch check, push related

__Initialize the git folder (.git file is created)__
git init

__Connect to the GitHub address__
git remote add origin [GitHub address]

__Create a branch__
git branch [branch name]

__Move to the branch__
git checkout [branch name]

__Create a branch and move to it immediately__
git branch -b [branch name]

__Check if you have moved to the desired branch__
git branch

__Check all branches__
git branch -a

__Add files and folders__
git add .

__Commit__
git commit -m "commit message"

__Push to the desired branch to send to the remote server__
git push origin [branch name]

__Delete a branch__
git branch -d [branch name]

__Merge changes from another branch into the current branch__
git merge [other branch name]


## SSH key setting problem

> git@github.com: Permission denied (publickey).
> fatal: Could not read from remote repository.
> Please make sure you have the correct access rights
> and the repository exists.

This error occurs because the SSH key associated with git@github.com is not set.

To solve this problem, simply create an SSH key and register it with your GitHub account.

1. First, create an SSH key.
> ssh-keygen -t rsa -C "Your GitHub account email"

2. The meaning of the above command is to create an SSH key using the rsa (public key encryption algorithm) method, and the C option is just a comment, so you can use it or not.

3. When you run ssh-keygen, you will be asked where to create the key in the terminal window. If you just press Enter, it will be created in the default location (~/.ssh/id_rsa.pub).

4. Next, you will be asked to set a password. If you want to set a password, enter it, but if you don't, just press Enter.

5. Then, the key will be created in ~/.ssh/id_rsa.pub. Never share this key with anyone. (If you share it, it means that you are free to use my GitHub.)

6. The generated key needs to be registered with GitHub, so please copy the contents that appear when you run cat ~/.ssh/id_rsa.pub.

7. Once you have created the key, you can register it with your GitHub account. First, log in to GitHub and go to Settings -> SSH and GPG Keys.

8. Click the New SSH key button, enter the title as you wish, and paste the copied SSH key (the ~/.ssh/id_rsa.pub key) in the Key field.

9. Now, if you run git pull or git push, you can confirm that the error has been resolved.


