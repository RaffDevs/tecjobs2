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

sql<BR>
CREATE TABLE usuario (
    id INT AUTO_INCREMENT PRIMARY KEY,<BR>
    login VARCHAR(50) UNIQUE NOT NULL,<BR>
    senha VARCHAR(255) NOT NULL<BR>
);<BR>

## Tabela `emprego`

sql
CREATE TABLE emprego (<BR>
    id INT AUTO_INCREMENT PRIMARY KEY,<BR>
    nome_empresa VARCHAR(100) NOT NULL,<BR>
    setor VARCHAR(100),<BR>
    localizacao VARCHAR(100),<BR>
    telefone VARCHAR(20),<BR>
    email VARCHAR(100)<BR>
);

## Tabela `vaga`

sql
CREATE TABLE vaga (<BR>
    id INT AUTO_INCREMENT PRIMARY KEY,<BR>
    titulo VARCHAR(100) NOT NULL,<BR>
    descricao TEXT NOT NULL,<BR>
    salario DECIMAL(10, 2),<BR>
    localizacao VARCHAR(100),<BR>
    requisitos TEXT,<BR>
    data_publicacao DATE,<BR>
    emprego_id INT,<BR>
    link VARCHAR(255),<BR>
    FOREIGN KEY (emprego_id) REFERENCES emprego(id)<BR>
);

## Conexão do banco

const mysql = require('mysql2');

const pool = mysql.createPool({<BR>
  host: 'mysqltrabalho.mysql.database.azure.com',<BR>
  user: 'arthur',<BR>
  password: '741258ar@',<BR>
  database: 'pi',<BR>
  port: 3306,<BR>
  waitForConnections: true,<BR>
  connectionLimit: 10,<BR>
  queueLimit: 0<BR>
});

module.exports = pool.promise();<BR>


### 2 - Documentação 📚

- [X] Criação do RUP do projeto
Link da documentação: [RUP PI TecJobs _ Entrega Final.pdf](https://github.com/user-attachments/files/15812266/RUP.PI.TecJobs._.Entrega.Final.pdf)

### 3 - Front-End 📄

Foi utlizado HTML, CSS, Javascript e Angular na criação da aplicação.

**Páginas:**

- Tela Inicial
- Tela Sobre Nós
- Tela Sobre Fatec Franca
- Tela Detalhamento da Vaga
- Tela de Cadastro de E-mail para Receber Novas Vagas

### 4 - Back-End 💻

Foi utilizado Node, JS e express para a criação do backend.
A Aplicação foi hospedada no render e faz uma conexão com o banco de dados azure, segue a imagem da documentação da api:
<img src="https://github.com/RaffDevs/tecjobs2/assets/136899628/d08dae68-722c-4983-80c0-63795b70ae95" alt="drawing" width="600"/>




