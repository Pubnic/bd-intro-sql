# Aula de BD

## O que é um banco de dados
    O banco de dados é a organização e armazenamento de informações.

    É muito comum entre empresas, precisam guardar e organizar informações, e acessar
    posteriormente.

    Aplicação (Web/Mobile/Desktop) <-> API <-> BD

    Hoje existem diversas formas de 
    armazenar e organizar essas informações, como por exemplo,
    arquivos de texto, excel, banco de dados, etc.

    Alguns dos principais tipos de banco 
    de dados são os relacionais, que são organizados em tabelas, 
    e os não relacionais, que podem ser 
    organizados em JSON (texto). SQL / NoSQL

    Os bancos de dados relacionais são um conjunto 
    de dados organizados em tabelas, onde cada linha 
    representa um registro e cada coluna um campo.

    Nome(String) Idade(Int) BlabLa
    Vitor 27 BlaBla

    Cada coluna pode ter um tipo de dado, como por exemplo, 
    inteiro, texto, etc. A linguagem SQL é uma das linguagens 
    mais utilizadas para manipular bancos de dados relacionais.

    Eles são muito utilizados para: ecommerce, 
    sistemas de gestão, sistemas financeiros, etc.
        - Bancos Relacionais mais comuns
            - Oracle
            - MySQL
            - PostgreSQL
            - SQL Server
            - Outros
    
    Já os bancos de dados não relacionais são um conjunto de dados organizados em JSON, onde cada registro é um objeto. Cada objeto pode ter um conjunto de chaves e valores, como por exemplo, nome, idade, etc. A linguagem JSON é uma das linguagens mais utilizadas para manipular bancos de dados não relacionais. Eles são muito utilizados para: aplicações como aplicativos de mensagens, aplicativos de chat, aplicativos de música, etc.
        - Banco de dados não relacionais mais comuns
            - MongoDB
            - CouchDB
            - DynamoDB
            - Redis
            - Outros

## Table, column, row
    - Ex em Excel
    - Ex em json

## Tipos de Dados
    - String:
        - CHAR: caracteres, com tamanho fixo e podendo ter tamanho de 0 a 255 caracteres. Default 1
        - VARCHAR: texto, com tamanho variável e podendo ter tamanho de 0 a 65535 caracteres. Precisa ser definido o tamanho máximo (255)

    - Number
        - INT/INTEGER: inteiros, com tamanho fixo e podendo ser entre -2147483648 a 2147483647
        - BIGINT: inteiros, com tamanho fixo e podendo ser entre -9223372036854775808 a 9223372036854775807
        - FLOAT: números reais, podendo o decimal ter tamanho de 0 a 25 caracteres
        - DOUBLE: números reais, podendo o decimal ter tamanho de 25 a 53 caracteres
        - DECIMAL: números reais, podendo o decimal ter tamanho de 0 a 38 caracteres porém com maior precisão
    
    - Boolean
        - BOOLEAN: valores lógicos, podendo ser true ou false
    
    - Date & Time
        - DATE: data, podendo ser definida como dd/mm/yyyy
        - DATETIME: data e hora, podendo ser definida como dd/mm/yyyy hh:mm:ss
        - TIMESTAMP: 
        - TIME: hora, podendo ser definida como hh:mm:ss
        - YEAR: ano, podendo ser definido como yyyy

    - Primary Key (PK - Chave Primária)
        - É a chave primária de um registro, ou seja, o dado que identifica um objeto.
        - É uma chave primária única, ou seja, não pode haver mais de uma chave primária no mesmo registro.
        - Os principais tipos utilizados para identificar:
            - INT/INTEGER/BIGINT
            - VARCHAR
        - Podem ser definidas com o seguinte comportamento:
            - Auto Increment: quando um registro é inserido, o valor da chave primária é incrementado automaticamente
            - Não Auto Increment: quando um registro é inserido, o valor da chave primária é definido pelo usuário
    
    - Foreign Key (FK - Chave Estrangeira)
        - É a chave estrangeira de um registro, ou seja, o dado referente a PK de outro registro.
        - Com ela é possível referenciar um registro de outra tabela. Ex.: Um aluno tem uma chave estrangeira para o curso que ele estuda.

    - Relacionamentos
        - Tipos
            - Um para um: Define que um registro de uma tabela é relacionado com apenas um registro de outra tabela. Ex.: Um aluno tem uma matrícula, e essa não pode ter mais de um aluno. 1:1

            - Um para muitos: Define que um registro de uma tabela é relacionado com vários registros de outra tabela. Ex.: Um curso pode ter vários alunos e um aluno só pode ter um curso. 1:n / n:1

            - Muitos para muitos: Define que um registro de uma tabela é relacionado com vários registros de outra tabela. Ex.: Um professor pode ter vários alunos e um aluno pode ter vários professores. N:N

## UML
## SQL
    - Exemplos
        - Criar banco de dados
            - CREATE DATABASE nome_do_banco;
        - Criar tabela
            - CREATE TABLE nome_da_tabela (
                coluna1 tipo_da_coluna1,
                coluna2 VARCHAR(255),
                coluna3 INT,
                ...
                colunaN FLOAT,
            );
        - Criar coluna
            - ALTER TABLE nome_da_tabela ADD COLUMN nome_da_coluna tipo_da_coluna;
            - ALTER TABLE Aluno ADD COLUMN email VARCHAR(255);

        - Criar registro
            - INSERT INTO nome_da_tabela (coluna1, coluna2, coluna3, ..., colunaN) VALUES (valor1, valor2, valor3, ..., valorN);
            - INSERT INTO Aluno (nome, idade, email) VALUES ('João', 20, 'joao@email.com');

        - Consultar registro
            - SELECT * FROM nome_da_tabela;
            - SELECT * FROM Aluno;

        - Alterar registro
            - UPDATE nome_da_tabela SET coluna1 = valor1, coluna2 = valor2, ..., colunaN = valorN WHERE coluna1 = valor1;
            - UPDATE Aluno SET nome = 'João', idade = 20 WHERE id = 1;

        - Deletar registro
            - DELETE FROM nome_da_tabela WHERE coluna1 = valor1;
            - DELETE FROM Aluno WHERE id = 1;

        https://www.w3schools.com/sql/

## Object-Relational Mapping (ORM), em português, mapeamento objeto-relacional
    - É uma técnica para facilitar o desenvolvimento de aplicações que utilizam banco de dados relacionais, normalmente através de bibliotecas.
    - Principais ORMs no python:
        - SQLAlchemy
        - Django ORM

## Na zapay utilizamos o PostgreSQL como principal banco de dados.

## Formas de subir um BD
    - Instalando diretamente na máquina
    - Docker + Docker Compose

## Ferramentas para acessar e manipular um banco de dados Postgres
    - psql: comando para acessar o banco de dados
    - pgAdmin: interface web para acessar o banco de dados
