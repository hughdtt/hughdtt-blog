---
layout: post
title:  "Welcome to Git: The Cheatsheet"
date:   2021-08-02 21:00:00 +1000
categories: cheatsheet programming
featuredPost: false
---
Hey everyone! 👋 I've recently been experimenting and learning more about Git as a versioning control tool. Thought I would share some things I've learnt and also some quick snippets of what I use on a day-to-day basis. 

This is more of a guide for Git for Windows (as that is what I'm using). If you have installed Git, you should be able run Git Bash to run the unix commands. Another option is to install a Windows Subsystem for Linux (WSL) in VSCode and use that instead (my preference).

## The basics
Usually the first thing you learn in git is how to save your working directory onto a git branch

```
# Usually you do something like this
git add . 
git commit -m "Example update"
```

You can actually save a bit of time by combining the add & commit into one line, like so

```
# Add & Commit combined
git commit -am "Cheeky one liner"
```
Neat! But there's actually an even faster way to do this - by using Aliases

The git config command allows you to create aliases that can shorten existing commands or create custom commands. For instance we can shorten this "-am" command to something like this

```
# Create alias
git config --global alias.ac "commit -am"

# So now we can do this
git ac "Speedy!" // Equivalent of git commit -am "Speedy!"
```

## Amend
Sometimes a good commit message can be alot more valuable than a code comment.

A quick `git log` can show you a timeline of commits and give you picture of how the code has changed. Making a mistake on these messages can lead to confusion. 

So what if we wanted to change the message of our last commit?

```
# Change message of last commit
git commit --amend -m "Fixed!"
```

And if you forgot to add some files that you want to commit aswell?

```
# Add everything
git add .

# Amend with the same message
git commit --amend -no-edit
```
Keep in mind, this only works if you haven't pushed it to a remote repository. 

## Revert
If you want to revert a previous commit that you pushed on a remote repository, you can use this command

```
git revert "[commit]"
```

## Codespaces
This is probably the coolest thing I came across. Let's say you're somewhere and don't have VScode or Git installed. You can simply go to the github repository and tap the `.` key to open up a web instance of VScode where you commit make changes to the file there.

That's all for now, but I'll make sure to keep this updated when I find new things! 

Thanks all! 😀


