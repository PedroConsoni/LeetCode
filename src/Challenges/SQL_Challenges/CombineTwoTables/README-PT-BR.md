# LeetCode SQL – Combine Two Tables

## Descrição do Desafio

O desafio **"Combine Two Tables"** do LeetCode tem como objetivo praticar o uso de **JOINs em SQL**, mais especificamente o **LEFT JOIN**.

O problema fornece duas tabelas:

### Tabela `Person`

| Coluna    | Tipo    |
| --------- | ------- |
| personID  | int     |
| firstname | varchar |
| lastname  | varchar |

### Tabela `Address`

| Coluna    | Tipo    |
| --------- | ------- |
| addressID | int     |
| personID  | int     |
| city      | varchar |
| state     | varchar |

Nem toda pessoa possui um endereço cadastrado, e o desafio pede que **todas as pessoas sejam retornadas**, mesmo que não exista um endereço associado.

---

## Objetivo

Retornar uma lista contendo:

* `firstname`
* `lastname`
* `city`
* `state`

Garantindo que **todas as pessoas da tabela `Person` apareçam no resultado**, mesmo que `city` e `state` sejam `NULL`.

---

## Solução em SQL

```sql
SELECT p.firstname, p.lastname, a.city, a.state
FROM person p
LEFT JOIN address a
ON p.personID = a.personID;
```

---

## Explicação da Query

### SELECT

```sql
SELECT p.firstname, p.lastname, a.city, a.state
```

Seleciona os campos desejados:

* Nome e sobrenome da pessoa (`Person`)
* Cidade e estado do endereço (`Address`)

---

### FROM

```sql
FROM person p
```

Define a tabela **principal** da consulta.

> Como queremos **todas as pessoas**, a tabela `Person` deve ser a tabela base.

---

### LEFT JOIN

```sql
LEFT JOIN address a
```

O `LEFT JOIN` garante que:

* Todas as linhas da tabela `Person` sejam retornadas
* Dados da tabela `Address` apareçam apenas quando houver correspondência

Se a pessoa **não tiver endereço**, os campos `city` e `state` serão `NULL`.

---

### ON (condição de junção)

```sql
ON p.personID = a.personID
```

Define como as tabelas se relacionam:

* A junção ocorre quando o `personID` é o mesmo nas duas tabelas

---

## 📈 Resultado Esperado

| firstname | lastname | city     | state |
| --------- | -------- | -------- | ----- |
| John      | Doe      | New York | NY    |
| Jane      | Smith    | NULL     | NULL  |

> Mesmo que `Jane Smith` não possua endereço, ela ainda aparece no resultado.

---

## Conclusão

Este desafio reforça conceitos fundamentais de SQL:

* Uso de **LEFT JOIN**
* Combinação de dados de múltiplas tabelas
* Tratamento de valores `NULL`

É um exercício essencial para quem está aprendendo **SQL para análise de dados ou back-end**.

---

