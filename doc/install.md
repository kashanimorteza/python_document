<!--------------------------------------------------------------------------------- Install -->
# Install
[Python]



<!--------------------------------------------------------------------------------- Linux -->
<br><br>

## Linux
<!-------------------------- General -->
### General
```bash
sudo apt update -y
sudo apt install software-properties-common -y
sudo add-apt-repository ppa:deadsnakes/ppa -y
sudo apt update -y
sudo apt install python3 -y
sudo apt install python3-pip -y
sudo apt install python3-venv -y
```

<!-------------------------- Pyenv -->
### Pyenv
```bash
sudo apt update
sudo apt install -y make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev \
libffi-dev liblzma-dev git
```
```bash
curl https://pyenv.run | bash
```
```bash
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> /root/.bashrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> /root/.bashrc
echo 'eval "$(pyenv init -)"' >> /root/.bashrc
echo 'eval "$(pyenv virtualenv-init -)"' >> /root/.bashrc
```
```bash
source /root/.bashrc
```
```bash
pyenv --version
```
```bash
pyenv install 3.7
pyenv install 3.9
```
```bash
pyenv global 3.9
pyenv local 3.7
python --version
```


<!--------------------------------------------------------------------------------- Mac -->
<br><br>

## Mac 
<!-------------------------- General -->
### General
```bash
brew install python
python3 --version
```

<!-------------------------- Pyenv -->
### Pyenv
```bash
brew install pyenv
```
```bash
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
```
```bash
source ~/.zshrc
```
```bash
pyenv --version
```
```bash
pyenv install 3.7
pyenv install 3.9
```
```bash
pyenv global 3.9
pyenv local 3.7
python --version
```

<!-------------------------- Pyenv X86_64 -->
### Pyenv X86_64
```bash
softwareupdate --install-rosetta --agree-to-license
arch -x86_64 /bin/zsh
arch
```
```bash
arch -x86_64 /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
ls /usr/local/bin/brew
file /usr/local/bin/brew
/usr/local/bin/brew install openssl readline zlib bzip2 sqlite xz
echo 'export PATH="/usr/local/bin:/usr/local/sbin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```
```bash
arch -x86_64 /bin/zsh
/usr/local/bin/brew update
/usr/local/bin/brew install pyenv
ls /usr/local/bin/pyenv
file /usr/local/bin/pyenv
```
```bash
echo 'export PYENV_ROOT="$HOME/.pyenv86"' >> ~/.zshrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(/usr/local/bin/pyenv init -)"' >> ~/.zshrc
source ~/.zshrc
```
```bash
arch -x86_64 /bin/zsh
env PYTHON_CONFIGURE_OPTS="--without-ensurepip" /usr/local/bin/pyenv install -v 3.7.17
/usr/local/bin/pyenv versions
ls /Users/morteza/.pyenv86/versions/3.7.17/bin/python
file /Users/morteza/.pyenv86/versions/3.7.17/bin/python
```


<!--------------------------------------------------------------------------------- Environment -->
<br><br>

## Environment 
<!-------------------------- model-1 -->
### model-1
```bash
pyenv local 3.7
python --version
python -m venv .myenv
.myenv/bin/python -m pip install --upgrade pip
source .myenv/bin/activate
pip install -r requirements.txt
pip list
```
<!-------------------------- model-2 -->
### model-2
```bash
arch -x86_64 /usr/local/bin/python3.7 -m venv .myenv3.7
.myenv3.7/bin/python -m pip install --upgrade pip
source .myenv3.7/bin/activate
pip install -r requirements.txt
pip list
python -c "import platform; print(platform.python_version(), platform.machine())"
```
<!-------------------------- Check -->
### Check
```bash
python -c "import platform; print(platform.python_version(), platform.machine())"
```


<!--------------------------------------------------------------------------------- Alias -->
<br><br>

## Alias
```bash
cat << 'EOF' >> ~/.bash_aliases
#-------------------------------------------------- [ Python ]
alias sr7='source .myenv3.7/bin/activate'
EOF
source ~/.bash_aliases
``` 



<!--------------------------------------------------------------------------------- Link -->
[Python]: https://github.com/kashanimorteza/python_document/blob/main/README.md