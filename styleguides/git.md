# Git Style Guide

Following are our Git conventions that should be followed. We like clean, cohesive,
and consistent history.

## Commits

We favor commit verbosity and context over number of commits. Repository history should make sense by use of commit messages coupled with diffs rather than a breadcrumb of many smaller commit changes.

### Squash Commits

**Before pushing your changes** it's good practice to [squash extra commits](https://help.github.com/articles/interactive-rebase) into as small of pieces as possible. Be careful that picked commits do not swallow squashed history.

### Commit Messaging

Messages should contain a Subject, Description, and any references to Issues or Tickets the commit might address. Not all commits need this much information, however, so it might be good practice to squash these into a more inclusive commit message.

A good commit message includes the following:

* Subject Line: present tense summary less than 50 characters
* More Information
* Links to references on Github

Here's a good sample commit message:

    Component: Add ability to find users [Closes #29]

    Some more information on this edit. Why it was needed. Any refs to
    Github issues or sources go here.

    #29

(Notice the use of #29 in the message. Github sees this and will actually close issue #29 for you and reference the issue via link.)

## Features

Work on new features in separate branches.

    git checkout master
    git pull --rebase
    git checkout -b feature-my-feature
    git push -u origin feature-my-feature

Incorporate upstream changes regularly.

    git fetch origin
    git rebase -i origin/master

When finished with your feature and tested, merge into master. View lastest commits and what files have been changed, making sure that no merge conflicts will arise.

    git log origin/master..feature-my-feature
    git diff --stat origin/master
    git checkout master
    git merge feature-my-feature --ff-only
    git push

Then clean up your feature branches.

    git push origin --delete feature-my-feature
    git branch -d feature-my-feature
