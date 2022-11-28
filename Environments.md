# Cheat Sheet
pip
- Install package: `pip install pandas`
- Install package version: `pip install pandas==1.5.2`
- Create requirements.txt: `pip freeze > requirements.txt`
- Install pacakges from requirements.txt: `pip install -r requirements.txt`

venv
- Create: `python -m venv .venv`
- Activate: `.venv\scripts\actiave`
- Deactivate: `deactivate`

pyenv
- Install python: `pyenv install 3.8.0`


# Overview
- The environment is all the code, data, and variables that your computer has access to
  - Your PATH variable is an example, see "Windows.md"
- Usually we talk about the three differet environments:
  - system environment (all the programs, code, data in C:\)
  - user environment (all the programs, code, data in C:\Users\YourUsername)
  - and also small, local, "virtual" environments that only apply to one code folder (and its sub-folders)
- Usually code is very dependent on the environment, especially Python packages that change very often like Tensorflow
- The advantage of virtual environments is that for one code project you can have Python v3.8 and Tensorflow v2.11.0, and in another code project something totally different
- When you hit the "play" button in your code editor, basically two things need to happen:
  - The editor needs to know what environment you are in, e.g. where to find python in your computer
  - The editor needs to use that environment to call your main code file

# Anaconda (conda) or venv?
- Honestly, conda doesn't technically support tensorflow, otherwise it works okay
- venv instead seems to work great, if you dont mind the command line

# Install Tensorflow in Virtual Environment
- Anaconda (Conda) does not officially support Tensorflow, so we don't recommend it
- Remember windows paths use the backslash \\, though powershell accepts either
- Use pyenv to manage your python versions, rather than just using a single version of python "System-wide" 

## 1. Install pyenv
- Open poweshell as admin
- Make sure you're not in a conda environment: In a shell window the conda environment is always left-most at the command prompt, surrounded by parens e.g. `(base) C:\Users\Admin` means I'm in the base environment
- Do the following:
 ```bash
 Set-ExecutionPolicy RemoteSigned
 # type A for [A] Yes to All
 Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1"
 ```
 - Restart powershell
   
## 2. Install python
 - Check which python version you need for your code
 - If you don't know, google "most recent stable python version"
 - In powershell:
 ```bash
 pyenv install <x.y.z>
 # e.g. pyenv install 3.7.9
 ```

## 3. Install packages
- Install tensorflow first, then later install easier things like pandas
- In powershell:
 ```bash
 cd <path-where-your-project is>
 pyenv local <x.y.z>
 python -m venv .venv # or maybe .\.venv
 .venv\scripts\activate # or .\.venv\scripts\activate
 python -m pip install --upgrade pip # seems to help
 pip install tensorflow
 # or if you need an exact version
 pip install tensorflow==2.11.0
 # or even
 pip install tensorflow>=2.0.0
 ```
