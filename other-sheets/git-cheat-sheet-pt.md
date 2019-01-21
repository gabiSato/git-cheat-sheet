Git Cheat Sheet Portuguese [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
===============

### Índex
* [Configuração](#configuração)
* [Arquivos de Configuração](#arquivos-de-configuração)
* [Criar](#criar)
* [Mudanças Locais](#mudanças-locais)
* [Pesquisar](#pesquisar)
* [Histórico de Commits](#histórico-de-commits)

<hr>

## Configuração

##### Mostrar a configuração mais recente:
```
$ git config --list
```
##### Mostrar configuração do repositório:
```
$ git config --local --list
```

##### Mostrar configuração global:
```
$ git config --global --list
```

##### Mostrar configuração do sistema:
```
$ git config --system --list
```

##### Defina um nome que seja indentificável para créditos ao revisar o histórico de versões:
```
$ git config --global user.name “[nome sobrenome]”
```

##### Defina um endereço de email que será associado com cada marcador histórico:
```
$ git config --global user.email “[email-válido]”
```

##### Defina a coloração automática da linha de comando do Git para facilitar a revisão:
```
$ git config --global color.ui auto
```

##### Defina um editor global para commits:
```
$ git config --global core.editor vi
```

<hr>

## Arquivos de Configuração

##### Arquivo de configuração específico do repositório [--local]:
```
<repo>/.git/config
```

##### Arquivo de configuração específico do usuário [--global]:

```
~/.gitconfig
```

##### Arquivo de configuração do sistema [--system]:
```
/etc/gitconfig
```

<hr>

## Criar

##### Clonar um repositório existente:

Existem duas maneiras:

Via SSH

```
$ git clone ssh://usuario@dominio.com/repo.git
```

Via HTTP

```
$ git clone http://dominio.com/usuario/repo.git
```

##### Crie um novo repositório local:
```
$ git init
```

<hr>


## Mudanças Locais

##### Mudanças no diretório de trabalho:
```
$ git status
```

##### Alterações nos arquivos rastreados:
```
$ git diff
```

##### Adicione todas as alterações atuais ao próximo commit:
```
$ git add .
```

##### Adicione algumas alterações no &lt;arquivo&gt; para o próximo commit:
```
$ git add -p <arquivo>
```

##### Crie um commit de todas as alterações locais em arquivos rastreados:
```
$ git commit -a
```

##### Crie um commit de alterações previamente preparadas:
```
$ git commit
```

##### Crie um commit com mensagem:
```
$ git commit -m 'mensagem aqui'
```

##### Crie um commit pulando a área de teste e adicionando uma mensagem:
```
$ git commit -am 'mensagem aqui'
```

##### Faça um commit para uma data anterior:
```
$ git commit --date="`date --date='n day ago'`" -am "<Mensagem do commit aqui>"
```

##### Altere o último commit:<br>
<em><sub>Não altere commits publicados!</sub></em>

```
$ git commit -a --amend
```

##### Altere o último commit mas usar a mensagem de log do commit anterior:
<em><sub>Não altere commits publicados!</sub></em>

```shell
$ git commit --amend --no-edit
```

##### Altere a data do último commit:
```
GIT_COMMITTER_DATE="date" git commit --amend
```

##### Altere a data do autor do último commit:
```shell
$ git commit --amend --date="date"
```

##### Mova as alterações sem commits(que não foram criados commits) da ramificação atual para outra ramificação:<br>
```
$ git stash
$ git checkout branch2
$ git stash pop
```

##### Restaure as alterações de stash de volta ao ramo atual:
```shell
$ git stash apply
```

#### Restaure uma alteração de stash especifica de volta ao ramo atual:
- *{stash_number}* pode ser obtido em `git stash list`

```shell
$ git stash apply stash@{stash_number}
```

##### Remova o último conjunto de alterações de stash:
```
$ git stash drop
```

<hr>

## Pesquisar

##### Pesquisa de texto em todos os arquivos do diretório:
```
$ git grep "Hello"
```

##### Pesquisa de texto em qualquer versão:
```
$ git grep "Hello" v2.5
```

<hr>


## Histórico de Commits

##### Mostrar todos os commits, começando com o mais recente (ele mostrará o hash, as informações do autor, a data e o título do commit):
```
$ git log
```

##### Mostrar todos os commits (mostrará apenas o hash e a mensagem do commit):
```
$ git log --oneline
```

##### Mostrar todos os commits de um usuário específico:
```
$ git log --author="nome de usuário"
```

##### Mostrar alterações ao longo do tempo para um arquivo específico:
```
$ git log -p <arquivo>
```

##### Exibir commits que estão presentes somente no remote/branch no lado direito:
```
$ git log --oneline <origin/master>..<remote/master> --left-right
```

##### Quem mudou, o que e quando em &lt;arquivo&gt;:
```
$ git blame <file>
```

##### Mostrar log de referência:
```
$ git reflog show
```

##### Excluir log de referência:
```
$ git reflog delete
```
<hr>

## Mover / Renomear

##### Renomear um arquivo:

Renomear Index.txt para Index.html

```
$ git mv Index.txt Index.html
```

<hr>

## Ramos & Etiquetas

##### Listar todas os ramos locais:
```
$ git branch
```

#### Listar ramos locais/remotos:
```
$ git branch -a
```

##### Listar todos os ramos remotos:
```
$ git branch -r
```

##### Mudar o ramo atual(HEAD branch):
```
$ git checkout <ramo>
```
