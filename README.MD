# Git - guia prático

## Git é um sistema de controle de versão, ele é utilizado para a criação de um histórico de alterações de projetos de desenvolvimento de software.

- Nos ajudam a manter um histórico de alterações
- Ajudam a ter controle sobre cada alteração no código;
- Ajudam para que uma alteração de determinada pessoa não influencie na alteração realizada por outra;

Antes de qualquer interação com o git, você precisa informar quem é você para que ele armazene corretamente os 
dados do autor de cada uma das alterações no código:

```bash
  git config --local user.name "Seu nome aqui"
  git config --local user.email "seu@email.aqui"
```
## Criando um novo repositório

Dentro da pasta do projeto, abra o bash e execute: 

```bash
  git init
```

## Obtendo um repositório

```bash
  git clone <caminho para o repositório>
```

## Fluxo de trabalho

Seus repositoórios locais consistem em três "árvores" mantidas pelo git:

- __Working Directory__ que contem os arquivos vigentes;
- __Index__ que funciona como uma área temporária;
- __HEAD__ que aponta para o último commit que você fez;

## Adicionar e confirmar 

Você pode incluir (Adicioná-las ao Index) as mudanças usando: 

```bash
  git add <nome do arquivo>
```
Ou adicionar todos os arquivos de uma vez: 

```bashRot
  git add .
```
Para realmente confirmar as mudanças (fazer um commit) use:

```bash
  git commit -m "Comentários das alterações"
```

## Verificando histórico de commits
O comando que poderemos utilizar para isto é **git log**, que nos mostrará diversas informações, sendo o primeiro deles um hash do commit, uma identificação única de cada commit.

```bash
  #git log

  commit 84a8bffe2fcfdf0b1815d6281fd5a6f3f041a8c9 (HEAD -> master)
  Author: user <seu@email.aqui>
  Date:   Sun Jul 25 17:27:54 2021 -0300

    Mensagem de commit
```
Uma das mais comuns nos permite visualizar todos os commits, sendo que cada uma ocupa uma única linha:
```bash
  #git log --oneline

  84a8bff (HEAD -> master) mensagem de commit
```

E se em vez de menos informações quisermos mais, como as alterações do commit, usaremos:

```bash
  #git log -p
```

## Repositórios remotos
Se você não clonou um repositório existente e quer conectar seu repositório a um servidor remoto, você deve adicioná-lo com:

```bash
  git remote add origin <servidor>

  #Obs: origin é so uma convenção usada para dá nome ao repositório remoto, podendo ser alterado para um nome de sua preferência
```

### Enviando as alterações 
Suas alterações agora estão no HEAD da sua cópia de trabalho local. Para enviar estas alterações ao seu repositório remoto, execute:

```bash
  git push origin master

  #Obs: Altere master para qualquer ramo (branch) desejado, enviando suas alterações para ele.
```

## Ramificando (branches)

Branches ("ramos") são utilizados para desenvolver funcionalidades isoladas umas das outras. O branch master é o branch "padrão" quando você cria um repositório. Use outros branches para desenvolver e mescle-os (merge) ao branch master após a conclusão.

Para criar um novo branch use: 

```bash
  git branch <nome da branch>
```

E alterne para essa branch usando: 

```bash
  git checkout <nome da branch>
```

Há a possibilidade de criar e mudar para a branch em apenas um comando usando: 

```bash
  git checkout -b <nome da branch>
```

### Removendo branch 

Remova o branch da seguinte forma

```bash
  git branch -d <nome da branch>
```
## Atualizar e mesclar 
Para atualizar seu repositório local com a mais nova versão, execute: 

```bash
  git pull <repositório> <branch>
```

Para fazer merge de um outro branch ao seu branch ativo (ex. master), use: 

```bash
  git merge <nome da branch>
```

Em ambos os casos o git tenta fazer o merge das alterações automaticamente. Infelizmente, isto nem sempre é possível e resulta em conflitos. Você é responsável por fazer o merge estes conflitos manualmente editando os arquivos exibidos pelo git. Depois de alterar, você precisa marcá-los como merged com: 

```bash
  git add <nome arquivo> || git add .
```

## Revertendo alterações
No caso de você ter feito algo errado, você pode sobrescrever as alterações locais usando o commando:

```bash
  git restore <arquivo>
```

ou 

```bash
  git checkout -- <arquivo>
```

Isto substitui as alterações na sua árvore de trabalho com o conteúdo mais recente no HEAD.

### Alterações já commitadas

Queremos desfazer uma alteração que já foi marcada para ser commitada (git add), então usaremos: 

```bash
  git restore --staged <file>
```

Em um caso mais critico pode ser que você já tenha feito o commit, para isso usamos o comando:
 ```bash
  git revert <hash do commit>

  #obs: esse comando gera um novo commit revertendo as alterações feitas no commit informado
 ```

 ## Viajando no tempo

 o comando git checkout muda o estado da aplicação, seja desfazendo alterações, navegando entre branches ou commits. Assim, é possível utilizarmos:

 ```bash
  git checkout ea539b3
 ```

 Se realizarmos qualquer alteração, incluindo outro git commit, o HEAD se locomoverá para um lugar sem nome, uma branch inexistente. E se fizermos git checkout master para voltar para o estado atual, nunca mais conseguiremos acessar o commit em que estávamos anteriormente, que fica desanexado das linhas de desenvolvimento,  se quisermos fazer alterações que sejam salvas a partir daqui, será necessário criar uma branch antes.

 ## Rotulando 

É recomendado criar rótulos para releases de software. Este é um conhecido conceito, que também existe no SVN. Você pode criar um novo rótulo chamado 1.0.0 executando o comando: git tag ``<nome> <hash do commit>``

```bash
  git tag 1.0.0 1b2e1d63ff
```
Depois enviamos a tag para o servidor usando: 

```bash
  git push <nome do servidor> v0.1.0
```
- 1b2e1d63ff representa os 10 primeiros caracteres do id de commit que você quer referenciar com seu rótulo

## Dicas úteis 

usar saídas do git coloridas:

```bash
  git config color.ui true
```

exibir log em apenas uma linha por commit:

```bash
  git config format.pretty oneline
```

fazer inclusões interativas:

```bash 
  git add -i
```

Sinta se livre para fazer alguma correção nas issues ou fazer um PR  adicionando mais comandos.

# :mailbox: Reach me	
[![Linkedin Badge](https://img.shields.io/badge/-Valdecy%20Júnior-6633cc?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/valdecy-j%C3%BAnior-7558b9184/)](https://www.linkedin.com/in/valdecy-j%C3%BAnior-7558b9184/) 
[![Gmail Badge](https://img.shields.io/badge/-borgesjuniior@hotmail.com-6633cc?style=flat-square&logo=Gmail&logoColor=white&link=mailto:valdecyborgesjr@hotmail.com)](mailto:valdecyborgesjr@hotmail.com)

>This project was developed by **[Valdecy Júnior](https://www.linkedin.com/in/valdecy-j%C3%BAnior-7558b9184/)**
If it helped you, give it ⭐, it will help me too 😉


