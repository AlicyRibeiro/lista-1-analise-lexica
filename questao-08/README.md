## Questão 8 — Análise Léxica

Crie tokens apropriados e realize a análise léxica dos seguintes códigos.

---

### a) Pascal

#### Código-fonte

```pascal
function max (i, j : integer ) : integer ;
{retorna o maior dos inteiros entre i e j }
begin
    if i > j then max := i
    else max := j
end;
```


### b) C

#### Código-fonte

```
int max (i, j) int i, j;
/* retorna o maior dos inteiros entre i e j */
{
    return i>j? i : j;
}

```


### c) Fortran 77

#### Código-fonte   

FUNCTION MAX (I, J)
C RETORNA O MAIOR DOS INTEIROS ENTRE I E J
    IF (I .GT. J) THEN
    MAX = I
    ELSE
    MAX = J
    END IF
RETURN
END