# 🧮 Palindrome Number — LeetCode Challenge

## 📘 Descrição do Problema

Dado um número inteiro `x`, determine se ele é um **palíndromo**.  
Um número é considerado **palíndromo** se ele lido de trás para frente for igual ao valor original.

**Exemplos:**
```
Entrada: x = 121
Saída: true
Explicação: 121 lido de trás para frente ainda é 121.

Entrada: x = -121
Saída: false
Explicação: De trás para frente seria 121-, não é igual ao original.

Entrada: x = 10
Saída: false
Explicação: De trás para frente seria 01, não é igual.
```


---

## 💡 Lógica da Solução

A ideia principal é **reverter os dígitos do número** e comparar o resultado com o valor original.

1. Guardamos o valor original de `x` em uma variável auxiliar (`comparator`), para não perder o número original durante o processo.  
2. Criamos uma variável `reverse` que armazenará o número invertido.  
3. Enquanto `comparator` for maior que zero:
   - Pegamos o **último dígito** usando o operador módulo `% 10`;
   - Adicionamos esse dígito no final de `reverse` (multiplicando `reverse` por 10 antes);
   - Removemos o último dígito de `comparator` com a **divisão inteira** `/ 10`.
4. Após o loop, comparamos se o número invertido (`reverse`) é igual ao número original (`x`).

Se forem iguais, o número é um **palíndromo**.
