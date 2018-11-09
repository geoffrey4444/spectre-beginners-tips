# Spectre tips for beginners
This repo holds tips and notes for how to do useful things when getting up to speed with [spectre](spectre-code.org).

# Git related code snippets etc.

## How to update your fork when the code you forked from changes
Here is how you update the develop branch of your fork to get the latest changes from the main spectre repo (called the "upstream repo."
~~~~
# Set up upstream (first time only)
git remote add upstream ORIGINAL-REPO-LOCATOR
# Update a fork
git fetch upstream
git checkout develop
git merge upstream/develop
git push
~~~~

## How do you squash commits
Let's say you have pushed 3 commits to your fork, but before doing a pull request, you want to squash them to one commit. Here's how:

Let's say your branch is called CylindricalBlastWave.

~~~~
git rebase -i origin/CylindricalBlastWave~3 CylindricalBlastWave
~~~~

Then, in the window that appears, you'll see the commits listed with the word "pick" next to each one. Keep the oldest commit as is, but for the newer ones, change "pick" to "fixup", then save and quit the editor. You can then push if you're happy with how this went.
