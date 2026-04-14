# Lista de Exercícios - Estruturas de Dados Heap

Esta lista de exercícios foi projetada para fortalecer sua lógica de programação na estrutura de dados **Heap** (Max-Heap e Min-Heap). Os problemas estão divididos por nível de dificuldade e detalham o funcionamento lógico, permitindo que sejam solucionados em qualquer linguagem de programação (C, C++, Java, Python, JavaScript, etc.).

<details>
<summary>🟢 Nível 1 - Fácil</summary>

### 1. Verificar se um array é um Heap

**Descrição:** Determine se os elementos de um array representam uma estrutura válida de Max-Heap binário.

**Passo a passo:**
1. Em um array representando uma árvore, os filhos do nó no índice `i` estão nos índices `2*i + 1` (esquerda) e `2*i + 2` (direita).
2. Percorra a primeira metade do array (os nós internos).
3. Para cada nó, verifique se seu valor é maior ou igual ao valor de seus filhos.
4. Se encontrar algum filho maior que o pai, retorne `Falso`. Caso contrário, retorne `Verdadeiro`.

**Entrada Exemplo:** `[90, 15, 10, 7, 12, 2]`  
**Saída Exemplo:** `Verdadeiro`

### 2. K-ésimo Menor e K-ésimo Maior Elemento

**Descrição:** Encontre o K-ésimo menor e o K-ésimo maior elemento em um array não ordenado.

**Passo a passo:**
1. **K-ésimo Menor**: Crie um Max-Heap de tamanho `K`. Insira os `K` primeiros elementos. Para o restante, se o elemento for menor que a raiz, remova a raiz e insira o novo elemento. A raiz será o resultado.
2. **K-ésimo Maior**: Crie um Min-Heap de tamanho `K`. Insira os `K` primeiros elementos. Para o restante, se o elemento for maior que a raiz, remova a raiz e insira o novo elemento. A raiz será o resultado.

**Entrada Exemplo:** `Array: [7, 10, 4, 3, 20, 15], K = 3`  
**Saída Exemplo:** `3º Menor: 7 | 3º Maior: 10`

### 3. Ordenação por Heap (Heap Sort)

**Descrição:** Ordene um array de números inteiros em ordem crescente utilizando o algoritmo Heap Sort.

**Passo a passo:**
1. Transforme o array em um Max-Heap.
2. Troque o primeiro elemento (o maior) com o último elemento do array.
3. Reduza o tamanho do heap em 1 e aplique heapify novamente na raiz.
4. Repita até sobrar apenas um elemento.

**Entrada Exemplo:** `[12, 11, 13, 5, 6, 7]`  
**Saída Exemplo:** `[5, 6, 7, 11, 12, 13]`

### 4. Heap Sort para Ordem Decrescente

**Descrição:** Ordene um array em ordem decrescente utilizando um Min-Heap.

**Passo a passo:**
1. Transforme o array original em um Min-Heap.
2. Troque o primeiro elemento (o menor) com o último elemento do array.
3. Reduza o tamanho do heap em 1 e aplique heapify na raiz.
4. Repita até sobrar apenas um elemento.

**Entrada Exemplo:** `[4, 10, 3, 5, 1]`  
**Saída Exemplo:** `[10, 5, 4, 3, 1]`

### 5. Altura de um Heap com N Nós

**Descrição:** Calcule a altura máxima de um Heap binário com `N` nós (raiz = nível 0).

**Passo a passo:**
1. Um heap é uma árvore binária completa.
2. A altura `h` é dada por: `Altura = floor(log2(N))`

**Entrada Exemplo:** `N = 14`  
**Saída Exemplo:** `3`

</details>

<details>
<summary>🟠 Nível 2 - Médio</summary>

### 6. Array Quase Ordenado

**Descrição:** Ordene um array onde cada elemento está, no máximo, `K` posições de distância da sua posição correta.

**Passo a passo:**
1. Crie um Min-Heap de tamanho `K + 1`.
2. Insira os primeiros `K + 1` elementos do array no Min-Heap.
3. Extraia o menor elemento e coloque-o na posição atual do array final.
4. Adicione o próximo elemento do array ao Min-Heap e repita até esvaziar.

**Entrada Exemplo:** `Array = [2, 6, 3, 12, 56, 8], K = 3`  
**Saída Exemplo:** `[2, 3, 6, 8, 12, 56]`

### 7. K Maiores e K Menores Elementos

**Descrição:** Retorne os `K` maiores e os `K` menores elementos sem ordenar o array por completo.

**Passo a passo:**
1. **K menores**: Use um Max-Heap de tamanho `K`, mantendo apenas os menores.
2. **K maiores**: Use um Min-Heap de tamanho `K`, mantendo apenas os maiores.
3. Retorne os elementos restantes em ambos os heaps.

**Entrada Exemplo:** `Array = [1, 23, 12, 9, 30, 2, 50], K = 3`  
**Saída Exemplo:** `3 Menores: [1, 2, 9] | 3 Maiores: [23, 30, 50]`

### 8. K Elementos Mais Próximos

**Descrição:** Dado um array e um valor `X`, encontre os `K` elementos mais próximos a `X`.

**Passo a passo:**
1. Crie um Max-Heap baseado na diferença absoluta `|elemento - X|`.
2. Percorra o array. Se o heap tiver menos de `K` elementos, adicione o elemento.
3. Se estiver cheio e a diferença for menor que a do topo, remova o topo e insira o novo.
4. O heap conterá os `K` elementos com menores diferenças.

**Entrada Exemplo:** `Array = [10, 2, 14, 4, 7, 6], X = 5, K = 3`  
**Saída Exemplo:** `[4, 6, 7]`

### 9. Diferença Máxima entre Dois Subconjuntos de Tamanho m

**Descrição:** Encontre a diferença máxima entre a soma de dois subconjuntos de `m` elementos.

**Passo a passo:**
1. Crie um Min-Heap e um Max-Heap com todos os elementos.
2. Extraia `m` elementos do Min-Heap para calcular a soma mínima.
3. Extraia `m` elementos do Max-Heap para calcular a soma máxima.
4. Subtraia soma mínima de soma máxima.

**Entrada Exemplo:** `Array = [5, 8, 11, 40, 15], m = 2`  
**Saída Exemplo:** `42` (Máxima: 40+15=55. Mínima: 5+8=13. 55 - 13 = 42)

### 10. Verificar se uma Árvore Binária é um Heap

**Descrição:** Dada uma árvore binária encadeada, verifique se ela forma um Max-Heap.

**Passo a passo:**
1. Verifique se a árvore é uma "Árvore Binária Completa" contando nós.
2. Faça uma travessia verificando se cada nó é maior ou igual aos seus filhos.

**Entrada Exemplo:** Árvore com raiz 10, filhos 9 e 8, filhos do 9: 7 e 6  
**Saída Exemplo:** `Verdadeiro`

### 11. Codificação de Huffman

**Descrição:** Gere a árvore de codificação de Huffman a partir de frequências de caracteres.

**Passo a passo:**
1. Calcule a frequência de cada caractere.
2. Crie um nó para cada caractere e insira-os em um Min-Heap.
3. Extraia os dois nós com menores frequências e crie um nó pai com a soma.
4. Insira o nó pai de volta no Min-Heap.
5. Repita até sobrar apenas a raiz da árvore.

**Entrada Exemplo:** `A: 5, B: 9, C: 12, D: 13, E: 16, F: 45`  
**Saída Exemplo:** Árvore de prefixos (esquerda=0, direita=1)

### 12. Nós Menores que um Valor em um Min Heap

**Descrição:** Dado um Min-Heap e um valor `X`, imprima todos os nós estritamente menores que `X`.

**Passo a passo:**
1. Inicie a busca pela raiz.
2. Se o valor for maior ou igual a `X`, pare nesse ramo.
3. Se for menor que `X`, imprima-o e busque recursivamente nos filhos.

**Entrada Exemplo:** `Heap = [2, 3, 15, 5, 4, 45, 80], X = 10`  
**Saída Exemplo:** `2, 3, 5, 4`

### 13. Conectar N Cordas com Custo Mínimo

**Descrição:** Encontre o custo mínimo para conectar `N` cordas de diferentes comprimentos.

**Passo a passo:**
1. Insira todos os comprimentos em um Min-Heap.
2. Enquanto houver mais de uma corda, extraia as duas menores.
3. Some os comprimentos e adicione ao custo total.
4. Insira a nova corda de volta ao heap.
5. Retorne o custo total acumulado.

**Entrada Exemplo:** `Comprimentos = [4, 3, 2, 6]`  
**Saída Exemplo:** `29`

### 14. K Combinações de Soma Máxima de Dois Arrays

**Descrição:** Encontre as `K` maiores somas formadas selecionando um elemento de cada array.

**Passo a passo:**
1. Ordene os dois arrays em ordem decrescente.
2. Use um Max-Heap para armazenar trios `(Soma, ÍndiceA, ÍndiceB)`.
3. Comece com `(ArrayA[0] + ArrayB[0], 0, 0)`.
4. Use uma estrutura para evitar índices repetidos.
5. Extraia `K` vezes, inserindo vizinhos `(i+1, j)` e `(i, j+1)` se não processados.

**Entrada Exemplo:** `A = [1, 4, 2, 3], B = [2, 5, 1, 6], K = 4`  
**Saída Exemplo:** `[10, 9, 9, 8]`

### 15. K-ésimo Maior Elemento em um Fluxo (Stream)

**Descrição:** Projete um sistema que leia números de um fluxo contínuo e informe o K-ésimo maior elemento a qualquer momento.

**Passo a passo:**
1. Mantenha um Min-Heap de tamanho máximo `K`.
2. Para cada número: se o heap tiver menos de `K` itens, adicione.
3. Se tiver `K` itens e o novo número for maior que a raiz, remova a raiz e adicione o novo.
4. A raiz será sempre o K-ésimo maior número.

**Entrada Exemplo:** `Fluxo = [10, 20, 11, 70, 50, 40, 100], K = 3`  
**Saída Exemplo:** `[-, -, 10, 11, 20, 40, 50]`

### 16. Maior Produto de Trios em um Fluxo

**Descrição:** Atualize o maior produto de 3 números conforme entram novos elementos no fluxo.

**Passo a passo:**
1. Armazene elementos em Max-Heap e Min-Heap conforme necessário.
2. O maior produto é o máximo entre: produto dos 3 maiores OU produto dos 2 menores vezes o maior.
3. Imprima o produto a cada novo elemento.

**Entrada Exemplo:** `Fluxo = [1, 2, 3, 4, 5]`  
**Saída Exemplo:** `[-1, -1, 6, 24, 60]`

### 17. K Elementos Mais Frequentes

**Descrição:** Retorne os `K` números que mais aparecem em um array.

**Passo a passo:**
1. Crie um HashMap com frequências de cada número.
2. Crie um Min-Heap armazenando pares `(Frequência, Número)`.
3. Percorra o HashMap: insira no heap e remova a raiz se ultrapassar `K`.
4. Os `K` elementos restantes são os mais frequentes.

**Entrada Exemplo:** `Array = [3, 1, 4, 4, 5, 2, 6, 1], K = 2`  
**Saída Exemplo:** `[1, 4]`

### 18. Converter Min Heap em Max Heap

**Descrição:** Modifique um array Min-Heap para que obedeça às regras de um Max-Heap.

**Passo a passo:**
1. Encontre o índice do último nó interno: `(N/2) - 1`.
2. A partir desse nó até a raiz, aplique Max-Heapify.
3. Max-Heapify troca o pai com o maior filho iterativamente para baixo.

**Entrada Exemplo:** `Min-Heap = [3, 5, 9, 6, 8, 20, 10, 12, 18, 9]`  
**Saída Exemplo:** `Max-Heap = [20, 18, 10, 12, 9, 9, 3, 5, 6, 8]`

### 19. Verificar se a Travessia em Nível Forma um Min Heap

**Descrição:** Verifique se um array (level order) representa um Min-Heap válido.

**Passo a passo:**
1. Trate o array como árvore onde filhos de `i` estão em `2i+1` e `2i+2`.
2. Itere de `i = 0` até o último nó interno `(N/2)-1`.
3. Verifique se cada nó é menor ou igual aos seus filhos.

**Entrada Exemplo:** `[10, 15, 14, 25, 30]`  
**Saída Exemplo:** `Verdadeiro`

### 20. Converter Árvore de Busca Binária (BST) em Min Heap

**Descrição:** Modifique uma BST para que se torne um Min-Heap.

**Passo a passo:**
1. Faça travessia In-Order armazenando valores em um array (crescente).
2. Faça travessia Pre-Order substituindo valores sequencialmente com o array ordenado.
3. O resultado formará um Min-Heap.

**Entrada Exemplo:** BST com Raiz=4, Esq=2, Dir=6, Esq.Esq=1, Esq.Dir=3, Dir.Esq=5, Dir.Dir=7  
**Saída Exemplo:** Min Heap com valores 1-7 na estrutura correta

### 21. K Pontos Mais Próximos da Origem

**Descrição:** Encontre os `K` pontos 2D mais próximos da origem `(0, 0)`.

**Passo a passo:**
1. Distância de `(x, y)` é `sqrt(x² + y²)` (use `x² + y²` para comparação).
2. Crie um Max-Heap armazenando pontos por distância.
3. Se o heap tiver menos de `K`, insira o ponto.
4. Se tiver `K` e o ponto for mais próximo que a raiz, remova a raiz e adicione o ponto.

**Entrada Exemplo:** `Pontos = [(1, 3), (-2, 2), (5, -1)], K = 2`  
**Saída Exemplo:** `[(-2, 2), (1, 3)]`

</details>

<details>
<summary>🔴 Nível 3 - Difícil</summary>

### 22. O Problema do Skyline

**Descrição:** Retorne o contorno do Skyline (pontos onde a altura muda) de um conjunto de edifícios.

**Passo a passo:**
1. Crie eventos de inícios e fins de edifícios ordenados por coordenada X.
2. Em empates de X: inícios antes de fins; maiores alturas antes de menores.
3. Use um Max-Heap para manter alturas ativas (comece com altura 0).
4. Ao encontrar início, adicione altura; ao encontrar fim, remova.
5. Se a altura máxima mudar, adicione `(X, altura máxima)` ao resultado.

**Entrada Exemplo:** `[(2, 9, 10), (3, 7, 15), (5, 12, 12)]`  
**Saída Exemplo:** `[(2, 10), (3, 15), (7, 12), (12, 0)]`

### 23. Mediana em um Fluxo de Dados

**Descrição:** Adicione números contínuamente e retorne a mediana a qualquer momento.

**Passo a passo:**
1. Mantenha um Max-Heap (metade inferior) e um Min-Heap (metade superior).
2. Max-Heap sempre tem igual ou um elemento a mais que Min-Heap.
3. Insira no Max-Heap se menor que seu topo; senão no Min-Heap.
4. Reequilibre movendo raízes entre heaps conforme necessário.
5. Mediana é o topo do Max-Heap (ímpar) ou média dos dois topos (par).

**Entrada Exemplo:** `Inserções: 5, 15, 1, 3`  
**Saída Exemplo:** `Medianas: 5, 10, 5, 4`

### 24. K-ésima Maior Soma de Subarray Contíguo

**Descrição:** Encontre a K-ésima maior soma possível de qualquer subarray contíguo.

**Passo a passo:**
1. Crie um Min-Heap de tamanho `K`.
2. Gere somas de prefixo do array.
3. Use loops aninhados para testar todas as somas de subarrays.
4. Se o heap não estiver cheio, insira; se estiver e a soma for maior que o topo, atualize.
5. O elemento no topo será a K-ésima maior soma.

**Entrada Exemplo:** `Array = [20, -5, -1], K = 3`  
**Saída Exemplo:** `14` (Somas: 20, 15, 14, -5, -6, -1)

### 25. Ordenar Elementos por Frequência

**Descrição:** Ordene decrescente pela frequência de aparecimento dos elementos.

**Passo a passo:**
1. Crie um HashMap com frequências.
2. Crie um Max-Heap personalizado comparando frequência e desempate.
3. Insira os dados no heap.
4. Extraia elementos multiplicando pelo número de frequências.

**Entrada Exemplo:** `[2, 5, 2, 8, 5, 6, 8, 8]`  
**Saída Exemplo:** `[8, 8, 8, 2, 2, 5, 5, 6]`

### 26. Mesclar K Arrays e Listas Encadeadas Ordenadas

**Descrição:** Junte `K` arrays/listas ordenados em um único array ordenado.

**Passo a passo:**
1. Crie um Min-Heap com primeiro elemento de cada array.
2. Armazene valor, índice do array e índice do elemento.
3. Enquanto o heap não estiver vazio, extraia o topo e adicione à lista final.
4. Pegue o próximo elemento da mesma estrutura e adicione ao heap.

**Entrada Exemplo:** `Listas = [[1, 4, 5], [1, 3, 4], [2, 6]]`  
**Saída Exemplo:** `[1, 1, 2, 3, 4, 4, 5, 6]`

### 27. Menor Intervalo Cobrindo K Listas Ordenadas

**Descrição:** Encontre o menor intervalo `[start, end]` contendo pelo menos um número de cada uma das `K` listas.

**Passo a passo:**
1. Inicialize um Min-Heap com o primeiro elemento de cada lista.
2. Rastreie o valor máximo atual.
3. Intervalo inicial: `[Min do Heap, Máximo rastreado]`.
4. Extraia o menor, adicione o próximo da mesma lista e compare com o menor intervalo.
5. Pare quando uma lista se esgotar.

**Entrada Exemplo:** `[[4, 10, 15], [1, 3, 6, 9], [2, 5, 7]]`  
**Saída Exemplo:** `[4, 7]`

### 28. Árvore Geradora Mínima de Prim

**Descrição:** Encontre o subconjunto de arestas com soma mínima conectando todos os vértices.

**Passo a passo:**
1. Comece de um vértice inicial e marque como visitado.
2. Insira todas as arestas adjacentes em um Min-Heap (por peso).
3. Enquanto houver nós não visitados: extraia a menor aresta.
4. Se o destino não foi visitado, adicione-o, some o custo e insira suas arestas.

**Entrada Exemplo:** `Vértices = 4. Arestas = (0-1: 10), (0-2: 6), (0-3: 5), (1-3: 15), (2-3: 4)`  
**Saída Exemplo:** `Custo Mínimo: 19`

### 29. Caminho Mais Curto de Dijkstra

**Descrição:** Encontre a menor distância do vértice origem para todos os outros (pesos não negativos).

**Passo a passo:**
1. Inicialize distâncias como infinito, exceto origem (0).
2. Insira `(Distância=0, Vértice=Origem)` em um Min-Heap.
3. Enquanto o heap não estiver vazio, extraia o vértice com menor distância.
4. Para cada vizinho, se `distância atual + peso` for menor, atualize e insira no heap.

**Entrada Exemplo:** `Grafo: 0→1(2), 0→2(4), 1→2(1), Origem: 0`  
**Saída Exemplo:** `Distâncias: 0: 0, 1: 2, 2: 3`

### 30. Ordenar Números Armazenados em Diferentes Máquinas

**Descrição:** Simule ordenação distribuída de números massivamente divididos em diferentes fontes ordenadas.

**Passo a passo:**
1. Cada máquina fornece lista ordenada consumida como fluxo.
2. Use Min-Heap na memória principal com primeiro número de cada máquina.
3. Grave o menor item do heap no arquivo de saída.
4. Puxe o próximo item da máquina que forneceu o item gravado.

**Entrada Exemplo:** `M1: [1, 5, 9], M2: [2, 6, 10], M3: [3, 7, 8]`  
**Saída Exemplo:** `[1, 2, 3, 5, 6, 7, 8, 9, 10]`

### 31. Maior Desarranjo de uma Sequência

**Descrição:** Gere a maior sequência onde nenhum elemento fique na sua posição original.

**Passo a passo:**
1. Calcule frequências usando um Max-Heap.
2. Em um desarranjo, posição `i` não deve ter `ArrayOriginal[i]`.
3. Consuma do Max-Heap alocando o mais frequente em posições permitidas, priorizando maiores numericamente.

**Entrada Exemplo:** `[1, 2, 3, 4]`  
**Saída Exemplo:** `[4, 3, 2, 1]`

### 32. Mesclar Dois Max Heaps Binários

**Descrição:** Mescle dois arrays Max-Heap em um novo array Max-Heap.

**Passo a passo:**
1. Concatene os dois arrays.
2. A partir do índice `(tamanhoTotal / 2) - 1` até 0, aplique Max-Heapify.

**Entrada Exemplo:** `Heap1 = [10, 5, 6, 2], Heap2 = [12, 7, 9]`  
**Saída Exemplo:** `[12, 10, 9, 2, 5, 7, 6]`

### 33. Soma dos Elementos entre o K1-ésimo e o K2-ésimo Menores

**Descrição:** Encontre a soma de elementos estritamente entre o K1-ésimo e K2-ésimo menores.

**Passo a passo:**
1. Encontre K1-ésimo menor usando Max-Heap de tamanho K1.
2. Encontre K2-ésimo menor usando Max-Heap de tamanho K2.
3. Percorra o array somando elementos estritamente entre ambos.

**Entrada Exemplo:** `Array = [20, 8, 22, 4, 12, 10, 14], K1 = 3, K2 = 6`  
**Saída Exemplo:** `26` (3º menor: 10. 6º menor: 20. Entre: 12 + 14 = 26)

### 34. Estrutura de Dados com Mínimo e Máximo O(1)

**Descrição:** Projete estrutura permitindo inserir/remover extremos em O(log N) e buscá-los em O(1).

**Passo a passo:**
1. Mantenha Min-Heap e Max-Heap.
2. Cada elemento inserido é um objeto com ponteiros/índices em ambos.
3. Adicione referências cruzadas: nó em um heap conhece seu índice no outro.
4. Acesse extremos em O(1), remova em O(log N) utilizando referências cruzadas.

**Entrada Exemplo:** `Insere(5), Insere(10), Insere(2), Max(), Min(), ExtraiMax()`  
**Saída Exemplo:** `Max: 10, Min: 2. Após extrair max, novo Max: 5.`

</details>