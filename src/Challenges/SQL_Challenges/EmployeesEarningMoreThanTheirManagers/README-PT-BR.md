# LeetCode SQL – Employees Earning More Than Their Managers

## Descrição do Desafio

O desafio **"Employees Earning More Than Their Managers"** do LeetCode tem como objetivo praticar **SELF JOIN** em SQL, ou seja, realizar um `JOIN` da tabela com ela mesma para comparar registros relacionados.

Neste problema, precisamos identificar funcionários que ganham **mais salário do que seus próprios gerentes**.

---

## Estrutura da Tabela

### Tabela `Employee`

| Coluna    | Tipo    |
| --------- | ------- |
| id        | int     |
| name      | varchar |
| salary    | int     |
| managerId | int     |

Cada funcionário pode ter um gerente, indicado pela coluna `managerId`, que referencia o `id` de outro funcionário na mesma tabela.

---

## Objetivo

Retornar o nome dos funcionários cujo **salário é maior que o salário de seus gerentes**.

### Coluna esperada:

* `Employee` (nome do funcionário)

---

## Solução em SQL

```sql
SELECT e.name AS Employee
FROM employee e
JOIN employee m
ON e.managerid = m.id
WHERE e.salary > m.salary;
```

---

## Explicação da Query

### SELF JOIN

```sql
FROM employee e
JOIN employee m
```

A tabela `employee` é utilizada duas vezes:

* `e` representa o **funcionário**
* `m` representa o **gerente**

Isso permite comparar dados entre funcionários e seus respectivos gerentes dentro da mesma tabela.

---

### Condição de Junção (ON)

```sql
ON e.managerid = m.id
```

Define o relacionamento:

* O `managerId` do funcionário (`e`) corresponde ao `id` do gerente (`m`).

---

### WHERE (comparação de salários)

```sql
WHERE e.salary > m.salary
```

Filtra apenas os funcionários cujo salário é **maior que o salário do gerente**.

---

## Resultado Esperado

| Employee |
| -------- |
| Joe      |
| Sam      |

> Apenas funcionários que ganham mais do que seus gerentes aparecem no resultado.

---

## Conclusão

Este desafio reforça conceitos importantes de SQL:

* Uso de **SELF JOIN**
* Comparação de registros dentro da mesma tabela
* Aplicação de filtros com **WHERE**

É um exercício essencial para compreender relacionamentos hierárquicos em bancos de dados.

---

📚 *Desafio disponível em:* LeetCode – SQL
