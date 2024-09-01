# BiblioTech
![nv1](https://github.com/user-attachments/assets/9341e233-a0f0-4dab-9d63-ad234093d283)

## Funcionalidades
- Tipos de usuários do sistema: Usuário administrativo e usuário comum.
- Permite que o usuário administrador faça inserções, consultas, alterações e exclusões de livros.
- Permite que o usuário normalmente realize consultas por livros e visualize as páginas "sobre" e "ajuda".
- Permite que usuários cadastrados diretamente pela aplicação visualizem apenas a página destinada à consulta de livros.
- Permite que usuários cadastrados como administradores diretamente no banco de dados possam visualizar uma página de gerenciamento.

## Visualização do usuário

![nv2](https://github.com/user-attachments/assets/fed9d140-a526-420a-9ca7-3d0c6a412113)

## Visualização do administrador

![nv3](https://github.com/user-attachments/assets/5b037551-a1ad-4f7b-b7a7-6ff16ee1c62c)

## Página de login

![nv4](https://github.com/user-attachments/assets/2fd14843-7e64-40d8-b536-2edde44915e6)

## Página de cadastro

![nv5](https://github.com/user-attachments/assets/fb1e77d2-00ad-41a2-861e-d732caa929d1)

## Instruções
- Baixe o aplicativo do GitHub e execute o IDE de sua preferência (IDEs testados: IntelliJ e NetBeans).
- Caso não queira criar um banco de dados, foi disponibilizado dentro da aplicação, uma conexão com um banco de dados já pronto para uso, hospedado em nuvem pelo site Tembo ( Tembo ).
- Caso queira criar um banco de dados local: Execute as instruções SQL no pgAdmin 4, uma ferramenta de administração e desenvolvimento para bancos de dados PostgreSQL.
- Dentro do projeto aberto na IDE, verifique se o arquivo BancoD.propertiescontém as informações que você precisa com o banco de dados criado localmente.
- Caso ocorra algum erro na execução, verifique se o PostgreSQL JDBC Driver foi inserido corretamente no projeto e se as configurações de conexão (URL, usuário, senha, etc.) estão corretas.

## Estrutura do Banco de Dados
Tabela:disponivel
Armazena informações sobre livros disponíveis na biblioteca.

## Campos:

- id_livro (INTEGER, PRIMARY KEY, NOT NULL): Identificador único para cada livro. Este campo é gerado automaticamente.
- titulo (VARCHAR(255), NOT NULL): Título do livro.
- autor (VARCHAR(150), NOT NULL): Autor do livro.
- editora (VARCHAR(255), NOT NULL): Editora do livro.
- genero (VARCHAR(50)): Gênero do livro.
- prateleira (VARCHAR(10), NOT NULL): Localização física do livro na prateleira.
- quantidade (INTEIRO): quantidade disponível do livro.
- corredor (VARCHAR(10), NOT NULL): Corredor onde o livro está localizado.
## Tabela:login
Armazene informações de login para usuários normais.

## Campos:

- id (INTEGER, PRIMARY KEY, NOT NULL): Identificador único para cada usuário. Este campo é gerado automaticamente.
= nome (VARCHAR(50), NOT NULL): Nome do usuário.
- email (VARCHAR(70), NOT NULL, UNIQUE): Endereço de e-mail do usuário. Deve ser único na tabela.
- senha (VARCHAR(50), NOT NULL): Senha do usuário.
## Tabela:loginadmin
Armazene informações de login para administradores.

## Campos:

- id (INTEGER, PRIMARY KEY, NOT NULL): Identificador único para cada administrador. Este campo é gerado automaticamente.
- nome (VARCHAR(100), NOT NULL): Nome do administrador.
- email (VARCHAR(100), NOT NULL, UNIQUE): Endereço de e-mail do administrador. Deve ser único na tabela.
- senha (VARCHAR(255), NOT NULL): Senha do administrador.
  
## Exemplo de Criação da Tabela

```java
CREATE TABLE disponivel (
    id_livro SERIAL PRIMARY KEY,
    titulo VARCHAR(255) NOT NULL,
    autor VARCHAR(150) NOT NULL,
    editora VARCHAR(255) NOT NULL,
    genero VARCHAR(50),
    prateleira VARCHAR(10) NOT NULL,
    quantidade INTEGER,
    corredor VARCHAR(10) NOT NULL
);

CREATE TABLE login (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(50) NOT NULL,
    email VARCHAR(70) NOT NULL UNIQUE,
    senha VARCHAR(50) NOT NULL
);

CREATE TABLE loginadmin (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    senha VARCHAR(255) NOT NULL
);

-- Precisa-se inserir um administrador para poder logar na aplicação, deve conter "@admin.com"
-- Segue o exemplo abaixo:

INSERT INTO loginadmin (nome, email, senha)
VALUES ('Administrador', 'administrador@admin.com', 'senhaSegura123'); 

```
Usuário administrativo disponibilizado caso decida utilizar o banco de dados hospedado no servidor pelo Tembo:
" admin@admin.com " e a senha é: "123"

## Links das aplicações utilizadas no projeto
- [NetBeans](https://netbeans.apache.org/front/main/download/index.html)
- [PostgreSQL](https://www.postgresql.org/download/)
- [Tembo](https://tembo.io/)
- [DBeaver](https://dbeaver.io/)


