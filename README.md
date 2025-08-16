# 🏦 LoanManagementAPI

API REST desenvolvida em **C# .NET** para gerenciamento de empréstimos bancários.  
O sistema permite cadastro de clientes, solicitação de empréstimos, simulação de juros compostos, aprovação automática baseada em score de crédito e acompanhamento das parcelas.

---

## 🚀 Funcionalidades

- Cadastro de clientes com CPF, renda e score de crédito  
- Solicitação de empréstimos com valor e número de parcelas  
- Aprovação automática de acordo com regras de crédito  
- Simulação de juros compostos e geração de parcelas  
- Acompanhamento do status do empréstimo (`Pendente`, `Aprovado`, `Reprovado`, `Em Andamento`, `Quitado`)  
- Pagamento de parcelas e quitação de empréstimos  
- Autenticação JWT com roles de **Cliente** e **Admin**  
- Documentação interativa com **Swagger**  

---

## 🏗️ Arquitetura

- **.NET 8 / ASP.NET Core Web API**  
- **Entity Framework Core** (SQL Server ou PostgreSQL)  
- **FluentValidation** para validações  
- **Swagger / OpenAPI** para documentação  
- **xUnit** para testes automatizados  
- **Docker Compose** para containerização da API e do banco de dados  

---

## 📡 Endpoints principais

### Clientes
- `POST /clientes` → cadastrar cliente  
- `GET /clientes/{id}` → buscar cliente  
- `GET /clientes` → listar clientes  

### Empréstimos
- `POST /emprestimos/solicitar` → solicitar novo empréstimo  
- `GET /emprestimos/{id}` → detalhes de um empréstimo  
- `GET /clientes/{id}/emprestimos` → listar empréstimos do cliente  

### Parcelas
- `GET /emprestimos/{id}/parcelas` → listar parcelas de um empréstimo  
- `POST /parcelas/{id}/pagar` → pagar uma parcela  

---

## 🔒 Segurança

- Autenticação via **JWT**  
- Perfis de usuário:
  - **Cliente** → acessa apenas os próprios dados  
  - **Admin** → acessa todos os clientes e empréstimos  

---

## 🛠️ Como rodar o projeto

### Pré-requisitos
- [.NET 8 SDK](https://dotnet.microsoft.com/download)  
- [Docker](https://www.docker.com/)  

### Passos
```bash
# Clonar o repositório
git clone https://github.com/luisfelipe03/LoanManagementAPI.git
cd LoanManagementAPI

# Rodar com Docker Compose
docker compose up -d

# Rodar a API
dotnet run --project src/LoanManagementAPI
```

API estará disponível em:
👉 `http://localhost:5000/swagger`

---

## ✅ Próximos passos

* Implementar envio de notificações (e-mail/SMS) para parcelas vencidas
* Adicionar relatórios financeiros (total emprestado, inadimplência, etc.)
* Criar testes de integração com banco de dados em memória
