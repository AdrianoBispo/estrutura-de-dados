# Lista de Exercícios - Estruturas de Dados Arrays

Este documento contém uma lista completa de exercícios focados na manipulação de Arrays (Vetores), divididos por nível de dificuldade. O objetivo principal é fortalecer a lógica de programação. O passo a passo descreve o fluxo algorítmico sem se prender a uma linguagem específica, permitindo que você implemente a solução na linguagem de sua preferência (C, C++, Java, Python, Javascript, etc.).

<details>
<summary><strong>🟢 Nível 1 - Fácil</strong></summary>

### 1. Imprimir Elementos Alternados

**Descrição:** Dado um array, imprima os elementos localizados em índices pares (0, 2, 4...).

**Passo a Passo:**
1. Crie um laço de repetição iniciando no índice `0`
2. A condição de parada deve ser o tamanho total do array
3. A cada iteração, incremente o índice em `2` passos
4. Imprima ou armazene o elemento atual

**Entrada:** `[10, 20, 30, 40, 50]`
**Saída:** `[10, 30, 50]`

### 2. Líderes em um Array

**Descrição:** Encontre todos os elementos maiores ou iguais a todos os elementos à sua direita.

**Passo a Passo:**
1. Crie uma variável `max_atual` inicializada com um valor baixo ou o último elemento
2. Percorra o array de trás para frente (do último índice até `0`)
3. Se o elemento atual for >= `max_atual`, é um líder; adicione à resposta e atualize `max_atual`
4. (Opcional) Inverta a lista de resposta no final

**Entrada:** `[16, 17, 4, 3, 5, 2]`
**Saída:** `[17, 5, 2]`

### 3. Remover Duplicatas de um Array Ordenado

**Descrição:** Remova elementos duplicados de um array ordenado, retornando o novo tamanho sem repetições (in-place).

**Passo a Passo:**
1. Se o array for vazio, retorne `0`
2. Use `indice_unico` iniciando em `0` para rastrear o último elemento único
3. Itere a partir do índice `1`
4. Se o elemento atual diferir de `indice_unico`, incremente `indice_unico` e substitua aquela posição

**Entrada:** `[1, 1, 2, 2, 3]`
**Saída:** `[1, 2, 3]` (array passa a ser `[1, 2, 3, x, x]`)

### 4. Gerar Todos os Subarrays

**Descrição:** Encontre e mostre todas as combinações contínuas (subarrays) possíveis.

**Passo a Passo:**
1. Crie um laço principal indicando o ponto de início `i`
2. Crie um segundo laço indicando o ponto final `j` (iniciando em `i`)
3. Crie um terceiro laço que percorre de `i` até `j` e imprime o subarray

**Entrada:** `[1, 2, 3]`
**Saída:** `[1], [1, 2], [1, 2, 3], [2], [2, 3], [3]`

### 5. Inverter um Array

**Descrição:** Altere a ordem dos elementos para que o primeiro torne-se o último e vice-versa.

**Passo a Passo:**
1. Defina dois ponteiros: `inicio` (índice `0`) e `fim` (último índice)
2. Crie um laço enquanto `inicio < fim`
3. Troque os valores nas posições `inicio` e `fim`
4. Incremente `inicio` em `1` e decremente `fim` em `1`

**Entrada:** `[4, 5, 1, 2]`
**Saída:** `[2, 1, 5, 4]`

### 6. Rotacionar um Array

**Descrição:** Desloque ciclicamente o array para a esquerda em `K` posições.

**Passo a Passo:**
1. Garanta que `K = K % tamanho`
2. Crie um array temporário para armazenar os primeiros `K` elementos
3. Mova os elementos restantes para a esquerda
4. Preencha os últimos `K` espaços com os valores do array temporário

**Entrada:** Array `[1, 2, 3, 4, 5]`, K = `2`
**Saída:** `[3, 4, 5, 1, 2]`

### 7. Mover Zeros para o Final

**Descrição:** Mova todos os zeros para o final, mantendo a ordem relativa dos elementos não nulos.

**Passo a Passo:**
1. Crie um contador `indice_nao_zero = 0`
2. Itere pelo array; se o elemento for diferente de zero, mova-o para `indice_nao_zero` e incremente
3. Após o laço, preencha o restante com zeros

**Entrada:** `[0, 1, 0, 3, 12]`
**Saída:** `[1, 3, 12, 0, 0]`

### 8. Incrementos Mínimos para Igualar Elementos

**Descrição:** Dado um array e alvo K, determine operações mínimas para igualar todos os elementos somando K.

**Passo a Passo:**
1. Encontre o maior elemento `max_val`
2. Para cada elemento, calcule a diferença até `max_val`
3. Verifique se a diferença é divisível por `K`
4. Se todas forem, retorne a soma das divisões (diferença / K)

**Entrada:** Array `[4, 7, 19, 16]`, K = `3`
**Saída:** `14` (alvo é 19; total de 10 operações)

### 9. Custo Mínimo para Reduzir Tamanho para 1

**Descrição:** Remova elementos aos pares onde o maior "custa" para ser retirado. Minimize o custo total.

**Passo a Passo:**
1. O menor elemento sobreviverá a todas as comparações
2. O custo é sempre a soma de todos menos o menor
3. Itere somando todos e subtraia o mínimo

**Entrada:** `[4, 3, 2]`
**Saída:** `7` (Soma = 9, Mínimo = 2, Custo = 7)

### 10. Segundo Maior Elemento

**Descrição:** Identifique o segundo maior número sem ordenar completamente.

**Passo a Passo:**
1. Inicialize `maior` e `segundo_maior` com valores muito baixos
2. Itere pelo array; se o número for maior que `maior`, desloque `maior` para `segundo_maior`
3. Se for menor que `maior` mas maior que `segundo_maior`, atualize apenas `segundo_maior`

**Entrada:** `[10, 5, 10, 8]`
**Saída:** `8`

### 11. Terceiro Maior Elemento

**Descrição:** Localize o terceiro maior elemento distinto; se não houver três, retorne o maior.

**Passo a Passo:**
1. Crie variáveis `primeiro`, `segundo` e `terceiro` com valores muito baixos
2. Itere comparando e deslocando valores em cascata
3. Atualize conforme o intervalo em que o elemento se encaixa

**Entrada:** `[1, 14, 2, 16, 10, 20]`
**Saída:** `14`

### 12. Inverter o Array (Repetição de Fixação)

**Descrição:** Crie um novo array invertido sem alterar os dados iniciais.

**Passo a Passo:**
1. Crie um novo array com o mesmo tamanho
2. Itere o array original do fim para o início (N-1 até 0)
3. Insira os elementos no novo array começando pelo índice 0

**Entrada:** `[8, 6, 4]`
**Saída:** `[4, 6, 8]`

### 13. Inverter Array em Grupos

**Descrição:** Inverta o array em blocos do tamanho K.

**Passo a Passo:**
1. Crie um laço pulando de `K` em `K`
2. Defina limites: `esquerda = i` e `direita = min(i + K - 1, último_índice)`
3. Inverta os elementos entre esses limites usando swap

**Entrada:** Array `[1, 2, 3, 4, 5, 6, 7]`, K = `3`
**Saída:** `[3, 2, 1, 6, 5, 4, 7]`

### 14. Rotação de Array (Repetição de Fixação)

**Descrição:** Desloque o array para a direita em D posições.

**Passo a Passo:**
1. Inverta todo o array
2. Inverta os primeiros `D` elementos
3. Inverta os elementos restantes a partir do índice `D`

**Entrada:** Array `[1, 2, 3, 4, 5]`, D = `2`
**Saída:** `[4, 5, 1, 2, 3]`

### 15. Maior Produto de um Trio

**Descrição:** Descubra o maior produto multiplicando três números quaisquer.

**Passo a Passo:**
1. Ordene o array em ordem crescente
2. O maior será o máximo entre: (três últimos) OU (dois primeiros × último)

**Entrada:** `[-10, -10, 1, 3, 2]`
**Saída:** `300` (-10 × -10 × 3)

### 16. Máximo de Uns Consecutivos

**Descrição:** Em array com apenas 0s e 1s, retorne o máximo de 1s em sequência.

**Passo a Passo:**
1. Crie `contagem_atual = 0` e `contagem_maxima = 0`
2. Se encontrar 1, incremente `contagem_atual`
3. Se encontrar 0, atualize `contagem_maxima` e zere `contagem_atual`
4. Valide ao final

**Entrada:** `[1, 1, 0, 1, 1, 1]`
**Saída:** `3`

### 17. Mover Todos os Zeros para o Final (Fixação)

**Descrição:** Use apenas swaps para colocar zeros ao fim, mantendo ordem dos demais.

**Passo a Passo:**
1. Use `ponteiro_zero` e `ponteiro_leitura`
2. `ponteiro_zero` guarda o índice do primeiro zero
3. Quando `ponteiro_leitura` encontra número diferente de zero, faça swap

**Entrada:** `[0, 1, 9, 8, 4, 0, 0, 2, 7, 0, 6, 0, 9]`
**Saída:** `[1, 9, 8, 4, 2, 7, 6, 9, 0, 0, 0, 0, 0]`

### 18. Array em Formato de Onda

**Descrição:** Organize o array obedecendo `a >= b <= c >= d <= e...`

**Passo a Passo:**
1. Ordene o array em ordem crescente
2. Crie um laço pulando de dois em dois elementos
3. Troque cada elemento com o próximo

**Entrada:** `[1, 2, 3, 4, 5]`
**Saída:** `[2, 1, 4, 3, 5]`

### 19. Somar Um

**Descrição:** Um array representa um número inteiro (cada índice é um dígito). Some 1 e retorne atualizado.

**Passo a Passo:**
1. Percorra de trás para frente
2. Adicione 1 ao dígito; se < 10, termine
3. Se = 10, transforme em 0 e continue (transporte)
4. Se o laço terminar, crie array com uma posição extra, começando com 1

**Entrada:** `[1, 2, 3]`
**Saída:** `[1, 2, 4]`

### 20. Comprar e Vender Ações – Uma Transação

**Descrição:** Escolha um dia para comprar e outro no futuro para vender; retorne o lucro máximo.

**Passo a Passo:**
1. Crie `preco_minimo_visto = infinito` e `lucro_maximo = 0`
2. Itere; se o preço for menor, atualize `preco_minimo_visto`
3. Caso contrário, calcule lucro e atualize `lucro_maximo`

**Entrada:** `[7, 1, 5, 3, 6, 4]`
**Saída:** `5` (compre a 1, venda a 6)

### 21. Comprar e Vender Ações – Múltiplas Transações

**Descrição:** Faça quantas compras/vendas quiser para maximizar lucro total.

**Passo a Passo:**
1. Defina `lucro_total = 0`
2. Percorra a partir do dia 1
3. Se preço atual > anterior, adicione a diferença em `lucro_total`

**Entrada:** `[7, 1, 5, 3, 6, 4]`
**Saída:** `7` (compre a 1, venda a 5 [+4]; compre a 3, venda a 6 [+3])

### 22. Remover Elementos Duplicados (Ordenado)

**Descrição:** Remova duplicatas em array ordenado, deixando uma ocorrência de cada valor.

**Passo a Passo:**
1. Use dois ponteiros (rápido e lento)
2. O lento dita local de inserção, o rápido busca números novos

**Entrada:** `[0, 0, 1, 1, 1, 2, 2, 3, 3, 4]`
**Saída:** `[0, 1, 2, 3, 4]`

### 23. Alternar Positivos e Negativos

**Descrição:** Intercale números positivos e negativos mantendo ordem original, com O(1) de espaço.

**Passo a Passo:**
1. Encontre o primeiro número fora de lugar
2. Encontre o próximo número de sinal oposto
3. Rotacione o trecho entre eles

**Entrada:** `[1, 2, 3, -4, -1, 4]`
**Saída:** `[-4, 1, -1, 2, 3, 4]`

### 24. Elementos Líderes (Fixação)

**Descrição:** Localize todos os líderes que dominam elementos à sua direita.

**Passo a Passo:**
1. Percorra do último para o primeiro elemento
2. Se > máximo armazenado, substitua máximo, adicione à lista

**Entrada:** `[10, 4, 2, 4, 1]`
**Saída:** `[10, 4, 1]`

### 25. Elemento Faltante e Repetido

**Descrição:** Em array de tamanho N com números 1 a N, encontre qual está faltando e qual está repetido.

**Passo a Passo:**
1. Itere manipulando índices; converta valor para seu índice correspondente
2. Se o índice já for negativo, o número é repetido; senão, torne-o negativo
3. Na segunda varredura, índice positivo revela número faltante

**Entrada:** `[3, 1, 3]`
**Saída:** Repetido: 3, Faltante: 2

### 26. Intervalos de Números Faltantes

**Descrição:** Em array ordenado sem duplicatas, descubra intervalos "faltantes" entre o mínimo e limite superior.

**Passo a Passo:**
1. Defina início esperado (alvo X)
2. Itere; se valor > X, há intervalo faltante de X até valor-1
3. Crie string do intervalo e atualize X

**Entrada:** `[0, 1, 3, 50, 75]`, limites 0-99
**Saída:** `["2", "4->49", "51->74", "76->99"]`

### 27. Soma de Todos os Subarrays

**Descrição:** Calcule a soma de todos os subarrays possíveis eficientemente.

**Passo a Passo:**
1. Para cada elemento A[i], calcule em quantos subarrays participa: `(i+1) × (tamanho-i)`
2. Multiplique o elemento por essa quantidade
3. Some ao total final

**Entrada:** `[1, 2, 3]`
**Saída:** `20`

</details>

<details>
<summary><strong>🟠 Nível 2 - Médio</strong></summary>

### 28. Próxima Permutação

**Descrição:** Encontre o próximo arranjo maior em ordem lexicográfica.

**Passo a Passo:**
1. Do fim, encontre o primeiro declínio `A[i] < A[i+1]`
2. Se não encontrar, reverta todo o array
3. Se encontrar A[i], procure o menor elemento > A[i] (chamaremos A[j])
4. Troque A[i] e A[j]
5. Inverta a parte à direita de i

**Entrada:** `[1, 2, 3]`
**Saída:** `[1, 3, 2]`

### 29. Elemento Majoritário

**Descrição:** Encontre o elemento que aparece > N/2 vezes (Algoritmo de Moore, O(N) tempo, O(1) espaço).

**Passo a Passo:**
1. Escolha candidato inicial e `votos = 1`
2. Itere; se = candidato, `votos++`; senão `votos--`
3. Se votos = 0, novo candidato com `votos = 1`
4. Candidato final é o majoritário

**Entrada:** `[2, 2, 1, 1, 1, 2, 2]`
**Saída:** `2`

### 30. Elemento Majoritário II

**Descrição:** Encontre todos os elementos com > N/3 ocorrências.

**Passo a Passo:**
1. Podem existir até 2 candidatos válidos
2. Rastreie `candidato1`, `votos1`, `candidato2`, `votos2`
3. Varra contando votos; se não for nenhum com ambos tendo votos, desconte ambos
4. Confirme em segunda checagem

**Entrada:** `[3, 2, 3]`
**Saída:** `[3]`

### 31. Minimizar as Alturas II

**Descrição:** Dado array de alturas e valor K, some/subtraia K em cada torre. Minimize diferença máxima-mínima.

**Passo a Passo:**
1. Ordene o array
2. Salve diferença base: `array[n-1] - array[0]`
3. Itere; em cada ponto, calcule novo mín/máx considerando modificações
4. Atualize menor resultado

**Entrada:** Array `[1, 5, 8, 10]`, K = `2`
**Saída:** `5`

### 32. Soma Máxima de Subarray (Algoritmo de Kadane)

**Descrição:** Encontre a soma máxima contínua no array.

**Passo a Passo:**
1. `soma_atual = 0`, `maximo_global = -∞`
2. Percorra; `soma_atual += array[i]`
3. Se `soma_atual > maximo_global`, atualize máximo
4. Se `soma_atual < 0`, resete para 0

**Entrada:** `[-2, 1, -3, 4, -1, 2, 1, -5, 4]`
**Saída:** `6` (subarray `[4, -1, 2, 1]`)

### 33. Produto Máximo de Subarray

**Descrição:** Encontre o produto máximo contínuo (considere negativos multiplicando em positivos).

**Passo a Passo:**
1. Rastreie `max_produto_atual`, `min_produto_atual` e `resultado_final`
2. Se elemento negativo, troque max e min
3. `max_produto_atual = max(elemento, elemento × max_produto_atual)`
4. Atualize `resultado_final`

**Entrada:** `[2, 3, -2, 4]`
**Saída:** `6` (subarray `[2, 3]`)

### 34. Produto do Array Exceto o Próprio Elemento

**Descrição:** Gere array onde `resposta[i]` = produto de todos elementos exceto `array[i]`, sem divisão.

**Passo a Passo:**
1. Crie array de resultados
2. Primeiro laço: armazene produtos à esquerda (índice 0 inicia com 1)
3. Segundo laço (inverso): multiplique produtos à direita contra resultados

**Entrada:** `[1, 2, 3, 4]`
**Saída:** `[24, 12, 8, 6]`

### 35. Subarrays com Produto Menor que K

**Descrição:** Conte subarrays cujo produto é estritamente < K.

**Passo a Passo:**
1. Se K ≤ 1, retorne 0
2. Janela deslizante com `esquerda` e `direita`
3. Multiplique elemento à direita; enquanto produto ≥ K, divida à esquerda e avance
4. Adicione `(direita - esquerda + 1)` à contagem

**Entrada:** Array `[10, 5, 2, 6]`, K = `100`
**Saída:** `8`

### 36. Dividir em Três Segmentos de Soma Igual

**Descrição:** Verifique se é possível dividir o array em 3 partes contínuas com somas iguais.

**Passo a Passo:**
1. Calcule soma total; se não divisível por 3, impossível
2. Alvo = `soma_total / 3`
3. Itere rastreando `soma_atual`; se = alvo, incremente contador e resete
4. Verifique se encontrou 3 pedaços

**Entrada:** `[0, 2, 1, -6, 6, -1, 2]`
**Saída:** `True`

### 37. Máximo de Uns Consecutivos Após Inverter Zeros

**Descrição:** Em array binário, converta até K zeros em uns; encontre maior segmento de 1s.

**Passo a Passo:**
1. Janela deslizante com `i` e `j` em 0
2. Expanda `j`; se encontrar 0, decremente K
3. Enquanto K < 0, avance `i`; se passar 0, incremente K
4. Meça cada janela válida

**Entrada:** Array `[1, 1, 1, 0, 0, 0, 1, 1, 1, 1, 0]`, K = `2`
**Saída:** `6`

### 38. Último Momento Antes das Formigas Caírem da Prancha

**Descrição:** Formigas em prancha 0 a N, caminhando L (esquerda) ou R (direita). Ao baterem, invertem direção. Qual o último momento de queda?

**Passo a Passo:**
1. Formiga L cai em tempo = sua distância de origem
2. Formiga R cai em tempo = N - posição
3. Último a cair = máximo entre todos

**Entrada:** Tamanho=4, L=[4,3], R=[0,1]
**Saída:** `4`

### 39. Encontrar o 0 com 1s Mais Distantes

**Descrição:** Em array de poltronas (0=livre, 1=ocupada), ache o 0 com máxima distância da pessoa mais próxima.

**Passo a Passo:**
1. Identifique grupos contínuos de zeros entre 1s
2. Para zeros no meio, distância = tamanho_grupo / 2
3. Para extremidades, distância = tamanho completo
4. Retorne maior

**Entrada:** `[1, 0, 0, 0, 1, 0, 1]`
**Saída:** `2`

### 40. Interseção de Listas de Intervalos

**Descrição:** Dadas duas listas de intervalos ordenados, retorne as partes em comum.

**Passo a Passo:**
1. Use dois ponteiros `i=0` e `j=0`
2. Início interseção = máximo dos inícios; fim = mínimo dos fins
3. Se `inicio <= fim`, registre intervalo
4. Descarte o que termina primeiro

**Entrada:** A=`[[0,2],[5,10]]`, B=`[[1,5],[8,12]]`
**Saída:** `[[1,2],[5,5],[8,10]]`

### 41. Reorganizar Elementos por Sinal

**Descrição:** Intercale positivos e negativos respeitando ordem original, iniciando por positivo.

**Passo a Passo:**
1. Crie array resposta
2. `indice_pos = 0`, `indice_neg = 1`
3. Positivos → `indice_pos`, incremente 2; negativos → `indice_neg`, incremente 2

**Entrada:** `[3, 1, -2, -5, 2, -4]`
**Saída:** `[3, -2, 1, -5, 2, -4]`

### 42. Agendador de Reuniões para Duas Pessoas

**Descrição:** Dada disponibilidade de duas pessoas e duração necessária, retorne primeiro horário viável.

**Passo a Passo:**
1. Ordene horários livres se necessário
2. Use dois ponteiros procurar interseções
3. Se tamanho interseção ≥ duração, retorne `[inicio, inicio+duracao]`

**Entrada:** P1=`[[10,50],[60,120]]`, P2=`[[0,15],[60,70]]`, duração=8
**Saída:** `[60, 68]`

### 43. Maior Subarray Montanha

**Descrição:** Encontre maior subarray padrão "montanha" (sobe até pico, desce estritamente; mínimo 3).

**Passo a Passo:**
1. Identifique picos: `A[i-1] < A[i] > A[i+1]`
2. Para cada pico, expanda contagem à esquerda e direita
3. Registre maior tamanho

**Entrada:** `[2, 1, 4, 7, 3, 2, 5]`
**Saída:** `5` (subarray `[1, 4, 7, 3, 2]`)

### 44. Transformar e Ordenar Array

**Descrição:** Aplique `A*x² + B*x + C` a array ordenado e retorne resultado ordenado eficientemente.

**Passo a Passo:**
1. Resultados formam parábola (crescem das pontas para meio ou vice-versa)
2. Use dois ponteiros nas extremidades
3. Compare qual é maior/menor e preencha novo array

**Entrada:** Array `[-4,-2,2,4]`, a=1, b=3, c=5
**Saída:** `[3, 9, 15, 33]`

### 45. Mínimo de Trocas para Agrupar Todos os Uns

**Descrição:** Determine quantos swaps para aglomerar todos os 1s em bloco íntegro.

**Passo a Passo:**
1. Conte total de 1s (janela tamanho W)
2. Itere com janela W contando zeros internos
3. Menores zeros = mínimas trocas necessárias

**Entrada:** `[1, 0, 1, 0, 1, 1]`
**Saída:** `1`

### 46. Movimentos Mínimos para Igualar o Array

**Descrição:** Incremente/decremente elementos para igualá-los; minimize movimentos totais.

**Passo a Passo:**
1. Converja para valor mediano (mínimo desperdício)
2. Ordene; identifique mediana em N/2
3. Some diferenças absolutas até mediana

**Entrada:** `[1, 2, 3]`
**Saída:** `2` (convergência em 2; 1 sobe 1, 3 desce 1)

### 47. Índices Mínimos para Igualar Somas Pares e Ímpares

**Descrição:** Conte formas de remover 1 elemento deixando somas de índices pares = ímpares.

**Passo a Passo:**
1. Calcule métricas de pré-somas e pós-somas (pares/ímpares)
2. Para cada exclusão, observe shift de paridade
3. Verifique igualdade

**Entrada:** `[2, 1, 6, 4]`
**Saída:** `1`

</details>

<details>
<summary><strong>🔴 Nível 3 - Difícil</strong></summary>

### 48. Retenção de Água da Chuva

**Descrição:** Array mapeia terreno; compute água empoçada (unidades cúbicas).

**Passo a Passo:**
1. Água por barra i = `min(MaxEsq, MaxDir) - AlturaAtual`
2. Dois ponteiros de fora para dentro
3. Rastreie `max_esq` e `max_dir`; colete volumes

**Entrada:** `[0, 1, 0, 2, 1, 0, 1, 3, 2, 1, 2, 1]`
**Saída:** `6`

### 49. Soma Máxima de Subarray Circular

**Descrição:** Encontre soma máxima em array circular (fim conecta ao início).

**Passo a Passo:**
1. Caso linear: soma máxima normal (Kadane)
2. Caso circular: inverta sinais, encontre mínima (Kadane), subtraia da soma total
3. Se todos negativos, ignore circular
4. Retorne maior

**Entrada:** `[5, -3, 5]`
**Saída:** `10` (fim+início: 5+5)

### 50. Menor Número Positivo Faltante

**Descrição:** Array desordenado com negativos; retorne menor positivo ausente (O(1) espaço).

**Passo a Passo:**
1. Troca cíclica: número correto em índice i seria i+1
2. Varra fazendo trocas de elementos 1 a N
3. Segunda varredura: primeiro índice onde conteúdo ≠ i+1 revela faltante

**Entrada:** `[3, 4, -1, 1]`
**Saída:** `2`

### 51. Jogo dos Pulos (Mínimo de Pulos)

**Descrição:** Cada valor = alcance máximo de pulo. Encontre mínimo de pulos para chegar ao fim.

**Passo a Passo:**
1. `pulos=0`, `alcance_atual=0`, `alcance_maximo_futuro=0`
2. Percorra atualizando `alcance_maximo_futuro`
3. Ao atingir fim de `alcance_atual`, pule (`pulos++`) e atualize para `alcance_maximo_futuro`

**Entrada:** `[2, 3, 1, 1, 4]`
**Saída:** `2`

### 52. Soma de Subsequência Mais Próxima

**Descrição:** Selecione elemento para soma mais próxima do alvo.

**Passo a Passo:**
1. "Meet in the middle": divida array, gere todas somas de cada metade
2. Ordene somas da direita
3. Para cada esquerda, busca binária encontra melhor complemento

**Entrada:** Array `[5,-7,3,5]`, alvo 6
**Saída:** `0`

### 53. Menor Soma Não Representável

**Descrição:** Encontre menor inteiro positivo **não** expressível como soma de subconjunto.

**Passo a Passo:**
1. `representa_max = 1`
2. Itere array ordenado; se elemento > `representa_max`, retorne `representa_max`
3. Senão, `representa_max += elemento_atual`

**Entrada:** `[1, 3, 6, 10, 11, 15]`
**Saída:** `2`

### 54. Menor Intervalo Contendo Elementos de K Listas

**Descrição:** Construa intervalo mínimo contendo elemento de cada lista.

**Passo a Passo:**
1. Min-Heap com primeiros elementos; rastreie máximo
2. Extraia mínima, atualize intervalo se menor
3. Insira próximo da mesma lista do extraído; recoloque heap

**Entrada:** `[[4,10,15,24,26],[0,9,12,20],[5,18,22,30]]`
**Saída:** `[20, 24]`

### 55. Contar Subarrays com K Elementos Distintos

**Descrição:** Conte subarrays com exatamente K elementos únicos.

**Passo a Passo:**
1. `AtMost(K) = subarrays com ≤ K distintos - subarrays com ≤ K-1 distintos`
2. Sliding window flexível com mapa rastreando distâncias
3. Contabilize cada janela válida

**Entrada:** Array `[1, 2, 1, 2, 3]`, K=2
**Saída:** `7`

### 56. Próximo Palíndromo Menor

**Descrição:** Dado número em array (dígitos), encontre numeração palíndromo descendente.

**Passo a Passo:**
1. Separe hemisférios numerais
2. Espelhe lado esquerdo na direita
3. Se > original, pronto; senão, incremente pivot central e espelhe

**Entrada:** `[1, 2, 5, 3, 2, 2]`
**Saída:** `[1, 2, 5, 5, 2, 1]`

### 57. Soma Máxima Entre Todas as Rotações

**Descrição:** Compute `i * Array[i]` máxima em **todas** rotações, O(N).

**Passo a Passo:**
1. Base: `S0 = (0*A[0] + 1*A[1] + ...)`; `SomaV = soma total`
2. Cada rotação: `ProxSoma = SomaAnterior + SomaV - N * UltimoElemento`
3. Rastreie máxima entre todas rotações

**Entrada:** `[8, 3, 1, 2]`
**Saída:** `29`

</details>

