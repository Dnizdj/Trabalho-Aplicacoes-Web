# Gerenciador de Tarefas - Spring Boot MVC

Este projeto é uma aplicação web de gerenciamento de tarefas, construída com o padrão arquitetural **MVC** e suporte a múltiplos bancos de dados: **H2**, **MariaDB** e **MongoDB**.

## 🔧 Tecnologias Utilizadas

- Java 17
- Spring Boot
- Spring Web
- Spring Data JPA
- Spring Data MongoDB
- Lombok
- Validation
- H2 Database
- MariaDB Driver
- Maven
- VS Code + Extensões Spring

## 📁 Estrutura de Pastas

```
src/main/java/com/exemplo/tarefas/
├── controller
│   └── TarefaController.java
├── model
│   └── Tarefa.java
├── repository
│   ├── TarefaRepository.java
│   └── TarefaMongoRepository.java
└── service
    └── TarefaService.java
```

## ⚙️ Configuração dos Bancos de Dados

Utilize perfis diferentes para alternar entre os bancos.

### `application.properties`

```properties
spring.profiles.active=h2
```

### `application-h2.properties`

```properties
spring.datasource.url=jdbc:h2:mem:tarefasdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.h2.console.enabled=true
```

### `application-mariadb.properties`

```properties
spring.datasource.url=jdbc:mariadb://localhost:3306/tarefasdb
spring.datasource.username=root
spring.datasource.password=sua_senha
spring.datasource.driver-class-name=org.mariadb.jdbc.Driver
spring.jpa.hibernate.ddl-auto=update
spring.jpa.database-platform=org.hibernate.dialect.MariaDBDialect
```

### `application-mongodb.properties`

```properties
spring.data.mongodb.uri=mongodb://localhost:27017/tarefasdb
```

## 🧪 Testando a Aplicação

1. Execute com:

```bash
./mvnw spring-boot:run
```

2. Teste com Postman ou cURL:

- `GET     /tarefas`
- `POST    /tarefas`
- `PUT     /tarefas/{id}`
- `DELETE  /tarefas/{id}`

3. H2 Console (quando ativo):

```
http://localhost:8080/h2-console
JDBC URL: jdbc:h2:mem:tarefasdb
```

## 🧩 Extensões Recomendadas para o VS Code

- Extension Pack for Java
- Spring Boot Extension Pack
- MongoDB for VS Code
- SQLTools ou DBeaver para MariaDB

## 📌 Notas

- A anotação `@Entity` é usada para bancos relacionais.
- A anotação `@Document` permite integração com o MongoDB.
- Você pode usar os dois repositórios (`JPA` e `Mongo`) conforme o perfil ativo.

## 💡 Futuras Melhorias

- Autenticação e autorização com Spring Security
- Interface frontend com React ou Thymeleaf
- Filtro e ordenação de tarefas por status ou data

---

Desenvolvido com 💻 por [Seu Nome] — sinta-se livre para contribuir!

