# Git Configuration Tips

Git has a lot of configuration options; here are some of the more important ones:

    Make sure that your name and email are set. See this page for details. The email should match your GitHub account email in order to make the GitHub UI correctly link your commits to your profile.
    There are lots of other useful customizations you can make to git. See this guide for details, or read man git-config. Some useful ones I've found:
        `git config --global color.ui true` for helpful coloring on common commands like diff, log, and status.
        `git config --global rerere.enabled true` turns on recording of merge resolutions so that if you ever do the same merge twice it will remember the resolution for you.
        `git config --global pack.threads 0` enables faster repository packing for multicore machines.
        `git config --global push.default upstream` tells git to only push your current branch when you type git push.
            Note: The default behavior is to push all branches when you type git push, which is really probably not what you want.
            Another thing you might see recommended is current rather than upstream.  current pushes the current branch to a remote branch from the same name, while upstream pushes the current branch to a tracking branch.  They're probably usually the same, but if they're not upstream is almost certainly the behavior you intended.  The exception is when the current branch isn't yet tracking anything, but in that case git push will spit out some output suggesting you set the upstream branch to track, along with a command you can copy and paste.
        `git config --global merge.conflictstyle diff3` shows the merge base in addition to the two conflicting results, making it much easier to see how to resolve conflicts.
        The "alias" section of your gitconfig allows you to define aliases for git subcommands.