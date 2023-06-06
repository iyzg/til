# Stash N Pull

If you forget to pull before you start coding and now have merge commits, an easy way to resolve this is to run `git stash`, `git pull`, then `git stash pop`. This will store your commits then bring them back after pulling the newest codebase.

> **Note:** After you pop the stash, you will probably have to go and resolve merge conflicts. Remember to do this before you commit your changes to any repo!