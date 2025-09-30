# Documentação da Arquitetura do Sistema

## [cite_start]1. Descrição da Arquitetura [cite: 139]

A arquitetura escolhida é uma **Arquitetura Monolítica com API RESTful**. Esta abordagem foi selecionada pela simplicidade e rapidez no desenvolvimento, sendo ideal para o escopo definido do projeto. O sistema terá um Backend único que servirá tanto a aplicação Web (cliente do bibliotecário) quanto o aplicativo Mobile (cliente do leitor).

## [cite_start]2. Componentes do Sistema [cite: 141]

1.  **Frontend Web (Admin):** Uma Single-Page Application (SPA) desenvolvida em React.js, consumindo a API do backend. Responsável pelas interfaces de gerenciamento do bibliotecário.
2.  **Frontend Mobile:** Um aplicativo híbrido desenvolvido em React Native para Android e iOS. Responsável pelas interfaces de consulta e acompanhamento para o leitor.
3.  **Backend (API Monolítica):** Uma aplicação em Node.js com o framework Express.js. Será responsável por toda a regra de negócio, autenticação e comunicação com o banco de dados.
4.  **Banco de Dados:** Um banco de dados relacional PostgreSQL para persistir os dados de usuários, livros e empréstimos.

## [cite_start]3. Padrões Arquiteturais Utilizados [cite: 142]

* **API RESTful:** Padrão utilizado para a comunicação entre o frontend e o backend, utilizando os verbos HTTP (GET, POST, PUT, DELETE) para manipulação de recursos.
* **MVC (Model-View-Controller):** O backend será estruturado seguindo este padrão para separar as responsabilidades entre o modelo de dados, as regras de negócio (controller) e a camada de resposta (view/JSON).

## [cite_start]4. Diagrama de Arquitetura [cite: 143]

` ` `
+----------------+      +------------------+
|   Aplicativo   |      |   Aplicação Web  |
|   Mobile       |      | (Bibliotecário)  |
| (React Native) |      |    (React.js)    |
+----------------+      +------------------+
        |                       |
        +----------+------------+
                   |
     +---------------------------+
     |   API RESTful (Backend)   |
     |        (Node.js)          |
     +---------------------------+
                   |
           +----------------+
           | Banco de Dados |
           | (PostgreSQL)   |
           +----------------+
` ` `

## [cite_start]5. Decisões Técnicas e Justificativas [cite: 144]

* **Monólito vs. Microsserviços:** A abordagem monolítica foi escolhida por ser mais simples de desenvolver, implantar e manter para uma aplicação de pequeno a médio porte como a "Páginas do Bairro", evitando a complexidade de uma arquitetura distribuída.
* **React e React Native:** A escolha permite reutilizar conhecimento e, potencialmente, parte da lógica de negócio entre as plataformas web e mobile.
* **PostgreSQL:** Selecionado por sua robustez, confiabilidade e por ser um padrão de mercado consolidado para bancos de dados relacionais.
* **Autenticação JWT (JSON Web Token):** Será utilizado para a gestão de sessões de forma stateless, simplificando a autenticação na API para múltiplos clientes (web e mobile).