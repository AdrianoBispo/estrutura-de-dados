# Lista de Exercícios - Estruturas de Dados Deque (Fila de Duas Pontas)

Esta lista tem o objetivo de fortalecer sua lógica de programação utilizando a estrutura de dados **Deque** (Fila de Duas Pontas). Um Deque permite inserções e remoções tanto no início quanto no final da estrutura em tempo constante `O(1)`. Sinta-se livre para resolver os problemas abaixo utilizando a linguagem de sua preferência (C, C++, Java, Python, Javascript/Typescript, Go, etc.).

<details>
<summary>🟢 Nível 1 - Fácil</summary>

### 1. Minimizar a Diferença Máxima Adjacente

**Descrição:** Reorganize os elementos de um array para que a diferença absoluta máxima entre dois elementos adjacentes seja a menor possível.

**Passo a Passo:**
1. Ordene o array em ordem crescente
2. Crie um Deque vazio
3. Percorra o array ordenado, alternando: primeiro elemento no final, segundo no início, terceiro no final, etc.
4. O Deque resultante conterá o array reorganizado minimizando a diferença máxima

**Input:** `[10, 5, 7, 2, 4]`  
**Output:** `[5, 2, 4, 7, 10]` _(exemplo de reorganização válida)_

### 2. Substring com Frequência Máxima

**Descrição:** Dada uma string e um valor `K`, encontre a substring de tamanho `K` que mais se repete.

**Passo a Passo:**
1. Utilize um mapa para contar frequências de substrings
2. Use um Deque como "janela deslizante" de tamanho `K`
3. Percorra a string adicionando caracteres no final do Deque
4. Quando o tamanho ultrapassar `K`, remova um caractere do início
5. Ao atingir tamanho `K`, incremente a contagem da substring no mapa
6. Retorne a substring com maior contagem

**Input:** `String: "ababab"`, `K: 2`  
**Output:** `"ab"` _(Frequência: 3)_

### 3. Prefixos como Sufixos de uma String

**Descrição:** Encontre os comprimentos de todos os prefixos que também são sufixos idênticos da própria string.

**Passo a Passo:**
1. Crie uma lógica de comparação espelhada nas bordas da string
2. Preencha um Deque com caracteres para facilitar comparações ou simule a lógica de um array LPS
3. Verifique iterativamente substrings do início e do final com mesmo comprimento
4. Se coincidirem, registre o tamanho da sequência

**Input:** `"abacaba"`  
**Output:** `[1, 3, 7]` _(Os prefixos/sufixos são "a", "aba" e "abacaba")_

### 4. Travessia de Níveis em Forma Espiral

**Descrição:** Percorra uma Árvore Binária nível por nível, alternando a direção de leitura (esquerda-direita, depois direita-esquerda).

**Passo a Passo:**
1. Inicialize um Deque com o nó raiz e uma variável booleana para rastrear direção
2. Enquanto o Deque não estiver vazio, determine o número de nós no nível atual
3. Se direção "direita-esquerda": remova do final e insira filhos (direita, esquerda) no início
4. Se direção "esquerda-direita": remova do início e insira filhos (esquerda, direita) no final
5. Inverta a direção para o próximo nível

**Input:** Níveis `[1]`, `[2, 3]`, `[7, 6, 5, 4]`  
**Output:** `1, 2, 3, 4, 5, 6, 7`

### 5. String após Processar Caracteres de Backspace

**Descrição:** Dada uma string com letras e `#` (backspace), determine a string resultante.

**Passo a Passo:**
1. Crie um Deque de caracteres vazio
2. Para cada caractere da string: se for letra, insira no final; se for `#`, remova do final
3. Transforme os elementos restantes em string

**Input:** `"a#bc#d"`  
**Output:** `"bd"`

### 6. Gerar uma Sequência Inserindo Posições

**Descrição:** Dado uma string com 'L' (Left) e 'R' (Right), gere uma sequência de 1 até N+1.

**Passo a Passo:**
1. Para string de tamanho N, organize números de 1 a N+1
2. Leia a string de trás para frente e insira números dinamicamente
3. Se 'R': insira no início do Deque; se 'L': insira no final
4. Extraia sequencialmente do Deque

**Input:** `"LLRR"`  
**Output:** `[5, 4, 1, 2, 3]` _(exemplo de sequência válida)_

### 7. Maior Permutação Lexicográfica

**Descrição:** Crie a maior permutação possível inserindo cada elemento no início ou no final de um Deque.

**Passo a Passo:**
1. Inicialize um Deque vazio
2. Itere sobre elementos do array: se for maior que o do início (ou Deque vazio), insira no início
3. Caso contrário, insira no final
4. Extraia os elementos

**Input:** `[3, 1, 5, 2, 4]`  
**Output:** `[5, 3, 1, 2, 4]`

### 8. Verificar se Strings Podem ser Iguais

**Descrição:** Verifique se duas strings podem ficar iguais inserindo no máximo uma substring em uma delas.

**Passo a Passo:**
1. Coloque as strings em dois Deques
2. Compare do início: remova caracteres iguais de ambos
3. Compare do final: remova caracteres iguais de ambos
4. Se um Deque ficar vazio, a condição é verdadeira

**Input:** `str1 = "abcde"`, `str2 = "ab123cde"`  
**Output:** `Verdadeiro` _(Inserindo "123")_

</details>

<details>
<summary>🟠 Nível 2 - Médio</summary>

### 9. Implementar Pilha e Fila usando Deque

**Descrição:** Crie estruturas LIFO (Pilha) e FIFO (Fila) usando internamente apenas um Deque.

**Passo a Passo:**
- **Pilha:** `push(x)` → `inserir_final()`, `pop()` → `remover_final()`
- **Fila:** `enqueue(x)` → `inserir_final()`, `dequeue()` → `remover_inicio()`

**Input:** Pilha: Push(10), Push(20), Pop() | Fila: Enqueue(1), Enqueue(2), Dequeue()  
**Output:** Pilha: 20 | Fila: 1

### 10. Gerar Sequência Bitônica

**Descrição:** Crie uma sequência que cresce até um pico e depois decresce (bitônica).

**Passo a Passo:**
1. Inicialize um Deque vazio
2. Alternadamente: adicione número no início e próximo no final
3. Os maiores valores vão para o meio, menores nas bordas

**Input:** Números de 1 a 5  
**Output:** `[1, 3, 5, 4, 2]`

### 11. Reorganizar Elementos do Array

**Descrição:** Mova elementos para o início do array conforme comandos.

**Passo a Passo:**
1. Coloque elementos do array em um Deque
2. Para cada comando "mover X para o início": remova X e insira no início
3. Extraia sequencialmente

**Input:** Array: `[1, 2, 3, 4]` | Comandos: Mover 3, depois 4 para o início  
**Output:** `[4, 3, 1, 2]`

### 12. Maior Subarray com Diferença Absoluta ≤ X

**Descrição:** Encontre o maior subarray contíguo onde max - min ≤ X.

**Passo a Passo:**
1. Use dois Deques: `maxDeque` (máximos em ordem decrescente) e `minDeque` (mínimos em ordem crescente)
2. Use janela deslizante com ponteiros esquerdo e direito
3. Mantenha propriedades dos Deques removendo elementos do final ao expandir
4. Se diferença > X, avance esquerda e remova do início
5. Atualize tamanho máximo iterativamente

**Input:** `[8, 2, 4, 7]`, X = 4  
**Output:** 2 _(Subarray [2, 4])_

### 13. Inverter uma Lista Encadeada em Grupos

**Descrição:** Inverta nós em blocos de tamanho K.

**Passo a Passo:**
1. Use Deque como armazenamento temporário
2. Adicione nós no final até completar K nós
3. Remova do final (invertendo ordem) e religue ponteiros
4. Repita para próximos blocos

**Input:** Lista: `1→2→3→4→5→6`, K = 3  
**Output:** `3→2→1→6→5→4`

### 14. Subsequência de Soma Máxima com Elementos a Distância K

**Descrição:** Encontre a maior soma de subsequência onde distância entre índices ≤ K.

**Passo a Passo:**
1. Use Programação Dinâmica: `DP[i]` = soma máxima terminando em i
2. Transição: `DP[i] = array[i] + MAX(DP[i-1], ..., DP[i-K])`
3. Use Deque com índices em ordem decrescente de valores de DP
4. Elemento no início fornece máximo em O(1)
5. Remova valores velhos que excedem distância K

**Input:** `[10, -5, -2, 4, 0, 3]`, K = 3  
**Output:** 17 _(Soma: 10 + (-2) + 4 + 3)_

### 15. N-ésimo Termo de Relação de Recorrência

**Descrição:** Calcule o N-ésimo termo onde cada termo é o produto/soma dos últimos K termos.

**Passo a Passo:**
1. Insira os primeiros K termos no Deque
2. Para próximos termos: multiplique/some elementos do Deque
3. Insira resultado no final
4. Remova termo mais antigo do início
5. Repita até alcançar o N-ésimo termo

**Input:** K primeiros: `[1, 2, 3]`, K = 3, N = 5  
**Output:** 36 _(T4 = 1×2×3 = 6; T5 = 2×3×6 = 36)_

### 16. Tamanho Máximo de Subarray com K Incrementos

**Descrição:** Encontre o maior subarray que pode ter todos elementos iguais com no máximo K incrementos.

**Passo a Passo:**
1. Ordene o array
2. Use janela deslizante: condição válida é `(tamanho × máximo) - soma ≤ K`
3. Rastreie o máximo da janela com Deque para eficiência

**Input:** `[1, 2, 4, 5]`, K = 3  
**Output:** 3

### 17. Maior String após Deletar K Caracteres

**Descrição:** Remova K caracteres para obter a maior string lexicograficamente.

**Passo a Passo:**
1. Crie um Deque para pilha de caracteres monotônica decrescente
2. Itere sobre caracteres: se maior que o do final e K > 0, remova do final
3. Adicione caractere atual no final
4. Se K > 0 ao fim, remova do final até K zerar

**Input:** `str = "abacaba"`, K = 2  
**Output:** `"bacba"`

### 18. Segregar Nós Pares e Ímpares em uma Lista Encadeada

**Descrição:** Mova nós pares para o início e ímpares para o final.

**Passo a Passo:**
1. Crie um Deque
2. Percorra a lista: se par, insira no início; se ímpar, no final
3. Religue ponteiros extraindo sequencialmente

**Input:** `17 → 15 → 8 → 12 → 5`  
**Output:** `12 → 8 → 17 → 15 → 5`

### 19. Gerar Permutação com Diferenças Adjacentes Únicas

**Descrição:** Construa array de 1 a N com exatamente K diferenças adjacentes únicas.

**Passo a Passo:**
1. Coloque números 1 a N em Deque
2. Extraia alternadamente do início e final K vezes
3. Organize restante em uma direção apenas

**Input:** N = 5, K = 2  
**Output:** `[1, 5, 4, 3, 2]` _(Diferenças únicas: 4 e 1)_

### 20. BFS 0-1 (Busca em Largura 0-1)

**Descrição:** Calcule caminho mais curto em grafo com arestas de peso 0 ou 1.

**Passo a Passo:**
1. Use Deque em vez de fila comum
2. Inicialize distâncias como infinito, origem com 0
3. Retire do início do Deque e percorra vizinhos
4. Se peso = 0: insira vizinho no início; se peso = 1: insira no final

**Input:** Grafo: 0→1(0), 1→2(1), 0→2(1) | Origem: 0  
**Output:** Distância mínima para nó 2 é 1

### 21. Mínimo de Deques para Ordenar Array

**Descrição:** Encontre quantidade mínima de partições (Deques lógicos) para ordenar o array.

**Passo a Passo:**
1. Analise posições baseado na versão ordenada
2. Converta em array de índices
3. Conte "inversões" que fogem da regra de inserção de bordas

**Input:** `[2, 4, 1, 3]`  
**Output:** Quantidade mínima de Deques (geralmente 1-2)

### 22. Número Mínimo Aplicando Operações de + e ×

**Descrição:** Aplique operações sequenciais de adição e multiplicação consumindo pelas extremidades para minimizar resultado.

**Passo a Passo:**
1. Insira dados em um Deque
2. Em cada rodada, retire do início e/ou final conforme estratégia
3. Aplique operações de forma gulosa para minimizar total

**Input:** `[1, 2, 3]` e um set de operações  
**Output:** Resultado mínimo possível

</details>
