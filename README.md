# scripts
Bash scripts that I use on multiple environments. You may find some of them useful!

## Installation

Clone the repository:

```git clone git@github.com:shane-smith/scripts.git scripts```

Then add the scripts directory to your path, by adding something like the following to your `.bashrc` or `.bash_profile`:

```PATH=$PATH:$HOME/scripts/bin```

The above line assumes that you checked out this repository into your home directory.

## Contributions

Feel free to fork and add your own scripts, then submit a pull request! You'll be listed clearly as a contributor in this readme.

## Available Scripts

### Git 

#### commit

This script was designed to match the preferred commit comment format for my workplace. We use a project management tool with the initials "LP", which has 8-digit task IDs. The preferred commit comment format is as follows:

```lp #22446688 - Comment goes here```

Our feature branches are labelled with 'lp' and the task ID: e.g. lp22446688

With that in mind, the bash script is designed to enforce this structure, and also make it extremely easy to commit from the terminal. All I need to run is `commit Adding stuff` and it'll automatically commit in the format that I want.

In addition, it should be noted that we use the Gitflow model. Therefore, in most cases I do not want to commit directly to the 'master' or 'develop' branches - instead, I want to commit to a feature or hotfix branch, and then merge those branches into the two core branches. Due to this, the script has in-built protection to prevent accidental committing to those branches.

#### undocommit

If you have not pushed to the remote repository, and the most recent commit in your Git history was a simple one (i.e. not a merge), you will likely find this shortcut helpful.

Essentially, it just reverts back to your second-to-last commit, removing the most recent one from the log and returning your files back to you with the edits in place.

I often use this command in lieu of a `git commit --amend`.

#### logs

I love running `git log -n 10 --oneline` so much, that I wrote an alias for it: logs. This alias has been converted into a dedicated script, so that I could add it to this repository as a separate file.

Feel free to make improvements to this if you wish! It would be a good beginner task, for anyone hoping to make a small contribution. 

### Other

#### findreport

This is a simple wrapper around the `find` command, which searches in a specific directory.

We use Jasper reports at work, which are written as .jrxml files and compile down to .jasper files. Generally, I use this command to search for a .jrxml file with a specific filename, because it's usually nested within one of many sub-directories. I'd rather not have to guess and jump from one directory to another to find the one I want.

And quite often... we have *multiple* with the same file name - the base report, and then a customised version that specific customers are using. This script will pull up all instances, and it makes it easy to find the one I'm looking for.

### Configuration Files

#### .screenrc

I've added the super-simple `.screenrc` file that I use on almost all environments that I connect to.

It's only a few lines - but it adds visible labels for each of the windows that you have open, making it super-easy to navigate between them and see which one you have active at a glance.
