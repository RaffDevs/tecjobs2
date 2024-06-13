# 🔹 TecJobs - PI/DSM 2° Período 💻🔹

Repositório do trabalho de PI dos estudantes do 2° período do curso de Desenvolvimento de Software Multiplataforma da Fatec Franca. O projeto em questão se trata de um portal de estágios para os alunos da universidade.

**Obs: A API está hospedada no Render, no plano gratuito. Por padrão, a plataforma deixa o serviço "dormindo" quando não está sendo usado e, quando solicitado, "desperta" o serviço novamente. Dado isso, caso ao acessar, as vagas não sejam carregadas ou demorem, é necessário recarregar a página para que a requisição possa reativar o serviço.**

Link: [TecJobs](https://tecjobs2.onrender.com)

<div>


![WhatsApp Image 2024-06-12 at 23 37 15](https://github.com/RaffDevs/tecjobs2/assets/56967435/cddfc6b0-f2ab-4e9d-a148-201826e4e99d)
![WhatsApp Image 2024-06-12 at 23 37 15 (1)](https://github.com/RaffDevs/tecjobs2/assets/56967435/0cbee467-ed33-4bfd-bbed-51caa779d882)
![WhatsApp Image 2024-06-12 at 23 37 15 (2)](https://github.com/RaffDevs/tecjobs2/assets/56967435/89c894e7-829b-42b9-8fa2-7926e0fa1a8b)
![WhatsApp Image 2024-06-12 at 23 37 15 (3)](https://github.com/RaffDevs/tecjobs2/assets/56967435/b5be854a-ff9f-4955-a751-a9179c37fb76)
![WhatsApp Image 2024-06-12 at 23 37 14](https://github.com/RaffDevs/tecjobs2/assets/56967435/29644608-fe19-4a6e-bc9d-48637b888580)
![WhatsApp Image 2024-06-12 at 23 37 14 (1)](https://github.com/RaffDevs/tecjobs2/assets/56967435/d8eadb72-9d48-4484-bd8c-1dba688df886)
![WhatsApp Image 2024-06-12 at 23 37 14 (2)](https://github.com/RaffDevs/tecjobs2/assets/56967435/486e8f1e-8bcd-4054-90e8-4745a28b96ff)


https://github.com/RaffDevs/tecjobs2/assets/56967435/eef6f06b-a9bd-415e-a63e-cb663d669003


  <img src="https://github.com/RaffDevs/tecjobs2/assets/136899628/19bb6a6b-657c-4972-950d-7a46ebfeb9de" alt="drawing" width="600"/>
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

```sql
CREATE TABLE usuario (
    id INT AUTO_INCREMENT PRIMARY KEY,<BR>
    login VARCHAR(50) UNIQUE NOT NULL,<BR>
    senha VARCHAR(255) NOT NULL<BR>
);

```
## Tabela `emprego`

```sql
CREATE TABLE emprego (<BR>
    id INT AUTO_INCREMENT PRIMARY KEY,<BR>
    nome_empresa VARCHAR(100) NOT NULL,<BR>
    setor VARCHAR(100),<BR>
    localizacao VARCHAR(100),<BR>
    telefone VARCHAR(20),<BR>
    email VARCHAR(100)<BR>
);
```

## Tabela `vaga`

```sql
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
```

## Conexão do banco

```
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
```
## Modelo Lógico do Banco de Dados 

![image](https://github.com/RaffDevs/tecjobs2/assets/141787340/ff0cbba7-46fd-4c1b-8818-c0ebb798e884)

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

Foi utilizado Node.js e Express para a criação do backend. A aplicação foi hospedada no Render e faz uma conexão com o banco de dados Azure.
<BR>
<BR>
<img src="https://github.com/RaffDevs/tecjobs2/assets/136899628/d08dae68-722c-4983-80c0-63795b70ae95" alt="drawing" width="600"/>
<BR>
<BR>
**Documentação da API:**

Link da doc: https://backend-pi-node.onrender.com/api-docs/#/
<BR>
API: https://backend-pi-node.onrender.com/




