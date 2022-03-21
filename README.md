<h1 align="center">Conceitos do Node.js</h1>

## ⚡ Sobre o desafio

Essa será uma aplicação para gerenciar tarefas. Será permitida a criação de um usuário com name e username, bem como fazer o CRUD de todos:

- Criar um novo _todo_;
- Listar todos os _todos_;
- Alterar o `title` e `deadline` de um _todo_ existente;
- Marcar um _todo_ como feito;
- Excluir um _todo_;

Tudo isso para cada usuário em específico (o username será passado pelo header).

#

## 🚀 Rodando o projeto

```bash
# Clone este repositório
$ git clone https://github.com/lucasmfg7/conceitos-node-js-todos

# Acesse a pasta do projeto no terminal/cmd
$ cd conceitos-node-js-todos

# Instale as dependências e rode o projeto
$ yarn
$ yarn dev

# Rode os testes
$ yarn test
```

#

## 🪧 Rotas da aplicação

### POST `/users`

A rota deve receber `name`, e `username` dentro do corpo da requisição. Ao cadastrar um novo usuário, ele deve ser armazenado dentro de um objeto no seguinte formato:

```javascript
{
	id: 'uuid', // precisa ser um uuid
	name: 'Lucas Fernandes',
	username: 'lucasmfg7',
	todos: []
}
```

### GET `/todos`

A rota deve receber `title` e `deadline` dentro do corpo da requisição e, uma propriedade `username` contendo o username do usuário dentro do header da requisição. Ao criar um novo todo, ele deve ser armazenada dentro da lista `todos` do usuário que está criando essa tarefa. Cada tarefa deverá estar no seguinte formato:

```javascript
{
	id: 'uuid', // precisa ser um uuid
	title: 'Nome da tarefa',
	done: false,
	deadline: '2021-02-27T00:00:00.000Z',
	created_at: '2021-02-22T00:00:00.000Z'
}
```

### PUT `/todos/:id`

A rota deve receber, pelo header da requisição, uma propriedade `username` contendo o username do usuário e receber as propriedades `title` e `deadline` dentro do corpo. É preciso alterar apenas o `title` e o `deadline` da tarefa que possua o id igual ao id presente nos parâmetros da rota.

### PATCH `/todos/:id/done`

A rota deve receber, pelo header da requisição, uma propriedade `username` contendo o `username` do usuário e alterar a propriedade `done` para `true` no todo que possuir um `id` igual ao `id` presente nos parâmetros da rota.

### DELETE `/todos/:id`

A rota deve receber, pelo header da requisição, uma propriedade `username` contendo o username do usuário e excluir o todo que possuir um `id` igual ao `id` presente nos parâmetros da rota.
