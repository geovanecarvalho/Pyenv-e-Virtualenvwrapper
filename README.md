> baseado no meu outro tutorial https://gist.github.com/luzfcb/1a7f64adf5d12c2d357d0b4319fe9dcd

Use o pyenv https://github.com/pyenv/pyenv para baixar, instalar e gerenciar múltiplas versões do INTERPRETADOR Python na sua maquina.


Primeiro instale as dependências:

Linux (Ubuntu):

Abra um terminal, apertando o atalho CRTL + ALT + T ou digite aperte a tecla do windows e digite terminal, ou clique com o botão direito na tela, e escolha a opção "Abrir Terminal" (somente para Ubuntu 15.10 ou superior, para 14.04 é necessário instalar o pacote nautilus-open-terminal e reiniciar)

Primeiro, atualize a lista de pacotes:

```bash
sudo apt-get update
```
Instale os pacotes básicos

```bash
sudo apt-get install -y build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm gettext libncurses5-dev tk-dev tcl-dev blt-dev libgdbm-dev git python-dev python3-dev aria2
depois:
```

```bash
curl -L https://raw.githubusercontent.com/pyenv/pyenv-installer/master/bin/pyenv-installer | bash
```

logo após, edite o arquivo .bashrc localizado na "Pasta Pessoal" ou Home do seu usuário, com o comando:

```bash
gedit ~/.bashrc
```

adicione esses comandos ao final do arquivo:

```bash
export PYTHON_BUILD_ARIA2_OPTS="-x 10 -k 1M"

export PATH="~/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

feito isso, salve o arquivo, feche o gedit e feche TODOS os terminais para poder aplicar a configuração.



Abra novamente um terminal, apertando o atalho CRTL + SHIFT + T .



Você pode ver as versões do interpretador Python que podem ser instalados com o comando:

```bash
pyenv install -l
```

Se a versão do interpretador Python que você quer instalar não aparecer na lista, tente atualizar da base de dados de versões do interpretadores rodando pyenv

```bash
pyenv update
```

Instale o pyenv (vou usar a versão 3.5.1 nos exemplos a seguir, mas você pode usar qualquer uma das versões listadas ao executar pyenv install -l )

```bash
pyenv install 3.5.1
```

logo após, defina o Python 3.5.1 como o python padrão do seu usuário:

```bash
pyenv global 3.5.1
```

ps: Se você instalou múltiplas versões do interpretador python e quer deixa-las disponíveis para uso execute

```bash
pyenv global versao_principal segunda_versao terceira_versao
```
exemplo, vamos supor que você instalou o Python 3.5.1, 3.6.2, 2.7.13 , então o comando seria:

```bash
pyenv global 3.5.1
```
Verifique a versão instalada com:

```bash
python -V
```
Verifique a versão em utilização:

```bash
pyenv versions
```

# pyenv-virtualenvwrapper

1. git clone https://github.com/pyenv/pyenv-virtualenvwrapper.git $(pyenv root)/plugins/pyenv-virtualenvwrapper
2. echo 'pyenv virtualenvwrapper' >> ~/.bashrc
3. source ~/.bashrc

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

# Mostrar Branch no Terminal
```
export PS1='\u@\h\[\033[01;34m\] \w\[\033[0;32m\]$(__git_ps1 " (%s)")\[\033[01;34m\]$\[\033[00m\] ' >> ~/.bashrc
```
