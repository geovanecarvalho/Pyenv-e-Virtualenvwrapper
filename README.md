# Pyenv-e-Virtualenvwrapper

pyenv (https://github.com/pyenv/pyenv)
pyenv-virtualenvwrapper (https://github.com/pyenv/pyenv-virtualenvwrapper)
pyenv
sudo apt-get update
sudo apt-get install -y git

git clone https://github.com/pyenv/pyenv.git ~/.pyenv
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bashrc
source ~/.bashrc

sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev \
     libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev \
     xz-utils tk-dev
## Comandos pyenv
pyenv install --list
pyenv install 3.6.3 # Vai demorar um pouco
pyenv global 3.6.3

# pyenv-virtualenvwrapper

git clone https://github.com/pyenv/pyenv-virtualenvwrapper.git $(pyenv root)/plugins/pyenv-virtualenvwrapper
echo 'pyenv virtualenvwrapper' >> ~/.bashrc
source ~/.bashrc

## Comandos virtualenvwrapper

para criar um virtualenv
```mkvirtualenv nomedovenv --python=versãodopython```
para desativar virtualenv
```deactivate```
para ativar virtualenv
```workon nomedavenv```
deletar virtualenv
```rmvirtualenv nomedavenv```
# Configura manage.py bashrc

```echo alias manage='python $VIRTUAL_ENV/../manage.py' >> ~/.bashrc```
