📦 Microservices Solution - Visual Studio (.NET 8)

🏗️ Project Overview

This solution follows the microservices architecture pattern using ASP.NET Core Web APIs, with services developed and deployed independently.

✅ Built with Visual Studio 2022+✅ Targeting .NET 8✅ Supports REST APIs, Swagger, and Docker

🧱 Microservices Structure

/src
  /AuthService           → Handles user authentication & authorization (JWT)
  /UserService           → Manages user profiles
  /ProductService        → Product catalog service
  /OrderService          → Handles order placement and status
  /ApiGateway            → Routes client requests to backend services
  /Shared                → Shared models, DTOs, common utilities

/docker-compose.yml      → Multi-service container setup

🚀 Getting Started

📅 1. Clone the Repository

git clone https://github.com/chandimajayaruwan90/universal-visualstudio-repo
cd microservices-solution

🖠️ 2. Open in Visual Studio

Launch MicroservicesSolution.sln

Set multiple startup projects (AuthService, UserService, etc.)

Run solution with F5 or Ctrl+F5

🐳 3. Run with Docker (Optional)

docker-compose up --build

📌 Configuration

Each microservice has its own appsettings.json for:

Port configurations

Database connections (SQL Server or PostgreSQL)

JWT secrets

Service discovery

Use UserSecrets or Azure Key Vault for sensitive data.

📂 Sample Service Setup (e.g., UserService)

Controllers/ – API endpoints

Services/ – Business logic

Repositories/ – Data access

Models/ – DTOs and domain models

Program.cs / Startup.cs – Service configuration

🔐 Authentication (JWT)

AuthService issues tokens on login/registration.Other services validate JWT using middleware:

builder.Services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
    .AddJwtBearer(...);

🧚️‍♂️ Testing & Tools

✅ Swagger UI at /swagger

✅ Postman collection available in /docs

✅ xUnit test projects for each service

✅ Logging with Serilog

✅ Optional: Prometheus + Grafana for monitoring

♻️ Communication

HTTP (REST) between services

Future enhancement: add MassTransit/RabbitMQ for async messaging

🔒 Security

HTTPS enforced in all services

JWT-based auth

CORS policy configured per service

📦 NuGet Packages Used

Microsoft.EntityFrameworkCore

Swashbuckle.AspNetCore (Swagger)

Serilog.AspNetCore

System.IdentityModel.Tokens.Jwt

AutoMapper.Extensions.Microsoft.DependencyInjection

📁 Environment Setup

Create the following .env or launchSettings.json per service if needed:

{
  "profiles": {
    "UserService": {
      "commandName": "Project",
      "launchBrowser": true,
      "applicationUrl": "https://localhost:5001;http://localhost:5000",
      "environmentVariables": {
        "ASPNETCORE_ENVIRONMENT": "Development"
      }
    }
  }
}

📙 Documentation

API docs via Swagger

Folder /docs contains:

Postman collections

DB schema

Sequence diagrams (if any)

👨‍💼 Developer Notes

Run dotnet restore before build

Use dotnet ef database update to apply migrations

Logs are written to logs/ folder and console

📬 Contact

Maintainer: [Your Name]Email: your.email@example.com

