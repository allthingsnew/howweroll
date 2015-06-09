# Git

Toward clean, cohesive, and consistent history.

## Commits

Favor commit verbosity and context over number of commits. Repository history should make sense by use of commit messages coupled with diffs rather than a breadcrumb of many smaller commit changes.

### Squashing Commits

**Before pushing your changes** it's good practice to [squash extra commits](https://help.github.com/articles/interactive-rebase) into as small of pieces as possible. Be careful that picked commits do not swallow squashed history.

### Commit Messages

Message Subject should be short and concise with no punctuation.

If more details are needed include a description.

* Subject Line: present tense summary less than 50 characters
* More Information
* Links to references on Github

Here's a good sample commit message:

    Component: Add ability to find users [Closes #29]

    Some more information on this edit. Why it was needed. Any refs to
    Github issues or sources go here.

    #29

(Notice the use of #29 in the message. Github sees this and will actually close issue #29 for you and reference the issue via link.)

## Branches

Own your own branches. It's best not to work directly on master.

Use [git-up](https://github.com/aanand/git-up) (rebase) to pull down the latest
changes.

Delete or close out branches when they have been merged into master.
