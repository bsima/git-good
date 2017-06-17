---
title: Git Good
---

> _This is a starting point for mastering git, a sisyphean task no
> doubt. Git is a complex software, nobody is expected to master
> **all** of it, so if you have a useful tip, please share!_

The git manual pages are actually very good. Start with `man git` and
maybe check out `man gittutorial`. Don't be shy about using `man
git-<subcommand>` when you don't know how to do something. If you're
curious about different ways to use git in your daily workflow, check
out `man gitworkflows`.

# Table of Contents

* [Guidelines](#guidelines)
* [Grokking Git](#grokking-git)
   * [Rebasing: the most important concept](#rebasing-the-most-important-concept)
   * [Branching](#branching)
* [Tools](#tools)
* [Commit Messages](#commit-messages)
   * [Seven Rules to Good Commit Messages](#seven-rules-to-good-commit-messages)
   * [Automate Good Commit Messages with .gitmessage](#automate-good-commit-messages-with-gitmessage)
* [Other References &amp; Tutorials](#other-references--tutorials)
* [DM Git Workflow](#dm-git-workflow)

# Guidelines

- <a name="small-commits"></a>
Separate commits into small, logical changes. [Avoid large diffs as much as possible.][large-diffs]
<sup>[link](#small-commits)</sup>

[larg-diffs]: https://medium.com/@kurtisnusbaum/large-diffs-are-hurting-your-ability-to-ship-e0b2b41e8acf#.n2fbjcuob

- <a name="commit-msg"></a>
In a commit message, the first line is a brief _what_, the rest is a succint
_why_.
<sup>[link](#commit-msg)</sup>

- <a name="wrap-lines"></a>
In commit messages, limit the first line to 50 characters, wrap the rest to 80 characters.
<sup>[link](#wrap-lines)</sup>

# Grokking Git

## Rebasing: the most important concept

I once read an interview with Linus where he said that every git command is
basically a different take on `rebase`. So, if you want to get good at git
quick, learn about rebasing - the rest will follow.

- [Git Book chapter on rebasing](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)
- [Ryan's tutorial](http://rypress.com/tutorials/git/rebasing)
- [Rebase as an alternative to merge](https://www.youtube.com/watch?v=PnHlnx_nmCI) [video]
- [Don't be scared of git rebase][leclaire]

[leclaire]: https://nathanleclaire.com/blog/2014/09/14/dont-be-scared-of-git-rebase/

## Branching

- [Learn git branching](http://learngitbranching.js.org/) - awesome interactive tutorial

# Tools

Git isn't perfect. These tools make it easier to work with:

- [GitHub Desktop](https://desktop.github.com/)
- [Magit](https://magit.vc/) (emacs package)
- [gitgutter](https://github.com/airblade/vim-gitgutter) (vim plugin)
- [fugitive](https://github.com/tpope/vim-fugitive) (vim plugin)

# Commit Messages

**Original article:** [How to Write a Git Commit Message](http://chris.beams.io/posts/git-commit/)

Git was originally used over email: someone would make a change to some
software, create a `.patch` file, and email it to the maintainer. In the email,
the author of the patch would add an appropriate subject with a brief line about
*what* the patch does, and then in the body they would explain _why_ the patch
is a good idea.

Commit messages retain this structure: the first line is a brief _what_, the
rest is a succint _why_.

## Seven Rules to Good Commit Messages

I guess they're really more like [guidelines](https://www.youtube.com/watch?v=jl0hMfqNQ-g)...

1. Separate subject from body with a blank line
1. Limit the subject line to 50 characters
1. Capitalize the subject line
1. Do not end the subject line with a period
1. Use the imperative mood in the subject line
1. Wrap the body at 72 characters
1. Use the body to explain what and why vs. how

## Automate Good Commit Messages with `.gitmessage`

Originally created by [David Winterbottom][david], this is a quick
hack to make you more likely to write helpful commit messages.

[david]: http://codeinthehole.com/writing/a-useful-template-for-commit-messages/

Save the following as `~/.gitmessage`:

```
# If applied, this commit will...


# Why was this change made?


# Any references to tickets, articles, etc?
```

Then, add the following to `~/.gitconfig`:

```
[commit]
  template = ~/.gitmessage
```

# Other References & Tutorials

- [Git Magic](http://www-cs-students.stanford.edu/~blynn/gitmagic/index.html)
