+++
title = "Using git with ssh keys"
date = 2017-03-03
tags= ['git', 'bash']
math = false
highlight = true
summary= "This is a post for github advances users that don't want to type their username and password everytime a change is commited and pushed to your branch"
+++

[Previously](https://www.aespindola.com/post/git_basics/) I have explored how would be the common way of `pushing` (uploading) changes to your repository. However in many instances we require to test our code in Linux/Unix platforms.  Usually once I finish testing my code in Linux I will have to drag and drop to my changed files to my current Windows repo folder and then push the changes. I have been doing this because pushing code directly from linux becomes a little annoying because I had to type my username and password every single time I push changes.

If you want to avoid this from the very beginning, you will have to clone your repository using ssh. By default whenever you clone a repository it is done through https, and, if later you want to use ssh you will require change the remote url utilized for syncronizing your repository.

1. Check if you have cloned your repository as https

```bash
cd repository_folder
git remote -v
```
origin  https://github.com/username/repository-name.git (fetch)
origin  https://github.com/username/repository-name.git (push)


2. If your found out that your repo contains https as above you will have to run the following code:

```bash
git remote set-url origin git@github.com:/username/repository_name.git
```

 to change it to ssh. Personally, I cloned all my repos using ssh so I will have to go through the small coding step before I can use ssh to push changes. 

I've found a nice video on how to incorporate ssh keys to our github repository once we have previously cloned our repo using https. 

{{< youtube id="6oTzYnQY17Q" autoplay="false" >}}

