# Lista de Exercícios - Estruturas de Dados Grafos

Esta lista contém uma série de exercícios estruturados por nível de dificuldade para o aprimoramento da lógica de programação utilizando Grafos. Siga o passo a passo de cada problema para chegar à solução, implementando na linguagem de sua preferência.

<details>
<summary>🟢 Nível 1 - Fácil</summary>

### 1. Travessia em Largura (BFS) em um Grafo

**Descrição:** Implemente a busca em largura (Breadth-First Search) para percorrer um grafo a partir de um nó de origem.

**Passo a Passo:**

1. Crie uma Fila (Queue) e um vetor/array de "visitados" (booleanos).
2. Marque o nó de origem como visitado e insira-o na fila.
3. Enquanto a fila não estiver vazia, remova o primeiro nó e adicione-o ao resultado.
4. Para cada vizinho não visitado deste nó, marque-o como visitado e coloque-o na fila.

**Entrada:** O número de vértices (V), uma lista de adjacências representando o grafo e o nó inicial.

**Saída:** Uma lista/array contendo a ordem dos vértices visitados na travessia.

### 2. Travessia em Profundidade (DFS) em um Grafo

**Descrição:** Implemente a busca em profundidade (Depth-First Search) para percorrer um grafo a partir de um nó de origem.

**Passo a Passo:**

1. Crie um vetor de "visitados" preenchido com falso.
2. Crie uma função recursiva que receba o nó atual.
3. Na função, marque o nó como visitado e adicione-o ao resultado.
4. Chame a função recursivamente para todos os vizinhos não visitados do nó atual.

**Entrada:** O número de vértices (V), a lista de adjacências e o nó inicial.

**Saída:** Lista contendo a ordem dos vértices visitados na travessia DFS.

### 3. Caminho Mais Curto em um Grafo Não Ponderado

**Descrição:** Encontre o tamanho do caminho mais curto (menor número de arestas) entre um nó de origem e um nó de destino.

**Passo a Passo:**

1. Utilize o algoritmo BFS. Crie uma fila e um vetor de distâncias inicializado com infinito (ou -1).
2. Defina a distância do nó de origem para ele mesmo como 0 e insira-o na fila.
3. Ao visitar um vizinho, se a sua distância for infinito, atualize-a para `distância_atual + 1` e coloque-o na fila.
4. Pare ou retorne o valor quando alcançar o nó de destino.

**Entrada:** Um grafo, o nó de origem `S` e o nó de destino `D`.

**Saída:** Um número inteiro representando a quantidade mínima de arestas para ir de `S` a `D`.

### 4. BFS 0-1 (Caminho Mais Curto em Grafo com Pesos Binários)

**Descrição:** Encontre o caminho mais curto em um grafo onde o peso de cada aresta é apenas 0 ou 1.

**Passo a Passo:**

1. Use uma Deque (Fila de Duas Pontas) e um array de distâncias preenchido com infinito.
2. Comece pelo nó raiz com distância 0 e coloque-o na frente da deque.
3. Retire um nó. Para cada vizinho, calcule a nova distância.
4. Se o peso for 0, insira o vizinho na _frente_ da deque. Se for 1, insira no _final_ da deque.

**Entrada:** Um grafo com arestas de peso 0 ou 1 e um vértice origem.

**Saída:** Um vetor de distâncias mínimas do nó de origem para todos os outros.

### 5. Contar o Número de Árvores em uma Floresta

**Descrição:** Determine a quantidade de componentes conexos (árvores independentes) que formam um grafo não direcionado (floresta).

**Passo a Passo:**

1. Crie um array de nós visitados preenchido com falso.
2. Inicie um contador de árvores em zero.
3. Percorra todos os vértices de `0` até `V-1`. Se um vértice não foi visitado, incremente o contador.
4. Faça uma travessia DFS ou BFS a partir desse vértice para marcar todos os nós pertencentes à mesma árvore como visitados.

**Entrada:** Número de vértices e lista de adjacências do grafo.

**Saída:** Inteiro representando o número de árvores.

### 6. Ordenação Topológica

**Descrição:** Encontre a ordenação linear dos vértices de um Grafo Direcionado Acíclico (DAG) onde para toda aresta U → V, U aparece antes de V.

**Passo a Passo:**

1. Crie uma Pilha (Stack) e um array de visitados.
2. Para cada vértice não visitado, aplique uma função recursiva (DFS).
3. Após visitar recursivamente todos os vizinhos de um vértice, adicione esse vértice ao topo da pilha.
4. Esvazie a pilha para obter a ordenação.

**Entrada:** Grafo Direcionado Acíclico (DAG).

**Saída:** Um vetor de vértices em ordem topológica.

### 7. Todas as Ordenações Topológicas de um Grafo Direcionado Acíclico

**Descrição:** Encontre e imprima todas as ordenações topológicas possíveis de um DAG.

**Passo a Passo:**

1. Calcule o grau de entrada (in-degree) de cada vértice.
2. Use Backtracking com recursão. Itere sobre todos os vértices.
3. Se um vértice tem grau de entrada 0 e não foi visitado, adicione ao resultado, marque-o como visitado e reduza o grau de entrada de seus vizinhos em 1.
4. Faça a chamada recursiva. Após voltar da recursão (backtrack), desfaça as alterações (restaure o grau de entrada e desmarque como visitado).

**Entrada:** Grafo Direcionado Acíclico (DAG).

**Saída:** Múltiplas listas, cada uma representando uma ordenação topológica válida.

### 8. Algoritmo de Kahn para Ordenação Topológica

**Descrição:** Solução iterativa (baseada em BFS e grau de entrada) para encontrar a ordenação topológica.

**Passo a Passo:**

1. Calcule o grau de entrada (in-degree) de todos os nós.
2. Coloque na Fila todos os nós com in-degree igual a 0.
3. Remova um nó da Fila, adicione à lista resultante, e para cada vizinho, subtraia 1 de seu in-degree.
4. Se o in-degree do vizinho se tornar 0, adicione-o à Fila. Repita até a fila esvaziar.

**Entrada:** Grafo Direcionado Acíclico (DAG).

**Saída:** Array contendo uma ordem topológica (ou erro se detectar ciclo).

### 9. Soma das Dependências em um Grafo

**Descrição:** Dado um grafo direcionado, conte o número total de dependências. O número de dependências de um nó é o número de arestas que saem dele (seu grau de saída).

**Passo a Passo:**

1. Inicialize um contador com zero.
2. Percorra a lista de adjacências de cada vértice do grafo.
3. O tamanho da lista de adjacência de cada vértice é o seu grau de saída. Adicione este tamanho ao contador.
4. Retorne o contador.

**Entrada:** Lista de adjacências de um grafo.

**Saída:** Um número inteiro representando o total de arestas no grafo.

### 10. Nó de Peso Máximo

**Descrição:** Encontre o nó que possui a maior soma de índices dos nós que apontam diretamente para ele.

**Passo a Passo:**

1. Inicialize um array de "pesos" com tamanho `V` preenchido com zero.
2. Percorra o array de entrada `Edge[]` onde `Edge[i] = j` significa que há uma aresta de `i` para `j`.
3. Para cada aresta apontando para `j`, some `i` ao peso do nó `j` (`pesos[j] += i`).
4. Encontre e retorne o índice do array de pesos que possui o maior valor absoluto.

**Entrada:** Um array `Edge` onde a posição `i` indica um ponteiro para `Edge[i]`.

**Saída:** O índice (nó) com a maior soma.

</details>

<details>
<summary>🟠 Nível 2 - Médio</summary>

### 11. Fecho Transitivo de um Grafo usando DFS

**Descrição:** Determine se um vértice `j` é alcançável a partir de um vértice `i` para todos os pares de vértices no grafo.

**Passo a Passo:**

1. Crie uma matriz de conectividade booleana `N x N` inicializada com falso.
2. Para cada vértice `i`, inicie uma travessia DFS considerando-o como origem.
3. Toda vez que alcançar um vértice `j` durante o DFS a partir de `i`, marque `matriz[i][j] = verdadeiro`.

**Entrada:** Matriz ou lista de adjacência de um grafo.

**Saída:** Uma matriz 2D binária onde a posição (i,j) é 1 se houver caminho de `i` a `j`.

### 12. Tomates Podres

**Descrição:** Matriz em que 0 é vazio, 1 é um tomate fresco e 2 é podre. A cada unidade de tempo, tomates podres apodrecem os vizinhos diretos frescos. Calcule o tempo mínimo para apodrecer todos.

**Passo a Passo:**

1. Encontre as posições iniciais de todos os tomates podres e coloque-os em uma fila para BFS simultâneo. Conte os frescos.
2. Processe a fila por níveis. Para cada podre removido, cheque acima, abaixo, esquerda e direita.
3. Se o vizinho for fresco, transforme em podre (2), reduza a contagem de frescos e insira na fila. Incremente o tempo (minutos).
4. Se após a BFS ainda houver tomates frescos, retorne -1.

**Entrada:** Uma matriz bidimensional de inteiros contendo 0, 1 e 2.

**Saída:** Inteiro representando os minutos decorridos (ou -1 se for impossível).

### 13. Ilhas em um Grafo

**Descrição:** Dado um mapa bidimensional (matriz booleana) onde 1 é terra e 0 é água, conte o número de ilhas (conjunto de 1s conectados horizontal, vertical ou diagonalmente).

**Passo a Passo:**

1. Crie uma matriz `visitados` de mesmo tamanho.
2. Itere por cada célula. Se for terra (1) e não visitada, incremente o contador de ilhas.
3. Acione uma DFS ou BFS a partir desta célula para marcar como visitada toda a terra adjacente em 8 direções.

**Entrada:** Matriz 2D de 0s e 1s.

**Saída:** Inteiro com a quantidade de ilhas.

### 14. Preenchimento por Inundação (Flood Fill)

**Descrição:** Semelhante à ferramenta "Balde de Tinta" do Paint. Mude a cor de um pixel escolhido e de todos os seus pixels vizinhos (conexos) da mesma cor original.

**Passo a Passo:**

1. Identifique a cor original nas coordenadas dadas. Se a cor nova for igual, retorne a matriz.
2. Realize DFS recursiva ou BFS passando as coordenadas atuais.
3. Se a coordenada estiver fora dos limites ou a cor for diferente da original, encerre a chamada.
4. Mude a cor atual e faça recursão para cima, baixo, esquerda, direita.

**Entrada:** Matriz 2D de inteiros (representando cores), coordenada inicial (x,y) e a nova cor.

**Saída:** A matriz atualizada com o preenchimento.

### 15. Verificar se é Bipartido

**Descrição:** Determine se é possível dividir os vértices de um grafo em dois conjuntos de forma que nenhuma aresta conecte vértices do mesmo conjunto (Coloração com 2 cores).

**Passo a Passo:**

1. Crie um vetor de cores (ex: 0 e 1), preenchido com -1 (não colorido).
2. Percorra todos os vértices. Se um vértice não foi colorido, inicie uma BFS.
3. Pinte o vértice inicial com cor 0. Para todos os vizinhos:
4. Se o vizinho não tiver cor, dê a ele a cor invertida e coloque na fila. Se o vizinho tiver a mesma cor do atual, retorne Falso.

**Entrada:** Lista de adjacência de um grafo.

**Saída:** Booleano (Verdadeiro ou Falso).

### 16. Escada de Palavras (Word Ladder)

**Descrição:** Encontre o número mínimo de palavras para ir de uma palavra origem até uma destino, mudando uma letra por vez, sempre existindo num dicionário.

**Passo a Passo:**

1. Insira todas as palavras do dicionário em um Set (Conjunto) para busca rápida em O(1).
2. Coloque a palavra de origem em uma fila junto com a distância inicial (1) para iniciar a BFS.
3. Remova a palavra da frente. Para cada caractere da palavra, tente substituir por letras de 'a' a 'z'.
4. Se a nova palavra existir no Set, é um vizinho válido. Remova do Set (para não revistar) e coloque na fila com a distância + 1. Pare quando atingir o alvo.

**Entrada:** Palavra de início, palavra de fim, lista (dicionário) de palavras válidas.

**Saída:** Inteiro com o tamanho do caminho mínimo (ou 0 se impossível).

### 17. Cobras e Escadas

**Descrição:** Encontre o número mínimo de lances de um dado (de 1 a 6) para ir da casa 1 a 100 num tabuleiro com atalhos (escadas sobem, cobras descem).

**Passo a Passo:**

1. Modele o tabuleiro como um grafo direcionado onde cada nó `i` pode ir para `i+1` até `i+6`.
2. Se o destino do dado possuir escada ou cobra, o destino real será o fim da cobra/escada.
3. Use BFS com uma fila contendo o nó atual e a quantidade de jogadas.
4. Evite revisitar posições utilizando um vetor de visitados. O BFS garante o menor caminho.

**Entrada:** Dois arrays/dicionários mapeando o início e fim de cobras e escadas, N = 100.

**Saída:** Número mínimo de jogadas de dado.

### 18. Problema dos Jarros de Água

**Descrição:** Tendo dois jarros com capacidades `A` e `B` e um suprimento de água, use BFS para ver se é possível obter exatamente a quantidade `C` em algum dos jarros.

**Passo a Passo:**

1. O estado na BFS é uma dupla `(atualA, atualB)`. Inicialmente `(0, 0)`.
2. Crie as transições possíveis: Encher A, Encher B, Esvaziar A, Esvaziar B, Passar A para B, Passar B para A.
3. Registre estados visitados para evitar loops infinitos.
4. Se em algum momento o estado alcançar `C` em um dos lados, retorne verdadeiro.

**Entrada:** Inteiros de capacidade A, B e meta C.

**Saída:** O número mínimo de passos para o objetivo, ou impossível.

### 19. Caminho Mais Curto em Matriz Binária

**Descrição:** Encontre o tamanho do caminho mais curto do canto superior esquerdo até o inferior direito de uma matriz, passando apenas por 1s (espaço livre) e movendo-se nas 4 direções.

**Passo a Passo:**

1. Trate cada célula `1` como vértice.
2. Inicie a BFS a partir da posição `(0,0)` com distância inicial 0 ou 1.
3. Ao visitar os vizinhos (cima, baixo, esquerda, direita), se for válido e for `1`, adicione à fila.
4. Registre distâncias num vetor bidimensional paralelo. Pare em `(n-1, m-1)`.

**Entrada:** Matriz bidimensional N x M.

**Saída:** Inteiro com a menor distância, ou -1.

### 20. Clonar um Grafo

**Descrição:** Faça uma cópia profunda (Deep Copy) de um grafo não direcionado conectado a partir de uma referência a um nó.

**Passo a Passo:**

1. Crie um Dicionário / Hash Map para mapear "Nó Original" para "Novo Nó Clonado".
2. Inicie uma travessia DFS ou BFS. Quando encontrar um nó, crie uma cópia dele e guarde no map.
3. Para cada vizinho do nó atual, se ele já estiver no map, adicione essa cópia à lista de vizinhos do nó recém-criado.
4. Se o vizinho não estiver no map, faça a chamada recursiva (no caso de DFS) para cloná-lo primeiro.

**Entrada:** Referência para um nó do grafo inicial.

**Saída:** Referência para a cópia (clone) correspondente ao nó inicial.

### 21. Detectar Ciclo em Grafo Direcionado

**Descrição:** Verifique se existe algum caminho que leve de volta a um nó que já está no caminho atual.

**Passo a Passo:**

1. Utilize o DFS. Mantenha dois arrays de booleanos: `visitados` e `na_pilha_de_recursao`.
2. Para cada vértice não visitado, chame a DFS.
3. Ao entrar no vértice, marque `visitados[v] = true` e `na_pilha_de_recursao[v] = true`.
4. Visite os vizinhos. Se um vizinho não foi visitado, prossiga a DFS. Se ele já foi visitado E está `na_pilha_de_recursao`, há um ciclo! Ao final, marque `na_pilha...[v] = false`.

**Entrada:** Número de Vértices e lista de adjacências direcionadas.

**Saída:** Booleano True se ciclo existir, senão False.

### 22. Detectar Ciclo em Grafo Não Direcionado

**Descrição:** Verifique se existe um ciclo no grafo onde as arestas vão nas duas direções.

**Passo a Passo:**

1. Use DFS ou BFS. Mantenha o vetor de visitados.
2. Em DFS, passe o vértice atual e o vértice `pai` de onde você veio.
3. Se durante a visita você encontrar um vizinho que já foi marcado como visitado E que não é o `pai` atual, então o grafo contém um ciclo.

**Entrada:** Lista de adjacência não direcionada.

**Saída:** Booleano indicando presença de ciclo.

### 23. Detectar Ciclo Negativo em um Grafo (Bellman Ford)

**Descrição:** Determine se o grafo direcionado ponderado contém ciclos onde a soma dos pesos das arestas é um número negativo.

**Passo a Passo:**

1. Inicialize as distâncias de uma origem para todos os nós como infinito, e 0 para origem.
2. Relaxe todas as arestas `(u, v, peso)` repetindo a fórmula `dist[v] = min(dist[v], dist[u] + peso)` `V-1` vezes (sendo V o total de vértices).
3. Faça uma última iteração sobre todas as arestas.
4. Se ainda assim a distância puder ser minimizada, o grafo contém um ciclo negativo.

**Entrada:** Total de vértices, total de arestas e lista de arestas com peso `(u, v, w)`.

**Saída:** Verdadeiro (há ciclo negativo) ou Falso.

### 24. Ciclos de Comprimento N em Grafo Não Direcionado e Conexo

**Descrição:** Conte quantos ciclos existem no grafo com o comprimento exato de `N` arestas.

**Passo a Passo:**

1. Utilize Backtracking / DFS modificada, começando por cada nó.
2. Na DFS, mantenha o comprimento do caminho percorrido até então (inicia em `n-1`).
3. Ao atingir o tamanho 0, verifique se há uma aresta conectando o nó atual de volta ao nó de origem do caminho. Se sim, incremente o contador de ciclos.
4. Como grafos não direcionados duplicarão a contagem e verificarão as duas direções, divida o resultado final por 2.

**Entrada:** Matriz de adjacência, total de nós V, e tamanho do ciclo N.

**Saída:** Número inteiro com o total de ciclos contados.

### 25. Detectar Ciclo Negativo usando Floyd Warshall

**Descrição:** Verifique todos os pares de arestas e detecte se a matriz possui ciclos com pesos negativos.

**Passo a Passo:**

1. Construa a matriz de distâncias com peso direto entre (i,j) ou infinito, e 0 na diagonal principal (i=j).
2. Execute os três loops de Floyd-Warshall (`k`, `i`, `j`) relaxando `dist[i][j] = min(dist[i][j], dist[i][k] + dist[k][j])`.
3. Após o algoritmo, verifique a diagonal principal da matriz.
4. Se existir algum valor negativo onde a linha e coluna sejam as mesmas (`dist[i][i] < 0`), há ciclo negativo.

**Entrada:** Matriz de grafos com pesos das arestas.

**Saída:** Retorno booleano sobre o ciclo negativo.

### 26. Clonar um Grafo Direcionado Acíclico (DAG)

**Descrição:** Crie uma cópia exata de nós em um Grafo Acíclico e Direcionado.

**Passo a Passo:**

1. Como o DAG não tem ciclos, DFS e um Mapa para referências já criadas é eficiente e suficiente.
2. Dado um nó, verifique se ele existe no Mapa de Clones. Se sim, retorne-o.
3. Se não, crie uma cópia. Aloque-o no mapa.
4. Iterativamente processe os filhos originais do nó, clone-os e ligue-os na cópia do nó atual.

**Entrada:** Vértice raiz/origem do DAG original.

**Saída:** Vértice clonado correspondente.

### 27. Introdução à Estrutura de Conjuntos Disjuntos (Union-Find)

**Descrição:** Implemente uma estrutura para verificar se vértices pertencem ao mesmo conjunto, ideal para detectar ciclos não direcionados e encontrar componentes.

**Passo a Passo:**

1. Crie um array `parent` preenchido onde cada elemento é seu próprio pai inicialmente (`parent[i] = i`).
2. Implemente o método `Find`: Suba na árvore do array `parent` até achar a raiz (um nó pai dele mesmo).
3. Implemente o método `Union(u, v)`: Encontre as raízes de `u` e `v`. Se forem diferentes, faça o pai de uma se tornar o pai da outra.

**Entrada:** Array de arestas.

**Saída:** Funções capazes de agrupar nós e verificar pertencimento ao grupo.

### 28. União por Rank e Compressão de Caminho no Union-Find

**Descrição:** Otimização obrigatória para operações eficientes em Disjoint Set O(α(N)).

**Passo a Passo:**

1. Crie dois arrays: `parent` e `rank` (profundidade da árvore, inicial=0).
2. Compressão (Find): Ao buscar um pai, faça recursivamente com que os nós visados apontem diretamente para a raiz `parent[x] = find(parent[x])`.
3. Union By Rank: Encontre raízes. Conecte a árvore com menor `rank` embaixo da árvore de maior `rank`. Se empatarem, aumente o rank da nova raiz principal em +1.

**Entrada:** Operações para união e busca de conjuntos.

**Saída:** Estrutura otimizada e eficiente para grafos grandes.

### 29. Algoritmo do Caminho Mais Curto de Dijkstra

**Descrição:** Obtenha o menor caminho saindo de um nó para todos os outros em grafos com pesos positivos.

**Passo a Passo:**

1. Crie array de distâncias inicializado com Infinito, e zero para a raiz.
2. Use uma Fila de Prioridade (Min-Heap) inserindo (0, origem).
3. Remova o vértice de menor custo. Se ele foi finalizado, descarte.
4. Verifique os vizinhos. Relaxamento: Se `dist[atual] + peso < dist[vizinho]`, atualize `dist[vizinho]` e adicione à Heap.

**Entrada:** Grafo valorado e positivo; nó de origem.

**Saída:** Array das distâncias mínimas do nó de origem a todos.

### 30. Algoritmo de Bellman-Ford

**Descrição:** O equivalente do menor caminho que suporta, diferentemente do Dijkstra, grafos contendo arestas de peso negativo.

**Passo a Passo:**

1. Guarde arestas no formato de lista simples. Inicialize distâncias como infinito (0 no inicial).
2. Faça um laço de tamanho `V-1` vezes.
3. Para cada aresta no grafo `u -> v` com peso `w`: atualize `dist[v]` caso seja mais vantajoso ir via `u`.

**Entrada:** Arestas e vértices. Nó origem.

**Saída:** Distâncias menores suportando pesos negativos.

### 31. Algoritmo de Floyd-Warshall

**Descrição:** Calcule o caminho mais curto entre todos os pares de vértices possíveis simultaneamente, O(V³).

**Passo a Passo:**

1. Construa matriz inicial (distâncias conhecidas com pesos das arestas, 0 na diagonal, infinito onde não há aresta).
2. Três aninhamentos `para k`, `para i` e `para j`.
3. `k` age como o nó intermediário. `dist[i][j] = Min(dist[i][j], dist[i][k] + dist[k][j])`.

**Entrada:** Matriz de adjacência com os pesos entre nós.

**Saída:** Matriz resultante completa com todos os caminhos mínimos para todos.

### 32. Algoritmo de Johnson para Todos os Caminhos Mais Curtos

**Descrição:** Obtenha menor caminho entre todos os pares, ideal para grafos esparsos (melhor que Floyd Warshall), suportando arestas negativas e resolvendo com Dijkstra adaptado.

**Passo a Passo:**

1. Adicione um novo vértice "dummy" `S` ligado a todos os outros com peso 0.
2. Rode Bellman-Ford a partir de `S` gerando novos "pesos potenciais" `h[v]`.
3. Repondere todas as arestas com: `novo_peso(u,v) = peso_antigo + h[u] - h[v]`. Agora o grafo é todo não negativo.
4. Remova o nó `S` e execute o rápido algoritmo de Dijkstra a partir de cada vértice.

**Entrada:** Matriz de adjacências, nós, arestas (podem ser negativas).

**Saída:** Matriz de caminhos mais curtos ajustada.

### 33. Grafo de Múltiplos Estágios (Caminho Mais Curto)

**Descrição:** Achar caminho mínimo de Origem a Destino, mas as arestas apenas transitam em "camadas" contínuas de um grafo ordenado progressivamente (1 a N).

**Passo a Passo:**

1. Inicialize um vetor `dist` do tamanho dos nós. O Destino recebe `dist[Dest] = 0`.
2. Itere do Destino até o Início (do nível superior ao inferior da camada).
3. Para o nó atual `i`, procure todos os destinos adjacentes `j`. Calcule e memorize o caminho mais vantajoso de i a j até o fim.

**Entrada:** Grafo multi-estágios ordenado em matriz ou listas adjacentes.

**Saída:** Distância mínima até o último nó.

### 34. Algoritmo de Karp para Ciclo de Peso Médio Mínimo

**Descrição:** Em um grafo direcionado onde a média do peso é a soma do peso dividido pelo número de arestas do ciclo. Encontre a média do ciclo menor.

**Passo a Passo:**

1. Encontre os menores caminhos a partir de um vértice arbitrário V para qualquer outro `v`, com comprimento exato variando de `0` a `V` arestas usando programação dinâmica.
2. Aplique a fórmula de Karp baseada nesses menores caminhos `max_{k} ((dist_V(v) - dist_k(v)) / (V-k))`.
3. Extraia o valor mínimo dentre esses máximos calculados, que resultará na média ótima.

**Entrada:** Matrizes com pesos do grafo.

**Saída:** Ponto Flutuante / Double representando a relação peso médio mínima.

### 35. Encontrar Ciclo de Peso Mínimo em Grafo Não Direcionado

**Descrição:** Em grafos de pesos não negativos e não direcionados, achar o menor laço fechado simples válido.

**Passo a Passo:**

1. Inicialize o MenorCiclo como infinito.
2. Remova a aresta (u,v) do grafo.
3. Aplique um algoritmo de Caminho Mínimo (Dijkstra) de u a v, para encontrar qual seria o caminho caso voltasse sem passar por aquela aresta.
4. Some a distância obtida com o peso da aresta (u,v). Guarde no mínimo. Restaure a aresta.

**Entrada:** Arestas e pesos de grafos não direcionados.

**Saída:** Peso total mínimo para criar um ciclo.

### 36. Árvore Geradora Mínima de Prim (MST)

**Descrição:** Conecte todos os nós do grafo usando a menor quantidade possível de pesos combinados através do crescimento de uma árvore.

**Passo a Passo:**

1. Crie vetor bool "incluído", vetor chave `key` com infinitos. Inicie Nó 0 com `key = 0`.
2. MinHeap para extrair vértices pela menor chave.
3. Remova um u, e defina-o incluído.
4. Veja vizinhos `v`: se não estiver na MST e `peso(u,v) < key[v]`, adicione à fila atualizando `key[v]` e o vetor de parentesco.

**Entrada:** Lista de arestas e nós valorados.

**Saída:** As arestas que compõem a MST resultante.

### 37. Algoritmo da Árvore Geradora Mínima de Kruskal

**Descrição:** Gera MST adicionando do menor até o maior peso dentre as arestas, evitando ciclos.

**Passo a Passo:**

1. Ordene TODAS as arestas pelo seu Peso, de forma ascendente.
2. Inicie a estrutura Disjoint Set / Union-Find para cada vértice.
3. Itere aresta por aresta ordenadas. Se `Find(origem)` for diferente de `Find(destino)`, adicione a aresta à MST e faça o `Union(origem, destino)`.

**Entrada:** Lista não direcionada com pesos e as conexões `u`, `v`, `w`.

**Saída:** Subgrafo contendo os pesos mínimos exigidos (MST).

### 38. Diferença entre Algoritmos de Prim e Kruskal para MST

**Descrição:** (Teórico/Reflexivo) Ambos resolvem o mesmo caso, porém possuem diferentes formas.

**Passo a Passo:**

1. Em Prim, a árvore construída cresce sendo um único componente conexo sem interrupções.
2. Em Kruskal, formam-se várias pequenas árvores em florestas e elas vão se unindo no final.
3. Kruskal lida bem com grafos esparsos (poucas arestas) porque sua métrica primária é ordenar as arestas. Prim favorece grafos muito densos utilizando uma fila de prioridade com seus vértices.

**Entrada:** Não requer código.

**Saída:** Conceito das duas MST.

### 39. Aplicações do Problema da Árvore Geradora Mínima

**Descrição:** (Teórico) Projetar redes elétricas, malhas de telecomunicação em cidades e algoritmos de mapeamento em visão computacional.

**Passo a Passo:**

1. Entenda que a MST conecta sempre todos os vértices possíveis sem fazer loops desnecessários e no menor custo de material possível (cabos de fibra ótica, cabos elétricos, redes de roteadores).

**Entrada:** N/A.

**Saída:** N/A.

### 40. Custo Mínimo para Conectar Todas as Cidades

**Descrição:** Dada uma matriz contendo conexões viáveis e seus preços entre cidades, calcule como interligar todo o sistema de modo mais barato.

**Passo a Passo:**

1. Se assemelha muito a Prim ou Kruskal.
2. Converta os dados matriz em um formato `Aresta(origem, destino, preco)`.
3. Aplique o Kruskal: ordene os preços ascendente.
4. Junte pelo Union-Find cada cidade conectada ignorando redundâncias (ciclos), some o preço de todas incluídas e retorne.

**Entrada:** Matriz `N x N` com Cidades e respectivos Custos Viáveis.

**Saída:** Custo Integrado.

### 41. Árvore Geradora de Produto Mínimo

**Descrição:** Em vez de minimizar a SOMA dos pesos da MST, você deverá encontrar a MST que minimiza o PRODUTO (multiplicação) de todos os seus pesos.

**Passo a Passo:**

1. Utilizar o logaritmo em teoria minimiza produtos. `log(A * B) = log(A) + log(B)`.
2. Altere o peso de todas as arestas do grafo atual substituindo seus `pesos` diretos por `log(peso)`.
3. Construa a Árvore de Kruskal ou Prim neste novo grafo logarítmico.
4. As mesmas arestas selecionadas compõem a MST verdadeira do menor produto.

**Entrada:** Arestas originais de um grafo.

**Saída:** Lista de caminhos da MST ótima para produto.

### 42. Algoritmo de Exclusão Reversa para Árvore Geradora Mínima

**Descrição:** Similar a Kruskal em inverso: comece com o grafo todo preenchido e quebre sempre a aresta de MAIOR peso, cuidando para não desconectar o mapa.

**Passo a Passo:**

1. Ordene todas as arestas de forma DECRESCENTE de peso.
2. Para cada aresta mais pesada: remova-a temporariamente do grafo.
3. Cheque com um BFS/DFS se o grafo todo continua conexo.
4. Se conectividade rompeu, você precisa obrigatoriamente dela: reinsira na MST. Se continuou conexo, exclua permanente.

**Entrada:** Grafo base conexo com os pesos.

**Saída:** O Grafo reduzido com características de MST.

### 43. Algoritmo de Boruvka para Árvore Geradora Mínima

**Descrição:** MST focado no paralelismo. Une árvores sempre checando a aresta mais próxima de menor peso em cada grupo.

**Passo a Passo:**

1. Inicie com V componentes isolados (1 por vértice).
2. Repita até o número de florestas virar 1 só: iterativamente procure, para todos componentes presentes, qual é a aresta mais leve e barata externa a este componente que saia dali e alcance um diferente.
3. Selecione e insira-as com o Union-Find, descartando componentes fundidos e reduzindo seu número.

**Entrada:** Número de N, Arestas E.

**Saída:** Conjunto e soma MST Boruvka.

### 44. Máximo de Arestas que podem ser Adicionadas a um DAG mantendo-o DAG

**Descrição:** Adicione caminhos diretos permitidos para não quebrar o ciclo e ainda mantê-lo unidirecional acíclico.

**Passo a Passo:**

1. Faça a Busca e gere a Ordenação Topológica linear desse Grafo de Entrada em um Array.
2. Crie uma matriz checando conexões diretas `u` e `v`.
3. Percorra da Esquerda à Direita sobre a Ordenação de Topologia `O[0]` para todo o resto. Se `O[i]` não conecta `O[i+1, 2...]`, essa é uma nova aresta que você PODE adicionar legalmente, sempre da esquerda apontando para os vértices subsequentes da direita.

**Entrada:** DAG Vértices V e Arestas E.

**Saída:** Número inteiro total de arestas potenciais adicionáveis sem ciclos.

### 45. Caminho Mais Longo em um Grafo Direcionado Acíclico

**Descrição:** Encontrar o caminho crítico (máximo percurso) em direção contínua com percursos positivos/negativos.

**Passo a Passo:**

1. A base é achar a Ordenação Topológica do grafo empilhada e processá-la.
2. Inicie distâncias todas com menos Infinito e do `NóInicial` como zero.
3. Desempilhe cada vértice processando topologia: Para cada aresta `v` partindo desse topo, re-avalie `Max(dist[v], dist[atual] + peso)`.

**Entrada:** Nó inicial e um DAG Pesado.

**Saída:** As distâncias mais longas alcançáveis de A para Todos.

### 46. Ordenação Topológica usando Tempo de Partida do Vértice

**Descrição:** Variação para alcançar a Ordenação onde um vértice com maior tempo de saída se apresenta como dependência precedente.

**Passo a Passo:**

1. DFS Padrão rastreando visitas. No entanto, mantenha um contador de "tempo".
2. Toda vez que encerra visitar 100% todos os vizinhos descendentes de um vértice recursivo na Pilha DFS, grave o tempo atual nele e incremente.
3. O array resultante ordenado inversamente pelos tempos mais Altos formará uma validada sortação topológica.

**Entrada:** DAG.

**Saída:** Topologia temporal.

### 47. Encontrar Itinerário a partir de uma Lista de Passagens

**Descrição:** Dados vários bilhetes de passagem no formato Dicionário `[A -> B]`, crie um itinerário completo seguido sem repetições que visite todos eles contiguamente.

**Passo a Passo:**

1. Reúna em Mapa e faça Mapa Reversivo (Destino apontando a Origem).
2. A Cidade Origem é a única cidade cujo nome não se encontra na lista Reversiva como sendo um destino recebido de outro.
3. Começando dessa Raiz, basta buscar e encadear sequencialmente da hash table base principal imprimindo passo a passo.

**Entrada:** Tuplas de Strings de passagens.

**Saída:** Impressão em console sequencial e ordenada dos lugares.

### 48. Caminho e Circuito Euleriano

**Descrição:** O Caminho Euleriano visita cada aresta exatamente 1 vez, Circuito Euleriano começa e volta ao ponto de início. Condição vital: analisar os Graus dos Vértices de grafos não direcionados.

**Passo a Passo:**

1. Teste a verificação de conexidade DFS.
2. Conte se os Nós têm Graus (Arestas ligadas) pares.
3. Se 100% dos vértices têm graus Pares → É CIRCUITO.
4. Se exatos 2 nós no grafo possuem graus Ímpares, o restante Par → É apenas CAMINHO.
5. Qualquer outro → Nenhuma possibilidade Euleriana.

**Entrada:** Vértices Não diretos E Arestas.

**Saída:** Enum: [Caminho, Circuito, ou Não-Euleriano].

### 49. Algoritmo de Fleury para Caminho ou Circuito Euleriano

**Descrição:** Percorre ativamente e imprime uma trajetória de Fleury passando 1 única vez em todas as arestas.

**Passo a Passo:**

1. Verifique Graus. Inicie pelo nó de Grau Ímpar se tiver, se não comece no Zero.
2. Analise recursivamente adjacências: O Nó pode atravessar arestas. Jamais atravesse arestas classificadas como 'Pontes' (que se apagadas isolam pedaços do grafo), _a não ser_ que aquela seja literalmente a última aresta remanescente em volta.
3. Faça cópias e vá suprimindo nós conforme passa.

**Entrada:** O mapa conectado V/E validado para Euler.

**Saída:** Impressão dos passes.

### 50. Componentes Fortemente Conexos (Kosaraju)

**Descrição:** Componentes em Grafo Direcionado em que toda porção `v` pode chegar para si mesmo `v` se caminhado pelas arestas internas (Sessão fechada do grupo).

**Passo a Passo:**

1. A técnica Algoritmo de Kosaraju resolve muito bem usando 2 passagens de profundidade.
2. Primeira passagem: DFS colocando tempos de "termino / partida" terminados em uma Pilha (Stack).
3. Inverta e Transporte (Reverse) todas arestas desse mesmo grafo montando o Grafo Transposto.
4. Desempilhe os elementos marcados recursivos ordenados do Stack rodando novamente nova DFS. Cada rodada desempilhada dessa revelará em grupo o componente.

**Entrada:** Direcionado grafo.

**Saída:** Array listando matrizes/listas dos grupos separados Fortemente Conectados.

### 51. Contar Caminhos de uma Origem ao Destino com Exatamente K Arestas

**Descrição:** O método exato para atingir um nó usando estritamente K distâncias precisas (pode revisitar lugares).

**Passo a Passo:**

1. Em Grafos pequenos/matrizes adjacentes, implementa-se 3 blocos em loop com programação dinâmica.
2. Tabule valores em `DP[i][j][k_etapas]` que diz qual total até ali. Recursivamente, chegue de origem para todos intermediários usando `e-1` percursos.
3. Em matrizes, elevar a Matriz Binária de Adjacência para a potência pura de Matriz `Matriz^K` com multiplicação tradicional fará as propriedades da matemática calcularem diretamente todos caminhos precisos M[u][v].

**Entrada:** Matriz Adjacente N/N, k valor.

**Saída:** Valor com a contagem total de chances.

### 52. Circuito de Euler em Grafo Direcionado

**Descrição:** Uma direção única de fluxo que volta à origem rodando estritamente em cima das setas.

**Passo a Passo:**

1. Calcule os Graus. Para cada nó ele precisa estritamente Grau ENTRADA == Grau SAIDA idênticos, não desequilibrando (In == Out).
2. Faça DFS confirmando que todos vértices com `grau > 0` se encontrem plenamente unidos e atrelados no mesmo pacote conectado.
3. Caso ambas as passagens confirmem retorno Booleano Positivo, é viável Euleriano-Direcionado.

**Entrada:** N/E Vértices e Direções.

**Saída:** Verdade / Falso para validez de Circuito.

### 53. Caminhos para Viajar por Todos os Nós usando Todas as Arestas

**Descrição:** É literalmente o histórico contexto de pontes "Sete Pontes de Königsberg", provando conceito Caminho Euleriano.

**Passo a Passo:**

1. Utilize o código de validador de Grau: Cada ilha na cidade (vértice) foi medida pelas águas (arestas).
2. Se existem mais de duas ilhas que ligavam quantidades impares de pontes à outras áreas de terra firma, é fisicamente e matematicamente impossível fazer a travessia contínua sem repetição.

**Entrada:** Um modelo representacional de Nós das Sete Pontes.

**Saída:** False para caminho em Königsberg real.

### 54. Comprimento da Menor Cadeia para Alcançar a Palavra Alvo

**Descrição:** Este exercício é um espelho ao Problema #16 de Categoria Escada de Palavras usando Fila FIFO (Busca BFS Básica). Repetido propositalmente conforme instruído.

**Passo a Passo:** Ver Item #16. Mesmas condições com String de Set e distanciamento `1..1..n`.

**Entrada:** Word Origem, Alvo.

**Saída:** Retorno menor Int.

### 55. Conectividade Dinâmica (Incremental)

**Descrição:** Acompanhe modificações constantes sendo feitas ao longo do processo no Grafo com adição progressiva sem recalcular todo DFS desde o início toda hora (Union-Find).

**Passo a Passo:**

1. A Union/Find em complexidade Disjoint Set resolve a Conectividade Incremental.
2. Crie e inicie a árvore vazia com ranks para vértices soltos.
3. Para cada nova "AddAresta", dê Update da União, mantendo raízes comprimidas.
4. Responda imediatamente a "EstãoConectados(a,b)" verificando as raízes pela `find` instantânea.

**Entrada:** Lote em processamento constante Arestas Novas / Buscas novas.

**Saída:** Array Dinâmico de validações (True/False para caminhos no exato momento).

### 56. Introdução ao Problema de Fluxo Máximo

**Descrição:** Problema fundamental de modelagem onde existem torneiras Origem (S) de líquido sem fim para Desaguadouros/Sumidouros Destinos (T), com canos contendo capacidades limite. Objetivo: calcular vazão máxima atingível no cano alvo.

**Passo a Passo:**

1. Represente Capacidades Restiduais e Formato Direcionado.
2. A meta principal requer achar "Caminhos de Aumento" no meio dos vazios residuais limitados.
3. Abordagens populares são Ford-Fulkerson ou Dinic Algorithm usando matriz adjacente para deduzir vazão subtraindo do limitador.

**Entrada:** Grafo/Rede Com Direções.

**Saída:** Capacidade T.

### 57. Algoritmo de Ford-Fulkerson para Fluxo Máximo

**Descrição:** Utilize Caminhos Residuais e BFS/DFS para descobrir estradas de gargalo remanescente para encher sua rede.

**Passo a Passo:**

1. Use e duplique a matriz em sua Matriz Residual atualizando ela cada ciclo.
2. Implemente BFS procurando um caminho contínuo de capacidade superior a `> 0` de `S` para `T`.
3. Ao encontrar tal caminho contínuo, descubra qual é o trecho de menor limite "Gargalo" em todo trajeto traçado.
4. Adicione e incremente esse valor para o Fluxo Total Max. Subtraia a capacidade utilizada do vetor normal, reverta ele subindo a cota oposta (retroativa do residual). Volte ao Passo 2.

**Entrada:** `N` Vertices, `S`, `T` alvo matriz de peso.

**Saída:** Total Fluído Numérico que se esgotou no Gargalo principal.

### 58. Número Máximo de Caminhos Disjuntos por Arestas entre Dois Vértices

**Descrição:** Calcule quantos caminhos completos e originais um nó faz de A para B sem sequer repetir nenhuma daquela Aresta/rua original previamente usada.

**Passo a Passo:**

1. Aplique exatamente o Algoritmo de Capacidade Ford-Fulkerson citado anterior.
2. Apenas altere o Grafo de entrada: Toda rua existente no mapa obrigatoriamente passará a conter e valer apenas com a Força de "Fluxo 1" Unitário constante nela toda.
3. Rodar a vazão por MaxFlow com gargalos Unitários limitará automaticamente cada caminho a não se sobrepôr. Retorne e confira o Fluxo Máximo Final (vai equivaler com os totais rotas sem colisão).

**Entrada:** Nós normais.

**Saída:** Result de Valor Fluído Total Unitário.

### 59. Emparelhamento Bipartido Máximo

**Descrição:** Num cenário Bipartido com Grupos A (Ex: Candidatos) e B (Ex: Empregos Vagos), maximize o total de pessoas conectadas aos empregos de sua preferência com limite 1 para 1 alocação.

**Passo a Passo:**

1. Implemente a variante Ford-Fulkerson também, ou DFS combinatório Hopcroft-Karp.
2. Insira um Nó Genérico S Falso para origem enviando para Candidatos. Envie de B (empregos) as arestas do pacote todas para um Destino T final Falso. Tudo Peso 1.
3. Se um Candidato curte Emprego A, ligue aresta Peso 1. O Total Flow computado de S até T revelará a conexão máxima ideal de casais que não sobram.

**Entrada:** Conexões entre grupos em matriz boolean / Listas A e B.

**Saída:** Máximo emparelhamento gerado com sucesso.

### 60. Problema de Atribuição de Canal

**Descrição:** Dadas estações transceptoras (TV/Telefones), você tem limitações de frequências/canais e restrição de ruídos, tendo que ser um Emparelhamento também Bipartido complexo ou de compatibilidade mútua de cores de grafo.

**Passo a Passo:**

1. Utilize de Matrizes Bipartite Flow em que A são emissores em área de interferências, e B os canais alvos.
2. Pode ser tratado via validador `Max-Flow` para distribuir e checar se `Flow === MaxDemand` totaliza na atribuição alocada completa.

**Entrada:** Exigências.

**Saída:** Verdade ou atribuição de frequências alocadas no pacote result.

### 61. Algoritmo de Karger para Corte Mínimo

**Descrição:** Separe seu grafo principal unido globalmente, exatamente em duas secções disjuntas removendo ou rompendo ao acaso o MENOR e mínimo das quantidades de arestas no percurso.

**Passo a Passo:**

1. Em vez de Determinístico, é algoritmo Aleatório (Randomized). Represente em Vetor com Componentes originais.
2. Sorteie e sorteie aleatoriamente repetidas vezes conectores de arestas no Array e proceda os esmagando: fundir dois nós afeitos ligados nela (contraí-los em supernó).
3. Limpe auto-ciclos locais formados do agrupamento esmagado interno.
4. Exatamente quando restarem apenas dois Super-Vertices Grandes remanescentes isolados globais, o total número da aresta sobrando no meio definirá e comporá probabilístico valor do corte. Repetir várias e várias rodadas de sementes para achar as chances garantidas min.

**Entrada:** Mapa global.

**Saída:** Contador das arestas do split aleatório que partiu no Menor Corte.

### 62. Algoritmo de Dinic para Fluxo Máximo

**Descrição:** Alternativa aprimorada, muito veloz em fluxo rede e O(V²E) que escala por construção de árvore limitando a navegação (Graphs de Nível).

**Passo a Passo:**

1. Implemente rotina de BFS para rodar e preencher uma camada de distâncias que é o "Level Graph": se você tá pra frente no Nível 2 o próximo aceitável só serve se for 3, impedindo zigue-zagues ou fluxos retornantes infinitos.
2. Usando o Level Graph atual, rode profundidade de busca DFS recursiva (SendFlow) despejando massiva e maior água com as distâncias.
3. Quando essa etapa estancar e saturar as torneiras e conexões e travar na falha, Refaça e Atualize a matriz nivelada de BFS denovo do 0 reiniciando camada.
4. Quando falhar gerar rede por zero destino `T`, devolva MaxFlow em acúmulo.

**Entrada:** Vertices (S e T). Residuos limites em Rede.

**Saída:** Número Max.

### 63. Encontrar Comprimento da Maior Região em Matriz Booleana

**Descrição:** Busque contar a massa com mais quadrados 1's fundidos de blocos numa área 2D em 8-Diagonais como expansão de zona.

**Passo a Passo:**

1. Construa Loop em `N x M` iterando e avaliando matriz visitada.
2. Para toda vez que encontrar Região '1' inexplorada, libere seu contador Global `Area Atual = 1` passando nas suas DFS / BFS Recursivas.
3. Toda adjacência legal 8-direções de uns vai iterar Recursiva chamando `Atual += Busca(Vizinho, x, y)`.
4. Maximize a variável de Resultado Maior final a cada ilha checada isoladamente.

**Entrada:** Tabuleiro ou campo M x N.

**Saída:** Valor em Inteiro com o Recorde Espacial medido em Area fundida.

### 64. Problema do Grafo de Peterson

**Descrição:** Com o famoso grafo regular Petersen pré-definido contendo nós Externos Pentágono atrelados com Estrelas centrais pentagonais invertidas em posições indexadas, percorra string de Caminhos Alfabeto nele contido.

**Passo a Passo:**

1. Ele não é processado, sendo estrutural Estático com lista de adjacência padronizada predeterminada pelo Teorema (Graus são constantes `1..3`). O nó de base das palavras sempre começa com `[CaminhoA = A, E..]` mapeados.
2. Acompanhar cada char atual no grafo indexado da String (por matriz Petersen local do vetor Array de caracteres/Índices). Se achar ligação do próximo, caminhe. Caso chegue no fundo de rua, retorne falso trajeto.

**Entrada:** Texto como `ABB...`.

**Saída:** Rota de nós passados (ex: `1 6 8...`) que permitiram andar nele.

### 65. Clonar um Grafo Não Direcionado

**Descrição:** Exata repetição (Exercício 20), reproduzindo matriz e dicionários associativos do clone integral usando profundidade DFS Map.

**Passo a Passo:** Ver item 20. Crie mapeamento base referencial do Clone Novo vs Velho apontados.

**Entrada:** Cabeçalho Origem do Node do mapa.

**Saída:** Seu profundo Clone total do Node e suas correntes.

### 66. Coloração de Grafos

**Descrição:** Distribua atribuições coloridas nos Vértices usando quantidade X sem que nenhum adjacente que se toque/esteja unido compartilhe a mesmíssima pigmentação.

**Passo a Passo:**

1. Backtracking Combinatório, de 0 ao V.
2. Tente definir Cor P do escopo (Cores 1 a M Mínimas) ao vértice Recursivo V atual. Se o vértice Puder e validar Segurança Segura adjacente (vizinho não contendo sua Cor) continue para a frente na lista no `Colorir(Vertice + 1)`.
3. Se falhar retorne recuando Recursão Despintando Cor. Se for ganho o V bater Final, Imprime tudo Sucesso com os tons.

**Entrada:** Grau e Max Cores em limite M permitido.

**Saída:** A Lista Pintada `[1:Vermelho, 2:Verde..]`.

### 67. Modelo Erdos-Renyi para Gerar Grafos Aleatórios

**Descrição:** Um experimento estatístico computacional criando e populando Redes ao acaso via probabilidade e proporções fixas de preenchimento P no campo.

**Passo a Passo:**

1. Com Número Nodes V constantes, itere de i a N de linha/colunas sobre N² e gere pseudo-numérico Random Aleatório.
2. Se número for menor na Proporção percentual P escolhida pelo Dev `P = 0.05`... Ative com Booleano "Existe Aresta aqui". Se maior, zero ou falso.
3. Produz um ambiente com asfalto gerado dinâmico, imprimindo Lista com as posições ativadas final.

**Entrada:** Nós, Semente Probabilística Float P.

**Saída:** Grafos pseudo-aleatórios e conectados para testes diversos de Stress de algoritmos.

### 68. Problema do Carteiro Chinês (Inspeção de Rotas)

**Descrição:** Busca transitar com menor e absoluto custo o grafo todo, mas passando em absolutamente TODAS estradas ao menos mínimo de uma única vez sem escapar.

**Passo a Passo:**

1. Analise Validade Inicial com o grau Eulerian do Euler.
2. Caso Par em todos, ele é Euler e o Caminho Circuito mínimo é já apenas a Soma Total Simples dos pesos de rotas globais. Não requer repetir rua.
3. Caso Ímpar de nós gerados for > 0, descubra com Floyd/Warshall ou Dijkstra o menor caminho atalho curtos ligando todos esse nós impares em grupos aos pares duplicando rotas lá dentro, resolvendo com Emparelhamentos Mínimos com os pesos e os integrando no Caminho Chinês.

**Entrada:** Grafos rotacionais e valores.

**Saída:** Float Integer ou percurso total do Carteiro Chinês otimizado numéricamente.

### 69. Algoritmo de Hierholzer para Grafo Direcionado

**Descrição:** Modo ultra rápido alternativo em vez da recursão pura Fleury, resolvendo circuitos Europeus O(E).

**Passo a Passo:**

1. Comece de nó aleatório no Circuito empilhando e caminhando sobre nós nas conexões válidas `[nós]`.
2. Retire e destrua na ida a lista ligada/aresta consumida na viajatória contínua.
3. Se ficar sem fuga (beco morto travado sem vizinhos vivos remanescente), comece a Extrair para Circuito Retorno o topo da Pilha no resultado `[Res_Array_Final]` e desça atrás (Backtrackando na Stack) de outro ramal perdido no topo da lista dele esquecido, abrindo ramais ignorados para dentro, completando linear e unificado o traçado final.

**Entrada:** Fluxograma / DAG direcional compatível.

**Saída:** Lista impressa revertida Array hierholzer finalizada do Circuito Caminho O(Arestas).

### 70. Verificar se um Grafo é Bipartido

**Descrição:** Revisão similar exata ao #15 (Verificar se é Bipartido de Cores). Utiliza dois matizes isolados invertidos (Conjunto U e V que não se tocam os irmãos locais no DFS de Pintura).

**Passo a Passo:** Ver Item #15. Fila BFS com Cor Alternante na vizinhança.

**Entrada:** Lista adj.

**Saída:** True se é de dois conjuntos válidos.

### 71. Problema de Cobras e Escadas

**Descrição:** Reprodução intencional idêntica e constante do Item Categoria #17.

**Passo a Passo:** Ver item #17. Implementação O(N) com Arrays. Menor número lances de Dados por BFS e Escadas Pulo.

**Entrada:** Vetores ou dict posições de Jogo de Tabuleiro 100.

**Saída:** Min jogadas.

### 72. Boggle (Encontrar Todas as Palavras em um Quadro)

**Descrição:** Encontre em Tabela Quadrada de 2D (Caracteres e letras soltas de Scrabble mistos em grades) todo Dicionário válido possível do array contendo "GATO, RATO, FACA".

**Passo a Passo:**

1. Insira dicionário ou crie estrutura Trie(Prefixos) ou HashTable (Set).
2. Com Visited DFS, Itere recursivamente todas direções (8 vizinhos vert/horizont/diagon).
3. Construa com Concatenadores de String cada char passado por cima. No topo DFS valide, ex `if(Dicionario.TemPrefix(String)) -> continue aprofundar busca`. Se achou `(String Completa Existe)` adicione Set Array Output Global de recorde das combinações.
4. Volte da célula limpa na Trilha para Backtracking puro.

**Entrada:** Vetor de Char M/N, Matriz de palavras String Busca.

**Saída:** Set Arrays encontradas de letras juntas.

### 73. Algoritmo de Hopcroft-Karp para Emparelhamento Máximo

**Descrição:** Soluciona MaxMatching em Set Bipartidos porém unificando Vantagens de DFS+BFS e correndo veloz do que Ford-Fulkerson padronizado O(E sqrt(V)).

**Passo a Passo:**

1. Possui o vetor Match[u] contendo a alma-gêmea encontrada dele e Distâncias Níveis via BFS separando para não criar Loops infinitos e curtas.
2. Fase BFS 1: Atualize Caminho Vago Aumento. Defina como O(Zero) a distância das unidades Solteiras vagabundas de raiz sem conexões em Grupos e desça o vizinhos alvos.
3. Fase DFS 2: Sobre a Trilha Exata das distâncias construídas BFS, tente realizar troca de casais alterando parceiras em emparelhamento solteiros livres vagos DFS puro `Match[v] = u`.
4. Incremente Count total enquanto o ciclo der true, e retorne contador final no falhar do Fluxo do Emparelhador Mágico.

**Entrada:** Set Emparelhados não preenchidos.

**Saída:** Número de match feito.

### 74. Tempo Mínimo para Apodrecer Todas as Laranjas

**Descrição:** Variação Idêntica a Tomates Podres (#12). Modificação e repetição de Tópicos exigidos.

**Passo a Passo:** Ver Item #12 Tomate Podre.

**Entrada:** Quadro grade Int 0..1..2 Laranjas.

**Saída:** Int (-1 ou minutos Exato do Relógio apodrecidos).

### 75. Construir um Grafo a partir dos Graus dos Vértices

**Descrição:** Teorema de Havel-Hakimi para confirmar, dada uma lista aleatória numérica de contagem como `[3, 3, 3, 3]`, ela permite desenhar um Grafo legítimo conexo?

**Passo a Passo:**

1. Ordene A lista descendente / Maior no Topo `[V_max.. a 0]`. Se tiver Valor de número Negativo dentro: Retorne Falha de criação Ilegal Falso. Se tiver só 0 zeros, retorna Possível Criar Positivo True.
2. Retire temporário e exclua/Puxe o Primeiro Inteiro D do topo inicial (Seria um vértice isolado recém criado).
3. A partir do índice abaixo de onde ele puxou, subtraia estritamente Exato de -1 do topo até o D posições à frente na lista dos arrays descendentes contiguos sequenciais em loop for para abater o que ele usou na conexão e repita Recursivamente até consumir ou Estourar Negativo (Negativo = Arestas Quebradas e Inválidas ou Nó insuficient para ligar).

**Entrada:** Array de graus de Vertices inteiros.

**Saída:** Boolean confirmando HavelHakimi construtor de grafo.

### 76. Determinar se Existe um Sumidouro Universal em Grafo Direcionado

**Descrição:** O Universal "Sink" é o Alvo final. Para que exista e seja a Celebridade, deve haver no Grafo de N vértices (Entradas = V-1) vindos do resto para ele. E saídas = ZERO Dele pro Resto do Mundo vazio na Matriz.

**Passo a Passo:**

1. Use Abordagem Matriz Adj em O(V). Index `i = 0`, `j = 0`.
2. Num `while (i < V e j < V)`: se Célula `Matriz[i][j]` é 1 ligado: Então O 'i' não pode ser Sink porque joga aresta para frente fora dele (I= i+1).
3. Se 0 e falso, O 'j' não recebe nada (j = j+1 pule coluna descartando candidata celebridade universal vazia j).
4. No último Índice sobrevivo 'i' resultante ou 'j': faça cheque manual por loop dele. Ele tem saída 0 absoluta total das colunas daquele Index, e recebimento Absoluta Inteira de In== V-1 nas colunas para si?

**Entrada:** Matrizes Direcionadas de Grafos.

**Saída:** Valida quem é Celebridade Sumidouro.

### 77. Número de Nós Sumidouros em um Grafo

**Descrição:** Quantifique exatamente a Existência Total isolada de componentes finais Terminais do Mapa.

**Passo a Passo:**

1. Faça For Loop na Estrutura do Grafo List.
2. Identifique qual array da Lista possui Tamanho (Tamanho_Size() == Zero Adjacência Absoluta Vazia Sem Elemento Nenhum listado nela da matriz).
3. Todo Size() Nulo conta um Incremento para seu número Counter Result Sink Nodes finais (Eles recebem ligações as vezes, mas não criam ligações apontando externo das saídas de lá).

**Entrada:** A matriz do Mapa global.

**Saída:** Contadores Inteiros Sumidouro Count = X.

### 78. Problema de Dois Cliques (Verificar Divisão do Grafo)

**Descrição:** Determinar no processador de Matriz Adjacente, se o mapa inteiro suporta exata divisão perfeita de apenas ser partido em Dois Extremos Grupos isolados 100% internos perfeitos em seu quadrado completo fechado (Dois Sub-Cliques fechados em si totais sem resto no meio).

**Passo a Passo:**

1. Obtenha e Mapeie o Grafo "Complemento Inverso de Si": Aonde Tinha linha na matriz apague. E onde ERA 0 Sem-Conexão e invisível e isolado, crie rua nova entre nós no Complemento Oposto.
2. Se o complementar Invertido resultante Desse Grafo original provar ser Totalmente Válido e "Ser um Grafo BIPARTIDO #15 Colorido Perfeito em duas metades Sem Conflitos".
3. Significa e atesta obrigatoriamente que Original suporta Perfeitas Exatas divisões Dois Clique Completos de matriz no Bipartite theorem.

**Entrada:** Matriz booleana normal G.

**Saída:** Result de Falso Verdade de dois Cliques fechados suportado pelo Bipartido invertido.

</details>

<details>
<summary>🔴 Nível 3 - Difícil</summary>

### 79. Fluxo de Água Pacífico-Atlântico

**Descrição:** Você está no meio da América, numa grade com Relevos/Altitudes variadas de Montanhas Terrestres na matriz 2D. Topo/Esquerda é Oceano Pacífico. Direita/Base do Grid é Oceano Atlântico. Você quer saber quais blocos/Células exatos de montanha deixam a Água e a chuva escorrer e pingar até bater no Nível menor que ela em caminho descendente válido para escoar tanto no Pacífico e no Atlântico (Em ambas direções escorrendo abaixo).

**Passo a Passo:**

1. Crie 2 Matrizes Visitadas independentes com mesmo Grid `(VisitouPacifico[][])`, `(VisitouAtlantico[][])` para espalhar de fora para centro Inverso.
2. Para O Pacifíco e Atlântico, Adicione em uma Fila as BORDAS e LIMITE externos literais da Tela Grid matriz e marque ali em sua Cópia. Inicie a DFS Subindo Montanha Reversa ao Inverso do Padrão.
3. Se Vizinho é Valido com "Sua Altitude Maior ou Igual" Recursivo na Inversão.. Ele Escorre ali então Marque-o em True no grid.
4. Faça Loop em toda matriz iterando as Células (i,j) verificando. Toda Célula que Possui GridPacifico `&&` GridAtlantico Marcados cruzados em Verdade Verdade nas Matrizes na sua Interseção local ali: Junte à lista Final Output.

**Entrada:** Quadrados de relevo e tamanhos Heights Matrix Inteiros 2D.

**Saída:** Vetor contendo a Tupla (Y, X) coordenadas centrais viáveis de desaguamento Bi-oceânico duplo.

### 80. Número Total de Árvores Geradoras em um Grafo

**Descrição:** Extraia com Teorema do MatrixTree Theorem de Kirchhoff (Álgebra Linear Pura) contando numericamente e combinatoriamente Sem desenhá-las graficamente ou extrai-las.

**Passo a Passo:**

1. Crie a Matriz Laplaceana (Matriz de Grau Global Absoluta (Aonde Vertices i=i diagonal principal têm Seu Grau) e Fora Subtraída com Valor Negativo -1 Menos Um nas ruas/Arestas Reais).
2. Deleta sumariamente uma Linha inteira Qualquer `X` e Mesma Coluna Qualquer `Y` excluindo-a sumariamente para sempre da Matriz quadrada. Ela é Agora um Cofator da laplaceana isolado e menor.
3. Simplesmente Calcule e extraia o Valor Determinante Absoluto matemático Puro em Array Flutuante Gaussiano ou Recursão do Array Cofator laplace.
4. O Inteiro absoluto Do Fator Determinante Extraído desse Laplace Co-Fatorizado é o Equivalente direto das arvores geradoras Mágicas possiveis escondidas.

**Entrada:** Grafos Adj matriz conectados puros.

**Saída:** Total Integer exato combinatório numérico determinantes Kirchhoff.

### 81. Caminho Mais Longo em um Grafo Direcionado Acíclico

**Descrição:** Este exercício se repete intencionalmente da categoria Mediana Categoria (#45). O Grafo Acíclico longo requer relaxamento topológico.

**Passo a Passo:** Ver #45. Baseia-se em Topological Sort com pesos negativos inversos acumulando os distanciamentos relaxando com máximo e não pelo mínimo das Dijkstra para long paths de critical timing.

**Entrada:** Nós, arestas direcionadas limitantes acíclicos.

**Saída:** Array caminhos otimizado e esticados em máximo absoluto de tempo processamento crítico total.

### 82. Pontes em um Grafo

**Descrição:** Encontre em um mundo com Ruas o Ponto e as Estradas Estratégicas "Gargalos/Pontes" que, Se Aquele Local em específico na aresta desabar/for destruído ou excluído em Teste, o País é rasgado ao Meio ou em dois Países Disjuntos no mapa.

**Passo a Passo:**

1. Algoritmo Tarjan em base com vetores em DFS de tempo Global `In[]` / Discovery e `LowLink[]` mais baixo alcançável. Tempos inicializados na Raiz e Incrementando num Time_Relogio global único.
2. Execute recursão profunda DFS acompanhando o nó Raiz. `low[Atual] = in[Atual] = Relogio`. Guarde Seu vizinho Parent/Pai passado.
3. Vasculhe Vizinhos dele no adjacente. Se O `vizinho == Parent` ignore pulando e prosseguindo iteração.
4. Se o vizinho já Foi alcançável visto (Tem Time discovery atrelado e Back-Edge para trás), Ajuste Seu Limitador local: `low[atual] = min(low[atual], in[vizinho])` retornando pro pai.
5. Recursão DFS Fundo: E se pós finalizado o processo, o Seu Tempo `low[VizinhoAlvo DFS]` for estritamente MAIOR `>` que o seu Tempo de Entrada Pessoal absoluto `In[Atual Discovery]`? Isso é Ponte. Não Tem caminho secreto menor paralelo do Vizinho para Voltar à Raiz da cidade exceto você. Armazene Array `Ponte`. E propague mínimo para cima pro Pai.

**Entrada:** Un-directed normal Grafos e Arrays.

**Saída:** O Grupo Vetorizado e pares impressos das Arestas-Vulneráveis (Pontes).

### 83. Pontos de Articulação em um Grafo

**Descrição:** Cidades Críticas - Se o Ponto e Cidade cair e desaparecer, tudo em volta Fica Desconectado/Particionado (Semelhante às Pontes, mas exclui o Nó Vértice em vez da aresta na medição de componentes disjuntos).

**Passo a Passo:**

1. Use as métricas do Tarjan com relógios DFS Time Low e IN idênticos Discovery de Base Pontes (Idêntica abordagem recursiva discovery `Low e IN`).
2. Adicione Exclusiva Variável `int Childrens = 0;` (Contando e checando quantas árvores florestas em DFS você desceu filhas desatreladas).
3. Na Finalização Recursive, Condição A: O Nó é a Exata RAIZ inicial Mestre que deu Início em Start à Função inteira original e ela mesma possuí Multiplos Filhos Absolutos DFS gerados Desconectados Filhos no Childrens `> 1` no Loop. Ele É ARTICULAÇÃO garantida Ponto.
4. Condição B: O Nó Não é Mestre Raiz base. Mero intermediário. Mas O Filhote Adjacente debaixo Recursivo não obteve um Time Link `low[Filhote Vizinho]` de fuga retroativo e Seguro Menor que o Seu `IN[Discovery_Pai_Atual]` Próprio local no percurso. (`low[vizinho] >= in[atual]`). Se ele depende da linha superior restrita sem atalho backedge retroativo que pule, O Atual Vértice Ponto Pai é OBRIGATÓRIA Cidade-Articulação na estrutura.

**Entrada:** Nodes sem Direções E arestas.

**Saída:** Vetores de Pontos Chave.

### 84. Componentes Biconexos

**Descrição:** Subgráficos Máximos Gigantes Conectados do País sem NENHUMA Cidade Ponto Crítico Articulação interno deles.

**Passo a Passo:**

1. Acompanhe a Lógica dos Pontos Articulação no Loop Tarjan.
2. Adicional: Crie Matriz e Pilha/Stack e Comece a Jogar as arestas visitadas Purgadas (A, B) por cima desse Topo dela Empurrando Push() Arestas que você pisar no percurso.
3. Se no Processo DFS o Loop esbarrar, Descobrir e Acionar O Alerta Gatilho Booleano Local "Essa Área é Limite Articulação Pai com Filho (`low[v] >= in[u]` e não Raiz)". Imediatamente Dispare Bloqueio! Tudo que Está Acumulado e Empilhado Dentro lá Pilha lá Em Cima, Puxe POP() extraindo fora todos itens da Fila enquanto aquele Desempilhado for Aresta igual a Sua Trilha Corrente `(u,v)`. Empacote Esse Sublote Extraído em Componente Array e Imprima no Log em Pacote isolado sem pontes atreladas, como Biconexo SubGrafo.

**Entrada:** N/E Vértices.

**Saída:** Uma Série Múltipla Lista-Pacotes Biconexas das suas Arestas isoladas e fortificadas.

### 85. Verificar se Vetor de Strings Forma um Círculo

**Descrição:** Lista de Strings como Nomes em Dominó `["geek", "king", "algo"]`. A Última letra de 1 se liga à 1ª Letra da outra em Anel Contínuo Final Perfeito encadeado? (Reutilização Lógica: Euleriano Direcionado adaptado à Alfabetos Char Letras base).

**Passo a Passo:**

1. Use as 26 Letras Inglesas de Alfabeto Inteiras como Nossos Grafos Vértices Raízes do Mapa de Char. Matriz `26` Arrays list do abecedário em Grau in e Graus Outs.
2. Itere sobre "geek": Trate Primeira char `'g' = 1 Vertice O(Letra)` e a Última `'k' = 1 Aresta Fim Letra Destino`. Insira em `LetrasAdj['g' - 'a'].push_back('k'-'a')`. E Out Degree / In Degrees de g e k atualizados para mais++.
3. Faça a verificação Se o Grafo é Euleriano Loop: Confira se Para Toda Letra e Cidades Alfabetos Neles Os IN Degree São Estritamente Idênticos Exatos aos OUT degree Dela (Validação do Euler em Direções O(In = Out)).
4. Confirmação B: Tudo tá Em Grupo Kosaraju DFS Integrado em Único Pedaço? Se todos Conectam-se ou se formaram Anéis Soltos Separados 1 a Parte do outro lado. Se Positivo em ambas aprovações Euler, Retorne Validado Verdade.

**Entrada:** Vetores Vet de Palavras Cadeia Strings.

**Saída:** Output verdadeiro/falso círculo.

### 86. Algoritmo de Tarjan para Componentes Fortemente Conexos

**Descrição:** Crie em um Grafo Direcional o Mapa em Áreas Onde todos Nós da área alcançam Todo Mundo dessa mesma sub-área, usando O(V+E) rápido apenas e usando Apenas Pilha Recursiva única (Superior e Otimizado e sem fazer e requerer 2 loops passagens de Kosaraju Reversed Transpose e sim Tarjan Relógio).

**Passo a Passo:**

1. Pilha Global Ativa Empilhatória `Na_Stack_Pilha_Verificador[]` Bool e Variáveis LowLinks Iniciais Mínimas igual a Pontes.
2. Entre em nó `v`, Push Empilhe nela Pilha, assinale os tempos correntes a ele local, Visite a árvore Direcional DFS dos seus destinos no percurso. Atualize Seu Minimum `Low` caso encoste e acesse alguém da Pilha acima que não seja finalizado isolado. (Backedge de cruzamento de ciclos).
3. Após encerrar chamadas Recursivas em Seus Filhos Todos lá em baixo e Retornar pra Ti no Loop em Acima, Teste. O Seu Time Absoluto inicial IN (Id) ainda se manteve Estritamente intocável e Idêntico Exato ao Seu Limite Menor (Low Link ID) Alcançável do Vizinho? `IN == LOW`. Se SIM. Você é oficialmente a Cabeça Final/Raiz e Topo do Aglomerado Fortemente Conexo Acumulado nas Chamadas. Desempilhe em repetição e extraia para Lista do Retorno todos os membros da Pilha do Stack até que Você Topo Raiz seja Extraído dela para Fora fechando pacote e formando Fortemente Componentes Unificados no Array.

**Entrada:** Graph Map Directed.

**Saída:** Pacotes/Vetores com Componentes Unificados Fortemente impressos conjuntos isolados.

### 87. Encontrar Corte Mínimo s-t em Rede de Fluxo

**Descrição:** Descobrir as Arestas Chaves com os Pesos Extremos Restantes do FordFulkerson. Se essas ruas Mágicas cortadas sumirem e Excluídas por estiletes de Grafos, O Cano S para T estanca total a vazão e Isolam Origem do Destino final.

**Passo a Passo:**

1. A base Inteira usa a Malha já preenchida Completa e Pronta de Fluído Capacidade Totalmente Calculada Rodada do Ford Fulkerson Finalizado em seu teto Máximo Residual Limitado e não entrando mais (Grafo G e Grafo Residuado GR).
2. Sem Água a empurrar. Inicie um Mini DFS ou BFS Normal na Origem `S` puramente sobre a malha de Residuo Limitante. Todas que possuírem espaço remanescente lá em Sobras (Força Fluido > 0) Pinte Visitados[V] com Verde Verdade, Você chega Nelas via S na Área Residual sem estancar limite ainda.
3. Analise As Bordas em Limite Cruzado original Pós-Caminhada: Repasse pelo Laço Iterativo todas N arestas originais do Mapa Intacto. Todo Conector em Rua Original e Aresta Inicial que liga Da Célula Que Você e o Relatório Alcançou Visitada Com Acesso verde e Seguro Da Parte Do `S` Ativadas, para um Alvo/vizinho `V` Destino Obscuro Cego Que Você Estancou e Literalmente Não Logrou Chegar do lado T Secado Cego e Falho Inacessado Pela Residual final em Falso Vermelho ali... Essas Arestas Na Quebra De Vínculo Cruzado Verde/Vermelho é o Seu Gargalo Do Corte Mínimo (Min Cut Mágico em Residuos).

**Entrada:** Flow Matriz Capacitados e Graph G Inicial Base N/N limitantes e Residuais da FordFolk.

**Saída:** O Valor Resultante Imprimindo as arestas Cortadas e as Duas seções criadas A vs B cortadas por S/T.

### 88. Implementação do Problema do Caixeiro Viajante

**Descrição:** O Imbatível NP-Difícil (TSP). Qual o traçado Minúsculo de Distância a passar por Todas e Únicas cidades exatamente 1 e Somente 1 vez, Retornando Por último E Ponto para A Raiz e Capital original e Fim da Rota Fechada Total Custo Barato Máximo Minimizando Perda?

**Passo a Passo:**

1. Implemente com Programação Dinâmica DP usando Máscaras Bitwise Bitmask 1/0 para representar estados visitados para eficiência de Cidades 20. Matriz `DP[Mascara_Conjunto][UltimaCidadeVisitada]`.
2. Para O Mask 000.. e Base Cidade Início 0: Encontre para Tudo, Qual Nova Cidade Não Foi Visada Adicionada Na Mascara Bitwise e Atualiza `Custo + CustoDaAresta`. Compare `Min(DistAtualMínimaCaminhada, Rota[Ultima][vizinho_novo_i] + TSP(Mask | 1<<i, vizinho_novo_i ))` do Percurso recursivo Memorizando Tudo nos nós DP Bitwise Cacheados do Grafo Memo.
3. Se o Mask Setado E Atingir Todo o Preenchimento Em Binário Ex 11111 de todas cidades rodadas marcadas (Mask == `(1<<n) -1` Todos), devolve Base Finalizando com A Rua Distanciada `23. Dist_Rua[cidadeAtual][Para A Capital Início 0]`.

**Entrada:** Quadrante com Distâncias. Matriz Bidimensional simétrica em Pesos Cidades.

**Saída:** Valor Minimo Flutuante Absoluto Custo e Rota Ótima Fechada TSP percorrida com BitMask TSP Resultant.

### 89. Problema da Cobertura de Vértices

**Descrição:** Coletar O Menor Set, Grupo Reduzido Fixo de Vértices Guardas Policias em cidades Em Um Vetor Cidades Base, onde se Eles Focarem e Policiarem Ali Canto na Cidade Guarda... Toda E Literalmente Qualquer Rua Adjacente (Aresta Global A) Do Mapa Inteiro Fique Sob Observação Policiada Segura no Radar Tocado Adjacente aos nós Policiais na Vertex Covering Problem NP.

**Passo a Passo:**

1. Aproxime a Solução Greed (Guloso Approximate em Polinomial em vez de Ótimo Perfeito Lento NP) usando array Bool e Loops.
2. Preencha Array Set Visto em Falso em todo Grafo sem Proteção/Guardas na base de cobertura Inicial Vazio. Crie Um Loop percorrendo as Arestas e ruas.
3. Pegue O Vizinho A (Origem rua) E O Destino B. Se O `u` Não tiver Guardas em volta visitado Ou Sem proteção E o Alvo `v` Também não Contiver Protegidos/Visitados Ainda (Ambos Vazios Cegos). Pegue Essa Rua Vulnerável e Coloque Em Ambos Guardas Protegendo Imediatamente `(Visto_U = Visto_V = True Protegidos em Vertex Cobertura)`. Adicione Ambas Na Lista De Policiados Finalizados Vertex Coverage Set Global.
4. Repasse todo o Loop em todas Arestas Remanescentes Adjacentes Vendo. A Resposta Será o Set List impresso. É Um Fator Multiplicado no Máximo 2x do Tamanho ótimo Matemático NP para resolver rápido na Área Prática sem travar as redes.

**Entrada:** N Verts e Array E. Lista de Adjacentes Global Grafo N-dimensional.

**Saída:** Arrays Vertex Set Impresso com O Grupo Chave Base Selecionados que Cobrem Toca Adjacente e Rádios Coberturas Mínimo Approx Gulosas no Local Coberto.

### 90. Problema dos K Centros

**Descrição:** Dado Conjunto com Diversas Cidades Num Mapa e 1 Limite Estrito Absoluto Estourado de Valor `K` Hospitais Exatos de Centro Tratamento Permitidos, Aonde Exatamente Espalhar/Posicionar A Localização desses Centros Na Matriz para fazer Com Que a MÁXIMA Pior Distância Dirigida Entre Algum Cidadão Morador Paciente Azarado até Chegar nesse Seu Novo Hospital K em Construção Ali Canto Seja A Menor do Universo Matemático Atingível Minimizando Sua Demora Exata Greed K Center Clustering NP-Time. Minimizando o Longest-Pior Ponto Distante Geográfico?

**Passo a Passo:**

1. Implementação Greed Aprox: Selecionar e Posicionar o Primeiro Centro Hosp. Aleatoriamente em Cidade de Início Vertex `0` Ou Qualquer na Lista Final dos Centers. (Loop para Preencher o Limitador até Fechar o Teto de N Hospitais K Permitidos Finais Acumulando Posições).
2. Tendo Instalado Algum, Inicie As Verificações Pior-Caso Num Loop Calculando o Distanciamento Euclidiano/Ou Array peso de TODOS Restantes Moradores Livres em Matriz até Seu Hospital Atualmente Instalado Global no Centro Mais Próximo Dele Atual e Atualize Dist Minima Pra Tudo no Recorde deles lá fora `Min_Dist_Hospitais[x]`.
3. Busque Entre Toda Multidão Exatamente QUAL Ponto Do Morador Restante Apresentou a Pior E Absurdamente Mais Extensa Maior Distância (Maior Valor no Mínimo Dos Registros), O Morador Mais Exilado E Longe Desamparado Geográfico Descoberto Daquele Momento na Rota Deixada. Coloque Exatamente Ali E Atribua Nele Posição Ali Sua Nova Construção K Hospital, Centro. Reinicie O Teto Com Loop Adicionando Novo Distancial até Instalar Tudo e Poupando Demoras Médias Pior Caso Reduzidas Exponencial. E Aja na Estrutura K Centros Approximate List Center Results devolvendo As Sedes Geográficas Cidades.

**Entrada:** Valor Array Matriz, Constante Teto Limit K de Pontos Sede de Center de Clusters.

**Saída:** Listas Impressas das Sedes e Hospitais Otimizados Geográficos com Distanciamentos O(K\*V) Exatos Finais Minimizadas Reduzidas no Pior-Morador.

</details>

