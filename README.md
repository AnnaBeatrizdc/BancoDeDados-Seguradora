# 🛡️ Banco de Dados — Sistema de Seguradora
 
Projeto desenvolvido como atividade prática (TP1 – 2º Bimestre) da disciplina de Banco de Dados. O script cria e popula um banco de dados relacional para gerenciamento de contratos, apólices, segurados e planos de uma seguradora, utilizando **SQL Server**.
 
---
 
## 📋 Descrição
 
O banco de dados **SEGURADORA** modela o relacionamento entre clientes, seguradoras, contratos, apólices, planos e segurados, aplicando constraints de integridade referencial e regras de negócio por meio de checks nas colunas de data.
 
---
 
## 🗂️ Estrutura do Banco de Dados
 
### Tabelas
 
| Tabela        | Descrição                                              |
|---------------|--------------------------------------------------------|
| `CLIENTE`     | Empresas clientes que contratam os planos              |
| `SEGURADORA`  | Empresas seguradoras que oferecem os planos            |
| `PLANO`       | Planos disponíveis com seus benefícios                 |
| `CONTRATO`    | Contratos firmados entre clientes e seguradoras        |
| `APOLICE`     | Apólices vinculadas a contratos e planos               |
| `SEGURADO`    | Pessoas físicas cobertas por uma apólice               |
 
### Diagrama de Relacionamento (resumido)
 
```
CLIENTE ──< CONTRATO >── SEGURADORA
               │
            APOLICE >─── PLANO
               │
            SEGURADO
```
 
---
 
## ⚙️ Constraints Implementadas
 
- **PRIMARY KEY** em todas as tabelas
- **FOREIGN KEY** garantindo integridade referencial entre tabelas relacionadas
- **CHECK** nas colunas de data:
  - `DT_ASSINATURA > CURRENT_DATE` — contratos só podem ter data de assinatura futura
  - `DT_VALIDADE > CURRENT_DATE` — apólices só podem ter validade futura
  - `DT_NASCIMENTO < CURRENT_DATE` — data de nascimento deve ser anterior à data atual
- **NOT NULL** na coluna `SG_PLANO` da tabela `PLANO`
---
 
## 🚀 Como Executar
 
### Pré-requisitos
 
- [SQL Server](https://www.microsoft.com/pt-br/sql-server/sql-server-downloads) instalado (2017 ou superior recomendado)
- [SQL Server Management Studio (SSMS)](https://aka.ms/ssmsfullsetup) ou Azure Data Studio
### Passos
 
1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git
   ```
 
2. Abra o arquivo `SEGURADORA.sql` no SSMS ou Azure Data Studio.
3. Execute o script completo. Ele irá:
   - Criar o banco de dados `SEGURADORA`
   - Criar todas as tabelas com suas constraints
   - Inserir os dados de exemplo
   - Exibir os registros de todas as tabelas via `SELECT`
---
 
## 📦 Conteúdo do Script
 
```
SEGURADORA.sql
├── CREATE DATABASE
├── CREATE TABLE (6 tabelas)
│   ├── CLIENTE
│   ├── SEGURADORA
│   ├── PLANO
│   ├── CONTRATO
│   ├── APOLICE
│   └── SEGURADO
├── INSERT INTO (4+ registros por tabela)
└── SELECT * (todas as tabelas)
```
 
---
 
## 🛠️ Tecnologias Utilizadas
 
- **SQL Server** — Sistema Gerenciador de Banco de Dados (SGBD)
- **T-SQL** — Linguagem de consulta utilizada
---
 
## 👨‍💻 Autor
 
Desenvolvido por Anna Beatriz D para fins acadêmicos — TP1 do 2º Bimestre.
