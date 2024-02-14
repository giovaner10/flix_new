# Flix New

Conectando amantes de filmes.

## Índice

- [Visão Geral](#visão-geral)
- [Funcionalidades](#funcionalidades)
- [Estrutura do Banco de Dados](#estrutura-do-banco-de-dados)
- [Imagens do projeto](#imagens-do-projeto)



## Visão Geral
#### Tecnologias empregadas
 <p align="center">

![php](https://img.shields.io/badge/php-00000F?style=for-the-badge&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white)
![html5](https://img.shields.io/badge/-HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![css3](https://img.shields.io/badge/-CSS3-1572B6?style=flat&logo=css3&logoColor=white)
  </p>
O projeto oferece uma plataforma na qual os usuários podem interagir com filmes. Eles podem criar uma conta, fazer login, deslogar, editar seu perfil e realizar várias ações relacionadas a filmes.

## Funcionalidades

- **Autenticação:**
  - O usuário pode criar uma conta.
  - O usuário pode fazer login.
  - O usuário pode deslogar.

- **Perfil do Usuário:**
  - O usuário pode editar seu perfil.
  - O usuário tem uma tela de perfil.

- **Filmes:**
  - O usuário pode adicionar um filme.
  - O usuário pode editar um filme (apenas se tiver adicionado).
  - O usuário pode apagar um filme (apenas se tiver adicionado).

- **Interação com Filmes:**
  - O usuário pode avaliar um filme (apenas se não o tiver adicionado).
  - O usuário pode comentar em um filme (apenas se não o tiver adicionado).
  - O usuário terá uma dashboard com todos os filmes que adicionou.
  - Deverá existir uma tela para a visualização detalhada dos filmes.

## Estrutura do Banco de Dados

O projeto utiliza um banco de dados para armazenar informações essenciais. Abaixo está a estrutura das tabelas no banco de dados.

![Estrutura do banco de dados.](https://github.com/giovaner10/flix_new/blob/main/img/proj/db.png)



```sql
CREATE DATABASE moviestar;
```

### Tabela `users`

```sql
CREATE TABLE users (
    id INT(11) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    lastname VARCHAR(100),
    email VARCHAR(100),
    password VARCHAR(100),
    image VARCHAR(300),
    token VARCHAR(300),
    bio TEXT 
);
```
- **id:** Identificador único do usuário.
- **name:** Nome do usuário.
- **lastname:** Sobrenome do usuário.
- **email:** Endereço de e-mail do usuário.
- **password:** Senha do usuário.
- **image:** URL da imagem de perfil do usuário.
- **token:** Token para autenticação.
- **bio:** Biografia do usuário.


```sql
CREATE TABLE movies (
    id INT(11) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(100),
    length VARCHAR(100),
    category VARCHAR(100),
    trailer VARCHAR(100),
    image VARCHAR(300),
    description TEXT,
    users_id INT(11) UNSIGNED,
    FOREIGN KEY(users_id) REFERENCES users(id)
);
```
- **id:** Identificador único do filme.
- **title:** Título do filme.
- **length:** Duração do filme.
- **category:** Categoria do filme.
- **trailer:** URL do trailer do filme.
- **image:** URL da imagem do filme.
- **description:** Descrição do filme.
- **users_id:** Identificador do usuário que adicionou o filme.


```sql
CREATE TABLE reviews (
    id INT(11) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    rating INT,
    review TEXT,
    users_id INT(11) UNSIGNED,
    movies_id INT(11) UNSIGNED,
    FOREIGN KEY(users_id) REFERENCES users(id),
    FOREIGN KEY(movies_id) REFERENCES movies(id)
);
```
- **id:** Identificador único da avaliação.
- **rating:** Classificação da avaliação.
- **review:** Comentário da avaliação.
- **users_id:** Identificador do usuário que fez a avaliação.
- **movies_id:** Identificador do filme avaliado.


## Imagens do projeto


>Home
![Funcionalidade Principal](https://github.com/giovaner10/flix_new/blob/main/img/proj/img1.png)


>Home continuação por categorias
![Funcionalidade Principal](https://github.com/giovaner10/flix_new/blob/main/img/proj/img2.png)


>Tela de busca
![Funcionalidade Principal](https://github.com/giovaner10/flix_new/blob/main/img/proj/img3.png)


>Tela do filme
![Funcionalidade Principal](https://github.com/giovaner10/flix_new/blob/main/img/proj/img4.png)

>Dashboard com os meus filmes
![Funcionalidade Principal](https://github.com/giovaner10/flix_new/blob/main/img/proj/img8.png)


>Avaliação com nota e comentario do filme
![Funcionalidade Principal](https://github.com/giovaner10/flix_new/blob/main/img/proj/img5.png)


>Tela de perfil do usuario + edição
![Funcionalidade Principal](https://github.com/giovaner10/flix_new/blob/main/img/proj/img6.png)
