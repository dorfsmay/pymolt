

**DANGER**: This script will delete all files matching gitignore.


# Purpose
Reinstall a python3 venv environment keeping attempting to keep all other files.

This will delete all files that matches the gitignore files pattern, but keep
files untracked by git, as well as changes not yet committed.

# Use cases
* renaming a directory or git repository
* flipping between python interpreters/compiles (eg: CPyton3 and pypy3)
* quickly get rid of packages installed manually (not in requirements.txt)

It is different than `python3 -m venv upgrade` as it relinks to a completely
different version of python as well as reinstall packages
from requirements.txt.


# Actions taken
* Delete all files matching the gitignore files (git clean -Xdf)
* Reinstall the python venv
* Reinstall (pip install) packages from requirements.txt
* Run activate in the current shell

# Prerequisites / Assumptions
* you are git-ignoring all the venv files
* All your packages are listed in a requirements.txt file
* you are fine with losing all files matching gitignore files  
  (not as obvious as it sounds, config files are often ignored)

# Example of gitignore
Example of a gitignore for python3 venv:

```
__pycache__/
bin/
include/
lib/
lib64
site-packages/
pyvenv.cfg
pip-selfcheck.json
share/
*.pyc

```


