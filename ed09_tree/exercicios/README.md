# Lista de Exercícios - Estruturas de Dados Árvores (Trees)

Esta lista contém desafios progressivos para aprofundar seu conhecimento em estruturas de dados do tipo Árvore (Trees) e Árvore Binária de Busca (BST). Os problemas não dependem de uma linguagem específica. Você pode resolvê-los em C, C++, Java, Python, JavaScript, ou qualquer outra linguagem de sua preferência.

> **Nota:** Nos exemplos de entrada, as árvores frequentemente são representadas por arrays seguindo a ordem de nível (level-order traversal), onde `null` ou `Nulo` indica a ausência de um nó.

<details>
<summary>🟢 Nível 1 - Fácil</summary>

### 1. Altura de uma Árvore Binária

**Descrição:** Determine a profundidade ou altura máxima de uma árvore binária. A altura é o número de nós no caminho mais longo da raiz até a folha mais distante.

**Passo a passo sugerido:**
1. Verifique se a árvore está vazia. Se sim, a altura é 0.
2. Calcule recursivamente a altura da subárvore esquerda.
3. Calcule recursivamente a altura da subárvore direita.
4. Compare ambas as alturas e retorne a maior delas somada de 1 (que representa o nó atual).

**Entrada (Exemplo):** `[1, 2, 3, null, null, 4, 5]`  
**Saída Esperada:** `3`

---

### 2. Árvores Idênticas

**Descrição:** Verifique se duas árvores binárias são exatamente iguais, tanto em estrutura quanto nos valores contidos em cada nó.

**Passo a passo sugerido:**
1. Se ambas as árvores forem nulas, retorne verdadeiro.
2. Se apenas uma delas for nula, retorne falso.
3. Se os valores dos nós atuais forem diferentes, retorne falso.
4. Chame a função recursivamente para os filhos esquerdos e direitos de ambas as árvores e retorne verdadeiro apenas se ambas as chamadas retornarem verdadeiro.

**Entrada (Exemplo):** Árvore A: `[1, 2, 3]`, Árvore B: `[1, 2, 3]`  
**Saída Esperada:** `Verdadeiro`

---

### 3. Árvores Espelhadas

**Descrição:** Crie uma função que converta uma dada árvore binária em sua imagem espelhada (inverta as posições dos filhos esquerdo e direito de cada nó).

**Passo a passo sugerido:**
1. Se o nó atual for nulo, apenas retorne.
2. Chame a função recursivamente para a subárvore esquerda e depois para a direita.
3. Troque os ponteiros do filho esquerdo com o filho direito do nó atual.

**Entrada (Exemplo):** `[1, 2, 3]`  
**Saída Esperada:** `[1, 3, 2]`

---

### 4. Árvores Simétricas

**Descrição:** Verifique se uma árvore binária é espelho de si mesma (ou seja, se ela é simétrica em relação ao seu centro).

**Passo a passo sugerido:**
1. Crie uma função auxiliar que receba a subárvore esquerda e a direita da raiz.
2. Se ambas forem nulas, são simétricas (retorne verdadeiro). Se apenas uma for nula, retorne falso.
3. Verifique se os valores são iguais.
4. Verifique recursivamente se o filho esquerdo de uma é igual ao filho direito da outra, e vice-versa.

**Entrada (Exemplo):** `[1, 2, 2, 3, 4, 4, 3]`  
**Saída Esperada:** `Verdadeiro`

---

### 5. Árvore Balanceada

**Descrição:** Determine se uma árvore binária é balanceada em altura. Uma árvore é balanceada se a diferença de altura entre a subárvore esquerda e a direita de qualquer nó não for maior que 1.

**Passo a passo sugerido:**
1. Crie uma função que calcula a altura da árvore.
2. Modifique essa função para retornar -1 (ou falso) se a diferença absoluta entre as alturas da esquerda e direita for > 1.
3. Se qualquer subchamada retornar -1, propague o -1 para cima.

**Entrada (Exemplo):** `[1, 2, 3, 4, 5]`  
**Saída Esperada:** `Verdadeiro`

---

### 6. Soma dos Filhos Igual ao Pai

**Descrição:** Verifique se para cada nó da árvore, o valor dele é exatamente igual à soma dos valores de seus filhos esquerdo e direito.

**Passo a passo sugerido:**
1. Se o nó for nulo ou for uma folha (sem filhos), retorne verdadeiro.
2. Some os valores do filho esquerdo e do direito (considere 0 se não existirem).
3. Verifique se a soma é igual ao valor do nó atual.
4. Retorne o resultado da condição acima junto com a chamada recursiva para as subárvores esquerda e direita.

**Entrada (Exemplo):** `[10, 8, 2, 3, 5, 2, null]`  
**Saída Esperada:** `Verdadeiro`

---

### 7. Array para Árvore Binária de Busca (BST)

**Descrição:** Converta um array ordenado de forma crescente em uma Árvore Binária de Busca (BST) balanceada em altura.

**Passo a passo sugerido:**
1. Encontre o elemento central do array para ser a raiz (isso garante o balanceamento).
2. Recursivamente construa a subárvore esquerda usando a metade esquerda do array.
3. Recursivamente construa a subárvore direita usando a metade direita do array.
4. Retorne o nó recém-criado.

**Entrada (Exemplo):** `[-10, -3, 0, 5, 9]`  
**Saída Esperada:** `[0, -3, 9, -10, null, 5]`

---

### 8. Nós a uma Distância Específica

**Descrição:** Dado o nó raiz e um valor k, imprima ou retorne todos os nós que estão a uma distância `k` da raiz.

**Passo a passo sugerido:**
1. Inicie uma travessia na árvore passando a raiz e o contador de distância iniciando em 0.
2. Se o nó for nulo, retorne.
3. Se a distância atual for igual a `k`, adicione o valor do nó à lista de resultados e retorne.
4. Chame recursivamente para os filhos esquerdo e direito incrementando a distância em 1.

**Entrada (Exemplo):** Raiz: `[1, 2, 3, 4, 5, 8]`, Distância `k = 2`  
**Saída Esperada:** `[4, 5, 8]`

---

### 9. Sucessor In-order em uma BST

**Descrição:** Dado um nó específico em uma Árvore Binária de Busca, encontre o seu sucessor na travessia in-order (o nó com o menor valor maior do que o valor do nó dado).

**Passo a passo sugerido:**
1. Se o nó possui um filho direito, o sucessor é o nó mais à esquerda dessa subárvore direita.
2. Se não possui, inicie da raiz da árvore: percorra a árvore descendo. Sempre que o valor da raiz atual for maior que o do nó alvo, atualize a variável "sucessor" e vá para a esquerda. Caso contrário, vá para a direita.

**Entrada (Exemplo):** Árvore: `[20, 8, 22, 4, 12, 10, 14]`, Nó alvo: `8`  
**Saída Esperada:** `10`

---

### 10. K-ésimo Maior Elemento em uma BST

**Descrição:** Encontre o k-ésimo maior elemento inserido em uma Árvore Binária de Busca usando espaço extra constante O(1) auxiliar além da pilha de recursão.

**Passo a passo sugerido:**
1. Crie um contador global ou passe-o por referência.
2. Realize uma travessia in-order reversa (Direita, Raiz, Esquerda) porque ela visitará os nós em ordem decrescente.
3. A cada nó visitado, incremente o contador. Se o contador atingir `k`, esse é o seu alvo.

**Entrada (Exemplo):** Árvore: `[5, 3, 6, 2, 4]`, k: `2`  
**Saída Esperada:** `5`

---

### 11. Balancear uma BST

**Descrição:** Dada uma BST que não está balanceada, modifique-a para que se torne uma BST balanceada em altura.

**Passo a passo sugerido:**
1. Faça uma travessia in-order da árvore para armazenar os valores em um array (os elementos já sairão ordenados).
2. Utilize a lógica do exercício "Array para Árvore Binária de Busca (BST)" para recriar a árvore de forma balanceada.

**Entrada (Exemplo):** `[1, null, 2, null, 3, null, 4]` (Árvore degenerada pendendo à direita)  
**Saída Esperada:** `[2, 1, 3, null, null, null, 4]` (ou estrutura balanceada equivalente)

</details>

<details>
<summary>🟠 Nível 2 - Médio</summary>

### 12. Diâmetro da Árvore

**Descrição:** Calcule o diâmetro da árvore binária, que é o número de nós no caminho mais longo entre quaisquer duas folhas. O caminho pode ou não passar pela raiz.

**Passo a passo sugerido:**
1. Crie uma variável para armazenar o diâmetro máximo.
2. Escreva uma função que calcula a altura da árvore. Dentro dela, a cada nó processado, calcule a soma das alturas dos filhos esquerdo e direito.
3. Atualize a variável do diâmetro máximo se a soma das alturas calculada no passo anterior for maior que o diâmetro atual.

**Entrada (Exemplo):** `[1, 2, 3, 4, 5]`  
**Saída Esperada:** `4` (caminho: 4 → 2 → 1 → 3 ou 5 → 2 → 1 → 3)

---

### 13. Verificar se é Subárvore

**Descrição:** Dadas duas árvores binárias T e S, verifique se a árvore S é uma subárvore exata dentro de T.

**Passo a passo sugerido:**
1. Escreva uma função auxiliar (como no exercício "Árvores Idênticas") que verifica se duas árvores são iguais.
2. Na função principal, faça uma travessia pela árvore T. Se o nó atual for nulo, retorne falso.
3. Se os nós coincidirem, use a função auxiliar. Se forem idênticas, retorne verdadeiro.
4. Caso contrário, verifique se S é subárvore do filho esquerdo ou direito de T recursivamente.

**Entrada (Exemplo):** Árvore T: `[3, 4, 5, 1, 2]`, Árvore S: `[4, 1, 2]`  
**Saída Esperada:** `Verdadeiro`

---

### 14. Verificar se é uma BST

**Descrição:** Dada uma árvore binária, verifique se ela obedece estritamente a todas as regras de uma Árvore Binária de Busca (valores da esquerda menores, direita maiores).

**Passo a passo sugerido:**
1. Crie uma função recursiva que receba o nó atual, um valor mínimo e um valor máximo permitido.
2. Se o nó for nulo, retorne verdadeiro.
3. Se o valor do nó estiver fora do limite (menor que o mínimo ou maior que o máximo), retorne falso.
4. Chame recursivamente para a esquerda (atualizando o limite máximo para o valor do nó atual) e para a direita (atualizando o limite mínimo para o valor atual).

**Entrada (Exemplo):** `[5, 1, 4, null, null, 3, 6]`  
**Saída Esperada:** `Falso` (O nó 4 está na direita do 5, mas tem valor menor, e o 3 está à direita do 5 mas é menor)

---

### 15. Subárvore de Valor Único

**Descrição:** Conte o número de subárvores onde todos os nós dentro dessa subárvore possuem o mesmo valor. Uma folha isolada conta como uma subárvore válida.

**Passo a passo sugerido:**
1. Crie uma variável contadora.
2. Faça uma travessia pós-ordem (esquerda, direita, raiz) para analisar os filhos antes do pai.
3. Retorne verdadeiro para subárvores nulas.
4. Em um nó, verifique se o filho esquerdo e o direito retornaram verdadeiro e se têm o mesmo valor que o nó atual. Se sim, incremente o contador e retorne verdadeiro.

**Entrada (Exemplo):** `[5, 5, 5, 5, 5, null, 5]`  
**Saída Esperada:** `6`

---

### 16. BSTs Únicas

**Descrição:** Dado um número `n`, descubra quantas Árvores Binárias de Busca estruturalmente únicas podem ser criadas armazenando valores de 1 até `n`.

**Passo a passo sugerido:**
1. Utilize programação dinâmica ou números de Catalan.
2. Crie um array `dp` de tamanho `n + 1` onde `dp[0] = 1` e `dp[1] = 1`.
3. Para cada número `i` de 2 até `n`, calcule a soma de `dp[j-1] * dp[i-j]` para `j` variando de 1 até `i`. O resultado em `dp[n]` é a resposta.

**Entrada (Exemplo):** `n = 3`  
**Saída Esperada:** `5`

---

### 17. Travessia em Zigue-zague

**Descrição:** Imprima os nós de uma árvore binária em ordem de nível, mas alternando a direção a cada nível (esquerda para direita, depois direita para esquerda, etc.).

**Passo a passo sugerido:**
1. Use duas pilhas, uma para o nível atual e outra para o próximo nível.
2. Defina uma flag booleana `esquerdaParaDireita` como verdadeira.
3. Ao retirar nós da pilha atual, adicione seus filhos à pilha do próximo nível. A ordem de inserção dos filhos (esquerdo depois direito, ou vice-versa) depende da flag.
4. Ao esvaziar a pilha atual, inverta a flag e troque as pilhas.

**Entrada (Exemplo):** `[1, 2, 3, 7, 6, 5, 4]`  
**Saída Esperada:** `[1, 3, 2, 7, 6, 5, 4]`

---

### 18. Travessia Vertical

**Descrição:** Imprima a árvore com base na distância horizontal (HD) de cada nó em relação à raiz (HD=0). Filhos esquerdos têm HD-1, filhos direitos têm HD+1. Imprima os nós do menor HD para o maior.

**Passo a passo sugerido:**
1. Use uma busca em largura (BFS) usando uma Fila, armazenando pares `(Nó, Distância Horizontal)`.
2. Use um Map (ou Dicionário) para agrupar nós que possuem a mesma Distância Horizontal.
3. Ao finalizar a BFS, itere sobre o Map ordenado pelas chaves (as distâncias HD) e adicione os resultados à lista final.

**Entrada (Exemplo):** `[1, 2, 3, 4, 5, 6, 7]`  
**Saída Esperada:** `[4, 2, 1, 5, 6, 3, 7]`

---

### 19. Travessia de Contorno (Limites)

**Descrição:** Imprima ou armazene todos os nós no limite da árvore (borda esquerda descendo, folhas da esquerda para a direita e borda direita subindo).

**Passo a passo sugerido:**
1. Adicione a raiz à lista.
2. Crie uma função que coleta o contorno esquerdo (descendo sempre pela esquerda, se não houver, vá pela direita; ignore as folhas).
3. Crie uma função que encontre todas as folhas usando travessia in-order ou pós-ordem.
4. Crie uma função que coleta o contorno direito (semelhante ao esquerdo, mas descendo pela direita, e armazenando os resultados na ordem reversa, de baixo para cima).

**Entrada (Exemplo):** `[20, 8, 22, 4, 12, null, 25, null, null, 10, 14]`  
**Saída Esperada:** `[20, 8, 4, 10, 14, 25, 22]`

---

### 20. Construir Árvore a partir de Travessias Pre-order e In-order

**Descrição:** Reconstrua uma árvore binária tendo recebido como entrada os arrays contendo a sua travessia pre-order e a in-order.

**Passo a passo sugerido:**
1. O primeiro elemento do pre-order sempre será a raiz da subárvore atual.
2. Localize esse elemento no array in-order. Tudo à esquerda dele pertence à subárvore esquerda; tudo à direita pertence à subárvore direita.
3. Chame recursivamente a função para construir as subárvores esquerda e direita limitando os índices de busca dos arrays de forma apropriada.

**Entrada (Exemplo):** Pre-order: `[3, 9, 20, 15, 7]`, In-order: `[9, 3, 15, 20, 7]`  
**Saída Esperada:** `[3, 9, 20, null, null, 15, 7]`

---

### 21. Construir BST a partir de Travessia Pre-order

**Descrição:** Dada a travessia pre-order de uma Árvore Binária de Busca, reconstrua a BST original.

**Passo a passo sugerido:**
1. Você pode usar uma técnica parecida com a de validar uma BST: defina um limite superior de valores.
2. O primeiro elemento é a raiz. Itere sobre o array, onde o limite superior de inserção para o filho esquerdo será o valor do próprio pai.
3. Se o próximo elemento exceder o limite atual, retorne, indicando que esse valor pertence a uma subárvore mais à direita.

**Entrada (Exemplo):** `[8, 5, 1, 7, 10, 12]`  
**Saída Esperada:** `[8, 5, 10, 1, 7, null, 12]`

---

### 22. Distância Mínima Entre Dois Nós

**Descrição:** Encontre a menor distância (quantidade de arestas) entre dois nós dados `a` e `b` em uma árvore binária.

**Passo a passo sugerido:**
1. Encontre o Menor Ancestral Comum (LCA) de `a` e `b`.
2. Encontre a distância entre a raiz (que neste caso é o LCA encontrado) e o nó `a` (D1).
3. Encontre a distância entre a raiz (LCA) e o nó `b` (D2).
4. A distância total será `D1 + D2`.

**Entrada (Exemplo):** Árvore: `[1, 2, 3]`, Nós alvo: `2` e `3`  
**Saída Esperada:** `2`

---

### 23. Caminho de Soma Máxima da Folha até a Raiz

**Descrição:** Descubra o caminho começando de qualquer folha e terminando na raiz que resulte na maior soma possível de valores dos nós. Retorne essa soma máxima.

**Passo a passo sugerido:**
1. Faça uma travessia pós-ordem.
2. Ao retornar dos filhos de um nó, traga o valor do filho que possuir o maior caminho já computado (esquerda ou direita).
3. A soma máxima neste nó atual em direção à raiz será o valor dele próprio somado com o maior caminho vindo dos seus filhos.

**Entrada (Exemplo):** `[10, -2, 7, 8, -4]`  
**Saída Esperada:** `17` (caminho: 7 → 10)

---

### 24. Diferença Entre Níveis Ímpares e Pares

**Descrição:** Calcule a diferença entre a soma dos valores de todos os nós em níveis ímpares e a soma dos nós em níveis pares da árvore. A raiz está no nível 1 (ímpar).

**Passo a passo sugerido:**
1. Utilize BFS com uma Fila para percorrer os níveis.
2. Mantenha controle de uma variável de nível. Se o nível for ímpar, adicione o valor dos nós a uma variável total. Se for par, subtraia da variável total.
3. O resultado final da variável será a resposta.

**Entrada (Exemplo):** `[10, 20, 30, 40, 60]`  
**Saída Esperada:** `40` ((10 + 40 + 60) - (20 + 30))

---

### 25. Menor Ancestral Comum em uma Árvore Binária

**Descrição:** Encontre o Menor Ancestral Comum (LCA) de dois nós dados em uma árvore binária. O LCA é o nó mais baixo na árvore que tem ambos como descendentes.

**Passo a passo sugerido:**
1. Inicie na raiz. Se a raiz for nula ou igual a um dos alvos, retorne a raiz.
2. Chame a função recursivamente para os filhos esquerdo e direito.
3. Se ambas as chamadas retornarem nós não-nulos, significa que a raiz atual é o LCA.
4. Se apenas um lado não for nulo, retorne aquele lado (o LCA está contido nele).

**Entrada (Exemplo):** Árvore: `[3, 5, 1, 6, 2, 0, 8]`, alvos: `5` e `1`  
**Saída Esperada:** `3`

---

### 26. Ancestrais em uma Árvore Binária

**Descrição:** Dado um nó alvo, imprima ou armazene todos os ancestrais desse nó desde a raiz até ele (excluindo o próprio nó).

**Passo a passo sugerido:**
1. Crie uma função recursiva que receba o nó alvo.
2. Se o nó for nulo, retorne falso. Se ele for o nó alvo, retorne verdadeiro.
3. Se a busca pela esquerda ou pela direita retornar verdadeiro, significa que o nó atual é ancestral. Armazene seu valor e retorne verdadeiro para cima.

**Entrada (Exemplo):** Árvore: `[1, 2, 3, 4, 5]`, alvo `4`  
**Saída Esperada:** `[2, 1]` (ou `[1, 2]`)

---

### 27. Remover Chaves da BST Fora do Intervalo

**Descrição:** Dado um intervalo de valores `[min, max]`, modifique a BST descartando todos os nós cujo valor esteja fora desse limite.

**Passo a passo sugerido:**
1. Percorra a árvore pós-ordem. Remova nós fora do limite retornando subárvores.
2. Se o valor do nó atual for menor que `min`, significa que esse nó e toda a subárvore esquerda não servem. Retorne a subárvore direita.
3. Se o valor for maior que `max`, retorne a subárvore esquerda.
4. Se o valor estiver no limite, apenas atualize os filhos e retorne o nó em si.

**Entrada (Exemplo):** Árvore: `[6, -13, 14, -8, 15, 13, 7]`, limite: `[-10, 13]`  
**Saída Esperada:** `[6, -8, 13, null, null, 7, null]`

---

### 28. Encontrar Par com a Soma Alvo na BST

**Descrição:** Dado um número alvo, verifique se existem dois nós distintos na BST cujos valores somados resultem no número alvo.

**Passo a passo sugerido:**
1. Faça uma travessia in-order iterativa (menor para o maior) e uma travessia in-order reversa iterativa (maior para o menor) utilizando duas pilhas.
2. Como a árvore é uma BST, essa abordagem imita o método de dois ponteiros em um array ordenado (um na esquerda, outro na direita).
3. Se a soma dos ponteiros bater o alvo, retorne verdadeiro. Se for menor, avance o ponteiro esquerdo; se maior, recue o direito.

**Entrada (Exemplo):** Árvore: `[15, 10, 20, 8, 12, 16, 25]`, alvo: `28`  
**Saída Esperada:** `Verdadeiro` (20 + 8 = 28)

---

### 29. Transformar BST em Árvore de Maior Soma

**Descrição:** Altere cada nó da BST substituindo o seu valor pela soma de seu valor original com a soma de todos os nós maiores do que ele na árvore.

**Passo a passo sugerido:**
1. Crie uma variável para guardar a soma acumulada, inicialmente 0.
2. Faça uma travessia in-order reversa (direita, raiz, esquerda).
3. Em cada nó visitado, atualize a soma acumulada com o valor do nó, e depois sobrescreva o valor do nó com essa soma.

**Entrada (Exemplo):** `[11, 2, 29, 1, 7, 15, 40]`  
**Saída Esperada:** `[114, 132, 69, 133, 121, 84, 40]`

---

### 30. Soma Máxima de Nós Não Adjacentes

**Descrição:** Encontre a maior soma de valores dos nós de uma árvore binária com a regra: se o valor de um nó for incluído na soma, o valor de seus filhos diretos não pode ser incluído.

**Passo a passo sugerido:**
1. Crie uma função recursiva para retornar um par de valores para cada nó: `[Soma com o nó, Soma sem o nó]`.
2. A soma "com o nó" é o valor atual + a soma "sem os nós" dos seus filhos.
3. A soma "sem o nó" é o máximo do retorno do filho esquerdo (com ou sem ele) + o máximo do retorno do filho direito.

**Entrada (Exemplo):** `[1, 2, 3, 1, null, 4, 5]`  
**Saída Esperada:** `11` (1(raiz) + 1 + 4 + 5)

---

### 31. Maior BST em uma Árvore Binária

**Descrição:** Encontre a maior subárvore que também seja uma BST válida dentro de uma árvore binária arbitrária. A função deve retornar o número de nós contidos nessa subárvore.

**Passo a passo sugerido:**
1. Faça uma travessia pós-ordem.
2. Para cada subárvore, passe para cima as seguintes informações: se ela é uma BST, o tamanho total (nós), valor mínimo contido nela e o valor máximo.
3. Uma árvore pai será uma BST se os filhos esquerdo e direito forem BSTs, o valor máximo da esquerda for menor que o pai, e o mínimo da direita for maior.
4. Mantenha rastreio do maior tamanho visto.

**Entrada (Exemplo):** `[10, 5, 15, 1, 8, null, 7]`  
**Saída Esperada:** `3` (Subárvore de 5: 5, 1, 8)

---

### 32. Nós Extremos em Ordem Alternada

**Descrição:** Imprima os nós nas extremidades de cada nível, porém alternando: no nível 1, imprima o nó mais à direita; no nível 2, o nó mais à esquerda, no nível 3 o mais à direita, e assim por diante.

**Passo a passo sugerido:**
1. Utilize a Busca em Largura (BFS) monitorando o tamanho da fila por nível.
2. Defina uma flag `esquerdaParaDireita` alternando por nível.
3. Se for pra pegar o esquerdo, pegue o primeiro elemento do loop interno do nível. Se direito, o último elemento do nível na fila.

**Entrada (Exemplo):** `[1, 2, 3, 4, 5, 6, 7]`  
**Saída Esperada:** `[1, 4, 7]` (Nível 1 Dir: 1. Nível 2 Esq: 2. Nível 3 Dir: 7. Nota: dependendo da interpretação do nível inicial pode ser `[1, 2, 7]`)

---

### 33. Conectar Nós no Mesmo Nível

**Descrição:** Altere a estrutura de nós da árvore para que cada nó aponte (através de um ponteiro `nextRight`) para o nó que está imediatamente à sua direita no mesmo nível.

**Passo a passo sugerido:**
1. Execute uma BFS padrão iterando pela fila nível a nível.
2. No loop de cada nível, antes de tirar um nó da fila, ligue o `nextRight` do nó previamente retirado a este (exceto o primeiro elemento do nível).
3. Para o último nó de cada nível, deixe o `nextRight` como nulo.

**Entrada (Exemplo):** `[1, 2, 3, 4, 5]`  
**Saída Esperada:** O campo auxiliar dos nós seria: (1 → null), (2 → 3 → null), (4 → 5 → null)

</details>

<details>
<summary>🔴 Nível 3 - Difícil</summary>

### 34. Lista Encadeada Ordenada para BST

**Descrição:** Dada uma Lista Encadeada cujos valores estão em ordem crescente de forma estrita, converta a lista em uma Árvore Binária de Busca balanceada.

**Passo a passo sugerido:**
1. Use uma abordagem de Divisão e Conquista (como Merge Sort).
2. Use os ponteiros rápido e devagar (Tortoise e Hare) para encontrar o elemento central da lista encadeada, ele será a raiz.
3. Desconecte a lista do meio para quebrar em duas partes menores.
4. Chame recursivamente a função para as metades para montar as subárvores esquerda e direita.

**Entrada (Exemplo):** Lista: `-10 → -3 → 0 → 5 → 9`  
**Saída Esperada:** `[0, -3, 9, -10, null, 5]`

---

### 35. Árvore Binária para Lista Duplamente Encadeada

**Descrição:** Achate a árvore binária transformando-a em uma Lista Duplamente Encadeada (DLL) no mesmo lugar, mantendo a ordem da travessia In-order (menor até maior). Ponteiros "esquerdo" funcionarão como "anterior" e "direito" como "próximo".

**Passo a passo sugerido:**
1. Tenha variáveis globais (ou passadas por referência) para monitorar o `head` da DLL e o nó `prev` (anterior) processado.
2. Faça uma travessia in-order.
3. Quando processar a raiz, se `prev` for nulo, a raiz é o `head`. Caso contrário, conecte o `prev.direito` à raiz e a `raiz.esquerdo` a `prev`.
4. Atualize `prev` para ser o nó atual e continue.

**Entrada (Exemplo):** `[10, 12, 15, 25, 30, 36]`  
**Saída Esperada:** `25 ↔ 12 ↔ 30 ↔ 10 ↔ 36 ↔ 15` (A lista estará unida in-order)

---

### 36. Caminho de Soma Máxima Entre Duas Folhas

**Descrição:** Diferente do anterior (folha para raiz), encontre a soma máxima possível de um caminho entre quaisquer DUAS folhas da árvore binária.

**Passo a passo sugerido:**
1. Utilize lógica recursiva pós-ordem similar ao diâmetro da árvore.
2. O retorno de um nó para seu pai deve ser o valor máximo daquele nó até alguma folha em suas subárvores (nó + max(esq, dir)).
3. Durante o processo de um nó específico, o caminho entre duas folhas passando por ele será: `valor do nó + caminho máx. da esquerda + caminho máx. da direita`.
4. Mantenha uma variável máxima atualizando com esse resultado, e retorne na chamada o ramo mais alto.

**Entrada (Exemplo):** `[-15, 5, 6, -8, 1, 3, 9]`  
**Saída Esperada:** `27` (Caminho: 9 → 6 → -15 → 5 → 1)

---

### 37. Caminhos com Soma K

**Descrição:** Conte quantos caminhos que iniciam de qualquer nó e terminam em qualquer nó descendo na árvore (do pai para filhos) resultam exatamente em uma soma `K`.

**Passo a passo sugerido:**
1. A abordagem eficiente exige o conceito de prefix sums + HashMap (como no "Two Sum" para Arrays).
2. Durante a descida pela árvore, mantenha a soma corrente.
3. Verifique se `(somaCorrente - K)` existe no HashMap. Se sim, adicione a frequência ao resultado final.
4. Adicione a soma corrente no HashMap e vá para os filhos. No retorno do backtracking da recursão, remova a soma corrente do mapa.

**Entrada (Exemplo):** Árvore: `[1, 2, 3]`, K: `3`  
**Saída Esperada:** `2` (Caminhos: o nó [3] sozinho, e o caminho 1 → 2)

---

### 38. Número de Curvas em uma Árvore Binária

**Descrição:** Calcule o número de "curvas" (mudança de direção) do caminho de um nó para o outro dentro da árvore binária. Uma curva é a troca de "ir para a esquerda" para "ir para a direita" e vice-versa.

**Passo a passo sugerido:**
1. Encontre o Menor Ancestral Comum (LCA) entre os dois nós.
2. Realize uma busca a partir do LCA para o primeiro alvo informando a direção tomada. Se for a mesma direção no próximo passo, 0 curvas; se trocar, conta +1.
3. Faça a mesma busca para o segundo alvo.
4. Some as curvas. Se o LCA não for igual a nenhum dos alvos em si, conte uma curva a mais (a passagem pelo próprio LCA).

**Entrada (Exemplo):** Árvore: `[1, 2, 3, 4, 5, 6, 7, 8]`, nós: `5` e `6`  
**Saída Esperada:** `3` (5 → 2 → 1 → 3 → 6 mudou a direção em 2, 1 e 3)

---

### 39. Mesclar Duas BSTs

**Descrição:** Dadas duas Árvores Binárias de Busca, mescle-as em apenas uma Árvore de Busca balanceada usando espaço extra limitado a um número constante O(h) correspondente à altura.

**Passo a passo sugerido:**
1. É preferível converter as duas BSTs para Listas Duplamente Encadeadas iterativamente, alterando os ponteiros "in place" em ordem crescente.
2. Mescle as duas listas de forma iterativa, mantendo-as ordenadas.
3. Converta a Lista final novamente para uma BST Balanceada extraindo o elemento central como no exercício 34.

**Entrada (Exemplo):** BST A: `[3, 1, 5]`, BST B: `[4, 2, 6]`  
**Saída Esperada:** `[3, 2, 5, 1, null, 4, 6]` (Depende do nó central exato selecionado)

---

### 40. Corrigir Dois Nós Trocados em uma BST

**Descrição:** Dois dos nós em uma Árvore Binária de Busca válida tiveram seus valores trocados por acidente. Restaure a BST e conserte a posição trocando seus valores.

**Passo a passo sugerido:**
1. Faça uma travessia in-order e rastreie o ponteiro do nó visitado `anterior`.
2. Como uma in-order em BST é estritamente crescente, caso um nó seja menor que o `anterior`, você encontrou uma anomalia.
3. Guarde os ponteiros do primeiro par de anomalias (`anterior` e `atual`). Continue iterando. Se houver uma segunda anomalia, guarde o nó `atual`.
4. Inverta o valor dos nós marcados como primeira e última anomalia ao final da travessia.

**Entrada (Exemplo):** `[3, 1, 4, null, null, 2]` (2 e 4 trocaram)  
**Saída Esperada:** `[3, 1, 2, null, null, 4]`

---

### 41. Queimar a Árvore Binária

**Descrição:** Dado um nó folha onde um incêndio começa. A cada segundo, o fogo queima nós adjacentes (pai, filho esquerdo, filho direito). Determine quanto tempo leva para toda a árvore ser queimada.

**Passo a passo sugerido:**
1. Converta a árvore em um Grafo não direcionado associando cada nó com a lista de adjacências contendo seus filhos e seu pai (usando uma travessia inicial).
2. Execute uma BFS iterativa a partir do nó alvo do incêndio.
3. A cada nível da BFS (cada iteração sobre os nós de um nível), conte como 1 segundo queimado. Retorne os segundos do último nível processado.

**Entrada (Exemplo):** Árvore: `[1, 2, 3, 4, 5, null, 6, null, null, 7, 8]`, Nó alvo: `8`  
**Saída Esperada:** `5` (Segundos)

---

### 42. Clonar Árvore Binária com Ponteiro Aleatório

**Descrição:** Cada nó de uma árvore binária tem um ponteiro normal de esquerdo e direito, mais um ponteiro especial chamado "aleatório" (random) que pode apontar para qualquer nó da árvore ou ser nulo. Crie um clone profundo de toda a árvore com todos os ponteiros referenciando os novos nós do clone.

**Passo a passo sugerido:**
1. Utilize um Hash Map associando o endereço do nó original na memória para o endereço do respectivo nó clonado.
2. Primeiro passo: Faça a clonagem usando BFS ou DFS ignorando completamente o ponteiro aleatório e registrando as cópias no HashMap.
3. Segundo passo: Realize a travessia de novo na árvore original. Para cada nó iterado, acesse seu clone pelo map e defina seu ponteiro aleatório buscando o clone do endereço aleatório do nó original no map: `cloneMap[nó].random = cloneMap[nó.random]`.

**Entrada (Exemplo):** Nós têm a estrutura `(valor, esq, dir, random)`  
**Saída Esperada:** Uma cópia na memória não acoplada à primeira contendo os apontamentos perfeitamente refletidos em suas cópias locais.

</details>
