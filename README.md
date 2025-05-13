

## 💡 Taskfy Wolf

### Taskfy — Gerenciador de Tarefas com Usuários, Permissões e Histórico

Um sistema realista e útil, com:

* Cadastro de usuários com perfis (ADMIN / USER)
* Login (JWT)
* Criação de tarefas com status (TODO, DOING, DONE)
* Histórico das alterações das tarefas
* Filtro e paginação
* Separação de responsabilidades
* Aplicação de princípios **SOLID**
* Uso de vários **design patterns** (Strategy, Factory, Builder, Singleton, Adapter, etc.)

---

## 📁 Estrutura de Pastas (Arquitetura em Camadas + Clean Code)

```text
src/
└── main/
    ├── java/
    │   └── com.taskfy/
    │       ├── TaskfyApplication.java
    │       ├── config/               <- Segurança, beans, configs
    │       ├── controller/           <- Camada de entrada HTTP
    │       ├── dto/                  <- Data Transfer Objects
    │       ├── entity/               <- Entidades JPA
    │       ├── enums/                <- Enums de status, papéis, etc.
    │       ├── exception/            <- Tratamento global de erros
    │       ├── repository/           <- Interfaces de acesso ao BD
    │       ├── security/             <- JWT, filtros, autenticação
    │       ├── service/              <- Regras de negócio
    │       ├── service/strategy/     <- Padrão Strategy aplicado
    │       ├── factory/              <- Factories usadas no sistema
    │       └── util/                 <- Helpers e utilitários
    └── resources/
        ├── application.properties
        └── data.sql / schema.sql (opcional)
```

---

## ✅ Tecnologias

* Java 21
* Spring Boot 3
* Spring Security (JWT)
* Spring Data JPA
* Lombok
* MySQL
* MapStruct (opcional)
* Flyway (migrações opcionais)

---

## 🧠 Princípios SOLID e Patterns Usados

| Princípio / Padrão | Onde será aplicado                                                            |
| ------------------ | ----------------------------------------------------------------------------- |
| **S** - SRP        | Cada classe (ex: `TaskService`, `UserService`) tem uma única responsabilidade |
| **O** - OCP        | Estratégias de criação de tarefas com `TaskCreationStrategy`                  |
| **L** - LSP        | `AdminUser` e `RegularUser` podem ser substituídos sem quebrar regras         |
| **I** - ISP        | Interfaces específicas para cada serviço (`ICreateTask`, `IFilterTasks`)      |
| **D** - DIP        | Inversão de dependência via Spring Beans e Interfaces                         |
| **Factory**        | Criação de usuários e tarefas via `Factory`                                   |
| **Strategy**       | Estratégias para status de tarefas e criação dinâmica                         |
| **Builder**        | Montagem de objetos complexos (como `TaskHistory`)                            |
| **Singleton**      | JWTUtils ou Mappers em singleton                                              |
| **Adapter**        | Adaptação de payloads externos, se necessário                                 |

---





