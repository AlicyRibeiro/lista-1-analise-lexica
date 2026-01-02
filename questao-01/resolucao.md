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

### Expressão regular

`10101[01]* | 1011[01]* | 11[01]*`


---

## e) Strings sobre o alfabeto `{a, b, c}` que **não contêm** a substring `baa`

> *(A definir)*

---

## f) Números binários `n` tais que existe solução inteira para  
`aⁿ + bⁿ = cⁿ`

> *(A definir)*
