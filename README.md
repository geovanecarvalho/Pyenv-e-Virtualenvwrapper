Use o pyenv https://github.com/pyenv/pyenv para baixar, instalar e gerenciar múltiplas versões do INTERPRETADOR Python na sua maquina.

Primeiro instale as dependências:

Linux (Ubuntu):

Abra um terminal, apertando o atalho CRTL + ALT + T ou digite aperte a tecla do windows e digite terminal, ou clique com o botão direito na tela, e escolha a opção "Abrir Terminal" (somente para Ubuntu 15.10 ou superior, para 14.04 é necessário instalar o pacote nautilus-open-terminal e reiniciar)

Primeiro, atualize a lista de pacotes:

sudo apt-get update
Instale os pacotes básicos

sudo apt-get install -y build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm gettext libncurses5-dev tk-dev tcl-dev blt-dev libgdbm-dev git python-dev python3-dev aria2
depois:
curl -L https://raw.githubusercontent.com/pyenv/pyenv-installer/master/bin/pyenv-installer | bash
logo após, edite o arquivo .bashrc localizado na "Pasta Pessoal" ou Home do seu usuário, com o comando:

gedit ~/.bashrc
adicione esses comandos ao final do arquivo:

export PYTHON_BUILD_ARIA2_OPTS="-x 10 -k 1M"

export PATH="~/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
feito isso, salve o arquivo, feche o gedit e feche TODOS os terminais para poder aplicar a configuração.

Abra novamente um terminal, apertando o atalho CRTL + SHIFT + T .

Você pode ver as versões do interpretador Python que podem ser instalados com o comando:

pyenv install -l
Se a versão do interpretador Python que você quer instalar não aparecer na lista, tente atualizar da base de dados de versões do interpretadores rodando pyenv

pyenv update
Instale o pyenv (vou usar a versão 3.5.1 nos exemplos a seguir, mas você pode usar qualquer uma das versões listadas ao executar pyenv install -l )

pyenv install 3.5.1
logo após, defina o Python 3.5.1 como o python padrão do seu usuário:

pyenv global 3.5.1
ps: Se você instalou múltiplas versões do interpretador python e quer deixa-las disponíveis para uso execute

pyenv global versao_principal segunda_versao terceira_versao
exemplo, vamos supor que você instalou o Python 3.5.1, 3.6.2, 2.7.13 , então o comando seria:

pyenv global 3.5.1 3.6.2 2.7.13
Verifique a versão instalada com:

python -V


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
1. pyenv install --list
2. pyenv install 3.6.3 # Vai demorar um pouco
3. pyenv global 3.6.3

# pyenv-virtualenvwrapper

git clone https://github.com/pyenv/pyenv-virtualenvwrapper.git $(pyenv root)/plugins/pyenv-virtualenvwrapper
echo 'pyenv virtualenvwrapper' >> ~/.bashrc
source ~/.bashrc

## Comandos virtualenvwrapper

1. para criar um virtualenv
**mkvirtualenv nomedovenv --python=versãodopython**

2.para desativar virtualenv
**deactivate**

3.para ativar virtualenv
**workon nomedavenv**

4. deletar virtualenv
**rmvirtualenv nomedavenv**

# Configura manage.py bashrc

echo alias manage='python $VIRTUAL_ENV/../manage.py' >> ~/.bashrc
