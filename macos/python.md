# MacOS Python Virtual Environments
## Context
This was written in November of 2022 using macOS Ventura 13.0 22A380 and Python version 3.10.8

## References
* [https://sourabhbajaj.com/mac-setup/Python/virtualenv.html](Python Virtualenv)

## Assumptions
* Homebrew is already installed
* Python is already installed via Homebrew
* Virtualenvswrapper is not used
* You virtualsenv for a project will be stored in a subfolder within the project folder
* You can use a .gitignore file to ignore the venv subfolder inside of each project


# Install Virtual Environments
```
brew install virtualenv
```

# Configure Terminal
Note: This assumes the Z shell (Zsh) is being used

## Edit shell config file
Note: If this is your first time configuring Z shell, .zshrc will be blank. That is normal.
```
vi ~/.zshrc file
```

## Place the following in the .zshrc file
```
# Setting PATH for Python 3 installed by brew
export PATH=$PATH:/usr/bin/python3

# Configuration for virtualenv
export VIRTUALENVWRAPPER_VIRTUALENV=/opt/homebrew/bin/virtualenv
alias sv='source ./venv/bin/activate && export PS1="(${PWD##*/}-venv)$_OLD_VIRTUAL_PS1"'
```

The alias command will create a command alias (sv) that will make it easier to switch into a projects virtual environment. This command also changes the shell prompt as a visual queue to remind you that you are working in a virtual environment. The the "Creating a virtual environment" section below as this command assumes the virtual environments will be storted in a subfolder within the project folder and that the sub folder will always be named "venv".

# Creating a virtual environment
My methodology is to store the virtual environment for a project within the project folder. This is not the only approach, but it is my preferred approach.

First a bit about my folder structure. All of my code is stored in my home directory in a subfolder named "Repos". For example "/Users/jimmy/Repos". Each project has it's own subfolder within repos (EX: /Users/jimmy/Repos/project1, etc.). Each project subfolder will have another subfolder named "venv" which contains the virtual environment for that file (EX: /Users/jimmy/Repos/project1/venv). This last part is my preference, but is also a key for the sv command alias defined in the previous section.

# Commands
* Change into your project directory
```
cd /Users/jimmy/Repos/project1
```
* Create the virutal environment
```
virtualenv venv
```