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
## How to relaunch a docker container
Here is how you relaunch your Spectre container if you used Docker to obtain a Spectre environment.
~~~~
#Make sure Docker is running. You can check if it's running by clicking the Docker icon from your menu bar, and towards the bottom of the menu it should read, "Docker is running."
docker start NameOfYourDockerContainer
docker exec -it NameOfYourDockerContainer /bin/bash -l
