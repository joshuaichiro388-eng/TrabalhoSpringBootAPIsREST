# SistemaHotel — API REST com Spring Boot

Projeto acadêmico desenvolvido para o trabalho **Introdução ao Spring Boot e APIs REST**, com o objetivo de praticar a criação de uma API REST para gerenciamento de quartos de hotel.

## Integrantes

- Joshua Ichiro Taniguchi
- Gabriel Pereira Jorge

## Sobre o projeto

A aplicação propõe uma API HTTP para consultar e administrar quartos. Nesta etapa inicial, os dados são mantidos em memória em uma lista; por isso, eles não são persistidos quando a aplicação é encerrada.

A arquitetura utiliza as seguintes camadas:

```text
Cliente HTTP → Controller → Service → Lista de quartos
```

- **Controller:** recebe as requisições HTTP e encaminha as operações.
- **Service:** concentra as regras e operações relacionadas aos quartos.
- **Lista em memória:** armazena os dados durante a execução da aplicação.

## Tecnologias e requisitos

- Java 17 ou superior
- Maven
- Spring Boot
- Spring Web
- JSON para troca de dados com a API

## Funcionalidades e endpoints

| Método | Endpoint | Operação |
| --- | --- | --- |
| `GET` | `/quartos` | Lista os quartos |
| `GET` | `/quartos/{id}` | Busca um quarto pelo ID |
| `POST` | `/quartos` | Cadastra um quarto |
| `PUT` | `/quartos/{id}` | Atualiza um quarto |
| `DELETE` | `/quartos/{id}` | Remove um quarto |
| `GET` | `/quartos/tipo?tipo=DUPLO` | Filtra quartos pelo tipo |

Os endpoints de disponibilidade, consulta combinada e cálculo de preço são desafios opcionais do trabalho e podem ser adicionados ao projeto.

### Exemplo de JSON

```json
{
  "numero": 101,
  "valorDiaria": 180.0,
  "tipo": "SIMPLES"
}
```

Os valores aceitos para `tipo`, conforme o enunciado, são `SIMPLES`, `DUPLO` e `COBERTURA`.

## Como executar

Na pasta do projeto, execute:

```bash
./mvnw spring-boot:run
```

No Windows, use:

```bat
mvnw.cmd spring-boot:run
```

Caso o Maven Wrapper não esteja disponível, execute com o Maven instalado:

```bash
mvn spring-boot:run
```

Com a aplicação em execução, a API estará disponível por padrão em `http://localhost:8080`.

## Testando a API

As requisições podem ser feitas com `curl`, Postman, Insomnia, Bruno ou outro cliente HTTP. Exemplo para listar quartos:

```bash
curl http://localhost:8080/quartos
```

Exemplo de cadastro:

```bash
curl -X POST http://localhost:8080/quartos \
  -H "Content-Type: application/json" \
  -d '{"numero":201,"valorDiaria":450.0,"tipo":"COBERTURA"}'
```

## Conteúdos abordados

O trabalho também contempla pesquisa e prática sobre Spring Framework e Spring Boot, Inversão de Controle (IoC), Injeção de Dependência (DI), Beans, API REST, HTTP, JSON, métodos e status HTTP, anotações Spring e separação de responsabilidades entre Controller, Service e Repository.

## Entrega

- **Prazo informado no enunciado:** 30/11/2026, até 23h59.
- **Formulário de entrega:** [Google Forms](https://forms.gle/cACBL5SdjMiy85Fz8)

---

Trabalho acadêmico — Introdução ao Spring Boot e APIs REST.
