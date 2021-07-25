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

```bash
  git add .
```
Para realmente comfirmar as mudanças (fazer um commit) use:

```bash
  git commit -m "Comentários das alterações"
```
