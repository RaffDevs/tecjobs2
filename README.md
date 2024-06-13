# 🔹 TecJobs - PI/DSM 2° Período 💻🔹

Repositório do trabalho de PI dos estudantes do 2° período do curso de Desenvolvimento de Software Multiplataforma da Fatec Franca. O projeto em questão se trata de um portal de estágios para os alunos da universidade.

**Obs: A API está hospedada no Render, no plano gratuito. Por padrão, a plataforma deixa o serviço "dormindo" quando não está sendo usado e, quando solicitado, "desperta" o serviço novamente. Dado isso, caso ao acessar, as vagas não sejam carregadas ou demorem, é necessário recarregar a página para que a requisição possa reativar o serviço.**

Link: [TecJobs](https://tecjobs-web.onrender.com/index.html)

<div>
  <img src="https://github.com/victorsoaresho/Colinhas-Nets/assets/136899628/4d8dc211-9312-423a-9250-23164d381fd9" alt="drawing" width="600"/>
  <img src="https://github.com/victorsoaresho/Colinhas-Nets/assets/136899628/bca35b6b-7eff-4f5c-972e-e9d37dba4e59" alt="drawing" width="600"/>
  <img src="https://github.com/victorsoaresho/Colinhas-Nets/assets/136899628/f067b8de-d853-40f8-b369-2d14f9797c10" alt="drawing" width="600"/>
  <img src="https://github.com/victorsoaresho/Colinhas-Nets/assets/136899628/0ac50183-ee75-4c49-9261-02a56b63a887" alt="drawing" width="600"/>
  <img src="https://github.com/victorsoaresho/Colinhas-Nets/assets/136899628/687bdd53-8d04-489a-9177-6b1bb58c820f" alt="drawing" width="600"/>
  <img src="https://github.com/victorsoaresho/Colinhas-Nets/assets/136899628/38bb01ed-4b3d-4cb9-a265-ed51387eb890" alt="drawing" width="600"/>
  <img src="https://github.com/victorsoaresho/Colinhas-Nets/assets/136899628/23d19ac2-07e2-4c09-adf1-bc92e2bfe2c5" alt="drawing" width="600"/>
</div>

## Etapas do projeto:

- **Gestão do Projeto:** Rafael
- **Banco de Dados Relacional:** Arthur
- **Documentação e Backend:** Victor
- **Front-End:** Samuel

## Criando o projeto:

### 1 - Banco de Dados Relacional 🎨

Criação do banco de dados usando um banco do Microsoft Azure MySQL com as tabelas de vaga, emprego e usuários.

## Tabela `usuario`

sql
CREATE TABLE usuario (
    id INT AUTO_INCREMENT PRIMARY KEY,
    login VARCHAR(50) UNIQUE NOT NULL,
    senha VARCHAR(255) NOT NULL
);

## Tabela `emprego`

sql
CREATE TABLE emprego (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome_empresa VARCHAR(100) NOT NULL,
    setor VARCHAR(100),
    localizacao VARCHAR(100),
    telefone VARCHAR(20),
    email VARCHAR(100)
);

## Tabela `vaga`

sql
CREATE TABLE vaga (
    id INT AUTO_INCREMENT PRIMARY KEY,
    titulo VARCHAR(100) NOT NULL,
    descricao TEXT NOT NULL,
    salario DECIMAL(10, 2),
    localizacao VARCHAR(100),
    requisitos TEXT,
    data_publicacao DATE,
    emprego_id INT,
    link VARCHAR(255),
    FOREIGN KEY (emprego_id) REFERENCES emprego(id)
);

## Conexão do banco

const mysql = require('mysql2');

const pool = mysql.createPool({
  host: 'mysqltrabalho.mysql.database.azure.com',
  user: 'arthur',
  password: '741258ar@',
  database: 'pi',
  port: 3306,
  waitForConnections: true,
  connectionLimit: 10,
  queueLimit: 0
});

module.exports = pool.promise();


### 2 - Documentação 📚

- [X] Criação do RUP do projeto

### 3 - Front-End 📄

- [X] Criação do HTML das páginas
- [X] Criação do CSS das páginas
- [X] Criação do JS das páginas

**Páginas:**

- Tela Inicial
- Tela Sobre Nós
- Tela Sobre Fatec Franca
- Tela Detalhamento da Vaga
- Tela de Cadastro de E-mail para Receber Novas Vagas

### 4 - Back-End 💻

- [X] Implementar integração com API
- [X] CRUD Backend (Node)
- [X] Deploy no Render


