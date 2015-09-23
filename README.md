1. [Install pyenv](https://github.com/bf4648/pyenv-setup#install-pyenv "Install pyenv")
2. [Update bash profile](https://github.com/bf4648/pyenv-setup#update-bash-profile "Update Bash Profile")
3. [Install python35](https://github.com/bf4648/pyenv-setup#install-python35)
4. [Install pyenv virtualenv](https://github.com/bf4648/pyenv-setup#install-pyenv-virtualenv)
6. [Source the bash profile entries](https://github.com/bf4648/pyenv-setup#source-the-bash-profile-entries)
7. [Clone the project](https://github.com/bf4648/pyenv-setup#clone-the-project "Clone the project")
8. [Create virtual environment](https://github.com/bf4648/pyenv-setup#create-virtual-environment "Create virtual environment")
9. [Activate virtualenv](https://github.com/bf4648/pyenv-setup#activate-virtualenv "Activate virtualenv")
10. [Install the module](https://github.com/bf4648/pyenv-setup#install-the-module "Install the module")
11. [View the installed modules](https://github.com/bf4648/pyenv-setup#view-the-installed-modules "View the installed modules")
12. [Run the project](https://github.com/bf4648/pyenv-setup#run-the-project "Run the project")
13. [Set up Pycharm](https://github.com/bf4648/pyenv-setup#set-up-pycharm "Set up Pycharm")

___

#Install pyenv

```
brew update
brew install pyenv

```

#Update bash profile
##Add the following to ~/.bash_profile

```
if which pyenv > /dev/null; then eval "$(pyenv init -)"; fi
```

##For fish prompts, update ~/.config/fish/config.fish
###Ref: [fish-prompts-using-pyenv](https://github.com/yyuu/pyenv/issues/32)
```
status --is-interactive; and . (pyenv init - | psub)
```
___

#Install python35

##See a list of versions
```
pyenv versions
```
##Install python version

```
pyenv install 3.5.0
```

##Switch to a python 3.5
```
pyenv global 3.5.0
```

##Ensure that python3.5.0 is the current global python version

```
pyenv versions
```
___

#Install pyenv virtualenv

```
brew install pyenv-virtualenv
```

##Update bash profile with the following entry

```
if which pyenv-virtualenv-init > /dev/null; then eval "$(pyenv virtualenv-init -)"; fi
```

##For fish prompts, update ~/.config/fish.config.fish
###Ref: [fish-prompts-using-pyenv](https://github.com/yyuu/pyenv/issues/32)
```
status --is-interactive; and . (pyenv virtualenv-init - | psub)
```
___

#Source the bash profile entries

```
source ~/.bash_profile
```
___

#Clone a project
```
git clone /path/to/project
```
___

#Create virtual environment
```
pyenv virtualenv 3.4.3 project-module-name-virtual-env-3.5.0
```
___

#Activate virtualenv

##List the virtualenvs

```
pyenv virtualenvs
```

##Activate the virtualenv
```
pyenv activate project-module-name-virtual-env-3.5.0
```

##To Deactivate virtualevn

```
pyenv deactivate
```
___
##To delete and existing pyenv 

```
pyenv uninstall my-virtual-env
```
___
#Install the module
## Ref: [editable-installs](https://pip.pypa.io/en/latest/reference/pip_install.html#editable-installs)
```
cd /path/to/project
pip install --allow-all-external -e .
pip install --upgrade pip
```
___

#View the installed modules
## Make sure that gtfsgenerator-cmd-proj is among the list of installed modules
```
pip list
```
___

#Run the project
`gtfsgenerator-cmd-proj -h` or
`python -m /path/to/project/module`
___

#Set up Pycharm
##Ref: [adding-existing-virtual-environment](https://www.jetbrains.com/pycharm/help/adding-existing-virtual-environment.html)

1.  Pycharm > Preferences > Project Interpreter
2.  In the drop-down list, choose **Add local**
3.  Select the Python Interpreter using the following path (symlink python will point to the current python)
	1.  `~/.pyenv/versions/gtfsgenerator-virtual-env-3.

