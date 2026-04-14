# Lista de Exercícios - Estruturas de Dados Pilha (Stack)

Este documento contém uma progressão de exercícios sobre Pilhas (Stacks), organizados por nível de dificuldade. O foco é o desenvolvimento da lógica de programação. Cada problema apresenta sua descrição, uma sugestão de passos para a solução e exemplos de entrada e saída, permitindo que você os implemente na linguagem de programação de sua escolha.

<details>
<summary>🟢 Nível 1 - Fácil</summary>

### 1. O Problema da Celebridade

**Descrição:** Em uma festa com `N` pessoas, uma celebridade é definida como alguém que não conhece ninguém na festa, mas todos na festa a conhecem. Dada uma matriz quadrada `M` onde `M[i][j] = 1` significa que a pessoa `i` conhece a pessoa `j`, encontre o índice da celebridade (ou retorne -1 se não houver).

**Passo a Passo:**
1. Adicione todas as pessoas (índices de 0 a N-1) em uma pilha.
2. Remova duas pessoas da pilha (A e B).
3. Verifique na matriz se A conhece B. Se sim, A não pode ser a celebridade; coloque B de volta na pilha. Se A não conhece B, B não pode ser a celebridade; coloque A de volta na pilha.
4. Repita até sobrar apenas uma pessoa na pilha.
5. Verifique a pessoa restante iterando pela matriz para garantir que ela não conhece ninguém e todos a conhecem.

**Input:** `M = [[0, 1, 0], [0, 0, 0], [0, 1, 0]]`  
**Output:** `1` (A pessoa 1 não conhece ninguém, mas as pessoas 0 e 2 conhecem a 1)

### 2. Fila usando Pilhas

**Descrição:** Implemente o comportamento de uma Fila (Queue) tradicional — que obedece à regra FIFO (First-In, First-Out) — utilizando apenas duas Pilhas (Stacks).

**Passo a Passo:**
1. Crie duas pilhas: `Pilha1` (para inserção) e `Pilha2` (para remoção).
2. Para a operação de *Enqueue* (inserir): Insira o elemento diretamente na `Pilha1`.
3. Para a operação de *Dequeue* (remover): Se a `Pilha2` estiver vazia, desempilhe todos os elementos da `Pilha1` e empilhe-os na `Pilha2`. Em seguida, remova e retorne o topo da `Pilha2`.

**Input:** `Enqueue(1), Enqueue(2), Enqueue(3), Dequeue(), Dequeue()`  
**Output:** `1, 2`

### 3. Duas pilhas em um array

**Descrição:** Implemente duas pilhas independentes compartilhando o mesmo array de tamanho `N`, de modo que nenhuma das pilhas acuse "Overflow" (estouro de capacidade) a menos que o array inteiro esteja cheio.

**Passo a Passo:**
1. Inicialize um array de tamanho `N`.
2. Crie dois ponteiros: `topo1` iniciando em `0` (início do array) e `topo2` iniciando em `N - 1` (final do array).
3. Para *Push1*: Verifique se há espaço (`topo1 < topo2 - 1`). Se sim, incremente `topo1` e adicione o valor.
4. Para *Push2*: Verifique se há espaço. Se sim, decremente `topo2` e adicione o valor.
5. Para *Pop*: Retire do respectivo topo e ajuste o ponteiro correspondente.

**Input:** Tamanho = `5`, `Push1(5)`, `Push2(10)`, `Push2(15)`, `Push1(11)`, `Push2(7)`  
**Output:** O array ficará cheio `[5, 11, 7, 15, 10]`. Um novo *Push* deverá retornar um erro de Overflow.

### 4. Infixa para Posfixa

**Descrição:** Converta uma expressão matemática comum (notação Infixa, ex: `A + B`) para a notação Posfixa (ex: `A B +`), onde os operadores vêm após os operandos.

**Passo a Passo:**
1. Percorra a string da expressão da esquerda para a direita. Se for operando (letra/número), adicione ao resultado.
2. Se for `(`, coloque na pilha. Se for `)`, desempilhe para o resultado até achar um `(`.
3. Se for operador (`+`, `-`, `*`, `/`), desempilhe para o resultado os operadores da pilha que tiverem precedência maior ou igual, e então empilhe o operador atual.
4. Ao final, desempilhe tudo que restou para o resultado.

**Input:** `"a+b*c"`  
**Output:** `"abc*+"`

### 5. Prefixa para Infixa

**Descrição:** Converta uma expressão Prefixa (operadores antes, ex: `+ A B`) para notação Infixa (`(A + B)`).

**Passo a Passo:**
1. Leia a string de trás para frente (da direita para a esquerda).
2. Se for operando, empilhe.
3. Se for operador, desempilhe dois operandos (op1 e op2), formate a string `(op1 operador op2)` e empilhe esse novo conjunto.
4. O último elemento restante na pilha é o resultado.

**Input:** `"*+AB-CD"`  
**Output:** `"((A+B)*(C-D))"`

### 6. Prefixa para Posfixa

**Descrição:** Converta uma expressão Prefixa (ex: `+ A B`) para notação Posfixa (`A B +`).

**Passo a Passo:**
1. Percorra a expressão de trás para frente.
2. Se for operando, coloque na pilha.
3. Se for operador, retire dois operandos da pilha, concatene-os na ordem com o operador no final (`op1 + op2 + operador`) e empilhe o resultado.

**Input:** `"*+AB-CD"`  
**Output:** `"AB+CD-*"`

### 7. Posfixa para Prefixa

**Descrição:** Converta uma expressão Posfixa (ex: `A B +`) para notação Prefixa (`+ A B`).

**Passo a Passo:**
1. Percorra a expressão da esquerda para a direita.
2. Se for operando, coloque na pilha.
3. Se for operador, retire dois operandos (o último a entrar é op2, o anterior é op1), coloque o operador antes deles (`operador + op1 + op2`) e empilhe.

**Input:** `"AB+CD-*"`  
**Output:** `"*+AB-CD"`

### 8. Posfixa para Infixa

**Descrição:** Converta uma expressão Posfixa para notação Infixa com parênteses.

**Passo a Passo:**
1. Percorra a expressão da esquerda para a direita.
2. Se for operando, coloque na pilha.
3. Se for operador, retire dois valores (op2 e op1), formate como `(op1 operador op2)` e coloque de volta na pilha.

**Input:** `"ab*c+"`  
**Output:** `"((a*b)+c)"`

### 9. Infixa para Prefixa

**Descrição:** Converta uma expressão em notação Infixa para notação Prefixa.

**Passo a Passo:**
1. Inverta a string inteira (trocando `(` por `)` e vice-versa).
2. Aplique o mesmo algoritmo de Infixa para Posfixa nesta string invertida.
3. Inverta o resultado obtido. O resultado final é a expressão Prefixa.

**Input:** `"(A-B/C)*(A/K-L)"`  
**Output:** `"*-A/BC-/AKL"`

### 10. Verificar parênteses balanceados

**Descrição:** Verifique se uma expressão com colchetes, chaves e parênteses `()`, `{}`, `[]` está corretamente balanceada e aninhada.

**Passo a Passo:**
1. Percorra a string. Se for caractere de abertura, empilhe.
2. Se for caractere de fechamento, verifique se a pilha está vazia (se sim, é inválido). Retire o topo da pilha e verifique se forma um par válido com o caractere atual.
3. No final da iteração, se a pilha estiver vazia, está balanceada; caso contrário, não está.

**Input:** `"{[()]}"`  
**Output:** `Verdadeiro (True)`

### 11. Avaliação de Expressão Posfixa

**Descrição:** Dado um conjunto de números e operadores matemáticos em notação posfixa, calcule o resultado da expressão.

**Passo a Passo:**
1. Percorra a string da esquerda para a direita.
2. Se for um número, empilhe.
3. Se for um operador, retire os dois números do topo da pilha, aplique a operação matemática entre eles (lembrando que o primeiro a sair é o operando da direita) e empilhe o resultado.
4. O topo final da pilha será o resultado do cálculo.

**Input:** `"231*+9-"`  
**Output:** `-4` (Explicação: 3×1=3 → 2+3=5 → 5-9=-4)

### 12. Inverter uma pilha usando recursão

**Descrição:** Inverta os elementos de uma pilha sem utilizar nenhuma estrutura de dados adicional (como arrays, filas ou loops do tipo while/for), usando apenas chamadas recursivas.

**Passo a Passo:**
1. Crie uma função recursiva `inverter(pilha)`. Se a pilha não estiver vazia, guarde o topo e chame `inverter(pilha)` novamente.
2. Crie uma função auxiliar `inserir_no_fundo(pilha, elemento)`. Se a pilha estiver vazia, empilhe o elemento. Se não, guarde o topo, chame `inserir_no_fundo` e depois devolva o topo guardado.
3. Na volta da recursão principal, chame a função auxiliar para colocar o item guardado no fundo.

**Input:** Topo → `[1, 2, 3, 4]` ← Fundo  
**Output:** Topo → `[4, 3, 2, 1]` ← Fundo

### 13. Invertendo os primeiros K elementos de uma Fila

**Descrição:** Dada uma fila de inteiros e um número `K`, inverta a ordem dos primeiros `K` elementos da fila, mantendo o restante na mesma ordem.

**Passo a Passo:**
1. Remova (dequeue) os primeiros `K` elementos da fila e coloque-os em uma Pilha.
2. Retire (pop) os elementos da pilha um por um e coloque-os (enqueue) de volta na fila.
3. Agora, os `K` elementos estão no final da fila. Calcule `Tamanho_da_fila - K`. Remova essa quantidade de elementos da frente da fila e coloque-os imediatamente no final da fila.

**Input:** Fila: `[1, 2, 3, 4, 5]`, K = `3`  
**Output:** `[3, 2, 1, 4, 5]`

### 14. Uma Estrutura de Dados com Operações O(1)

**Descrição:** Crie uma estrutura de dados que permita empilhar (push), desempilhar (pop), visualizar o topo (top) e obter o elemento mínimo (getMin) em tempo constante (Big O(1)).

**Passo a Passo:**
1. Use duas pilhas: `PilhaPrincipal` e `PilhaMinimos`.
2. No `Push(x)`: Insira `x` na `PilhaPrincipal`. Compare `x` com o topo da `PilhaMinimos`; se `x` for menor ou igual, insira `x` nela também.
3. No `Pop()`: Retire da `PilhaPrincipal`. Se o valor retirado for igual ao topo da `PilhaMinimos`, retire dela também.
4. O `getMin()` simplesmente retorna o topo da `PilhaMinimos`.

**Input:** `Push(18), Push(19), Push(15), getMin(), Pop(), getMin()`  
**Output:** `15` (após o primeiro getMin) e `18` (após o segundo getMin)

</details>

<details>
<summary>🟠 Nível 2 - Médio</summary>

### 15. K Pilhas em um Array

**Descrição:** Implemente `K` pilhas utilizando um único array bidimensional ou arrays auxiliares, otimizando o espaço para que não haja erro a menos que o array total esteja cheio.

**Passo a Passo:**
1. Use três arrays auxiliares: `dados[]` (para guardar valores), `topo[]` (guarda o índice do topo de cada uma das K pilhas) e `prox[]` (guarda o índice do próximo elemento na pilha, ou o próximo espaço livre).
2. Mantenha uma variável `livre` indicando o primeiro índice disponível no array `dados`.
3. Para `Push(pilha_k, valor)`: Encontre a posição `livre`, atualize `livre` para o próximo espaço apontado por `prox[livre]`. Guarde o valor. Atualize `prox` para apontar para o `topo` antigo, e atualize o `topo` da pilha_k para este novo índice.

**Input:** Array tamanho 10, K = 3. `Push(0, 15)` (na pilha 0), `Push(2, 45)` (na pilha 2)  
**Output:** Nenhuma saída específica além de evitar overflow prematuro e manter as K estruturas separadas logicamente.

### 16. Pilha Mesclável

**Descrição:** Desenhe uma estrutura de pilha que suporte adicionar, remover e mesclar (merge) duas pilhas em tempo O(1).

**Passo a Passo:**
1. Como arrays não permitem mesclagem O(1), implemente as pilhas usando Listas Encadeadas (Linked Lists) circulares ou mantendo ponteiros para o nó `topo` e o nó `base`.
2. Para mesclar `PilhaA` na `PilhaB`: aponte a `base` da `PilhaA` para o `topo` da `PilhaB`.
3. O novo topo da `PilhaB` passa a ser o topo da `PilhaA`.

**Input:** Pilha 1: `[1, 2]`, Pilha 2: `[3, 4]`  
**Output:** Pilha 2 fundida: `[1, 2, 3, 4]`

### 17. Pilha usando Filas

**Descrição:** Implemente o comportamento de uma Pilha (LIFO) utilizando duas Filas (Queue).

**Passo a Passo:**
1. Usando a estratégia onde o `Push` é O(1) e o `Pop` é O(N):
2. No `Push`: insira o elemento na `Fila1`.
3. No `Pop`: mova todos os elementos da `Fila1` para a `Fila2`, exceto o último. Guarde esse último elemento (ele é o retorno). Em seguida, troque os nomes de `Fila1` e `Fila2` (ou mova os itens de volta).

**Input:** `Push(1), Push(2), Push(3), Pop(), Pop()`  
**Output:** `3, 2`

### 18. Elemento Menor Anterior

**Descrição:** Dado um array, para cada elemento encontre o primeiro elemento menor que ele que está à sua esquerda. Se não existir, retorne -1.

**Passo a Passo:**
1. Percorra o array da esquerda para a direita. Mantenha uma pilha para guardar elementos visitados.
2. Para cada elemento, enquanto a pilha não estiver vazia e o topo for maior ou igual ao elemento atual, desempilhe (pop).
3. Se a pilha ficar vazia, não há menor à esquerda (-1). Se não, o topo é o menor. Empilhe o elemento atual para a próxima iteração.

**Input:** `[4, 10, 5, 8, 20, 15]`  
**Output:** `[-1, 4, 4, 5, 8, 8]`

### 19. Próximo Elemento Maior

**Descrição:** Dado um array, para cada elemento encontre o primeiro elemento maior que ele à sua direita. Se não existir, retorne -1.

**Passo a Passo:**
1. Percorra o array de trás para frente (direita para esquerda). Mantenha uma pilha.
2. Enquanto a pilha não estiver vazia e o topo da pilha for menor ou igual ao elemento atual, desempilhe.
3. Se a pilha ficou vazia, retorne -1 para este índice. Se não, o topo é a resposta.
4. Empilhe o elemento atual.

**Input:** `[4, 5, 2, 25]`  
**Output:** `[5, 25, 25, -1]`

### 20. Problema do Intervalo de Ações (Stock Span)

**Descrição:** Dado o preço diário de uma ação ao longo de N dias, calcule a "extensão" (span) da ação para cada dia. O span de um dia `i` é o número máximo de dias consecutivos antes dele (incluindo o próprio dia) em que o preço da ação foi menor ou igual ao preço no dia `i`.

**Passo a Passo:**
1. Crie uma pilha que armazenará os **índices** dos dias. Crie um array para os resultados.
2. Percorra os preços. Enquanto a pilha não estiver vazia e o preço do dia atual for maior ou igual ao preço do índice no topo da pilha, desempilhe.
3. Se a pilha ficar vazia, o span é `(índice atual + 1)`. Caso contrário, o span é `(índice atual - índice no topo da pilha)`.
4. Empilhe o índice atual.

**Input:** `[100, 80, 60, 70, 60, 75, 85]`  
**Output:** `[1, 1, 1, 2, 1, 4, 6]`

### 21. Prédios Voltados para o Sol

**Descrição:** Dado um array que representa as alturas de prédios consecutivos, conte quantos prédios conseguirão ver o sol nascendo à esquerda. Um prédio vê o sol se não houver um prédio maior ou igual à sua esquerda.

**Passo a Passo:**
1. Considere o primeiro prédio do array como o atual prédio mais alto (ele sempre vê o sol). Contador = 1.
2. Percorra o restante do array. Se a altura do prédio atual for estritamente maior que a altura máxima registrada até agora, incremente o contador e atualize a altura máxima.

**Input:** `[7, 4, 8, 2, 9]`  
**Output:** `3` (Prédios de altura 7, 8 e 9)

### 22. Próximo Menor do Próximo Maior

**Descrição:** Para cada elemento do array, encontre o "Próximo Elemento Maior" (à direita) e, a partir deste, encontre o "Próximo Elemento Menor" (ainda mais à direita). Se alguma das partes falhar, retorne -1.

**Passo a Passo:**
1. Resolva em duas etapas usando pilhas. Primeiro, crie um array `ProxMaior` que guarda o índice do Próximo Maior Elemento para cada item (usando a lógica do exercício 19).
2. Crie um array `ProxMenor` que guarda a resposta do Próximo Menor Elemento (lógica análoga, guardando índices).
3. Para cada elemento `i` do array original: se `ProxMaior[i]` não for -1, busque `ProxMenor[ProxMaior[i]]`. Caso contrário, -1.

**Input:** `[5, 1, 9, 2, 5, 1, 7]`  
**Output:** `[2, 2, -1, 1, -1, -1, -1]`

### 23. Próxima Maior Frequência

**Descrição:** Dado um array, para cada elemento encontre o primeiro elemento à direita cuja frequência em todo o array seja estritamente maior que a frequência do elemento atual.

**Passo a Passo:**
1. Conte a frequência de todos os elementos usando um Mapa/Dicionário de frequências.
2. Crie um array de resultados. Percorra o array original da direita para a esquerda.
3. Mantenha uma pilha. Verifique o topo: enquanto não estiver vazia e a frequência do elemento no topo for menor ou igual à frequência do elemento atual, desempilhe.
4. Se esvaziar, não há resposta (-1). Se não, a resposta é o valor do topo. Empilhe o elemento atual.

**Input:** `[1, 1, 2, 3, 4, 2, 1]` (Frequências: 1→3, 2→2, 3→1, 4→1)  
**Output:** `[-1, -1, 1, 2, 2, 1, -1]`

### 24. Produto Máximo de Índices do Maior à Esquerda e Direita

**Descrição:** Para cada elemento em um array, encontre os índices (base 1) do "Próximo Maior à Esquerda" e "Próximo Maior à Direita". O valor de um índice será 0 se não houver maior. Calcule o produto dos dois índices e retorne o maior produto obtido no array.

**Passo a Passo:**
1. Crie o array `Esquerda` e `Direita`. Use pilhas para preenchê-los armazenando índices.
2. Para achar os da esquerda, percorra do índice 0 ao fim. Para a direita, percorra do fim até 0.
3. Se não encontrar o maior, o índice anotado é 0.
4. Multiplique `Esquerda[i] * Direita[i]` (lembrando que são índices na base-1, ou seja, `index+1`) e acompanhe o máximo valor.

**Input:** `[5, 4, 3, 4, 5]`  
**Output:** `8` (Para o valor 3 no índice 2, Esq = índice 1, Dir = índice 4. Produto 1×4=4. Verificar detalhadamente para o máximo)

### 25. Torre de Hanói Iterativa

**Descrição:** Resolva o famoso problema da Torre de Hanói (mover N discos do pino Origem para o Destino usando um pino Auxiliar) usando apenas pilhas e laços de repetição (sem recursividade).

**Passo a Passo:**
1. Crie três pilhas: Origem, Destino e Auxiliar. Empilhe os discos de N a 1 na Origem.
2. Calcule o número total de movimentos: `2^N - 1`.
3. Se `N` for par, troque o Destino pelo Auxiliar mentalmente para o algoritmo.
4. Em um loop de `i = 1` até o total de movimentos:
  - Se `i % 3 == 1`: Mova um disco entre Origem e Destino (aquele que for menor ou se um estiver vazio).
  - Se `i % 3 == 2`: Mova um disco entre Origem e Auxiliar.
  - Se `i % 3 == 0`: Mova um disco entre Auxiliar e Destino.

**Input:** N = `3` discos  
**Output:** Sequência de movimentos, ex: "Mover disco 1 da Origem para Destino"

### 26. Ordenar uma Pilha

**Descrição:** Dada uma pilha com elementos desordenados, ordene a pilha de modo que os menores valores fiquem no topo. Você pode usar apenas uma pilha temporária adicional.

**Passo a Passo:**
1. Crie uma `PilhaTemp`.
2. Enquanto a Pilha original não estiver vazia, dê *Pop* no valor (chame de `tmp`).
3. Enquanto a `PilhaTemp` não estiver vazia e o seu topo for maior que `tmp`, dê um *Pop* na `PilhaTemp` e empurre para a Pilha original.
4. Empurre `tmp` para a `PilhaTemp`. Ao final, passe os itens de `PilhaTemp` para a original.

**Input:** Topo → `[34, 3, 31, 98, 92, 23]`  
**Output:** Topo → `[3, 23, 31, 34, 92, 98]`

### 27. Inverter uma Pilha (Sem Espaço Extra)

**Descrição:** Inverta a pilha em tempo O(N²) sem usar bibliotecas, pilhas extras ou strings.

**Passo a Passo:**
1. Resolva puramente com a estrutura de recursão, que utiliza a própria pilha de execução do sistema em vez de estruturas declaradas. Vide exercício 12.
2. Ou implemente a pilha subjacente como uma Lista Encadeada e simplesmente reverta os ponteiros da lista em tempo O(N).

**Input:** `[1, 2, 3]`  
**Output:** `[3, 2, 1]`

### 28. Deletar o meio de uma pilha

**Descrição:** Remova o elemento do meio de uma pilha. Se a pilha tiver tamanho `N`, o meio é calculado arredondando para baixo (ex: para N=5, remover índice 2; para N=4, remover índice 2).

**Passo a Passo:**
1. Calcule o tamanho N e determine o alvo: `K = (N / 2) + 1` (contando do topo).
2. Escreva uma função recursiva ou use uma pilha auxiliar que remova o elemento do topo. Decremente um contador.
3. Se o contador chegar ao alvo, remova definitivamente o elemento (sem guardar).
4. Recoloque os elementos anteriores retirados na pilha original.

**Input:** Pilha: `[1, 2, 3, 4, 5]` (5 no topo)  
**Output:** `[1, 2, 4, 5]`

### 29. Verificar se a fila é ordenável

**Descrição:** Dada uma Fila de inteiros, verifique se é possível ordenar a fila para outra fila, operando e utilizando apenas uma Pilha auxiliar, de modo que do outro lado saiam os números de 1 a N na ordem.

**Passo a Passo:**
1. Defina um `esperado` iniciando em 1.
2. Enquanto a fila original tiver itens: observe a frente da fila. Se for o valor `esperado`, remova e mande para a saída. Aumente o `esperado`.
3. Caso contrário, verifique o topo da pilha. Se o topo for o `esperado`, desempilhe e mande para a saída. Aumente o `esperado`.
4. Se nenhum dos dois for, pegue a frente da fila e jogue na pilha.
5. Ao final da fila, enquanto a pilha não estiver vazia, verifique o topo. Se for igual ao `esperado`, desempilhe. Se for diferente, a ordenação é impossível.

**Input:** Fila: `[5, 1, 2, 3, 4]`  
**Output:** `Verdadeiro (True)`

### 30. Verificar se o array é ordenável com pilha

**Descrição:** Determinar se um array (uma permutação de números de 1 a N) pode ser ordenado usando exatamente uma pilha (conhecido como Stack Sortable). O mesmo conceito do problema 29, mas os dados de entrada são um array.

**Passo a Passo:** A lógica é exatamente a mesma da Fila ordenável do exercício 29. Itere pelo array. Jogue números na pilha, e caso o topo da pilha bata com o próximo número ordenado aguardado, desempilhe. Retorne Falso se a pilha travar com algo fora de ordem.

**Input:** Array: `[2, 3, 1]`  
**Output:** `Falso (False)`

### 31. Índice do colchete de fechamento

**Descrição:** Dada uma string com colchetes balanceados e um índice `i` indicando a posição de um colchete de abertura `[`, encontre o índice numérico do colchete de fechamento `]` correspondente.

**Passo a Passo:**
1. Se o caractere no índice `i` não for `[`, retorne erro.
2. Inicialize um `contador = 1`.
3. Faça um loop do índice `i+1` até o final da string.
4. Se achar um `[`, incremente o contador. Se achar um `]`, decremente o contador.
5. Quando o contador chegar a 0, retorne a posição atual.

**Input:** `"[ABC[23]][89]"`, índice inicial `0`  
**Output:** `8` (O último colchete do primeiro bloco)

### 32. Diferença Máxima entre o menor mais próximo à esquerda e à direita

**Descrição:** Dado um array, para cada item `i` encontre o menor à esquerda `LE[i]` e o menor à direita `RE[i]`. Se não existir, assume-se valor 0. Encontre o maior valor absoluto da diferença `|LE[i] - RE[i]|`.

**Passo a Passo:**
1. Crie o array `LE` percorrendo o array da esquerda para direita usando uma pilha (descartando maiores para encontrar o menor).
2. Crie o array `RE` percorrendo da direita para esquerda usando o mesmo método.
3. Zere os casos em que a pilha esvaziou.
4. Itere pelo array calculando `Max = max(Max, abs(LE[i] - RE[i]))`.

**Input:** `[2, 4, 8, 7, 7, 9, 3]`  
**Output:** `4`

### 33. Deletar palavras iguais consecutivas

**Descrição:** Dada uma sequência de palavras, se houver duas palavras consecutivas idênticas, destrua-as. Se após a destruição novas palavras adjacentes idênticas se formarem, destrua-as também, até não sobrar nenhum par.

**Passo a Passo:**
1. Percorra o array de palavras.
2. Crie uma pilha vazia.
3. Para cada palavra, se a pilha estiver vazia, empilhe a palavra.
4. Se não estiver vazia, compare a palavra atual com o topo da pilha. Se forem iguais, retire do topo (destruição). Se forem diferentes, empilhe a palavra atual.
5. O número de itens na pilha no final é a quantidade de palavras que restaram.

**Input:** `["tom", "jerry", "jerry", "tom"]`  
**Output:** `0` (Ambos os pares se destroem)

</details>

<details>
<summary>🔴 Nível 3 - Difícil</summary>

### 34. Maior Retângulo em um Histograma

**Descrição:** Dado um array de inteiros que representa as alturas de barras em um histograma contíguo (largura de cada barra = 1), encontre a área do maior retângulo que pode ser formado dentro desse histograma.

**Passo a Passo:**
1. Mantenha uma pilha para armazenar índices das barras.
2. Itere pelo array. Enquanto o elemento atual for menor que a altura do índice no topo da pilha, este é o limite direito para o retângulo da barra do topo.
3. Dê *Pop* na barra do topo. Calcule sua área: Altura = `histograma[topo_removido]`. A largura é `i` (se pilha vazia) ou `i - novo_topo_da_pilha - 1`. Compare com a Área Máxima salva e guarde a maior.
4. Quando acabar o loop, repita o processo de pop e cálculo de área até que a pilha esteja vazia (limite direito = final do array).

**Input:** `[2, 1, 5, 6, 2, 3]`  
**Output:** `10` (Retângulo formado pelas barras de altura 5 e 6)

### 35. Soma dos Máximos de todos os Subarrays

**Descrição:** Dado um array, considere todos os subarrays possíveis. Encontre o elemento máximo de cada subarray e some todos esses valores máximos.

**Passo a Passo:**
1. Para cada elemento `i`, precisamos saber em quantos subarrays ele é o valor máximo absoluto.
2. Usando pilhas, encontre o índice do "Próximo Maior Elemento à Esquerda" (`L`) e "Próximo Maior Elemento à Direita" (`R`).
3. O número de subarrays em que `arr[i]` é o máximo será dado pela fórmula: `(i - L) * (R - i)`.
4. Multiplique este número de subarrays pela grandeza do elemento (`arr[i]`) e acumule na soma total.

**Input:** `[1, 3, 2]`  
**Output:** `15` (Subarrays: [1]=1, [3]=3, [2]=2, [1,3]=3, [3,2]=3, [1,3,2]=3. Soma: 1+3+2+3+3+3=15)

### 36. Máximo dos Mínimos para cada tamanho de janela

**Descrição:** Dado um array inteiro de tamanho `N`, gere um array de resposta contendo o "maior valor entre os valores mínimos" para cada janela deslizante de tamanho `1` a `N`.

**Passo a Passo:**
1. Use pilhas para encontrar o Próximo Menor à Esquerda e à Direita de cada índice.
2. A diferença `(Direita - Esquerda - 1)` é o "tamanho da maior janela" onde aquele elemento `i` consegue ser o valor mínimo.
3. Crie um array de resultados `Ans` e inicie-o com 0. Para cada `i`, o valor `arr[i]` pode ser candidato para responder a janela de tamanho `len = Dir - Esq - 1`. Salve `Ans[len] = max(Ans[len], arr[i])`.
4. Faça uma passagem reversa: `Ans[i] = max(Ans[i], Ans[i+1])` para completar as lacunas.

**Input:** `[10, 20, 30, 50, 10, 70, 30]`  
**Output:** `[70, 30, 20, 10, 10, 10, 10]`

### 37. Pilha que suporta getMin() em O(1) de tempo e espaço

**Descrição:** Implemente o `getMin()` de uma pilha em tempo O(1), mas sem utilizar nenhuma estrutura auxiliar de pilha. O espaço extra deve ser O(1).

**Passo a Passo:**
1. Mantenha uma variável `minEle` guardando o menor atual.
2. Na operação de `Push(x)`: Se `x` >= `minEle`, apenas empilhe. Se `x` < `minEle`, o novo valor empilhado será um "código numérico": `(2 * x) - minEle`, e então você atualiza `minEle = x`.
3. Na operação de `Pop()`: Retire o topo `y`. Se `y` >= `minEle`, retorne `y` e fim. Se `y` < `minEle`, quer dizer que retiramos o item que engatilhou uma mudança de mínimo. O valor real deletado é o atual `minEle`. Após isso, desfaça o código reajustando o `minEle` para seu valor anterior, que será `(2 * minEle) - y`.

**Input:** `Push(3), Push(5), getMin(), Push(2), Push(1), getMin(), Pop(), getMin()`  
**Output:** A sequência de getMin será `3`, `1` e `2`

### 38. Pilha com frequência máxima

**Descrição:** Projete uma estrutura onde a função `Pop()` retorna não o último a ser empilhado, mas o elemento mais frequente que está na pilha neste momento. Se houver empate, remova o que entrou mais recentemente (comportamento de pilha padrão para desempates).

**Passo a Passo:**
1. Utilize um Dicionário/Mapa (`freqMap`) para associar o elemento à sua contagem atual de aparições.
2. Mantenha uma variável `maxFreq` para saber a frequência global do sistema.
3. Crie um Dicionário de Pilhas (`pilhasMap`), onde a chave é uma Frequência e o valor é uma Pilha de elementos.
4. No `Push(x)`: Incremente a frequência de `x`. Atualize `maxFreq` se necessário. Coloque `x` na pilha correspondente à sua nova frequência (dentro de `pilhasMap`).
5. No `Pop()`: Vá na pilha atrelada à chave `maxFreq` e retire o elemento do topo. Decremente a frequência dele no `freqMap`. Se a pilha em `maxFreq` ficar vazia, decremente a variável `maxFreq`.

**Input:** `Push(5), Push(7), Push(5), Push(7), Push(4), Push(5), Pop(), Pop()`  
**Output:** Retornará `5`, depois `7`

### 39. Substring Válida Mais Longa

**Descrição:** Dada uma string com colchetes/parênteses, encontre o tamanho da maior substring (trecho contíguo) em que a formatação dos parênteses esteja perfeitamente balanceada e válida.

**Passo a Passo:**
1. Inicialize a pilha com `-1`. Isso servirá de "âncora" base para o começo da string.
2. Percorra a string. Se for caractere de abertura `(`, empilhe seu índice na string.
3. Se for fechamento `)`, dê um *Pop* na pilha.
4. Se a pilha ficar vazia, significa que o fechamento foi irregular. Empilhe o índice atual para ser a nova "âncora" inválida.
5. Se não ficar vazia, a extensão atual é válida! Calcule o tamanho: `índice atual - valor no topo da pilha`. Mantenha o acompanhamento do maior tamanho encontrado.

**Input:** `")()())"`  
**Output:** `4` (a substring válida é `"()()"`)

### 40. Verificar Colchetes Redundantes

**Descrição:** Dada uma expressão matemática validamente pareada em forma de string, identifique se existem parênteses extras e inúteis encapsulando um operando vazio ou que já possua parênteses (ex: `((a+b))` possui colchete redundante).

**Passo a Passo:**
1. Itere pela string. Se o caractere não for um fecha-parêntese `)`, empilhe-o.
2. Se encontrar um `)`, inicialize uma variável `operadores = 0`.
3. Desempilhe os elementos do topo da pilha e conte os operadores (`+`, `-`, `*`, `/`) que encontrar até dar de cara com um `(`.
4. Quando remover o `(`, veja quantos operadores você contou. Se for 0, isso significa que não houve computação matemática dentro desses parênteses, logo eles são **redundantes**.

**Input:** `"(a+(b)/c)"`  
**Output:** `Verdadeiro (True)` (Os parênteses ao redor de `b` são redundantes)

### 41. Permutações de Pilha

**Descrição:** Dados dois arrays (Original e Alvo), determine se o array Alvo pode ser gerado a partir do Original executando sequências de Push e Pop utilizando exatamente uma pilha auxiliar.

**Passo a Passo:**
1. Inicialize ponteiros para as posições dos arrays Original `i = 0` e Alvo `j = 0`. Crie uma pilha vazia.
2. Empilhe `Original[i]` e avance `i`.
3. Verifique constantemente o topo da pilha: enquanto ela não for vazia e o seu topo for estritamente igual ao `Alvo[j]`, dê *Pop* na pilha e avance o cursor do alvo (`j++`).
4. Ao final da exploração de `i`, se a pilha estiver completamente vazia, é uma permutação válida.

**Input:** Original = `[1, 2, 3]`, Alvo = `[2, 1, 3]`  
**Output:** `Verdadeiro (True)` (Possível fazendo: push 1, push 2, pop 2, pop 1, push 3, pop 3)

### 42. Remover colchetes contendo operadores + e -

**Descrição:** Dada uma string com expressão algébrica contendo letras, parênteses e os operadores de soma e subtração (`+`, `-`), simplifique a expressão avaliando a distribuição matemática de sinais, removendo todos os parênteses.

**Passo a Passo:**
1. Utilize uma Pilha para armazenar os sinais (`+1` para soma/positivo, `-1` para subtração/negativo) que estão afetando os valores momentaneamente, começando com a base `+1` na pilha e um `sinal_atual = +1`.
2. Itere a string:
  - Se for operando/variável, anexe ao resultado mantendo seu sinal final (calculado como `sinal local * sinal topo pilha`).
  - Se encontrar um `(`, empilhe o último `sinal_atual` atrelado aos parênteses.
  - Se encontrar um `)`, apenas dê *Pop* na pilha para fechar o escopo daquele sinal.
3. Recoloque a lógica matemática na saída. Ex: um `-` antes de `(a-b)` resultará em `-a+b`.

**Input:** `"a-(b-c-(d+e))-f"`  
**Output:** `"a-b+c+d+e-f"`

</details>
