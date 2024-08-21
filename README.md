# To Do API Go

Este projeto é uma API simples para gerenciar tarefas usando Go e o pacote `gorilla/mux`. A API permite criar, ler, atualizar e excluir tarefas.

## Instalação

1. Clone o repositório:

   ```sh
   git clone https://github.com/lualbertoni/ToDo-API-Go.git
   cd ToDo-API-Go
   ```

2. Instale as dependências:
   ```sh
   go mod tidy
   ```

## Execução

Para executar o servidor, use o comando:

```sh
go run main.go
```

O servidor estará disponível em `http://localhost:8000`.

## Endpoints

### Listar Todas as Tarefas

- **Método:** GET
- **Endpoint:** `/tasks`
- **Resposta:** Lista de tarefas em formato JSON.

### Obter Tarefa por ID

- **Método:** GET
- **Endpoint:** `/tasks/{id}`
- **Parâmetros:** `id` (ID da tarefa)
- **Resposta:** Tarefa em formato JSON ou erro 404 se a tarefa não for encontrada.

### Criar Nova Tarefa

- **Método:** POST
- **Endpoint:** `/tasks`
- **Corpo da Requisição:**
  ```json
  {
    "title": "Título da Tarefa",
    "status": "pendente"
  }
  ```
- **Resposta:** Tarefa criada em formato JSON.

### Atualizar Tarefa

- **Método:** PUT
- **Endpoint:** `/tasks/{id}`
- **Parâmetros:** `id` (ID da tarefa)
- **Corpo da Requisição:**
  ```json
  {
    "title": "Novo Título",
    "status": "andamento"
  }
  ```
- **Resposta:** Tarefa atualizada em formato JSON ou erro 404 se a tarefa não for encontrada.

### Excluir Tarefa

- **Método:** DELETE
- **Endpoint:** `/tasks/{id}`
- **Parâmetros:** `id` (ID da tarefa)
- **Resposta:** Lista de tarefas após a exclusão em formato JSON.

## Validação de Status

Os status válidos para uma tarefa são:

- `pendente`
- `descartada`
- `andamento`
- `realizada`

Qualquer outro status retornará um erro 400 (Status inválido).
