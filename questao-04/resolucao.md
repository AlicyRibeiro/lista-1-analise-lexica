## a) Expressão regular `(if | then | else)`

### Passo a passo

#### Tokens individuais
- `if`, `then` e `else` são **strings literais**.
- Cada palavra-chave é convertida em um **NFA linear**, no qual cada caractere corresponde a uma transição entre estados.

#### Operador de alternância (`|`)
- Os NFAs correspondentes a `if`, `then` e `else` são conectados por meio de **transições ε (epsilon)** a partir de um único estado inicial.
- Cada sub-NFA possui seu próprio estado final.

### NFA para a expressão `(if | then | else)`

![NFA para (if | then | else)](figuras/alternativa-a-etapa-1.png)

---

### Estrutura do NFA

- **Explicação:**  
  Um único estado inicial com transições ε para os estados iniciais dos NFAs de `if`, `then` e `else`.

- **Estados Iniciais:**
  Cada sub-NFA (if, then, else) tem seu próprio estado final.

- **Transições:**
   Seguem os caracteres das palavras-chave.
  
- **Estados finais:**  
  Os estados finais de cada sub-NFA são estados de aceitação.
  Cada sub-NFA (if, then, else) tem seu próprio estado final.
  

### DFA obtido pelo algoritmo de subconjuntos

![DFA para (if | then | else)](figuras/alternativa-a-etapa-2.png)
