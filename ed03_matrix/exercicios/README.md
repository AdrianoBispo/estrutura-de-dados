# Lista de Exercícios - Estruturas de Dados Matrizes

Este documento contém uma lista progressiva de exercícios focados na manipulação de matrizes (arrays bidimensionais). O objetivo é fortalecer a lógica de programação. Sinta-se à vontade para resolver estes problemas na linguagem de programação da sua escolha (C, C++, Java, Python, Javascript, etc.).

<details>
<summary><strong>🟢 Nível 1 - Fácil</strong></summary>

### 1. Busca em uma Matriz

**Descrição:** Dado um número inteiro `X` e uma matriz, crie um algoritmo para verificar se o elemento `X` está presente nela.

**Passo a Passo:**
1. Inicialize dois laços de repetição aninhados: um para percorrer as linhas e outro para as colunas.
2. Em cada iteração, compare o elemento atual `Matriz[i][j]` com o alvo `X`.
3. Se forem iguais, retorne a posição `(i, j)`.
4. Se os laços terminarem sem encontrar o elemento, retorne que não foi encontrado.

**Input:** `Matriz = [[1, 2, 3], [4, 5, 6], [7, 8, 9]], X = 5`

**Output:** `Encontrado na posição (1, 1)`

### 2. Adição, Subtração e Multiplicação

**Descrição:** Crie funções para realizar as três operações matemáticas básicas entre duas matrizes A e B.

**Passo a Passo:**
1. **Adição/Subtração:** Verifique se as matrizes têm as mesmas dimensões. Crie uma matriz resultante `C`. Para cada `i` e `j`, faça `C[i][j] = A[i][j] +/- B[i][j]`.
2. **Multiplicação:** Verifique se o número de colunas de A é igual ao número de linhas de B.
3. Crie `C` com as dimensões (linhas de A × colunas de B).
4. Para cada elemento `C[i][j]`, calcule o produto escalar da linha `i` de A com a coluna `j` de B.

**Input:** `A = [[1, 2], [3, 4]], B = [[5, 6], [7, 8]]`

**Output (Adição):** `[[6, 8], [10, 12]]`

### 3. Ordenar a Matriz Fornecida

**Descrição:** Dada uma matriz, retorne a mesma matriz com todos os seus elementos ordenados em ordem crescente.

**Passo a Passo:**
1. Crie um array unidimensional auxiliar.
2. Copie todos os elementos da matriz para este array.
3. Ordene o array (usando Bubble Sort, Quick Sort ou funções nativas).
4. Preencha a matriz original substituindo os valores na ordem sequencial do array ordenado.

**Input:** `[[5, 4, 7], [1, 3, 8], [2, 9, 6]]`

**Output:** `[[1, 2, 3], [4, 5, 6], [7, 8, 9]]`

### 4. Busca em uma Matriz Ordenada

**Descrição:** Encontre um elemento em uma matriz onde todas as linhas e colunas estão ordenadas de forma crescente.

**Passo a Passo:**
1. Comece a busca no canto superior direito da matriz: `linha = 0`, `coluna = n - 1`.
2. Se o valor atual for igual ao alvo, retorne a posição.
3. Se o valor for maior que o alvo, mova para a esquerda (`coluna--`).
4. Se o valor for menor que o alvo, mova para baixo (`linha++`).
5. Repita até encontrar ou sair dos limites da matriz.

**Input:** `Matriz = [[10, 20], [15, 25]], X = 15`

**Output:** `Encontrado na posição (1, 0)`

### 5. Percorrer Matriz usando Recursão

**Descrição:** Imprima todos os elementos de uma matriz sem usar laços de repetição (for/while).

**Passo a Passo:**
1. Crie uma função recursiva que receba a matriz, a `linha_atual` e a `coluna_atual`.
2. Caso base: se a `linha_atual` for igual ao total de linhas, encerre.
3. Se a `coluna_atual` for igual ao total de colunas, chame a função para a próxima linha (`linha_atual + 1`, `0`).
4. Caso contrário, imprima o elemento atual e chame a função para a próxima coluna (`linha_atual`, `coluna_atual + 1`).

**Input:** `[[1, 2], [3, 4]]`

**Output:** `1 2 3 4`

### 6. Transposição de uma Matriz

**Descrição:** Encontre a transposta de uma matriz (transforme linhas em colunas e vice-versa).

**Passo a Passo:**
1. Crie uma nova matriz `Transposta` onde as dimensões são invertidas.
2. Percorra a matriz original com `i` (linhas) e `j` (colunas).
3. Atribua `Transposta[j][i] = Matriz[i][j]`.

**Input:** `[[1, 1], [2, 2], [3, 3]]`

**Output:** `[[1, 2, 3], [1, 2, 3]]`

### 7. Determinante de uma Matriz

**Descrição:** Calcule o determinante de uma matriz quadrada (n × n).

**Passo a Passo:**
1. Caso base: se for uma matriz 1×1, retorne o único elemento. Se 2×2, calcule `(A[0][0]*A[1][1]) - (A[0][1]*A[1][0])`.
2. Para matrizes maiores, fixe a primeira linha.
3. Itere sobre as colunas da primeira linha, calcule o cofator usando recursão para as submatrizes resultantes.
4. Some os valores multiplicados pelos sinais alternados (+, −, +, ...).

**Input:** `[[1, 2], [3, 4]]`

**Output:** `-2`

### 8. Matriz Adjunta e Inversa

**Descrição:** Calcule a matriz inversa de uma matriz dada. A inversa é calculada como `(1 / Determinante) * Adjunta`.

**Passo a Passo:**
1. Calcule o determinante (use a lógica do exercício 7). Se for 0, a inversa não existe.
2. Calcule a matriz de cofatores (determinantes das submatrizes).
3. Transponha a matriz de cofatores para obter a matriz Adjunta.
4. Divida cada elemento da Adjunta pelo determinante.

**Input:** `[[1, 2], [3, 4]]`

**Output:** `[[-2.0, 1.0], [1.5, -0.5]]`

### 9. Sudoku Válido

**Descrição:** Verifique se um tabuleiro de Sudoku 9×9 (parcialmente preenchido) é válido.

**Passo a Passo:**
1. Use HashSets (ou vetores booleanos) para registrar números já vistos em cada linha, cada coluna e cada sub-grade 3×3.
2. Percorra cada célula `[i][j]`. Ignore se estiver vazia.
3. Se o número atual já existir no registro da linha `i`, da coluna `j`, ou no bloco `(i/3, j/3)`, o Sudoku é inválido.
4. Se passar por tudo, é válido.

**Input:** Um tabuleiro 9×9 válido com números e espaços vazios (0)

**Output:** `Verdadeiro`

### 10. Validar Jogo da Velha

**Descrição:** Verifique se o estado atual de um tabuleiro de Jogo da Velha (3×3) é possível/válido, sabendo que o 'X' começa.

**Passo a Passo:**
1. Conte a quantidade de 'X' e 'O'. 'X' deve ser igual a 'O' ou 'O' + 1. Se não, é inválido.
2. Verifique se 'X' ganhou (verificando linhas, colunas e diagonais).
3. Verifique se 'O' ganhou.
4. Se ambos ganharam, é inválido. Se 'O' ganhou, a contagem de 'X' e 'O' deve ser igual. Se 'X' ganhou, 'X' deve ser 'O' + 1.

**Input:** `[['X', 'O', 'X'], ['O', 'X', 'O'], ['X', 'X', 'O']]`

**Output:** `Válido`

### 11. O Problema da Celebridade

**Descrição:** Em uma festa com `N` pessoas, uma celebridade é aquela que não conhece ninguém, mas é conhecida por todos. Encontre-a usando uma matriz onde `Matriz[i][j] = 1` significa que `i` conhece `j`.

**Passo a Passo:**
1. Use a técnica de eliminação. Defina dois ponteiros: `A = 0` e `B = N - 1`.
2. Enquanto `A < B`, se `A` conhece `B` (`Matriz[A][B] == 1`), `A` não é celebridade, então `A++`.
3. Caso contrário, `B` não é celebridade, então `B--`.
4. O ponteiro restante é um candidato. Verifique separadamente se ele não conhece ninguém e todos o conhecem.

**Input:** `[[0, 1, 0], [0, 0, 0], [0, 1, 0]]` (Pessoa 1 é a celebridade)

**Output:** `1`

### 12. Elementos de Contorno

**Descrição:** Imprima apenas os elementos que estão nas bordas (contorno) da matriz.

**Passo a Passo:**
1. Identifique as 4 bordas: primeira linha, última coluna, última linha, primeira coluna.
2. Imprima a primeira linha (esquerda para direita).
3. Imprima a última coluna (cima para baixo, ignorando o primeiro já impresso).
4. Imprima a última linha (direita para esquerda, se não for a primeira).
5. Imprima a primeira coluna (baixo para cima, se não for a última).

**Input:** `[[1, 2, 3], [4, 5, 6], [7, 8, 9]]`

**Output:** `1 2 3 6 9 8 7 4`

### 13. Matriz em Ziguezague

**Descrição:** Imprima os elementos da matriz em formato de ziguezague por linha (linha 1: esq→dir, linha 2: dir→esq...).

**Passo a Passo:**
1. Crie um laço que percorre as linhas de `i = 0` até `N-1`.
2. Se `i` for par, percorra as colunas de `0` a `M-1` (imprimindo da esquerda para a direita).
3. Se `i` for ímpar, percorra as colunas de `M-1` até `0` (imprimindo da direita para a esquerda).

**Input:** `[[1, 2], [3, 4], [5, 6]]`

**Output:** `1 2 4 3 5 6`

### 14. Rotacionar Elementos da Matriz em 1

**Descrição:** Desloque os elementos da matriz circularmente no sentido horário, anel por anel.

**Passo a Passo:**
1. Defina quatro limites: `topo`, `base`, `esquerda`, `direita`.
2. Enquanto `esquerda < direita` e `topo < base`, pegue o primeiro elemento da segunda linha (`prev = Matriz[topo+1][esquerda]`).
3. Percorra o anel de fora (topo esq→dir, direita cima→baixo, base dir→esq, esquerda baixo→cima), trocando o valor atual com `prev` e atualizando `prev`.
4. Incremente `topo`, `esquerda` e decremente `base`, `direita` para ir para o anel interno.

**Input:** `[[1, 2], [3, 4]]`

**Output:** `[[3, 1], [4, 2]]`

### 15. Matriz em Espiral

**Descrição:** Imprima os elementos de uma matriz seguindo um padrão espiral começando do canto superior esquerdo para dentro.

**Passo a Passo:**
1. Semelhante aos Elementos de Contorno, defina `topo`, `base`, `esquerda`, `direita`.
2. Faça um loop `while(topo <= base && esquerda <= direita)`.
3. Imprima o `topo` e faça `topo++`. Imprima a `direita` e faça `direita--`.
4. Se `topo <= base`, imprima a `base` (invertida) e faça `base--`.
5. Se `esquerda <= direita`, imprima a `esquerda` (invertida) e faça `esquerda++`.

**Input:** `[[1, 2, 3], [4, 5, 6], [7, 8, 9]]`

**Output:** `1 2 3 6 9 8 7 4 5`

### 16. Elementos Únicos em uma Matriz

**Descrição:** Imprima todos os elementos que aparecem exatamente uma única vez em toda a matriz.

**Passo a Passo:**
1. Crie uma Tabela de Dispersão (Hash Map) ou um array de frequência.
2. Percorra a matriz inteira. Para cada elemento, incremente sua contagem na tabela.
3. Percorra a matriz (ou a tabela) novamente e imprima apenas os elementos cuja contagem seja `1`.

**Input:** `[[1, 2], [2, 3]]`

**Output:** `1 3`

### 17. Trocar Diagonais Principal e Secundária

**Descrição:** Dada uma matriz quadrada, troque os elementos da diagonal principal com os da diagonal secundária.

**Passo a Passo:**
1. Crie um loop com `i` variando de `0` até `N-1`.
2. O elemento da diagonal principal é `Matriz[i][i]`.
3. O elemento da diagonal secundária é `Matriz[i][N - 1 - i]`.
4. Faça o swap (troca) entre esses dois elementos, pulando se for o elemento central (`i == N - 1 - i`).

**Input:** `[[1, 2, 3], [4, 5, 6], [7, 8, 9]]`

**Output:** `[[3, 2, 1], [4, 5, 6], [9, 8, 7]]`

### 18. Verificar Matriz Idempotente

**Descrição:** Verifique se uma matriz é idempotente. Uma matriz `M` é idempotente se `M * M = M`.

**Passo a Passo:**
1. Crie uma função que multiplique a matriz por ela mesma, gerando uma matriz temporária `Temp`.
2. Após calcular a multiplicação, compare `Temp` com a matriz original `M`.
3. Se todos os elementos correspondentes forem iguais, retorne `Verdadeiro`, senão `Falso`.

**Input:** `[[2, -2, -4], [-1, 3, 4], [1, -2, -3]]`

**Output:** `Verdadeiro`

### 19. Triângulo de Pascal

**Descrição:** Gere as primeiras `N` linhas do Triângulo de Pascal e armazene em uma matriz inferior (ou lista de listas).

**Passo a Passo:**
1. Crie uma matriz onde a primeira coluna e a diagonal principal sejam preenchidas com `1` (`Matriz[i][0] = 1` e `Matriz[i][i] = 1`).
2. Para os demais elementos na linha `i` e coluna `j` (onde `0 < j < i`):
3. `Matriz[i][j] = Matriz[i-1][j-1] + Matriz[i-1][j]`

**Input:** `N = 4`

**Output:** `[[1], [1, 1], [1, 2, 1], [1, 3, 3, 1]]`

### 20. Matriz de Toeplitz

**Descrição:** Verifique se todas as diagonais descendentes da esquerda para a direita têm os mesmos elementos.

**Passo a Passo:**
1. Percorra a matriz começando da primeira linha (`i = 1`) e da primeira coluna (`j = 1`).
2. Compare o elemento atual `Matriz[i][j]` com o elemento diagonalmente superior esquerdo `Matriz[i-1][j-1]`.
3. Se em algum momento eles forem diferentes, retorne `Falso`.
4. Se o laço terminar, retorne `Verdadeiro`.

**Input:** `[[1, 2, 3], [4, 1, 2], [5, 4, 1]]`

**Output:** `Verdadeiro`

### 21. Movimentos Possíveis do Cavalo

**Descrição:** Dada uma posição no tabuleiro de xadrez (matriz 8×8), determine todas as posições válidas para as quais o cavalo pode se mover.

**Passo a Passo:**
1. O cavalo se move em "L". Defina os 8 pares de deslocamento direcional: `(2,1), (2,-1), (-2,1), (-2,-1), (1,2), (1,-2), (-1,2), (-1,-2)`.
2. Dado o índice atual `(L, C)`, some cada um dos 8 pares.
3. Verifique se as novas coordenadas `(L_nova, C_nova)` estão dentro dos limites `0 <= L_nova < 8` e `0 <= C_nova < 8`.
4. Se válido, adicione à lista de saídas.

**Input:** Posição atual: `(4, 4)`

**Output:** `(6, 5), (6, 3), (2, 5), (2, 3), (5, 6), (5, 2), (3, 6), (3, 2)`

</details>

<details>
<summary><strong>🟠 Nível 2 - Médio</strong></summary>

### 22. O Jogo da Vida de Conway

**Descrição:** Dada uma matriz contendo o estado atual do Jogo da Vida (1 = vivo, 0 = morto), calcule o próximo estado. Regras: Célula viva com 2 ou 3 vizinhos vive, senão morre. Célula morta com 3 vizinhos revive.

**Passo a Passo:**
1. Crie uma matriz cópia ou utilize estados temporários (ex: 2 para vivo→morto, 3 para morto→vivo) para não interferir na geração atual.
2. Para cada célula `(i, j)`, conte seus vizinhos vivos nas 8 direções.
3. Aplique as regras lógicas para determinar o próximo estado.
4. Atualize a matriz para o novo estado final (converta estados temporários de volta para 0 e 1).

**Input:** `[[0, 1, 0], [0, 1, 0], [0, 1, 0]]`

**Output:** `[[0, 0, 0], [1, 1, 1], [0, 0, 0]]`

### 23. Rotacionar uma Matriz em 90 Graus

**Descrição:** Rotacione uma matriz quadrada `N × N` em 90 graus no sentido anti-horário, preferencialmente sem criar uma nova matriz auxiliar.

**Passo a Passo:**
1. Primeiro, encontre a Transposta da matriz (troque `Matriz[i][j]` por `Matriz[j][i]`).
2. Em seguida, para rotacionar 90 graus no sentido anti-horário, inverta as colunas (troque a primeira linha pela última, a segunda pela penúltima, etc.).
3. _(Dica: para sentido horário, inverta os elementos de cada linha, da esquerda para a direita.)_

**Input:** `[[1, 2], [3, 4]]`

**Output:** `[[2, 4], [1, 3]]`

### 24. Rotacionar uma Matriz em 180 Graus

**Descrição:** Rotacione a matriz 180 graus sem usar espaço extra (In-place).

**Passo a Passo:**
1. A rotação de 180 graus equivale a inverter completamente a matriz tanto na vertical quanto na horizontal.
2. Trate a matriz como um array plano e faça o swap do primeiro elemento com o último, do segundo com o penúltimo, até o meio.
3. Matematicamente: troque `Matriz[i][j]` com `Matriz[N-1-i][N-1-j]`. Pare na metade da matriz.

**Input:** `[[1, 2], [3, 4]]`

**Output:** `[[4, 3], [2, 1]]`

### 25. Maior Submatriz com Bordas de 'X'

**Descrição:** Dada uma matriz de 'O's e 'X's, encontre a maior submatriz quadrada cujas bordas são inteiramente formadas por 'X'.

**Passo a Passo:**
1. Crie duas matrizes auxiliares: `Horizontal` e `Vertical`.
2. Para cada célula de baixo para cima, da direita para a esquerda: se for 'X', calcule quantos 'X's consecutivos existem à direita (em `Horizontal`) e para baixo (em `Vertical`).
3. Para cada célula `(i, j)`, teste tamanhos `t` a partir do valor mínimo entre `Horizontal[i][j]` e `Vertical[i][j]`, reduzindo o tamanho `t` até achar uma borda válida verificando o outro canto.
4. Salve e retorne a maior dimensão.

**Input:** `[['X', 'O', 'X'], ['X', 'X', 'X'], ['X', 'X', 'X']]`

**Output:** `2` (Quadrado 2×2 no canto inferior)

### 26. Maior Submatriz Quadrada com Todos os 1s

**Descrição:** Dada uma matriz binária (0s e 1s), encontre a maior submatriz quadrada onde todos os elementos são 1s.

**Passo a Passo:**
1. Crie uma matriz de Programação Dinâmica `DP` do mesmo tamanho da original.
2. Copie a primeira linha e a primeira coluna da matriz original para `DP`.
3. Para as demais células `(i, j)`, se `Matriz[i][j] == 1`, defina `DP[i][j] = min(DP[i-1][j], DP[i][j-1], DP[i-1][j-1]) + 1`.
4. Se for 0, `DP[i][j] = 0`. O maior valor na matriz `DP` é o lado do maior quadrado.

**Input:** `[[0, 1, 1], [0, 1, 1], [0, 0, 0]]`

**Output:** `2`

### 27. Zeros em Matriz Ordenada por Linha e Coluna

**Descrição:** Conte a quantidade de zeros em uma matriz de inteiros onde cada linha e coluna está classificada em ordem crescente.

**Passo a Passo:**
1. Comece no canto inferior esquerdo: `i = N - 1`, `j = 0`.
2. Se o valor atual for `<= 0`, o total de zeros na coluna (daquele ponto para cima) será `i + 1`. Adicione à contagem e mova para a direita `j++`.
3. Se `> 0`, suba na linha `i--`.

**Input:** `[[0, 0, 1], [0, 1, 1], [1, 1, 1]]`

**Output:** `3`

### 28. Consultas em uma Matriz

**Descrição:** Começando com uma matriz zerada de tamanho N×M, você recebe um array de consultas no formato `(linha, coluna)`. Cada consulta significa que você deve somar 1 a todos os elementos da respectiva linha e coluna. Retorne o resultado final.

**Passo a Passo:**
1. Em vez de iterar pelas linhas e colunas para cada consulta, mantenha dois arrays unidimensionais: `SomaLinha` e `SomaColuna`.
2. Para cada consulta `(l, c)`, faça `SomaLinha[l]++` e `SomaColuna[c]++`.
3. No final, construa a matriz resultado onde `Matriz[i][j] = SomaLinha[i] + SomaColuna[j]`.

**Input:** `N=2, M=2, Consultas = [(0,0), (1,1)]`

**Output:** `[[2, 1], [1, 2]]`

### 29. Contar Pares com Soma de 2 Matrizes

**Descrição:** Dadas duas matrizes A e B ordenadas e um valor `X`, encontre quantos pares `(A[i][j], B[k][l])` somam `X`.

**Passo a Passo:**
1. Trate as matrizes como arrays 1D ordenados. Use a técnica de dois ponteiros.
2. Defina `P1` apontando para o início de `A` (linha 0, coluna 0) e `P2` apontando para o fim de `B` (linha N-1, coluna M-1).
3. Calcule `soma = Valor de P1 + Valor de P2`.
4. Se `soma == X`, incremente a contagem, avance `P1` e recue `P2`.
5. Se `soma < X`, avance `P1`. Se `soma > X`, recue `P2`.

**Input:** `A=[[1,2],[3,4]], B=[[2,4],[5,8]], X=6`

**Output:** `2` (Pares: 1+5, 2+4)

### 30. Soma de Pares de Linhas Diferentes

**Descrição:** Dada uma matriz e um alvo, encontre todos os pares de elementos que somam o alvo, garantindo que ambos os elementos do par pertençam a linhas diferentes da matriz.

**Passo a Passo:**
1. Utilize uma Tabela Hash (Dicionário ou Map). A chave será o valor do elemento e o valor associado será a linha do elemento.
2. Percorra a matriz elemento por elemento.
3. Para cada elemento `Matriz[i][j]`, verifique se o complemento (`Alvo - Matriz[i][j]`) existe na Hash.
4. Se existir, verifique se a linha associada na Hash é diferente da linha atual `i`. Se sim, encontrou um par válido.
5. Adicione o elemento atual na Hash.

**Input:** `Matriz=[[1, 2], [3, 4]], Alvo=5`

**Output:** `Pares: (1, 4), (2, 3)`

### 31. Encontrar Todas as Linhas Permutadas de uma Linha Dada

**Descrição:** Dada uma matriz e o índice de uma linha específica, encontre os índices de todas as outras linhas que são uma permutação exata da linha alvo (possuem exatamente os mesmos elementos, mesmo que em outra ordem).

**Passo a Passo:**
1. Crie uma Tabela de Frequência para registrar a contagem de cada elemento na linha alvo.
2. Para cada outra linha da matriz, crie uma Tabela de Frequência temporária.
3. Compare a tabela atual com a tabela da linha alvo.
4. Se forem estritamente iguais, guarde o índice dessa linha.

**Input:** `Matriz=[[3,1,2], [1,2,3], [3,2,1], [4,5,6]], Linha_alvo=0`

**Output:** `1, 2`

### 32. Número de Transformações para Fazer Duas Matrizes Iguais

**Descrição:** Dadas duas matrizes A e B, encontre o número mínimo de operações (+1 em uma linha ou +1 em uma coluna inteira) para tornar A igual a B. Retorne -1 se impossível.

**Passo a Passo:**
1. Calcule a diferença `C` onde `C[i][j] = B[i][j] - A[i][j]`. O problema agora é: podemos zerar `C` subtraindo valores de linhas/colunas inteiras?
2. Em `C`, perceba que se realizamos operações por linha/coluna, a diferença entre elementos da mesma linha em colunas diferentes deve ser a mesma em todas as linhas.
3. Verifique a validade: Para qualquer `i`, `C[i][0] - C[0][0]` deve ser igual a `C[i][j] - C[0][j]`. Se não, é impossível.

**Input:** `A=[[1,1],[1,1]], B=[[2,3],[2,3]]`

**Output:** `2`

### 33. Mínimo de Inversões para Fazer Matriz Binária Simétrica

**Descrição:** Matriz simétrica significa que `Matriz[i][j] == Matriz[j][i]`. Qual o número mínimo de elementos (bits) que precisam ser flipados (0 para 1 ou 1 para 0) para alcançar a simetria?

**Passo a Passo:**
1. Você só precisa analisar a parte superior direita da matriz (onde `i < j`).
2. Compare o elemento `Matriz[i][j]` com o seu reflexo na diagonal principal `Matriz[j][i]`.
3. Se forem diferentes, você terá que flipar obrigatoriamente um deles. Incremente um contador.
4. Retorne o contador ao fim do laço duplo.

**Input:** `[[0, 1, 0], [0, 0, 1], [0, 0, 0]]`

**Output:** `1`

### 34. Quadrado Mágico

**Descrição:** Verifique se uma matriz dada forma um "Quadrado Mágico" (todas as linhas, colunas e ambas as diagonais somam exatamente o mesmo valor constante).

**Passo a Passo:**
1. Calcule a soma da primeira linha para ser sua "soma alvo".
2. Itere linha por linha para garantir que a soma bate com a alvo.
3. Itere coluna por coluna garantindo a mesma soma.
4. Calcule a soma da diagonal principal e da diagonal secundária e verifique se batem com o alvo.
5. Se tudo conferir, é um quadrado mágico.

**Input:** `[[2, 7, 6], [9, 5, 1], [4, 3, 8]]`

**Output:** `Verdadeiro`

</details>

<details>
<summary><strong>🔴 Nível 3 - Difícil</strong></summary>

### 35. Mediana em Matriz Ordenada por Linha

**Descrição:** Encontre a mediana de uma matriz onde as linhas são independentemente ordenadas de forma crescente. A matriz tem tamanho ímpar (N × M ímpar).

**Passo a Passo:**
1. Use Busca Binária nos valores em vez de extrair e ordenar (que custaria O(N×M log(N×M))).
2. Encontre o menor elemento geral `min_val` (primeira coluna) e o maior `max_val` (última coluna).
3. A mediana procurada `mid` deve ter exatamente `(N × M) / 2` elementos menores que ela na matriz inteira.
4. Faça busca binária no intervalo `[min_val, max_val]`. Para o valor provisório `mid_val`, use o `upper_bound` em cada linha para contar elementos `<= mid_val`. Ajuste a busca com base nessa contagem.

**Input:** `[[1, 3, 5], [2, 6, 9], [3, 6, 9]]`

**Output:** `5`

### 36. Questão da Matriz Booleana

**Descrição:** Dada uma matriz booleana, modifique-a de modo que, se `Matriz[i][j]` for `1`, toda a linha `i` e coluna `j` se tornem `1`. Modifique "in-place" se possível.

**Passo a Passo:**
1. Verifique e salve o estado da primeira linha e da primeira coluna se há algum `1`.
2. Itere do índice 1,1 até o fim. Se `Matriz[i][j] == 1`, marque `Matriz[i][0] = 1` e `Matriz[0][j] = 1`.
3. Percorra novamente a matriz (pulando linha 0 e col 0). Se a marcação na linha 0 ou coluna 0 tiver um `1`, converta `Matriz[i][j]` em `1`.
4. Por fim, se as verificações iniciais da primeira linha/coluna mostraram a presença de `1`s, preencha a respectiva primeira linha/coluna inteira de `1`s.

**Input:** `[[1, 0], [0, 0]]`

**Output:** `[[1, 1], [1, 0]]`

### 37. Multiplicação de Cadeia de Matrizes

**Descrição:** Dado um array que representa as dimensões de matrizes `[p0, p1, p2...]`, encontre o número mínimo de operações de multiplicação escalar necessárias para multiplicar toda a cadeia.

**Passo a Passo:**
1. Use uma tabela `DP[i][j]` que armazenará o custo mínimo de multiplicar as matrizes de `i` até `j`.
2. Para matrizes únicas (`i == j`), o custo é 0.
3. Tente quebrar a cadeia em cada `k` possível entre `i` e `j-1`.
4. O custo é `DP[i][k] + DP[k+1][j] + (p[i-1] * p[k] * p[j])`. Escolha o mínimo.

**Input:** Dimensões = `[10, 20, 30, 40]` (Matrizes 10×20, 20×30, 30×40)

**Output:** `18000`

### 38. Submatriz Quadrada de Soma Máxima com Tamanho Dado

**Descrição:** Dada uma matriz N × N e um inteiro `K`, encontre e imprima a submatriz K × K que possui a soma máxima entre seus elementos.

**Passo a Passo:**
1. Pré-calcule a soma das tiras verticais. Crie uma matriz temporária que na posição `[i][j]` guarde a soma dos elementos `Matriz[x][j]` onde `x` vai de `i` até `i+K-1`.
2. Após somar em colunas, processe a matriz resultante deslizando uma janela na horizontal de tamanho `K` usando a técnica de `Sliding Window`.
3. Acompanhe o índice máximo e retorne a submatriz original daquela posição.

**Input:** `Matriz = [[1, 1, 1], [2, 2, 2], [3, 3, 3]], K = 2`

**Output:** `[[2, 2], [3, 3]]` (Soma = 10)

### 39. Maior Submatriz Retangular com Todos os 1s

**Descrição:** Encontre a maior submatriz retangular (não necessariamente quadrada) consistindo unicamente de `1`s.

**Passo a Passo:**
1. reduza o problema ao "Maior Retângulo em um Histograma".
2. Trate cada linha da matriz binária como a base de um histograma. Acumule os valores "1" de cima para baixo formando alturas. Se um elemento for 0, resete a altura daquela coluna para 0.
3. Para cada linha (como base do seu histograma acumulado), use uma Pilha (Stack) para calcular em O(Colunas) a área do maior retângulo possível com base nas alturas das barras.
4. Guarde o valor máximo global durante todo o processo.

**Input:** `[[0, 1, 1], [1, 1, 1], [0, 1, 1]]`

**Output:** `6` (Retângulo nas últimas 2 colunas com 3 de altura)

### 40. Construir Matriz Ancestral a partir de uma Árvore Binária

**Descrição:** Dada uma Árvore Binária, construa uma matriz de adjacência (N × N) onde `Matriz[i][j] = 1` se o nó `i` for um ancestral do nó `j`.

**Passo a Passo:**
1. Crie a matriz inicializada com `0`s.
2. Utilize Busca em Profundidade (DFS). Para cada nó pai na chamada recursiva, passe adiante uma lista ou conjunto de todos os seus ancestrais.
3. Quando alcançar um nó `j`, percorra a lista de ancestrais recebida. Para cada ancestral `i` da lista, defina `Matriz[i][j] = 1`.
4. Adicione o nó `j` atual à lista e faça as chamadas recursivas para a esquerda e para a direita.

**Input:** Árvore: 5 → (1, 2) (Nó raiz 5 tem filhos 1 e 2)

**Output:** Matriz onde índice do 5 aponta para índices de 1 e 2 com '1'

### 41. K-ésimo Elemento na Forma Espiral da Matriz

**Descrição:** Imprima o K-ésimo elemento visitado ao percorrer a matriz em formato de espiral.

**Passo a Passo:**
1. Reutilize a lógica do Exercício 15 (Matriz em Espiral).
2. Em cada passo onde você normalmente "imprime" o elemento, simplesmente diminua 1 do contador de `K`.
3. Assim que `K` chegar a `0` (ou `1`, dependendo de como indexar), pare e retorne o elemento que foi processado.

**Input:** `[[1, 2, 3], [4, 5, 6], [7, 8, 9]], K=4`

**Output:** `6` (Trajeto: 1→2→3→6)

### 42. Maior '+' Formado por Todos os Uns em Matriz Binária

**Descrição:** Encontre o tamanho do maior formato em cruz ("+") que seja composto apenas por elementos iguais a `1` em uma matriz com `0`s e `1`s.

**Passo a Passo:**
1. Crie quatro matrizes N × N auxiliares para rastrear o número de 1s consecutivos em cada direção: `Esquerda`, `Direita`, `Cima`, `Baixo`.
2. Preencha `Esquerda` e `Cima` iterando da esquerda para direita, cima para baixo.
3. Preencha `Direita` e `Baixo` iterando da direita para esquerda, baixo para cima.
4. Para toda célula `(i, j)`, o tamanho da braçadeira da cruz centrada nela é o menor valor entre `Esquerda[i][j]`, `Direita[i][j]`, `Cima[i][j]` e `Baixo[i][j]`. O maior limite encontrado responde a questão.

**Input:** `[[0, 1, 0], [1, 1, 1], [0, 1, 0]]`

**Output:** `1` (O cruz tem centro em (1,1) com extensão 1 em cada direção)

### 43. Caminho Mais Curto em um Labirinto Binário

**Descrição:** Dada uma matriz contendo espaços abertos (`1`) e paredes (`0`), ache o menor trajeto em passos de uma célula Inicial para um Destino.

**Passo a Passo:**
1. Use Busca em Largura (BFS) para garantir encontrar o caminho mais curto.
2. Crie uma Fila para os nós a visitar, guardando `(Linha, Coluna, Distância)`.
3. Comece na origem adicionando-a na fila com distância = 0 e marcando como "visitado".
4. No loop, extraia o próximo da fila. Verifique adjacentes cima/baixo/esq/dir. Se for destino, retorne `Distância + 1`. Se for `1`, adicione na fila.

**Input:** `Matriz=[[1, 0, 1], [1, 1, 1], [0, 0, 1]], Origem=(0,0), Destino=(2,2)`

**Output:** `4` passos

### 44. Pontos Iniciais Mínimos para Chegar ao Destino

**Descrição:** Matriz com valores positivos, negativos e zeros representando energia. Qual o menor nível positivo de energia inicial (no ponto `0,0`) para chegar no destino `N-1, M-1`, sabendo que a energia em nenhum momento pode ficar ≤ 0? Só pode mover para baixo ou para direita.

**Passo a Passo:**
1. Resolva com Programação Dinâmica de trás para frente (Bottom-up partindo do destino).
2. Tabela `DP` onde `DP[i][j]` é a energia inicial mínima antes de entrar nessa célula.
3. `DP[destino] = max(1, 1 - Matriz[destino])`.
4. Para células acima ou à esquerda do destino, `DP[i][j] = max(1, min(DP[i+1][j], DP[i][j+1]) - Matriz[i][j])`.
5. Retorne `DP[0][0]`.

**Input:** `[[-2, -3, 3], [-5, -10, 1], [10, 30, -5]]`

**Output:** `7`

### 45. Multiplicação de Matrizes de Strassen

**Descrição:** Implemente o método engenhoso de Divide and Conquer de Strassen que multiplica matrizes de forma mais rápida que o clássico O(N³), mas com mais lógica condicional.

**Passo a Passo:**
1. O algoritmo divide cada matriz em 4 submatrizes. (Requer matrizes de tamanho potência de 2, ex: 2×2, 4×4, etc.)
2. Crie submatrizes menores A11, A12, A21, A22 e o mesmo para B.
3. Calcule 7 matrizes temporárias `M1` a `M7` que envolvem somas e multiplicações específicas destas partições.
4. Reagrupe o resultado usando regras fixas (ex: `C11 = M1 + M4 - M5 + M7`).

**Input:** Matrizes 4×4 A e B

**Output:** Matriz resultante 4×4 C (Igual à multiplicação tradicional, mas computado diferentemente)

### 46. Retângulo de Soma Máxima em uma Matriz 2D

**Descrição:** Expansão do algoritmo de Kadane para matrizes 2D. Encontre um sub-retângulo qualquer onde a soma de seus elementos seja o maior valor absoluto.

**Passo a Passo:**
1. Fixe limites de colunas para esquerda e direita (`esq` iterando de `0` a `M-1`, `dir` de `esq` a `M-1`).
2. Crie um array 1D que armazena a soma cumulativa dos elementos de todas as linhas delimitadas por essa `esq` e `dir`.
3. Use o Algoritmo de Kadane no array 1D resultante para achar a "soma máxima contígua".
4. Atualize a variável "Soma Máxima Global" se a chamada retornar algo maior.

**Input:** `[[1, 2, -1, -4, -20], [-8, -3, 4, 2, 1], [3, 8, 10, 1, 3], [-4, -1, 1, 7, -6]]`

**Output:** `29` (A submatriz central inferior)

### 47. Gerador de Sudoku

**Descrição:** Crie uma função capaz de gerar tabuleiros de Sudoku válidos e preenchidos, com uma quantidade variável de peças escondidas para o jogador interagir.

**Passo a Passo:**
1. Inicialize uma grade vazia 9×9.
2. Preencha diagonalmente de forma independente os três blocos 3×3 na diagonal principal.
3. Utilize Recursão via Backtracking (tentativa e erro) para preencher o resto do tabuleiro validando se as regras do Sudoku são mantidas ao inserir os números 1 a 9.
4. Após o tabuleiro estar perfeitamente preenchido e válido, remova (transforme em zero) K elementos de forma aleatória para gerar o puzzle a ser jogado.

**Input:** Nível de dificuldade / K peças a serem removidas

**Output:** Uma matriz 9×9 válida de Sudoku gerada aleatoriamente com K zeros

</details>
