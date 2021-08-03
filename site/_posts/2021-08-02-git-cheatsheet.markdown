---
layout: post
title:  "Welcome to Git: The Cheatsheet"
date:   2021-08-02 21:00:00 +1000
categories: cheatsheet git
---
Git is an amazing source control tool. But for those who are just learning to use it in a team setting, it can be daunting to make changes knowing that it *could* potentially destory everything (I'm kidding). The beauty of Git is that even if you mess things up you can always just roll back to last working save. You can always rely on the fact that a senior engineer will swoop in to save the day if you have any questions or do something wrong. After all, the only way you're gonna get good at it is if you use it alot. 

Given that this is meant to be a cheatsheet, I'll keep things simple. I've added a little component below that you can switch between branch workflows and actually git commands cheatsheet.

## Cheatsheet
<div class='half-bleed'>
{% highlight powershell %}
# Set a name that is identifiable for credit when review version history
git config --global user.name “[firstname lastname]”

# set an email address that will be associated with each history marker
git config --global user.email “[valid-email]”

# Set automatic command line coloring for Git for easy reviewing
git config --global color.ui auto
{% endhighlight %}
</div>
## Workflow 
But even then, using it is a hell of a lot easier if you had a clear picture or process of what to do. Luckily for you I have just the thing.

If you're working on a new feature and don't want to touch the `MASTER` branch, you can make a new feature branch and use that instead.

{% highlight powershell %}
# Create a new feature branch
git branch jc_new_feature

# Checkout your new feature branch
git checkout jc_new_feature
{% endhighlight %}

Once a branch is set up, you'll just working on it until the feature is done and ready to merge to `MASTER`. I've added some commands I like to use to keep track of what's going on while I'm working.

{% highlight powershell %}
# Check where you are and what's happening
git status
git log

# Check the differences that haven't been added
git diff

# If your happy with it, add all files to the stage
git add .

# Commit files with message
git commit -m "Description of this commit"

# Optional (but recommended) push local branch to remote
git push origin jc_feature_name
{% endhighlight %}