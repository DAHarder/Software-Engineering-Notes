# PIP
Pip is the standard package manager for Python. It allows you to install, upgrade, and manage Python packages and their dependencies easily.

## Installed Package Directory Structure 
![[Pasted image 20230405165758.png]]

## Common Commands
### `pip show <package>`
Shows information about the package including its installed location

### `python3 -c "import sys; print(sys.path)"`
Shows paths that python will look in for installed packages

### `pip install <package>`
Installs package
- **-r**: Used with installing requirements.txt file (`pip install -r requirements.txt`)
### `pip install <package> --upgrade `
Upgrades package to newest version

### `pip uninstall <package>`
Uninstalls package