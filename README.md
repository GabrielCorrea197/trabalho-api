ALuno: Gabriel Correa da Silva
RU: 4709634

API RESTful desenvolvida em C# (.NET 8) para gerenciar cadastros de empresas e funcionários, com persistência em MySQL, documentação via Swagger e arquitetura em camadas.

A API permite:

✅ CRUD de Empresas (GET, POST, PUT, DELETE)
✅ CRUD de Funcionários (com vinculação à empresa)
✅ Validação de dados (CNPJ, CPF, salário)
✅ Proteção contra exclusão de empresas com funcionários
✅ Tratamento de erros com mensagens amigáveis
🚀 Como Executar
Pré-requisitos
.NET 8 SDK
Docker Desktop
1. Subir o banco de dados
docker run -d
--name mysql-empresas
-p 3306:3306
-e MYSQL_ROOT_PASSWORD=12345678
-e MYSQL_DATABASE=empresasdb
-v empresas_/var/lib/mysql
mysql:8.0 --default-authentication-plugin=mysql_native_password

2. Aplicar Migrações
cd ApiEmpresarial dotnet ef database update

3. Rodar API
dotnet run

Estrutura do Projeto
ApiEmpresarial/ ├── Controllers/ # Endpoints REST (EmpresasController, FuncionariosController) ├── DTOs/ # Objetos de transferência (CreateEmpresaDto, FuncionarioDto, etc.) ├── Models/ # Entidades de domínio (Empresa, Funcionario) ├── Data/ # DbContext e configurações do EF Core ├── Services/ # Lógica de negócio e validações ├── appsettings.json # Configurações (conexão com BD) └── Program.cs # Configuração da aplicação
