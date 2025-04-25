# Projeto Spring Boot: Gerenciamento de Produtos e Categorias

## Objetivo
Este projeto tem como objetivo demonstrar o uso de relacionamento entre entidades em uma aplicação Spring Boot, utilizando MariaDB como banco de dados, juntamente com as bibliotecas Lombok, Spring Web, DevTools e JPA. As entidades utilizadas neste projeto são **Produto** e **Categoria**, com um relacionamento **One-to-Many** (uma categoria possui vários produtos).

## Tecnologias Utilizadas
- Java 17
- Spring Boot
- Spring Web
- Spring Data JPA
- Lombok
- MariaDB
- DevTools
- Maven

## Estrutura do Projeto
- `controller`: Contém os controladores REST (`ProdutoController`, `CategoriaController`).
- `model`: Contém as classes de modelo JPA (`Produto`, `Categoria`).
- `repository`: Contém interfaces que estendem `JpaRepository` para operações de CRUD.
- `resources/application.properties`: Configuração de conexão com o banco de dados MariaDB.
- `LojaApplication.java`: Classe principal que inicia a aplicação.

## Configuração do Ambiente
1. Instale o [XAMPP](https://www.apachefriends.org/index.html) e inicie o MariaDB.
2. Crie o banco de dados `loja` com o seguinte comando SQL:
```sql
CREATE DATABASE loja;
```
3. Atualize seu `application.properties` com as credenciais corretas:
```properties
spring.datasource.url=jdbc:mariadb://localhost:3306/loja
spring.datasource.username=root
spring.datasource.password=
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

## Como Rodar o Projeto
1. Clone o repositório.
2. Navegue até a pasta do projeto.
3. Execute o projeto em uma IDE como VS Code ou IntelliJ.
4. A aplicação iniciará na porta padrão (8080).

## Testando os Endpoints
Utilize uma ferramenta como [Postman](https://www.postman.com/) ou [Bruno](https://www.usebruno.com/) para testar os endpoints.

### Endpoints para Categoria
- `GET /categorias`: Lista todas as categorias.
- `POST /categorias`: Cria uma nova categoria.
- `PUT /categorias/{id}`: Atualiza uma categoria existente.
- `DELETE /categorias/{id}`: Deleta uma categoria.

### Endpoints para Produto
- `GET /produtos`: Lista todos os produtos.
- `POST /produtos`: Cria um novo produto.
- `PUT /produtos/{id}`: Atualiza um produto existente.
- `DELETE /produtos/{id}`: Deleta um produto.

## Relacionamento Entre Entidades
- A classe `Categoria` possui uma lista de produtos anotada com `@OneToMany`.
- A classe `Produto` referencia `Categoria` com `@ManyToOne`.
- O relacionamento está corretamente mapeado e persistido no banco de dados MariaDB.

## Considerações Finais
Este projeto foi desenvolvido como parte de uma atividade avaliativa da disciplina de Arquitetura de Microsserviços, com foco na prática de mapeamento de entidades, persistência com JPA, e exposição de APIs RESTful com Spring Boot.

