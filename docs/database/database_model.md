# [cite_start]Modelo de Dados [cite: 148]

## [cite_start]1. Descrição das Entidades e Relacionamentos [cite: 149]

O modelo de dados é composto por três entidades principais: `Users`, `Books` e `Loans` (empréstimos).
* Um `User` (usuário) pode ser um Leitor ou um Bibliotecário.
* Um `Book` (livro) pertence ao acervo da biblioteca.
* Um `Loan` (empréstimo) representa a relação entre um `User` (leitor) e um `Book` (livro), contendo datas e status do empréstimo. Um usuário pode ter vários empréstimos e um livro pode ser emprestado várias vezes (mas apenas uma vez por vez).

## [cite_start]2. Diagrama ER [cite: 150]

` ` `
+-----------+       +-----------+       +-----------+
|   Users   |       |   Loans   |       |   Books   |
+-----------+1    N +-----------+ N    1+-----------+
| user_id (PK)|-----| loan_id (PK) |-----| book_id (PK)|
| name      |       | user_id (FK) |       | title     |
| email     |       | book_id (FK) |       | author    |
| password  |       | loan_date    |       | status    |
| role      |       | due_date     |       +-----------+
+-----------+       | return_date  |
                    +-----------+
` ` `

## [cite_start]3. Dicionário de Dados [cite: 151]

**Tabela: Users**
| Coluna | Tipo | Descrição |
| :--- | :--- | :--- |
| user_id | UUID | Chave Primária |
| name | VARCHAR(255) | Nome completo do usuário |
| email | VARCHAR(255) | E-mail de login (único) |
| password | VARCHAR(255) | Senha criptografada |
| role | VARCHAR(50) | Papel do usuário ('LEITOR', 'BIBLIotecario') |

**Tabela: Books**
| Coluna | Tipo | Descrição |
| :--- | :--- | :--- |
| book_id | UUID | Chave Primária |
| title | VARCHAR(255) | Título do livro |
| author | VARCHAR(255) | Autor do livro |
| status | VARCHAR(50) | Status do livro ('DISPONIVEL', 'EMPRESTADO') |

**Tabela: Loans**
| Coluna | Tipo | Descrição |
| :--- | :--- | :--- |
| loan_id | UUID | Chave Primária |
| user_id | UUID | Chave Estrangeira para `Users` |
| book_id | UUID | Chave Estrangeira para `Books` |
| loan_date | DATE | Data em que o empréstimo foi realizado |
| due_date | DATE | Data prevista para devolução |
| return_date| DATE | Data em que a devolução foi efetuada (opcional) |