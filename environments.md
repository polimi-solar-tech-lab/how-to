# Cheat Sheet
|What                            |Command|
|----                            |----|
|Install package                 |`pip install pandas`|
|Install package version x.y.z   |`pip install pandas==x.y.z`|
|Install python x.y.z            |`pyenv install x.y.z`|
|Create env                      | `python -m venv .venv`|
|Activate env                    | `.venv\scripts\actiave`|
|Deactivate                      | `deactivate`|
|Create requirements.txt         | `pip freeze > requirements.txt`|
|Create env from .txt            | `pip install -r requirements.txt`|


# Tensorflow venv
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
