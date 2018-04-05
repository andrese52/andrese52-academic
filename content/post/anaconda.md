+++
title = "Anaconda and conda basics"
date = 2018-03-04
tags= ['conda', 'anaconda']
math = false
highlight = true
summary= "While installing Anaconda updates through the Anaconda navigator I encountered an issue: Although a prompt showing a progress bar of the update was actively moving, it was taking too long (hours) to update the anaconda navigator. I decided to go through the Anaconda prompt and it took 30 seconds. Here are my findings."
+++


Updating anaconda navigator.  I had issues by using the GUI to update and decided to use the anaconda prompt. Updating the `ipykernel` solved the issue.
I had to execute the `Anaconda Prompt` as Administrator in windows.

```Anaconda
conda update ipykernel
```
then

```Anaconda
conda update anaconda-navigator
```

If you want to update all packages you can use:
```Anaconda
conda update --all
```
You can check the issue [here](https://github.com/ContinuumIO/anaconda-issues/issues/8733)
