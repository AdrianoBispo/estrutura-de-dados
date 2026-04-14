# Lista de Exercícios - Estruturas de Dados Fila (Queue)

Este documento contém uma lista de exercícios práticos com o objetivo de fortalecer a lógica de programação através do uso da estrutura de dados Fila (Queue). Os problemas estão organizados por nível de dificuldade e podem ser implementados em qualquer linguagem de programação (C, C++, Java, Python, C#, etc.).

<details>
<summary>🟢 Nível 1 - Fácil</summary>

### 1. Pilha usando Filas (Stack using Queues)

**Descrição:** Implementar as operações básicas de uma Pilha (LIFO) utilizando apenas operações de Fila (FIFO).

**Algoritmo:**
1. Crie duas filas: `Fila1` e `Fila2`
2. Para adicionar um elemento (Push):
  - Insira o novo elemento em `Fila2`
  - Remova e transfira todos os elementos de `Fila1` para `Fila2`
  - Troque as referências de `Fila1` e `Fila2`
3. Para remover um elemento (Pop): Apenas remova o primeiro elemento de `Fila1` (Dequeue)

**Exemplo:**
- Input: `Push(1), Push(2), Push(3), Pop()`
- Output: `3`

### 2. Fila usando Pilhas (Queue using Stacks)

**Descrição:** Implementar o comportamento de uma Fila (FIFO) usando apenas Pilhas (LIFO).

**Algoritmo:**
1. Crie duas pilhas: `PilhaEntrada` e `PilhaSaida`
2. Para inserir (Enqueue): Faça Push do elemento em `PilhaEntrada`
3. Para remover (Dequeue):
  - Se `PilhaSaida` estiver vazia, transfira todos os elementos de `PilhaEntrada` para `PilhaSaida` (inverte a ordem)
  - Faça Pop de `PilhaSaida` e retorne o valor

**Exemplo:**
- Input: `Enqueue(10), Enqueue(20), Dequeue()`
- Output: `10`

### 3. Travessia em Nível (Level Order Traversal)

**Descrição:** Percorrer todos os nós de uma Árvore Binária nível por nível, de cima para baixo e da esquerda para direita.

**Algoritmo:**
1. Inicialize uma Fila e insira o nó raiz
2. Enquanto a fila não estiver vazia:
  - Remova o nó da frente e guarde seu valor
  - Se houver filho à esquerda, adicione à fila
  - Se houver filho à direita, adicione à fila

**Exemplo:**
- Input: Árvore `[1, 2, 3, 4, 5]` (1 é raiz; 2 e 3 são filhos de 1; 4 e 5 são filhos de 2)
- Output: `1 2 3 4 5`

### 4. Busca em Largura para um Grafo (BFS for a Graph)

**Descrição:** Percorrer um grafo começando de um vértice inicial, visitando vizinhos em largas antes de aprofundar.

**Algoritmo:**
1. Crie um array booleano `visitados` para evitar revisitas
2. Crie uma Fila e adicione o nó inicial marcando como visitado
3. Enquanto a fila não estiver vazia:
  - Remova o nó atual e imprima
  - Para cada vizinho não visitado: marque como visitado e adicione à fila

**Exemplo:**
- Input: 4 vértices; Arestas: (0→1, 0→2, 1→2, 2→0, 2→3, 3→3); Partida: 2
- Output: `2 0 3 1`

### 5. Substituição de Página FIFO (FIFO Page Replacement)

**Descrição:** Contar falhas de página quando a memória está limitada. Remove a página mais antiga quando necessário.

**Algoritmo:**
1. Use uma Fila para ordem de chegada e um Set para busca rápida
2. Para cada página de entrada:
  - Se já está no Set, ignore
  - Se não está: incremente contador, remova a mais antiga se capacidade máxima atingida, adicione a nova
3. Retorne o total de falhas

**Exemplo:**
- Input: Capacidade = 3; Páginas = `[1, 3, 0, 3, 5, 6, 3]`
- Output: `6` (falhas de página)

</details>

<details>
<summary>🟠 Nível 2 - Médio</summary>

### 1. K Filas em um Array (K Queues in an Array)

**Descrição:** Implementar K filas diferentes usando um único array na memória.

**Algoritmo:**
1. Crie um array principal para valores e arrays auxiliares: `front[]`, `rear[]`, `next[]`
2. Mantenha variável `free_spot` indicando primeiro índice livre
3. Para Enfileirar: pegue índice livre, atualize `free_spot`, insira dado, vincule ao fim da fila
4. Para Desenfileirar: pegue índice de `front[]`, mova para próximo, libere índice

**Exemplo:**
- Input: K = 3, N = 10; Enfileirar 15 na Fila 2; Enfileirar 45 na Fila 2; Desenfileirar da Fila 2
- Output: `15`

### 2. Inverter uma Fila (Reverse a Queue)

**Descrição:** Inverter a ordem de todos os elementos de uma Fila.

**Algoritmo:**
1. Inicialize uma Pilha auxiliar
2. Remova todos os elementos da Fila e faça Push na Pilha
3. Desempilhe e reinsira na Fila (ordena inversamente)

**Exemplo:**
- Input: `[10, 20, 30, 40, 50]`
- Output: `[50, 40, 30, 20, 10]`

### 3. Primeiro Caractere Não Repetido em um Fluxo (First non-repeating Character)

**Descrição:** Em tempo real, encontrar o primeiro caractere inserido que não foi repetido.

**Algoritmo:**
1. Use mapa de frequência para contar aparições
2. Use Fila para manter ordem cronológica
3. Para cada novo caractere: incremente frequência e insira na fila
4. Limpe o início da fila removendo caracteres com frequência > 1 até encontrar frequência = 1

**Exemplo:**
- Input: `"a a b c"`
- Output: `"a -1 b b"`

### 4. Passos Mínimos do Cavalo para o Alvo (Min Knight Steps)

**Descrição:** Encontrar o número mínimo de movimentos de cavalo em xadrez até o alvo.

**Algoritmo:**
1. Use BFS em matriz não ponderada para caminho mais curto
2. Fila armazena: `(posição X, posição Y, distância)`
3. Para cada nó, calcule 8 movimentos em 'L' possíveis
4. Se dentro do tabuleiro e não visitado, insira com Distância + 1

**Exemplo:**
- Input: Tabuleiro 6×6; Posição Atual: (4,5); Alvo: (1,1)
- Output: `3` movimentos

</details>

<details>
<summary>🔴 Nível 3 - Difícil</summary>

### 1. Inverter os Primeiros K Elementos da Fila (Reverse First K)

**Descrição:** Inverter apenas os primeiros K elementos deixando o resto inalterado.

**Algoritmo:**
1. Remova os primeiros K elementos e insira em uma Pilha
2. Desempilhe e reinsira na Fila (invertidos, mas no fim)
3. Mova os elementos não invertidos do início para o fim

**Exemplo:**
- Input: K = 3; Fila = `[1, 2, 3, 4, 5]`
- Output: `[3, 2, 1, 4, 5]`

### 2. Máximo da Janela Deslizante (Sliding Window Maximum)

**Descrição:** Encontrar o elemento máximo em cada janela de tamanho K que desliza pelo array.

**Algoritmo:**
1. Use Deque (Fila Duplamente Terminada) com complexidade O(N)
2. Deque armazena índices em ordem decrescente de valores
3. Para cada elemento: remova do final índices com valores menores; remova do início índices fora da janela
4. Início do Deque contém índice do máximo da janela

**Exemplo:**
- Input: Array = `[1, 2, 3, 1, 4, 5, 2, 3, 6]`; K = 3
- Output: `[3, 3, 4, 5, 5, 5, 6]`

### 3. Caminho Mais Curto em Labirinto Binário (Shortest Path in Binary Maze)

**Descrição:** Encontrar o menor caminho entre origem e destino em matriz onde 1 = passagem e 0 = parede.

**Algoritmo:**
1. Use BFS com matriz de visitados
2. Fila armazena: `(x, y, distância)`
3. Inicie na origem com distância 0
4. Tente movimentos: cima, baixo, esquerda, direita; valide limites e valor = 1
5. Retorne distância ao encontrar destino

**Exemplo:**
- Input: Matriz com 0s e 1s; Origem: (0,0); Destino: (3,4)
- Output: `11` passos (ou `-1` se impossível)

### 4. Gerar Números Binários de 1 a n (Generate Binary Numbers)

**Descrição:** Imprimir representação binária de todos os números de 1 até n usando Fila.

**Algoritmo:**
1. Crie Fila de Strings com `"1"`
2. Execute n iterações:
  - Remova elemento (string atual)
  - Imprima-o
  - Enfileire: string + `"0"` e string + `"1"`

**Exemplo:**
- Input: N = 5
- Output: `"1"`, `"10"`, `"11"`, `"100"`, `"101"`

### 5. Caminho de Custo Máximo com K Nós Intermediários (Maximum Cost Path)

**Descrição:** Encontrar caminho de maior custo da origem ao destino passando por no máximo K nós intermediários.

**Algoritmo:**
1. BFS modificada com tuplas: `(nó, custo acumulado, profundidade)`
2. Explore cada aresta até profundidade K+1
3. Compare custos ao atingir destino e armazene o máximo
4. Não use matriz de visitados estrita (múltiplos caminhos)

**Exemplo:**
- Input: Grafo com pesos; Origem: 0; Destino: 3; K: 2
- Output: Valor inteiro do maior custo

### 6. Problema do Jogo de Cobras e Escadas (Snake and Ladder)

**Descrição:** Número mínimo de jogadas de dado (1-6) para vencer tabuleiro com cobras e escadas.

**Algoritmo:**
1. Tabuleiro é grafo direcionado; cada espaço é vértice
2. BFS a partir da posição 1
3. Fila armazena: `(posição, quantidade de lançamentos)`
4. Se destino é base de escada, vá para o topo; se é boca de cobra, vá para cauda

**Exemplo:**
- Input: Array/Map com posições de cobras e escadas num tabuleiro
- Output: Número mínimo de jogadas

### 7. Caminho Seguro Mais Curto com Minas (Shortest Safe Route)

**Descrição:** Menor caminho da primeira coluna até última coluna. Minas (0) contaminam células adjacentes.

**Algoritmo:**
1. Pré-processe: marque minas e adjacentes como inseguras (-1)
2. BFS Multi-Source: injete todas as células seguras da primeira coluna com distância 0
3. Retorne distância ao atingir última coluna

**Exemplo:**
- Input: Matriz 10×10 com 0s (minas) e 1s (caminho)
- Output: Distância mínima (ou erro se impossível)

### 8. Todos os Caminhos com Exatamente K Arestas (All Walks with K Edges)

**Descrição:** Contar todos os caminhos distintos entre U e V usando exatamente K arestas.

**Algoritmo:**
1. BFS com fila controlando profundidade dos nós
2. Itere enquanto profundidade < K; enfileire vizinhos com profundidade + 1
3. Incremente contador quando atinge V com profundidade = K

**Exemplo:**
- Input: Grafo; U = 0; V = 3; K = 2
- Output: `2` rotas

### 9. Caminho de Custo Mínimo Direcionado (Minimum Cost Path - Dijkstra)

**Descrição:** Encontrar caminho de menor custo total em grafo direcionado com pesos nas arestas.

**Algoritmo:**
1. Use Dijkstra com Fila de Prioridade
2. Array de distâncias inicializadas com "infinito"; origem = 0
3. Fila armazena: `(vértice, distância acumulada)`
4. Relaxe arestas: se novo custo < distância registrada, atualize e enfileire vizinho

**Exemplo:**
- Input: Grafo com pesos; Origem; Destino
- Output: Soma do menor custo do trajeto

### 10. Caminho de Custo Mínimo via Nós Intermediários (Min Cost via Intermediates)

**Descrição:** Menor custo passando obrigatoriamente por vértices intermediários específicos.

**Algoritmo:**
1. Fracione em sub-problemas: calcule distâncias mínimas entre pares usando Dijkstra
2. Calcule rotas: origem → intermediários → destino
3. Verifique todas as permutações de ordem dos intermediários
4. Retorne a soma total mínima

**Exemplo:**
- Input: Grafo ponderado; Vértice inicial; Vértice final; Array de nós obrigatórios
- Output: Custo numérico da rota mais barata

</details>
