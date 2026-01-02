## a) Strings sobre {a, b, c} onde o primeiro `a` precede o primeiro `b`

**Expressão regular:**

 `(c)*(a|c)a(a|b|c)`

### Justificativa
- `(c)*`: permite qualquer quantidade de `c`, inclusive nenhuma, antes da ocorrência de `a`.
- `(a|c)*a`: garante que o primeiro `a` apareça antes de qualquer `b`, pois `b` não é permitido antes desse `a`.
- `(a|b|c)*`: permite qualquer sequência de símbolos após o primeiro `a`, incluindo `b`.

### Exemplos
**Strings válidas:**  
- `cacaabb`  
- `acbc`  
- `cccaaab`  
- `ccccc`

**Strings inválidas:**  
- `bca`  
- `bac`

---

## b) Strings sobre o alfabeto `{a, b, c}` com um número **par** de `a`’s

### Expressão regular

 `((b|c)a(b|c)a(b|c))`

 
### Justificativa
- Os símbolos `a` são agrupados **dois a dois**.
- Entre os `a`’s pode haver qualquer quantidade de `b` ou `c`.
- Cada grupo contribui com exatamente **2 ocorrências de `a`**.
- A repetição do grupo garante que o número total de `a`’s seja sempre par.

### Exemplos
**Strings válidas:**  
- `abac`  
- `bb`  
- `aabbaa`  
- `ε` (string vazia)

**Strings inválidas:**  
- `a`  
- `aaab`

---

## c) Números binários múltiplos de quatro

### Expressão regular

`(0|1)*00`


### Justificativa
- `(0|1)*`: representa qualquer número binário.
- `00`: garante que o número termina com dois zeros, condição necessária para ser múltiplo de 4 em binário.

### Exemplos
**Strings válidas:**  
- `100`  
- `1100`  
- `100100`

**Strings inválidas:**  
- `101`  
- `11`  
- `1110`

---

## d) Números binários maiores que `101001`

Deseja-se definir, por meio de uma expressão regular, o conjunto de números binários
que representam valores **estritamente maiores** que `101001`.

O número `101001₂` possui **6 bits**. Para realizar a comparação, consideramos dois casos
principais:

### 1. Números com mais de 6 bits
Em representação binária sem zeros à esquerda, **qualquer número com mais de 6 bits**
é automaticamente maior que `101001`.  
Assim, todas as strings binárias que começam com `1` e possuem **7 ou mais bits**
pertencem à linguagem.

### 2. Números com exatamente 6 bits
Para strings de mesmo comprimento, a comparação é feita **bit a bit**, da esquerda
para a direita, de forma lexicográfica:

- Se o prefixo for `1011`, o número já é maior que `101001`, pois difere no quarto bit.
- Se o prefixo for `10101`, o número permanece igual até o quinto bit e será maior
  independentemente do valor do último bit.

Strings exatamente iguais a `101001` **não** são incluídas, pois o problema exige valores
estritamente maiores.


### Expressão regular

``
(1011|10101)[01]* | 1[01]{6,} ``

### Exemplos

#### Strings válidas:

- 101010   (42)
- 101100   (44)
- 110000   (48)
- 1111111  (127)


##### Strings inválidas:

- 101001   (igual a 101001)
- 101000   (menor)
- 100111   (menor)

---

## e) Strings sobre o alfabeto `{a, b, c}` que **não contêm** a substring `baa`

Deseja-se definir a linguagem formada por todas as strings sobre o alfabeto  
\(\Sigma = \{a, b, c\}\) que **não possuem** a substring proibida `baa`.

Isso significa que, em nenhuma posição da string, pode ocorrer a sequência
consecutiva de símbolos `b`, seguido de `a`, seguido de `a`.

---

### Estratégia de construção

Para garantir que a substring `baa` nunca apareça, observamos o seguinte:

- O símbolo `c` é sempre seguro, pois não participa da substring proibida.
- Após a ocorrência de um `b`, **não podem aparecer dois `a` consecutivos**.
- Após um `ba`, o próximo símbolo permitido é apenas `b` ou `c`
  (um `a` geraria `baa`, o que é proibido).

Assim, a expressão regular deve controlar cuidadosamente os símbolos que
seguem um `b`.

---

### Expressão regular

Uma expressão regular que descreve corretamente essa linguagem é:

```
(c|a|ba|b(c|b))* 
```

### Intuição da expressão

- a → símbolo isolado permitido
- c → símbolo isolado permitido
- ba → permitido, desde que não seja seguido por outro a
- b(c|b) → após um b, garante que não venha a em seguida
- `*` → permite qualquer quantidade desses blocos, inclusive a string vazia

Essa construção garante que a substring baa nunca ocorra.

### Exemplos

#### Strings válidas:

- ´""´        (string vazia)
- abc
- bac
- bbac
- cabab

#### Strings inválidas:

- baa
- cbaa
- bbaa

### Observação

Essa linguagem é regular, pois pode ser reconhecida por um autômato finito
que controla os últimos símbolos lidos para evitar a ocorrência da substring
baa. Portanto, ela pode ser descrita tanto por expressões regulares quanto
por autômatos finitos (NFA ou DFA).

---

## f) Números binários `n` tais que existe solução inteira para  
`aⁿ + bⁿ = cⁿ`

> *(A definir)*
