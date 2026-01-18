## Questão 8 — Análise Léxica

Crie tokens apropriados e realize a análise léxica dos seguintes códigos.

---

### a) Pascal

#### Código-fonte

```pascal
function max (i, j : integer ) : integer ;
{ retorna maior dos inteiros entre i e j }
begin
    if i > j then max := i
    else max := j
end;
```

## Tabela de Tokens

| Lexema    | Token     | Categoria                  |
|-----------|-----------|----------------------------|
| function  | FUNCTION  | Palavra-chave              |
| max       | ID        | Identificador (função)     |
| (         | LPAREN    | Delimitador                |
| i         | ID        | Identificador (parâmetro)  |
| ,         | COMMA     | Delimitador                |
| j         | ID        | Identificador (parâmetro)  |
| :         | COLON     | Delimitador                |
| integer   | INTEGER   | Palavra-chave              |
| )         | RPAREN    | Delimitador                |
| ;         | SEMICOLON | Delimitador                |
| begin     | BEGIN     | Palavra-chave              |
| if        | IF        | Palavra-chave              |
| >         | GT        | Operador relacional        |
| then      | THEN      | Palavra-chave              |
| :=        | ASSIGN    | Operador de atribuição     |
| else      | ELSE      | Palavra-chave              |
| end       | END       | Palavra-chave              |
| { … }     | COMMENT   | Comentário                 |

> **Observação:** Comentários são ignorados pelo analisador léxico (Seção 3.1.5 — comentários não geram tokens).


## Expressões Regulares

| Token       | Expressão Regular             | Exemplo           |
|-------------|-------------------------------|-------------------|
| FUNCTION    | `function`                    | `function max`    |
| BEGIN       | `begin`                       | `begin`           |
| END         | `end`                         | `end`             |
| IF          | `if`                          | `if i > j`        |
| THEN        | `then`                        | `then max := i`   |
| ELSE        | `else`                        | `else max := j`   |
| INTEGER     | `integer`                     | `i : integer`     |
| ID          | `[a-zA-Z][a-zA-Z0-9_]*`       | `max, i, j`       |
| NUM         | `[0-9]+`                      | `10`              |
| LPAREN      | `\(`                          | `(i, j)`          |
| RPAREN      | `\)`                          | `)`               |
| COMMA       | `,`                           | `,`               |
| COLON       | `:`                           | `:`               |
| SEMICOLON   | `;`                           | `;`               |
| ASSIGN      | `:=`                          | `max := i`        |
| GT          | `>`                           | `i > j`           |
| COMMENT     | `\{[^\}]*\}`                  |                   |

## Prioridade e Ambiguidade

### Maior casamento possível (guloso)
O analisador léxico sempre escolhe o lexema mais longo que corresponda a uma expressão regular.

**Exemplos:**
- `if8` é reconhecido como um identificador (não `if` + `8`)
- `:=` é reconhecido como um único token (não `:` + `=`)

### Prioridade de tokens
Se duas expressões regulares casarem o mesmo lexema, a primeira definida na especificação tem prioridade.

---


## Autômatos

### a) Operador de atribuição (`:=`)

#### NFA (Autômato Finito Não-determinístico)
![NFA para o operador :=](figuras/alternativa-a-nfa.png)

#### DFA (Autômato Finito Determinístico)
![DFA para o operador :=](figuras/alternativa-a-dfa.png)

### b) Identificador (`[a-zA-Z][a-zA-Z0-9_]*`)

#### NFA (Autômato Finito Não-determinístico)
![NFA para identificador](figuras/nfa_identifier.png)

#### DFA (Autômato Finito Determinístico)
![DFA para identificador](figuras/dfa_identifier.png)

---



Quando um autômato encontra um símbolo que não corresponde a nenhuma transição válida, ele segue para um estado de erro (`q_erro`), indicando que o lexema atual é inválido.
