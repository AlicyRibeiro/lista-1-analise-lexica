## a) Strings de `a`’s e `b`’s onde há mais `a`’s do que `b`’s

Para verificar se o número de ocorrências de `a` é maior que o de `b`, a linguagem precisa **contar** a quantidade de cada símbolo e **compará-las**.

Autômatos finitos, que reconhecem linguagens regulares, **não possuem memória suficiente** para armazenar contagens arbitrárias de símbolos. Eles operam com um número finito de estados, o que impossibilita comparações quantitativas desse tipo.

Esse tipo de verificação exige um modelo computacional mais poderoso, como um **autômato com pilha**, característico das **linguagens livres de contexto**.

### Exemplos
**String válida:**  
- `aaab` (3 `a`’s e 1 `b`)

**String inválida:**  
- `aabb` (2 `a`’s e 2 `b`’s)

---

## b) Strings de `a`’s e `b`’s que são palíndromos

Palíndromos exigem que a string seja igual à sua reversa, o que implica **comparar símbolos simetricamente opostos**, como o primeiro com o último, o segundo com o penúltimo, e assim por diante.

Um autômato finito **não consegue armazenar os símbolos iniciais** da entrada para compará-los com os símbolos finais quando a string possui tamanho arbitrário. Essa limitação impede o reconhecimento de palíndromos por expressões regulares.

Esse tipo de linguagem requer um **autômato com pilha**, que permite armazenar informações intermediárias durante a leitura da entrada.

### Exemplos
**Strings válidas:**  
- `abba`  
- `aabaa`

**String inválida:**  
- `abab`

---

## c) Programas Java sintaticamente corretos

A sintaxe da linguagem Java envolve **estruturas recursivas e aninhadas**, como blocos delimitados por chaves `{ ... }`, parênteses `( ... )` e outros construtores hierárquicos.

Expressões regulares **não conseguem lidar com estruturas aninhadas** ou com a verificação de correspondência correta entre símbolos de abertura e fechamento, como garantir que cada `(` tenha um `)` correspondente.

Linguagens de programação, como Java, são descritas por **gramáticas mais poderosas**, geralmente **livres de contexto** ou até **sensíveis ao contexto**, sendo reconhecidas por autômatos mais complexos do que autômatos finitos.

---

## Observação Geral

Expressões regulares definem **linguagens regulares**, que são reconhecidas por **autômatos finitos determinísticos (AFDs)**. No entanto, algumas linguagens não são regulares porque exigem:

- Contagem precisa de ocorrências
- Comparações entre partes distantes da string
- Memória ilimitada

Essas características estão além da capacidade de um autômato finito.

**Exemplo clássico:**  
> Strings com mais `a`’s do que `b`’s  

Um autômato finito não consegue armazenar quantos `a`’s ou `b`’s já foram lidos, tornando esse tipo de linguagem não regular.
- `abab`

