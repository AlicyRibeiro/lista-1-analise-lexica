
### b) C

#### Código-fonte

```c
int max (i, j) int i, j;
/* retorna o maior dos inteiros entre
i e j  */
{
    return i>j?    i  :  j;
}

```

## Tabela de Tokens

| Token     | Lexema       | Categoria                    |
|-----------|--------------|------------------------------|
| `int`     | `int`        | Palavra-chave (tipo)         |
| `max`     | `max`        | Identificador (função)       |
| `(`       | `lparen`     | Delimitador                  |
| `i`, `j`  | `id`         | Identificador (parâmetro)    |
| `)`       | `rparen`     | Delimitador                  |
| `,`       | `comma`      | Delimitador                  |
| `;`       | `semicolon`  | Delimitador                  |
| `{`       | `lbrace`     | Delimitador                  |
| `return`  | `return`     | Palavra-chave                |
| `i>j? i : j` | `cond_expr` | Expressão condicional        |
| `>`       | `gt`         | Operador relacional          |
| `?`       | `question`   | Operador condicional         |
| `:`       | `colon`      | Operador condicional         |
| `}`       | `rbrace`     | Delimitador                  |
| `/* … */` | -            | Comentário                   |

> **Observação:** Comentários são ignorados pelo analisador léxico e não geram tokens.

## Expressões Regulares

| Token       | Expressão Regular                     | Exemplo                  |
|-------------|---------------------------------------|--------------------------|
| INT         | `int`                                 | `int max`                |
| return      | `return`                              | `return i>j? i : j`      |
| id          | `[a-zA-Z_][a-zA-Z0-9_]*`              | `max, i, j`              |
| num         | `[0-9]+`                              | `42`                     |
| lparen      | `\(`                                  | `(`                      |
| rparen      | `\)`                                  | `)`                      |
| comma       | `,`                                   | `i, j`                   |
| semicolon   | `;`                                   | `;`                      |
| lbrace      | `\{`                                  | `{`                      |
| rbrace      | `\}`                                  | `}`                      |
| gt          | `>`                                   | `i>j`                    |
| question    | `\?`                                  | `i>j?`                   |
| colon       | `:`                                   | `:`                      |
| comment     | `\/\*[^*]*\*+([^/*][^*]*\*+)*\/`      | `/* retorna o maior */`  |

## Autômatos

### a) Número Inteiro (`[0-9]+`)

#### NFA (Autômato Finito Não-determinístico)
![NFA para números inteiros](figuras/nfa_numero_inteiro.png)

#### DFA (Autômato Finito Determinístico)
![DFA para números inteiros](figuras/dfa_numero_inteiro.png)

---

### b) Comentário (`\/\*.*?\*\/`)

#### NFA (Autômato Finito Não-determinístico)
![NFA para comentários](figuras/nfa_comentario.png)

#### DFA (Autômato Finito Determinístico) (simplificado)
![DFA simplificado para comentários](figuras/dfa_comentario_simplificado.png)

---

### Nota sobre Transições "outro"

Em autômatos finitos (NFAs e DFAs), a transição rotulada como **"outro"** (ou "qualquer outro símbolo não especificado") é uma transição genérica que captura todos os caracteres que não estão definidos explicitamente nas arestas do autômato.
