
# DSList

Projeto desenvolvido como parte do **Intensivão Java Spring** da [DevSuperior](https://devsuperior.com.br), com o objetivo de criar uma API REST para gerenciamento de listas de jogos. O sistema permite que os usuários consultem jogos, organizem-nos em listas personalizadas e alterem a ordem dos jogos conforme desejado.

Este projeto representa uma aplicação real de conceitos essenciais no desenvolvimento backend com Java e Spring Boot, simulando práticas profissionais como estruturação por camadas, criação de endpoints RESTful, e deploy com CI/CD.

---

## 📌 Contextualização

Durante o intensivão foram abordados fundamentos essenciais da construção de sistemas web modernos. O projeto DSList reflete a estrutura de uma aplicação backend robusta, aplicando conceitos como:

- Cliente/servidor, HTTP, JSON e API REST
- Boas práticas de padronização de endpoints
- Padrão de camadas (Controller → Service → Repository)
- Padrão DTO para transferência segura de dados
- Relacionamentos entre entidades com JPA
- Consultas com SQL nativo e projections
- Perfis de projeto: desenvolvimento, homologação e produção

---

## 🚀 Tecnologias Utilizadas

- **Java 17**
- **Spring Boot**
- **Spring Data JPA**
- **PostgreSQL**
- **H2 Database**
- **Maven**
- **Docker**

---

## 🧠 Conhecimentos Aplicados

### Aula 1 – Fundamentos e Estruturação
- Modelo cliente/servidor e API RESTful
- Entidade `Game`, seed inicial
- Camadas da aplicação
- Padrão DTO

### Aula 2 – Relacionamentos e Consultas
- Relacionamento muitos-para-muitos
- `GameList` com chave composta
- Consultas SQL com projections

### Aula 3 – Ambientes e CORS
- Perfis de execução (dev, test, prod)
- Configuração de variáveis e CORS

### Aula 4 – Endpoint Especial
- POST /lists/{listId}/replacement

### Aula 5 – Conclusão e Deploy
- CI/CD com Railway (Apenas acompanhei pela aula, não realizei o deploy)
- Testes com Postman

---

## 🗂️ Estrutura do Projeto

```
dslist/
├── src/
│   ├── main/
│   │   ├── java/com/devsuperior/dslist/
│   │   │   ├── controllers/
│   │   │   ├── dto/
│   │   │   ├── entities/
│   │   │   ├── projections/
│   │   │   ├── repositories/
│   │   │   └── services/
│   │   └── resources/
│   │       ├── application.properties
│   │       ├── application-dev.properties
│   │       ├── application-test.properties
│   │       └── import.sql
├── pom.xml
└── system.properties
```

---

## 🐳 Uso do Docker

Durante o desenvolvimento do projeto, o Docker foi utilizado para facilitar a criação de um ambiente de homologação local. Através da configuração de containers, foi possível simular a infraestrutura do banco de dados PostgreSQL sem a necessidade de instalação manual na máquina local.

### Etapas realizadas com Docker:

- **Criação de container PostgreSQL** para o perfil `dev`, permitindo testes em um banco real.
- Configuração das variáveis de ambiente no arquivo `application-dev.properties` apontando para o container.
- Execução do app com o perfil de desenvolvimento (`dev`) conectado ao banco hospedado no container Docker.
- Uso opcional de ferramentas como **DBeaver** ou **pgAdmin** para conexão e visualização dos dados.

### Comando típico para subir o container:

```bash
docker run --name dslist-pg \
  -e POSTGRES_DB=dslist \
  -e POSTGRES_USER=postgres \
  -e POSTGRES_PASSWORD=123456 \
  -p 5432:5432 \
  -d postgres


## 📦 Como Executar o Projeto

1. Clone o repositório:
   ```bash
   git clone https://github.com/leonardorosario/dslist.git
   cd dslist
   ```

2. Configure o banco de dados PostgreSQL local ou use H2.

3. Execute o projeto via sua IDE ou terminal:
   ```bash
   ./mvnw spring-boot:run
   ```

---

## 🔗 Endpoints Disponíveis

- `GET /games`
- `GET /games/{id}`
- `GET /lists`
- `GET /lists/{listId}/games`
- `POST /lists/{listId}/replacement`

---

## 💼 Sobre o Projeto

Este projeto foi desenvolvido com foco no aprendizado prático de tecnologias modernas para backend com Java, sendo uma excelente base para aplicações mais completas.

---

## 🙋‍♂️ Autor

**Leonardo Rosario Teixeira**  
[GitHub: @leonardorosario](https://github.com/leonardorosario)
