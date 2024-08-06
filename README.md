# Desafio do HackerRank para a Ubots

[Link do desafio](https://www.hackerrank.com/challenges/detect-whether-a-linked-list-contains-a-cycle/problem?isFullScreen=true)

Este repositório contém uma implementação em Java para detectar ciclos em uma lista ligada simples, pelo desafio `Cycle Detection`. O algoritmo utilizado é o Algoritmo de Detecção de Ciclo de Floyd, também conhecido como algoritmo da Tartaruga e Lebre. Este método determina eficientemente se existe um ciclo na lista.

## Explicação do Algoritmo

A função `hasCycle` é projetada para detectar um ciclo em uma lista ligada simples. A função recebe a cabeça da lista como entrada e retorna um booleano indicando se há um ciclo presente.

### Assinatura da Função

```java
static boolean hasCycle(SinglyLinkedListNode head)
```

### Parâmetros

- `head`: Uma referência ao nó cabeça da lista ligada simples.

### Valor de Retorno

- `true`: Se houver um ciclo na lista.
- `false`: Se não houver um ciclo na lista.

### Como o Algoritmo Funciona

1. **Verificação Inicial**:
    - A função primeiro verifica se a lista está vazia (`head == null`). Se estiver, retorna `false` imediatamente, pois uma lista vazia não pode conter um ciclo.
2. **Inicialização**:
    - Dois ponteiros, `fast` e `slow`, são inicializados. O ponteiro `slow` começa na cabeça da lista, e o ponteiro `fast` começa no segundo nó (`head.next`).
3. **Travessia**:
    - A função entra em um loop `while` que continua enquanto `fast` e `fast.next` não forem `null`.
    - Dentro do loop, verifica se `fast` e `slow` estão apontando para o mesmo nó. Se estiverem, um ciclo é detectado, e a função retorna `true`.
    - Caso contrário, `fast` avança dois nós por vez (`fast = fast.next.next`) e `slow` avança um nó por vez (`slow = slow.next`).
4. **Sem Ciclo**:
    - Se o loop terminar sem que `fast` e `slow` se encontrem, a função retorna `false`, indicando que não há ciclo na lista.
