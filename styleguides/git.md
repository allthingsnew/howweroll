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

## Git Flow

The branch model known as GitFlow keeps everything working correctly by separating out different development timelines into topic branches. Install GitFlow useing Homebrew:

	# We use the AVH edition because its maintainer is active.
    brew install git-flow-avh

Work on new features only in their respective branches:

    git flow feature start foo

    # make some changes relevent to only this feature
    git add .
    git commit

Incorporate upstream changes regularly.

	git checkout master
    git pull --rebase
    git flow feature checkout foo
    git flow feature rebase

When finished with your feature and tested, make sure your up to date with upstream changes
on master, squash commits into as small pieces as possible, and close out the feature.

	# On feature foo branch
    git rebase -i
    git flow feature finish
    # Then push your changes
    git push
