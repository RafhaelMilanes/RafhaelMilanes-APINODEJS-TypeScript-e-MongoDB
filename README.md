# API de Gerenciamento de Clientes com Fastify, TypeScript e Prisma

Este projeto consiste em uma API de gerenciamento de clientes desenvolvida com Node.js, Fastify, TypeScript e Prisma. A API permite cadastrar novos clientes, listar todos os clientes cadastrados e deletar clientes com base em seus IDs.

## Conteúdos

- [Controllers](#controllers)
- [Services](#services)
- [Routes](#routes)
- [Server](#server)
- [Instalação](#instalação)
- [Uso](#uso)
- [Contribuindo](#contribuindo)
- [Licença](#licença)

## Controllers

Os controllers são responsáveis por receber as requisições HTTP, chamar os serviços correspondentes e enviar as respostas adequadas.

### `CreateCustomerController`

- Rota: `POST /customer`
- Método: `handle(request, reply)`
  - Recebe nome e email do corpo da requisição.
  - Chama o serviço `CreateCustomerService` para cadastrar um novo cliente.
  - Retorna o cliente cadastrado como resposta.

### `DeleteCustomerController`

- Rota: `DELETE /customer`
- Método: `handle(request, reply)`
  - Recebe o ID do cliente a ser deletado dos parâmetros da consulta.
  - Chama o serviço `DeleteCustomerService` para deletar o cliente.
  - Retorna uma mensagem de sucesso como resposta.

### `ListCustomersController`

- Rota: `GET /customers`
- Método: `handle(request, reply)`
  - Chama o serviço `ListCustomersServices` para listar todos os clientes cadastrados.
  - Retorna a lista de clientes como resposta.

## Services

Os serviços são responsáveis por executar as operações de negócio da aplicação, como criar, deletar e listar clientes.

### `CreateCustomerService`

- Método: `execute({ name, email })`
  - Valida os campos `name` e `email`.
  - Cadastra um novo cliente no banco de dados com status ativo.
  - Retorna o cliente cadastrado.

### `DeleteCustomerService`

- Método: `execute({ id })`
  - Valida o ID do cliente.
  - Verifica se o cliente existe no banco de dados.
  - Deleta o cliente do banco de dados.
  - Retorna uma mensagem de sucesso.

### `ListCustomersServices`

- Método: `execute()`
  - Lista todos os clientes cadastrados no banco de dados.
  - Retorna a lista de clientes.

## Routes

As rotas definem os endpoints da API e direcionam as requisições para os controllers correspondentes.

## Server

O servidor é responsável por configurar e iniciar a aplicação Fastify, registrando os plugins, rotas e tratando erros.

## Instalação

1. Clone o repositório:

```bash
git clone https://github.com/RafhaelMilanes/APINODEJS-TypeScript-e-MongoDB
```

2. Instale as dependências:
```bash
cd backend
npm install

```

## Uso

Para iniciar o servidor, execute o seguinte comando:

```
npm run dev

```
O servidor estará acessível em http://localhost:3333.

## Conhecimento Adquirido

Durante o desenvolvimento deste projeto, adquiri conhecimento em:

- Configuração e uso do framework Fastify para criação de APIs em Node.js.
- Implementação de controllers para lidar com requisições HTTP.
- Organização e separação de responsabilidades utilizando serviços para lógica de negócio.
- Utilização do Prisma como ORM para interação com o banco de dados MongoDB.
- Desenvolvimento de aplicações usando TypeScript para tipagem estática e melhor manutenção do código.

Este projeto me proporcionou uma compreensão mais profunda sobre o desenvolvimento de APIs RESTful, boas práticas de programação e a importância da estruturação e organização do código-fonte.