# Documento de Requisitos

## [cite_start]1. Perfis de Usuários [cite: 137]

* **Leitor:** Membro da comunidade que utiliza a biblioteca. Deseja consultar o acervo e gerenciar seus empréstimos de forma simples pelo celular.
* **Bibliotecário:** Responsável pela gestão da biblioteca. Precisa de uma ferramenta web para organizar o acervo de livros, cadastrar novos leitores e controlar os empréstimos.

## [cite_start]2. Requisitos Funcionais (RF) [cite: 134]

* **RF01:** O sistema deve permitir o cadastro de usuários com os perfis de Leitor e Bibliotecário.
* **RF02:** O sistema deve permitir a autenticação de usuários através de e-mail e senha.
* **RF03 (Bibliotecário):** O Bibliotecário deve poder cadastrar, visualizar, editar e excluir livros do acervo.
* **RF04 (Bibliotecário):** O Bibliotecário deve poder registrar um novo empréstimo de livro para um leitor.
* **RF05 (Bibliotecário):** O Bibliotecário deve poder registrar a devolução de um livro.
* **RF06 (Leitor):** O Leitor deve poder buscar por livros no acervo através do título, autor ou gênero.
* **RF07 (Leitor):** O Leitor deve poder visualizar os detalhes de um livro, incluindo sua sinopse e status (disponível/emprestado).
* **RF08 (Leitor):** O Leitor deve poder visualizar seu histórico de empréstimos (atuais e passados).

## [cite_start]3. Requisitos Não-Funcionais (RNF) [cite: 135]

* **RNF01:** A plataforma web deve ser compatível com os principais navegadores (Chrome, Firefox, Safari).
* **RNF02:** O aplicativo móvel deve ser compatível com sistemas Android e iOS.
* **RNF03:** O tempo de resposta para as buscas no acervo não deve exceder 2 segundos.
* **RNF04:** Os dados dos usuários devem ser armazenados de forma segura.
* **RNF05:** A interface deve ser intuitiva e acessível para usuários com pouca familiaridade com tecnologia.

## [cite_start]4. Histórias de Usuário [cite: 136]

* **HU01 (Leitor):** "Como um leitor, eu quero buscar por um livro pelo nome do autor para encontrar outras obras dele disponíveis na biblioteca."
* **HU02 (Leitor):** "Como um leitor, eu quero ver a lista dos livros que peguei emprestado para saber quando preciso devolvê-los."
* **HU03 (Bibliotecário):** "Como bibliotecário, eu quero cadastrar um novo livro que recebemos de doação informando título, autor e capa, para que ele apareça no acervo digital."