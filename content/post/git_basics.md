---
title = "Git Basics and Advanced"
date = 2017-03-03
tags: ['git', 'bash']
math = false
highlight = true
output: html_document
summary: "This is a basic post on how to interact with github through command line"
---

Most important commands for keeping versions of your code on github are: 

```bash
git add --all .
git status
git commit -m "$message"
git pull origin master
git push origin master
```

Each of the commands above have their importance.

The `git add --all .` is saying that you want git to check all your current directory
for changes and add them to the cache.

Once changes have been determined you want to see those changes in the cache, you use `git status`
to achieve that purpose. This will show you actual changes made to your repository.

If you want to "upload" those changes to your repository on `github` you have to commit with 
a message. Then you use `git commit -m "Your message with information about changes"`.

To upload your changes, you first have to pull any changes in the master branch (There might be other branches if multiple users are collaborating in one project at the same time). 
To pull those changes made in master you use `git pull origin master`.

Finally, once you've retrieved any changes in master you can `push` (upload) all those changes that you made
to the master repository by using `git push origin master`


If you are using the github application in windows that should be relatively easy because you will have already installed 
`gitbash` and they have a very easy GUI. However if you use linux and you are working remotely, you will have to type your
username and password every time.   