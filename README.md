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
