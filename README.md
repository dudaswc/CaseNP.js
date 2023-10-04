# CaseNP.js

Este repositório contém um exemplo de aplicação Node.js que se conecta a um servidor MySQL e oferece endpoints RESTful para realizar operações relacionadas a tabelas do banco de dados. 
O projeto inclui a criação de tabelas (Produtor, Propriedade e Usuario) e a implementação de um endpoint de login que verifica as credenciais no banco de dados.

Recursos e Tecnologias:
- Node.js: Plataforma de tempo de execução JavaScript
- MySQL: Sistema de gerenciamento de banco de dados
- Express.js: Framework para criar APIs RESTful
- mysql2: Pacote Node.js para conexão com bancos de dados MySQL

- Este projeto demonstra como criar uma aplicação Node.js que se conecta a um banco de dados MySQL e oferece serviços de autenticação básica e gerenciamento de tabelas.

- Aqui está uma descrição detalhada do que foi feito:

Importação das bibliotecas necessárias:

mysql2: É importado para estabelecer uma conexão com o servidor MySQL.
express: É utilizado para criar endpoints RESTful.
body-parser: É utilizado para analisar os corpos das requisições como JSON.

Criação de uma conexão com o servidor MySQL:

Uma conexão é criada com o servidor MySQL local (host: 'localhost').
As informações de usuário (user) e senha (password) são fornecidas para autenticar a conexão.
A base de dados (database) que será utilizada é especificada como 'niceplanet'.

Função para criar tabelas:

A função createTables é definida para criar três tabelas ('Produtor', 'Propriedade' e 'Usuario') no banco de dados.
Para cada tabela, uma query SQL CREATE TABLE é definida para criar a tabela com suas colunas.
As queries SQL são executadas usando connection.query para criar as tabelas no banco de dados.
Os erros são tratados e mensagens de sucesso são exibidas.

Conexão ao banco de dados e chamada da função createTables:

A conexão com o banco de dados é estabelecida usando connection.connect.
Se ocorrer um erro na conexão, uma mensagem de erro é exibida.
Se a conexão for bem-sucedida, a função createTables é chamada para criar as tabelas.

Configuração do servidor Express:

Um aplicativo Express é criado usando express().
O middleware body-parser é utilizado para analisar os corpos das requisições como JSON.

Endpoint de login:

Um endpoint POST /login é definido para lidar com operações de login.
Os dados de nome de usuário (nomeUsuario) e senha de usuário (senhaUsuario) são extraídos do corpo da requisição.
É feita uma verificação se os campos de nome e senha estão presentes na requisição.
Uma query SQL SELECT é usada para verificar se as credenciais são válidas no banco de dados.
A resposta depende do resultado da verificação: erro interno, credenciais inválidas ou login bem-sucedido.

Inicialização do servidor Express:

O servidor Express é iniciado usando app.listen na porta 3000.
Uma mensagem é exibida no console informando que o servidor está em execução na porta 3000.
Esse código cria um servidor Express que lida com operações de login e cria tabelas no banco de dados MySQL. 
  
