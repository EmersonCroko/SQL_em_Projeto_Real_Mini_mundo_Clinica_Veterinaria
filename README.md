# SQL_em_Projeto_Real_Mini_mundo_Clinica_Veterinaria

# 🐾 Clínica Veterinária – Banco de Dados Relacional

Este repositório contém a implementação completa do banco de dados do projeto **Clínica Veterinária**, incluindo scripts **DDL**, **DML**, **consultas SQL**, **updates**, **deletes**, além das instruções para execução no **MySQL** e **PostgreSQL**.

## 📌 Conteúdo do Repositório

📁 /
├── 01_ddl.sql                # Criação das tabelas e relacionamentos
├── 02_inserts.sql            # Povoamento inicial do banco
├── 03_selects.sql            # Consultas com SELECT, JOIN, ORDER BY, LIMIT etc.
├── 04_updates_deletes.sql    # Comandos UPDATE e DELETE
├── DER.md                    # Documento com o Diagrama ER
└── README.md                 # Este arquivo

## 🧩 Modelo do Projeto

O sistema modela a operação de uma clínica veterinária com as seguintes entidades principais:

* **Tutor** – dono do animal
* **Animal** – paciente da clínica
* **Veterinário** – responsável pelos atendimentos
* **Serviço** – procedimentos oferecidos
* **Consulta** – registro dos atendimentos realizados

O DER completo encontra-se em `DER.md`.

## 🛠️ Tecnologias Suportadas

Este projeto pode ser executado tanto no **MySQL** quanto no **PostgreSQL**.

Ferramentas sugeridas:

* MySQL Workbench
* DBeaver
* PGAdmin 4
* Azure Data Studio (com plugin de PostgreSQL)

# 🚀 Instruções de Execução

A seguir estão os passos completos para criar e executar o banco.

# 🐬 **Opção 1 – Executar no MySQL**

## 1️⃣ Criar o banco de dados
```sql
CREATE DATABASE clinica_veterinaria;
USE clinica_veterinaria;
```
## 2️⃣ Rodar o script DDL
No MySQL Workbench:
```
File → Open SQL Script → selecione 01_ddl.sql
Execute (⚡)
```
## 3️⃣ Inserir os dados
Execute o arquivo:
```
02_inserts.sql
```
## 4️⃣ Testar consultas
```
03_selects.sql
```
## 5️⃣ Testar updates e deletes
```
04_updates_deletes.sql
```



# 🐘 **Opção 2 – Executar no PostgreSQL**

## 1️⃣ Criar o banco
```sql
CREATE DATABASE clinica_veterinaria;
```
Conectar ao banco criado.
## 2️⃣ Executar o script DDL
No PGAdmin:
```
Tools → Query Tool → Open File → 01_ddl.sql → Execute (F5)
```
## 3️⃣ Inserir dados
Execute:
```
02_inserts.sql
```
## 4️⃣ Consultas
Execute:
```
03_selects.sql
```
## 5️⃣ Atualizações e exclusões
Execute:
```
04_updates_deletes.sql
```

---
# 📦 Estrutura das Tabelas

As tabelas foram geradas a partir do modelo lógico conforme o DER e incluem:

* Chaves primárias
* Chaves estrangeiras
* Tipos de dados adequados
* Relacionamentos 1:N e N:1

Para detalhes, veja o arquivo **01_ddl.sql**.

---

# 📝 Notas Importantes

* Certifique-se de executar os scripts na ordem correta.
* No PostgreSQL, tipos `AUTO_INCREMENT` devem ser substituídos por `SERIAL`.
* Em ambos os SGBDs, respeite a ordem de inserção devido às chaves estrangeiras.

---

# 📚 Aprendizados (Taxonomia de Bloom e Fink)

### Bloom

* **Aplicar:** execução de comandos SQL reais.
* **Criar:** desenvolvimento de scripts completos.

### Fink

* **Aplicação:** uso de Workbench/PGAdmin.
* **Integração:** conexão entre DER, lógica e DML.
* **Aprendendo a aprender:** interpretação de erros de SQL durante a execução.

---

# 📬 Contato

Caso deseje sugestões de melhorias, diagramas completos ou ajuda com versionamento Git, é só solicitar!
