## 🏦 Itaú Unibanco - Desafio de Programação Backend

Este projeto é uma implementação do desafio técnico proposto pelo Itaú Unibanco, com foco em desenvolvimento e engenharia de software. O objetivo principal é criar uma **API RESTful** utilizando **Java + Spring Boot**, capaz de receber transações e calcular estatísticas com base nelas.


---

## 🚀 Tecnologias Utilizadas

- Java 21+
- Spring Boot
- Maven
- JUnit 5
- Mockito
- Java Time API (`OffsetDateTime`)
- Coleções em memória

---

## 🔍 Objetivo

Desenvolver uma API REST que:

1. Receba transações com valor e data/hora.
2. Calcule estatísticas das transações ocorridas nos últimos **60 segundos**.
3. Permita limpar as transações armazenadas.
4. **Sem** uso de banco de dados ou cache externo. Todos os dados devem estar apenas em memória.

---

## 📌 Restrições Técnicas

- ✅ Repositório hospedado no GitHub (sem fork de outro projeto).
- ✅ Mínimo de 3 commits (1 por endpoint).
- ✅ JSON como formato de entrada e saída.
- ✅ Armazenamento 100% em memória (sem H2, PostgreSQL, Redis, etc).
- ❌ Transações no futuro ou com valores negativos não são permitidas.

---

## 📦 Endpoints da API

### 🔸 POST `/transacao`

Recebe uma nova transação.

#### ✅ Payload de exemplo:

```json
{
  "valor": 123.45,
  "dataHora": "2020-08-07T12:34:56.789-03:00"
}
```

#### 🧪 Regras de validação:
- `valor` deve ser ≥ 0.
- `dataHora` deve estar no passado (não pode ser no futuro).
- Ambos os campos são obrigatórios.

#### 🔁 Respostas possíveis:
- `201 Created`: Transação válida e registrada.
- `422 Unprocessable Entity`: Transação rejeitada por violar alguma regra de negócio.
- `400 Bad Request`: Payload inválido ou malformado.

---

### 🔸 DELETE `/transacao`

Remove todas as transações armazenadas em memória.

#### 🔁 Resposta esperada:
- `200 OK`: Transações removidas com sucesso.

---

### 🔸 GET `/estatistica`

Retorna as estatísticas das transações ocorridas nos últimos **60 segundos**.

#### ✅ Exemplo de resposta:

```json
{
  "count": 10,
  "sum": 1234.56,
  "avg": 123.456,
  "min": 12.34,
  "max": 123.56
}
```

#### 📌 Observações:
- Quando **não houverem transações** nos últimos 60 segundos, todos os valores retornados devem ser **0**.
- A precisão decimal deve ser adequada para representar corretamente os valores.

---

## 🧪 Testes

O projeto conta com cobertura de testes unitários que validam:

- Casos de sucesso e falha dos endpoints.
- Validação de entrada.
- Cálculo correto das estatísticas.
- Regras de negócios.

---

## 🛠️ Build & Execução

### 🔧 Pré-requisitos:
- Java 17+
- Maven 3.8+

### ▶️ Para rodar o projeto localmente:

```bash
# Clone o projeto
git clone https://github.com/seu-usuario/desafio-itau-backend.git

# Acesse a pasta
cd desafio-itau-backend

# Execute a aplicação
./mvnw spring-boot:run
```

---

## 📫 Contato

Desenvolvido por **Gabriel Barros**  
*Desenvolvedor back-end*

- 💌 Email: **gabrielbarrosg11@gmail.com**
- 💼 [LinkedIn](https://www.linkedin.com/in/gabriel-sbarros)
- 🌐 [Portfolio](https://bielbarros.github.io/Projeto-Portfolio-Gabriel/)
