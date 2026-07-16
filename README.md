# Todo List - Vue 3

Aplicação de gerenciamento de tarefas desenvolvida com **Vue 3**, **Vite**, **Tailwind CSS** e **json-server**.

O projeto permite criar, editar, concluir e excluir tarefas, utilizando uma API REST simulada para persistência dos dados.

## 🚀 Tecnologias utilizadas

- [Vue 3](https://vuejs.org/)
- [Vite](https://vite.dev/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Axios](https://axios-http.com/)
- [json-server](https://github.com/typicode/json-server)
- JavaScript (ES6+)

## 📌 Funcionalidades

✅ Listagem de tarefas
✅ Adição de novas tarefas
✅ Edição de tarefas diretamente no campo de texto
✅ Concluir/desmarcar tarefas
✅ Alteração visual de tarefas concluídas
✅ Exclusão de tarefas
✅ Persistência dos dados via API REST
✅ Interface responsiva com Tailwind CSS

## 📂 Estrutura do projeto

```
Todo-list/
│
├── api/
│   └── database.json       # Banco de dados simulado (json-server)
│
├── src/
│   ├── components/
│   │   ├── TodoList.vue
│   │   ├── TodoFormAdd.vue
│   │   ├── TodoItems.vue
│   │   ├── TodoItem.vue
│   │   ├── TodoEmpty.vue
│   │   └── TodoSpinner.vue
│   │
│   ├── services/
│   │   └── api.js          # Configuração do Axios
│   │
│   ├── App.vue
│   └── main.js
│
├── package.json
└── vite.config.js
```

## ⚙️ Instalação

Clone o repositório:

```bash
git clone https://github.com/seu-usuario/todo-list.git
```

Entre na pasta do projeto:

```bash
cd todo-list
```

Instale as dependências:

```bash
npm install
```

## ▶️ Executando o projeto

Execute o frontend:

```bash
npm run dev
```

Execute a API fake:

```bash
npm run server
```

A aplicação estará disponível em:

```
http://localhost:5173
```

A API estará disponível em:

```
http://localhost:3000
```

## 🔌 Endpoints da API

### Listar tarefas

```
GET /todos
```

### Criar tarefa

```
POST /todos
```

Exemplo:

```json
{
  "title": "Estudar Vue",
  "completed": false
}
```

### Atualizar tarefa

```
PUT /todos/:id
```

### Excluir tarefa

```
DELETE /todos/:id
```

## 🖼️ Preview

![Todo List Preview](./screenshots/todo-list.gif)

## 📝 Aprendizados

Este projeto foi desenvolvido para praticar:

- Componentização no Vue 3
- Composition API (`script setup`)
- Comunicação entre componentes com eventos
- Consumo de APIs REST com Axios
- Gerenciamento de estado local
- Estilização com Tailwind CSS

## 📄 Licença

Este projeto está sob a licença MIT.

---

Desenvolvido por **Ivan Henriques**
Baseado no projeto do Professor Tiago Matos
