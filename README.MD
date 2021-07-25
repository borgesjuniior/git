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