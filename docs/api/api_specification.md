# Especificação da API

## [cite_start]1. Autenticação e Autorização [cite: 156]

A autenticação será feita via token JWT, que deve ser enviado no cabeçalho `Authorization: Bearer <token>` em todas as requisições protegidas. Rotas de gerenciamento (ex: POST /books) serão autorizadas apenas para usuários com o papel 'BIBLIOTECARIO'.

## [cite_start]2. Endpoints Previstos [cite: 153]

### Autenticação
* `POST /auth/login`: Autentica um usuário e retorna um token.
* `POST /users`: Cadastra um novo usuário (leitor).

### Livros
* `GET /books`: Lista todos os livros do acervo. Permite filtros via query string (ex: `?search=`).
* `GET /books/{id}`: Obtém os detalhes de um livro específico.
* `POST /books`: Adiciona um novo livro ao acervo (Apenas Bibliotecário).
* `PUT /books/{id}`: Atualiza as informações de um livro (Apenas Bibliotecário).

### Empréstimos
* `POST /loans`: Registra um novo empréstimo (Apenas Bibliotecário).
* `PUT /loans/{id}/return`: Registra a devolução de um livro (Apenas Bibliotecário).
* `GET /users/{id}/loans`: Lista os empréstimos de um usuário específico.

## [cite_start]3. Parâmetros de Requisição e Formatos de Resposta [cite: 154, 155]

**Endpoint:** `POST /loans`
* **Parâmetros (Corpo da Requisição):**
    ```json
    {
      "userId": "uuid-do-leitor",
      "bookId": "uuid-do-livro"
    }
    ```
* **Resposta (201 Created):**
    ```json
    {
      "loanId": "uuid-do-emprestimo",
      "bookTitle": "O Pequeno Príncipe",
      "userName": "Nome do Leitor",
      "dueDate": "2025-10-13"
    }
    ```

## [cite_start]4. Exemplo de Chamada e Resposta [cite: 157]

**Requisição:** `GET /books?search=Saramago`
**Resposta (200 OK):**
```json
[
    {
        "bookId": "uuid-do-livro-1",
        "title": "Ensaio sobre a Cegueira",
        "author": "José Saramago",
        "status": "DISPONIVEL"
    },
    {
        "bookId": "uuid-do-livro-2",
        "title": "As Intermitências da Morte",
        "author": "José Saramago",
        "status": "EMPRESTADO"
    }
]