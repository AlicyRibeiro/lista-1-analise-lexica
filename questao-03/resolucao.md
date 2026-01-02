
## a) Autômato com alfabeto `{0, 1}`

![autômato](figuras/alternativa-a.jpeg)

---
A linguagem reconhecida por esse autômato consiste em **strings binárias que contêm uma subcadeia de 4 símbolos consecutivos** que permite a transição completa pelos estados do autômato até um estado final.

Em outras palavras, o autômato aceita cadeias que possuem **quatro símbolos consecutivos** formando um padrão válido de transições.

### Exemplos de strings aceitas
- `1111`
- `1100`
- `1011`
- `0111`
- `0000`
- `0011`

---

## b) Autômato com alfabeto `{a}`

A linguagem reconhecida por esse autômato é composta por todas as strings da forma `aⁿ` tais que:

`n ≡ 1 (mod 4)`

Ou seja, o número de símbolos `a` na string deixa **resto 1** quando dividido por 4.

---

## c) Autômato com alfabeto `{0, 1}`

A linguagem reconhecida por esse autômato consiste em **strings binárias que possuem um número par de símbolos `1`**, independentemente da quantidade de símbolos `0`.

O autômato alterna entre estados que representam quantidade par e ímpar de `1`’s, aceitando apenas quando a contagem é par.

### Exemplos de strings aceitas
- `ε` (string vazia, 0 ocorrências de `1`)
- `11` (2 ocorrências de `1`)
- `1100` (2 ocorrências de `1` e quaisquer `0`’s)
- `0101` (2 ocorrências de `1`)

### Exemplos
- `a` (1 símbolo `a`)
- `aaaaa` (5 símbolos `a`)
- `aaaaaaaaa` (9 símbolos `a`)

---
