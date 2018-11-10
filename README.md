# Spectre tips for beginners
This repo holds tips and notes for how to do useful things when getting up to speed with [spectre](spectre-code.org).

# Tips for writing new spectre code
## Things to do before making a pull request to merge into `sxs-collaboration/spectre`

  - Format your code with `git-clang-format-5.0`
  - Make sure your code compiles by running `make -j2` in your build directory 
  (in docker, typically `/work/spectre-build-clang`). Replace `2` with the number of processors if you're on a machine with 
  more than 2 cores, like a high-end Mac/PC or a cluster. If the process hangs, you might have run out of memory; in that 
  case, try using fewer cores. Fix any compiler errors and warnings you get. 
  - Also in your build directory, make sure all tests pass with `ctest -j2` where 2 is the number of processors.
  - For each `*.cpp` file you created or modified, in your build directory, run `make clang-tidy FILE=/path/to/file.cpp`. 
  [Clang-tidy](http://clang.llvm.org/extra/clang-tidy/) is a "linter", a tool that helps to find and fix common 
  programming mistakes that the compiler won't catch with a compiler error.
  - Make a second build directory, e.g. `/work/iwyu-spectre-build-clang` and `cd` into it. Configure as usual, but add the 
  option `-DUSE_PCH=OFF` to `cmake`. Then, in the second build directory, for each `*.cpp` file, 
  run `make iwyu FILE=/path/to/*.cpp`. This will check that your `#include` lines. If you get errors from this, check 
  with an experienced spectre developer, as these error messgaes sometimes are wrong.
  - In your normal build directory, run `make doc`. Copy thre `docs/html` directory outside of docker (if you are using 
  docker), and then open `docs/html/index.html` in your browser. Make sure documentation you made looks right
  

## How to format your code
For each file you have changed (`git status` before commit, or look in github after commit), do this, replacing `/path/to/file` with the path to the file you want to format:
~~~~
git-clang-format-5.0 -f /path/to/file
~~~~
This will automagically format only the lines you changed to google style. If you want to reformat an entire file 
(useful if you made a brand new file), just do 
~~~~
clang-format -i /path/to/file
~~~~

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


