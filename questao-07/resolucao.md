## a) Pascal

### Identificadores

#### Regras
- Começam com uma letra (`A–Z`, `a–z`).
- Podem conter letras, dígitos (`0–9`) e `_`.

#### Exemplos
**Válidos:**  
- `x`, `somaTotal`, `contador1`, `_valor`

**Inválidos:**  
- `@nome`, `até` (acentos não permitidos)

---

### Palavras-chave

Palavras-chave são **símbolos reservados** que representam comandos, estruturas de controle, declarações ou operações específicas da linguagem.

- **Função no lexer:** são reconhecidas como tokens especiais, distintos de identificadores.
- **Impacto:** servem de base para a gramática da linguagem e para a análise sintática.
- **Observação:** sem palavras-chave, não seria possível distinguir comandos de nomes arbitrários.

#### Exemplos
- `program`, `var`, `begin`, `end`, `if`, `then`, `else`, `while`, `for`, `procedure`, `function`

---

## b) C

### Identificadores

#### Regras
- Começam com uma letra (`A–Z`, `a–z`) ou `_`.
- Podem conter letras, dígitos e `_`.

#### Exemplos
**Válidos:**  
- `i`, `soma_total`, `Contador1`, `_temp`

**Inválidos:**  
- `1var`, `@nome`, `até` (acentos não permitidos)

---

### Palavras-chave

#### Exemplos
- `int`, `float`, `if`, `else`, `while`, `for`, `return`, `switch`, `case`, `break`, `#include`, `#define`

---

## c) Java

### Identificadores

#### Regras
- Começam com uma letra (`A–Z`, `a–z`), `_` ou `$`.
- Podem conter letras, dígitos, `_` e `$`.
- São *case-sensitive* (`nome ≠ Nome`).
- Aceitam Unicode (não recomendado na prática).

#### Exemplos
**Válidos:**  
- `idade`, `somaTotal`, `$valor`, `_contador`, `variável` (Unicode permitido, mas não recomendado)

**Inválidos:**  
- `public`, `class`, `static`, `void`, `if`, `else`, `while`, `for`, `try`, `catch`, `finally`, `new`

---

### Palavras-chave

#### Exemplos
- `public`, `class`, `static`, `void`, `if`, `else`, `while`, `for`, `try`, `catch`, `finally`, `new`

---

## d) Python

### Identificadores

#### Regras
- Começam com uma letra (`A–Z`, `a–z`) ou `_`.
- Podem conter letras, dígitos e `_`.
- São *case-sensitive* (`nome ≠ Nome`).
- Aceitam Unicode, embora não seja recomendado.

#### Exemplos
**Válidos:**  
- `x`, `soma_total`, `_valor`, `Contador1`, `variável` (Unicode permitido)

**Inválidos:**  
- `1var`, `@nome`, `def` (palavra-chave)

---

### Palavras-chave

#### Exemplos
- `def`, `class`, `if`, `else`, `while`, `for`, `try`, `except`, `finally`, `return`, `async`

---

## Observações Gerais

- **Unicode:** Java e Python permitem identificadores Unicode, mas seu uso não é comum.
- **Palavras-chave:** não podem ser usadas como identificadores (ex.: `int x;` é válido em C, mas `if = 10;` não).
- **Sensibilidade a maiúsculas/minúsculas:**  
  - C, Java e Python diferenciam maiúsculas de minúsculas.  
  - Pascal tradicionalmente não diferencia.

Essas regras são fundamentais para o funcionamento de **analisadores léxicos (lexers)** em compiladores e interpretadores.
