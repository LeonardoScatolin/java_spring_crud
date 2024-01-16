# Resumo do Projeto

Este projeto é uma API de CRUD (Create, Read, Update, Delete) desenvolvida em Java com o framework Spring Boot. Seu objetivo é gerenciar informações sobre produtos, proporcionando operações para listar todos os produtos ativos, registrar novos produtos, atualizar dados de produtos existentes e desativar produtos específicos.

## Principais Componentes

### Controllers

### ProductController

- **Listar todos os produtos ativos:**
  - **Endpoint:** `GET /product`
  
- **Registrar um novo produto:**
  - **Endpoint:** `POST /product`
  
- **Atualizar informações de um produto existente:**
  - **Endpoint:** `PUT /product`
  
- **Desativar um produto por ID:**
  - **Endpoint:** `DELETE /product/{id}`

#### RequestProductDTO

- DTO (Data Transfer Object) para receber dados na criação ou atualização de um produto.
- Campos: `id` (UUID), `name` (Nome do produto), `price_in_cents` (Preço em centavos).

#### ProductRepository

- Interface JPA para operações de banco de dados relacionadas aos produtos.
- Método adicional: `findAllByActiveTrue()` para obter todos os produtos ativos.

### Infra

#### ExceptionDTO

- DTO para representar informações de exceção.
- Campos: `message` (Mensagem de erro), `status` (Código de status HTTP).

#### RequestsExceptionHandler

- Manipulador de exceções para a classe `EntityNotFoundException`.
- Retorna uma resposta personalizada quando uma entidade não é encontrada.

## Configuração do Projeto (pom.xml)

- Java 17
- Spring Boot 3.2.1
- Dependências para web, devtools, Lombok, teste, JPA, validação, PostgreSQL, Flyway.

## Maven Plugins

- `spring-boot-maven-plugin` para empacotamento do projeto.
- `flyway-maven-plugin` para migração de banco de dados.
