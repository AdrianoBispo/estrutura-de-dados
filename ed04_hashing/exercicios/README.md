# Lista de Exercícios - Estruturas de Dados Hashing

Este documento contém uma curadoria de problemas focados em lógica de programação utilizando Estruturas de Dados Baseadas em Hashing (Tabelas Hash, Dicionários, Mapas ou Conjuntos). O objetivo é fornecer uma base sólida, detalhando o comportamento esperado e a lógica passo a passo para resolver cada questão na sua linguagem de programação favorita (C, C++, Java, Python, Javascript, etc.).

<details>
<summary>🟢 Nível 1 - Fácil</summary>

#### 1. Verificar Subconjunto

**Descrição:** Determinar se todos os elementos de um array pertencem a outro array maior.

**Passo a passo:**
1. Insira todos os elementos do array principal em uma Tabela Hash (Set).
2. Percorra o array candidato a subconjunto.
3. Se algum elemento não for encontrado na Tabela Hash, retorne Falso. Se todos forem encontrados, retorne Verdadeiro.

**Entrada:**
```
arr1 = [11, 1, 13, 21, 3, 7]
arr2 = [11, 3, 7, 1]
```

**Saída:**
```
Verdadeiro
```

#### 2. Verificar Conjuntos Disjuntos

**Descrição:** Checar se dois conjuntos não possuem nenhum elemento em comum.

**Passo a passo:**
1. Crie um Hash Set com todos os elementos do primeiro array.
2. Itere pelo segundo array.
3. Se qualquer elemento do segundo array existir no Hash Set, retorne Falso. Caso contrário, retorne Verdadeiro.

**Entrada:**
```
set1 = [12, 34, 11, 9, 3]
set2 = [2, 1, 5]
```

**Saída:**
```
Verdadeiro
```

#### 3. Verificar se Arrays são Iguais

**Descrição:** Verificar se dois arrays contêm os mesmos elementos com a mesma frequência, independente da ordem.

**Passo a passo:**
1. Verifique se possuem o mesmo tamanho. Se não, retorne Falso.
2. Use um Hash Map para contar a frequência de cada elemento do primeiro array.
3. Percorra o segundo array subtraindo a frequência no mapa. Se um elemento não existir ou a contagem ficar negativa, retorne Falso.

**Entrada:**
```
A = [1, 2, 5, 4, 0]
B = [2, 4, 5, 0, 1]
```

**Saída:**
```
Verdadeiro
```

#### 4. Fizz Buzz

**Descrição:** Problema clássico mapeando divisores para strings específicas.

**Passo a passo:**
1. Crie um Mapa relacionando divisores às strings (ex: `{3: "Fizz", 5: "Buzz"}`).
2. Itere de 1 a N. Para cada número, verifique as chaves do Mapa. Se for divisível, concatene a string. Se não for divisível por nenhum, retorne o próprio número.

**Entrada:**
```
N = 5
```

**Saída:**
```
["1", "2", "Fizz", "4", "Buzz"]
```

#### 5. Distância Máxima entre Duas Ocorrências

**Descrição:** Encontrar a maior distância (diferença de índices) entre duas aparições do mesmo elemento no array.

**Passo a passo:**
1. Crie um Hash Map onde a chave é o elemento e o valor é o índice da sua **primeira** aparição.
2. Itere pelo array. Se o elemento já estiver no mapa, calcule a distância `(índice atual - índice armazenado)`.
3. Mantenha o registro da maior distância encontrada.

**Entrada:**
```
arr = [3, 2, 1, 2, 1, 4, 5, 8, 6, 7, 4, 2]
```

**Saída:**
```
10 (referente ao número 2)
```

#### 6. Duplicata dentro de uma Distância K

**Descrição:** Checar se existe algum valor repetido em um array a uma distância máxima de `k` índices.

**Passo a passo:**
1. Utilize um Hash Map para guardar o último índice visto de cada elemento.
2. Percorra o array. Se o elemento já está no mapa e a diferença entre o índice atual e o índice do mapa for `<= k`, retorne Verdadeiro.
3. Caso contrário, atualize o índice do elemento no mapa.

**Entrada:**
```
arr = [1, 2, 3, 1, 4, 5]
k = 3
```

**Saída:**
```
Verdadeiro
```

#### 7. Interseção de Dois Arrays

**Descrição:** Encontrar elementos que estão presentes simultaneamente em dois arrays.

**Passo a passo:**
1. Insira todos os elementos do primeiro array em um Hash Set.
2. Itere pelo segundo array. Se o elemento existir no Set, adicione-o à lista de resultados e remova-o do Set (para evitar duplicatas no resultado).

**Entrada:**
```
A = [1, 2, 2, 1]
B = [2, 2]
```

**Saída:**
```
[2]
```

#### 8. União de Dois Arrays

**Descrição:** Retornar todos os elementos distintos presentes em ambos os arrays.

**Passo a passo:**
1. Crie um Hash Set.
2. Itere pelo primeiro array adicionando seus elementos ao Set.
3. Itere pelo segundo array adicionando seus elementos. O Set ignorará automaticamente os duplicados.

**Entrada:**
```
A = [1, 2, 3]
B = [1, 2, 3, 4, 5]
```

**Saída:**
```
[1, 2, 3, 4, 5]
```

#### 9. Elemento Mais Frequente

**Descrição:** Descobrir qual elemento aparece mais vezes em um array.

**Passo a passo:**
1. Crie um Hash Map para rastrear a frequência de cada elemento (Chave: elemento, Valor: contagem).
2. Encontre a chave que possui o maior valor de contagem no mapa.

**Entrada:**
```
arr = [1, 3, 2, 1, 4, 1]
```

**Saída:**
```
1
```

#### 10. 2 Sum - Encontrar se existe algum par

**Descrição:** Identificar se existem dois números no array cuja soma seja um alvo especificado.

**Passo a passo:**
1. Crie um Hash Set vazio.
2. Percorra o array. Para cada número, calcule `diferença = alvo - numero`.
3. Se a `diferença` existir no Set, o par existe (retorne Verdadeiro). Se não, adicione o `numero` ao Set.

**Entrada:**
```
arr = [0, -1, 2, -3, 1]
alvo = -2
```

**Saída:**
```
Verdadeiro (Par: 1 e -3)
```

#### 11. 2 Sum - Contar Pares

**Descrição:** Contar quantos pares somam um valor exato.

**Passo a passo:**
1. Crie um Hash Map para guardar as frequências dos números.
2. Para cada elemento, calcule `complemento = alvo - elemento`. Verifique quantas vezes o complemento aparece no mapa e some ao contador total.
3. Adicione a ocorrência do elemento atual no mapa.

**Entrada:**
```
arr = [1, 5, 7, -1, 5]
alvo = 6
```

**Saída:**
```
3
```

#### 12. Contar Pares com Diferença Dada

**Descrição:** Encontrar o número de pares cuja diferença absoluta é igual a K.

**Passo a passo:**
1. Crie um Hash Map para armazenar as frequências dos números do array.
2. Percorra o mapa. Para cada chave `x`, verifique se `x + K` existe no mapa.
3. Se sim, multiplique a frequência de `x` pela de `x + K` e some ao resultado.

**Entrada:**
```
arr = [1, 5, 3, 4, 2]
K = 3
```

**Saída:**
```
2 (Pares: {1,4} e {2,5})
```

#### 13. Único Elemento Repetido de 1 a n-1

**Descrição:** Em um array de tamanho `n` contendo números de 1 a `n-1`, encontrar o único número que se repete.

**Passo a passo:**
1. Crie um Hash Set.
2. Percorra o array adicionando os elementos.
3. Se você tentar adicionar um elemento que já está no Set, esse é o número repetido.

**Entrada:**
```
arr = [1, 3, 2, 3, 4]
```

**Saída:**
```
3
```

#### 14. Elementos Faltantes de um Intervalo

**Descrição:** Dado um array e um intervalo `[low, high]`, encontrar os números desse intervalo que não estão no array.

**Passo a passo:**
1. Insira todos os elementos do array em um Hash Set.
2. Faça um loop de `low` até `high`.
3. Se o número não estiver no Set, adicione-o ao resultado.

**Entrada:**
```
arr = [10, 12, 11, 15]
low = 10
high = 15
```

**Saída:**
```
[13, 14]
```

#### 15. Elementos Faltantes do Mínimo ao Máximo do Array

**Descrição:** Descobrir quais elementos faltam para completar o intervalo contínuo entre o menor e o maior número do array.

**Passo a passo:**
1. Encontre o mínimo e o máximo do array.
2. Adicione todos os elementos do array a um Hash Set.
3. Itere do mínimo ao máximo, verificando quem não está no Set.

**Entrada:**
```
arr = [3, 5, 8]
```

**Saída:**
```
[4, 6, 7]
```

#### 16. Mínimo de Subconjuntos com Elementos Distintos

**Descrição:** Dividir o array no menor número de subconjuntos possíveis onde cada subconjunto possui apenas elementos distintos.

**Passo a passo:**
1. O número de subconjuntos necessários é igual à frequência do elemento que mais se repete.
2. Use um Hash Map para mapear a contagem de frequências e retorne o valor máximo.

**Entrada:**
```
arr = [1, 2, 3, 4, 1, 2, 1]
```

**Saída:**
```
3 (O número 1 repete 3 vezes)
```

#### 17. Remoções Mínimas para Nenhum Elemento Comum

**Descrição:** Número mínimo de remoções em dois arrays para que eles fiquem sem nenhuma interseção.

**Passo a passo:**
1. Adicione os elementos do array 1 em um Hash Set.
2. Itere pelo array 2. Para cada elemento, se ele existir no Set, incremente o contador de remoções.

**Entrada:**
```
A = [1, 2, 3, 4]
B = [2, 3, 4, 5, 8]
```

**Saída:**
```
3
```

#### 18. Máximo de Pontos na Mesma Linha

**Descrição:** Dada uma lista de pontos 2D, encontrar o número máximo de pontos que colidem numa mesma reta.

**Passo a passo:**
1. Para cada ponto, calcule a inclinação (slope) em relação a todos os outros pontos.
2. Use um Hash Map `(inclinação -> contagem)` para registrar a quantidade de pontos com a mesma inclinação a partir daquele ponto âncora.
3. O resultado global será o máximo encontrado neste mapa mais 1 (o próprio ponto).

**Entrada:**
```
pontos = [[1,1],[2,2],[3,3]]
```

**Saída:**
```
3
```

</details>

<details>
<summary>🟠 Nível 2 - Médio</summary>

#### 1. Soma de Pares Divisíveis por k

**Descrição:** Checar se um array pode ser totalmente dividido em pares cuja soma é divisível por `k`.

**Passo a passo:**
1. Crie um Hash Map de contagem de restos (`num % k`).
2. Para cada resto `R`, verifique se a frequência de `R` é igual à frequência do complemento `k - R`.
3. Casos especiais: se `R == 0` ou `2 * R == k`, a frequência deve ser par.

**Entrada:**
```
arr = [9, 5, 7, 3]
k = 6
```

**Saída:**
```
Verdadeiro (Pares: {9, 3} e {5, 7})
```

#### 2. Subarray com Soma Divisível por k

**Descrição:** Encontrar o comprimento do maior subarray cuja soma seja divisível por `k`.

**Passo a passo:**
1. Mantenha a `soma_prefixo` atual. O resto atual é `soma_prefixo % k` (ajuste para restos negativos).
2. Use um Hash Map para armazenar `(resto, primeiro_índice_encontrado)`.
3. Se você vir um resto que já está no mapa, o subarray entre esse índice passado e o atual é divisível por `k`. Calcule o tamanho e guarde o máximo.

**Entrada:**
```
arr = [2, 7, 6, 1, 4, 5]
k = 3
```

**Saída:**
```
4 (Subarray: [7, 6, 1, 4])
```

#### 3. 3 Sum - Contar todos os Tripletos com Soma Dada

**Descrição:** Contar tripletos no array que somam um alvo específico.

**Passo a passo:**
1. Otimize fixando o primeiro elemento com um loop.
2. O problema se reduz a um "2 Sum". Utilize um Hash Map interno ou técnica de dois ponteiros para encontrar os dois elementos restantes.

**Entrada:**
```
arr = [1, 5, 3, 2]
alvo = 6
```

**Saída:**
```
1 (O tripleto é 1, 3, 2)
```

#### 4. 3 Sum - Encontrar todos os Tripletos com Soma Zero

**Descrição:** Encontrar todas as trincas únicas que dão soma igual a zero.

**Passo a passo:**
1. Ordene o array.
2. Fixe o elemento `i`. Use a lógica de um Hash Map (para rastrear complementos vistos) no restante do array para procurar os outros dois elementos que somem `-arr[i]`.
3. Use um Hash Set de tuplas ordenadas para evitar adicionar trincas repetidas.

**Entrada:**
```
arr = [-1, 0, 1, 2, -1, -4]
```

**Saída:**
```
[[-1, -1, 2], [-1, 0, 1]]
```

#### 5. Itinerário a partir de uma Lista de Passagens

**Descrição:** Dado um dicionário de passagens (`Origem -> Destino`), reconstruir a rota completa da viagem.

**Passo a passo:**
1. Guarde todas as passagens num Hash Map.
2. Crie um segundo Hash Map reverso (`Destino -> Origem`).
3. Encontre a cidade de partida (aquela que existe como Chave no mapa normal, mas não no reverso).
4. Siga as chaves no mapa original reconstruindo a rota em ordem.

**Entrada:**
```
{"A": "C", "C": "D", "B": "A"}
```

**Saída:**
```
B -> A -> C -> D
```

#### 6. Maior Subarray com Maioria Maior que K

**Descrição:** Encontrar o maior subarray onde a quantidade de elementos maiores que `k` é estritamente maior que a quantidade do resto.

**Passo a passo:**
1. Trate o array como `1` se `num > k`, e `-1` caso contrário.
2. O problema se torna encontrar o maior subarray com soma `> 0`.
3. Use `soma_prefixo` e um Hash Map para guardar índices de somas prefixadas.

**Entrada:**
```
arr = [2, 3, 4, 5]
k = 3
```

**Saída:**
```
3 (Subarray: [3, 4, 5])
```

#### 7. Número de Funcionários sob cada Gerente

**Descrição:** Dado um mapa Gerente-Funcionário, encontrar a contagem total de subordinados diretos e indiretos de cada um.

**Passo a passo:**
1. Crie uma lista de adjacência usando Hash Map (`Gerente -> Lista de Funcionários`).
2. Encontre o CEO (quem reporta a si mesmo ou não tem gerente).
3. Execute uma recursão (DFS) onde o número de funcionários de `X` é a soma recursiva dos funcionários reportados a `X`. Faça a memoização em um mapa de resultados.

**Entrada:**
```
{"A":"C", "B":"C", "C":"F", "D":"E", "E":"F", "F":"F"}
```

**Saída:**
```
{"A":0, "B":0, "C":2, "D":0, "E":1, "F":5}
```

#### 8. Maior Subarray com Soma 0

**Descrição:** Retornar o comprimento máximo de um subarray cujos elementos somam zero.

**Passo a passo:**
1. Variável `soma_prefixo` inicia em 0.
2. Hash Map guardará `(soma_prefixo -> primeiro_índice)`.
3. Se a `soma_prefixo` já existe no mapa, um subarray com soma 0 foi encontrado. Atualize o comprimento máximo.

**Entrada:**
```
arr = [15, -2, 2, -8, 1, 7, 10, 23]
```

**Saída:**
```
5 (Subarray: [-2, 2, -8, 1, 7])
```

#### 9. Subarray com Soma Dada

**Descrição:** Encontrar se existe um subarray contíguo que soma um valor especificado.

**Passo a passo:**
1. Crie um Hash Map onde a chave é a soma prefixada atual e o valor é o índice.
2. Ao iterar, calcule a `soma_prefixo`. Se `(soma_prefixo - soma_alvo)` já estiver no mapa, você encontrou o limite inicial do subarray.

**Entrada:**
```
arr = [10, 2, -2, -20, 10]
alvo = -10
```

**Saída:**
```
Soma encontrada entre os índices 0 e 3
```

#### 10. Maior Subsequência Consecutiva

**Descrição:** Encontrar o comprimento da maior sequência de números consecutivos (ex: 1, 2, 3, 4).

**Passo a passo:**
1. Insira todos os elementos num Hash Set.
2. Para cada elemento `x`, se `x - 1` não estiver no Set, significa que `x` é o início de uma sequência.
3. Se for o início, faça um loop verificando `x+1`, `x+2`, etc., até a cadeia quebrar, e atualize o valor máximo.

**Entrada:**
```
arr = [100, 4, 200, 1, 3, 2]
```

**Saída:**
```
4 (Sequência: 1, 2, 3, 4)
```

#### 11. Maior Subconjunto de Fibonacci

**Descrição:** Filtrar o array e retornar apenas a subsequência composta unicamente por números de Fibonacci.

**Passo a passo:**
1. Descubra o maior número no array.
2. Pré-compute a sequência de Fibonacci até esse valor máximo e coloque os números num Hash Set.
3. Filtre o array original: mantenha o elemento somente se ele estiver presente no Set.

**Entrada:**
```
arr = [1, 4, 3, 9, 10, 13, 7]
```

**Saída:**
```
[1, 3, 13]
```

#### 12. Particionamento de Subconjuntos Consecutivos

**Descrição:** Contar o número mínimo de partições necessárias para dividir os elementos do array em sequências consecutivas puras.

**Passo a passo:**
1. Use um Hash Map para a frequência dos elementos.
2. Simule a criação de grupos lógicos: priorize encaixar um elemento numa sequência vizinha existente. Caso não possa, inicie um novo subconjunto.

**Entrada:**
```
arr = [1, 2, 3, 5, 6]
```

**Saída:**
```
2 (Subconjuntos: {1,2,3} e {5,6})
```

#### 13. Elementos Distintos em cada Janela de Tamanho k

**Descrição:** Array com uma janela deslizante de tamanho `k`. Imprimir a quantidade de números distintos a cada passo da janela.

**Passo a passo:**
1. Crie um Hash Map. Insira a frequência dos primeiros `k` elementos. Imprima o tamanho do mapa.
2. Para os demais passos, diminua em 1 a contagem do elemento que sai da janela. Se ficar 0, remova do mapa.
3. Adicione o novo elemento que entra na janela ao mapa. O tamanho das chaves do mapa é a resposta.

**Entrada:**
```
arr = [1, 2, 1, 3, 4, 2, 3]
k = 4
```

**Saída:**
```
[3, 4, 4, 3]
```

#### 14. Inserir, Deletar, Buscar e Obter Aleatório (O(1))

**Descrição:** Projetar uma estrutura de dados que faz operações `insert`, `remove`, `search` e `getRandom` em tempo constante médio O(1).

**Passo a passo:**
1. Use um array tradicional aliado a um Hash Map `(Valor -> Índice_no_Array)`.
2. **Deletar:** Pegue o índice pelo mapa. Troque o elemento atual com o _último_ elemento do array. Atualize o mapa para este "último elemento", remova o final do array (pop) e exclua a chave do mapa.
3. **GetRandom:** Puxe um índice aleatório do array base (tempo O(1)).

#### 15. Inserções Mínimas para Permutação de Palíndromo

**Descrição:** Qual o mínimo de letras que devemos adicionar à string para que ela possua alguma permutação que forme um palíndromo?

**Passo a passo:**
1. Conte as frequências dos caracteres em um Hash Map.
2. Conte quantos caracteres têm frequência ímpar.
3. Se `contagem_impar > 1`, as inserções mínimas são `contagem_impar - 1`. Caso contrário, é 0.

**Entrada:**
```
str = "abcde"
```

**Saída:**
```
4 (ex: abcde -> abcdcba)
```

#### 16. Menor Subarray com K Números Distintos

**Descrição:** Achar o subarray de menor comprimento que contenha exatamente `k` elementos únicos.

**Passo a passo:**
1. Use técnica de Dois Ponteiros (Sliding Window) associada a um Hash Map para guardar as contagens.
2. Avance o ponteiro direito adicionando no mapa até ter `k` chaves distintas.
3. Tente encolher a janela pela esquerda o máximo possível enquanto mantiver os `k` distintos para registrar a menor largura possível.

**Entrada:**
```
arr = [1, 1, 2, 2, 3, 3, 4, 5]
k = 3
```

**Saída:**
```
[2, 3, 3, 4] (Tamanho 4)
```

#### 17. Todos os pares (a, b) em um array tal que a % b = k

**Descrição:** Encontrar pares onde o resto da divisão entre eles resulte num `k` específico.

**Passo a passo:**
1. Encontre frequências de elementos em um Hash Map.
2. Todo número `b` precisa ser divisor de `a - k` (e `b > k`).
3. Para cada elemento `a`, encontre divisores de `a - k` usando fatoração e cheque no mapa quantos `b` adequados existem.

**Entrada:**
```
arr = [2, 3, 5, 4, 7]
k = 2
```

**Saída:**
```
4 (Pares: (2,3), (5,3), (2,4), (2,7))
```

#### 18. Agrupar Palavras com o Mesmo Conjunto de Caracteres

**Descrição:** Agrupar palavras que são formadas exatamente pelas mesmas letras (ex: 'may' e 'yam').

**Passo a passo:**
1. Para cada string, ordene os caracteres e use isso como chave (ou crie um Hash Set das letras).
2. O Hash Map usará essa assinatura ordenada como chave e uma Lista de palavras originais como valor.

**Entrada:**
```
["may", "student", "students", "dog", "studentssess", "god", "cat", "act", "tab", "bat", "flow", "wolf", "lambs", "amy", "yam", "balms", "looped", "poodle"]
```

**Saída:**
```
[["may", "amy", "yam"], ["dog", "god"], ...]
```

#### 19. K-ésimo Elemento Distinto (ou Não Repetido)

**Descrição:** Obter o `k`-ésimo elemento do array que apareceu apenas uma vez (com base na ordem de chegada).

**Passo a passo:**
1. Mapeie a frequência das chaves com um Hash Map (Linked Hash Map é excelente pois guarda a ordem de inserção).
2. Itere pelo array original (ou pelas chaves do Linked Map).
3. Conte os elementos cuja frequência é igual a 1 e, quando chegar em `k`, retorne-o.

**Entrada:**
```
arr = [1, 2, 1, 3, 4, 2]
k = 2
```

**Saída:**
```
4
```

</details>

<details>
<summary>🔴 Nível 3 - Difícil</summary>

#### 1. Representar Fração como String

**Descrição:** Dado o numerador e denominador, retornar a representação decimal como string. Dígitos decimais periódicos devem estar entre parênteses.

**Passo a passo:**
1. Calcule a divisão inteira. Adicione a vírgula.
2. Trate o resto `(resto = numerador % denominador)`.
3. Use um Hash Map `(resto -> posição_na_string)`. Se o resto se repetir no loop de divisões subsequentes, encontramos a repetição periódica. Envolva em `()` usando o índice salvo.

**Entrada:**
```
Num = 1, Den = 3
```

**Saída:**
```
"0.(3)"
```

#### 2. 4 Sum - Contar Quadrúplos

**Descrição:** Contar número de tuplas de 4 elementos cujo somatório seja um valor estipulado.

**Passo a passo:**
1. Agrupar pares: crie um Hash Map com as somas das metades, ou seja, some cada par possível `(arr[i] + arr[j])`.
2. Itere num loop duplo `(arr[x] + arr[y])` garantindo a não sobreposição de índices, consultando `alvo - soma_atual` no Hash Map.

**Entrada:**
```
arr = [1, 5, 3, 1, 2, 10]
alvo = 20
```

**Saída:**
```
1
```

#### 3. 4 Sum - Encontrar todos os Quadrúplos

**Descrição:** Retornar os arrays literais com 4 elementos que chegam numa soma sem duplicar a resposta.

**Passo a passo:**
1. Ordene o array.
2. Faça dois laços for externos (`i` e `j`) fixando os dois primeiros valores.
3. Faça a busca com ponteiros ou Hash Set na fatia do array à direita de `j` visando os 2 valores finais. Para unicidade, trate pulando índices adjacentes iguais.

**Entrada:**
```
arr = [1, 0, -1, 0, -2, 2]
alvo = 0
```

**Saída:**
```
[[-2, -1, 1, 2], [-2, 0, 0, 2], [-1, 0, 0, 1]]
```

#### 4. 4 Sum - A partir de Quatro Arrays Ordenados

**Descrição:** Pegar exatamente um elemento de cada array de modo que a soma total seja X.

**Passo a passo:**
1. Crie todas as somas de pares entre Array 1 e Array 2 num Hash Map `(Soma -> Frequência)`.
2. Itere por todos os pares do Array 3 e Array 4.
3. Calcule `complemento = alvo - (elem_arr3 + elem_arr4)`. Se existir no Hash Map, some a frequência à resposta global.

**Entrada:**
```
A=[1, 2], B=[2, 3], C=[1, 2], D=[0, 1]
alvo = 5
```

**Saída:**
```
4 (Pares viáveis)
```

#### 5. Maior Subarray com Quantidades Iguais de 0s e 1s

**Descrição:** Achar o comprimento máximo de um subarray onde o nº de `0`s seja igual ao de `1`s.

**Passo a passo:**
1. Substitua os zeros por `-1`.
2. Trate o problema igual ao "Maior Subarray com Soma 0".
3. Acumule prefixos e jogue no Hash Map de primeira ocorrência para tirar a distância máxima quando a soma der zero.

**Entrada:**
```
arr = [1, 0, 1, 1, 1, 0, 0]
```

**Saída:**
```
6 (Do índice 1 ao 6)
```

#### 6. Maior Extensão de Soma Comum entre Dois Arrays Binários

**Descrição:** Dados dois arrays binários do mesmo tamanho, achar a maior extensão do subarray comum contíguo onde suas somas são iguais.

**Passo a passo:**
1. Crie um array auxiliar preenchido com as diferenças locais: `diff[i] = arr1[i] - arr2[i]`.
2. Encontre o maior subarray nesse array `diff` cuja soma seja igual a 0. Aplique o uso do Hash Map de somas prefixadas.

**Entrada:**
```
arr1 = [0, 1, 0, 0, 0, 0]
arr2 = [1, 0, 1, 0, 0, 1]
```

**Saída:**
```
4
```

#### 7. Consultas de Substring Palíndroma

**Descrição:** Dada uma string e múltiplas consultas de limites `[L, R]`, responder eficientemente (tempo sub-linear após pré-processamento) se a substring dada é um palíndromo.

**Passo a passo:**
1. Utilize a lógica de Hashing (String Hashing / Rabin-Karp prefix hashing).
2. Pré-compute arrays de hashes normais e hashes reversos da string inteira.
3. Para checar limites em tempo O(1), pegue o valor de Hash correspondente no recorte `[L, R]` das direções normal e reversa. Se baterem, é palíndromo.

**Entrada:**
```
str = "abaaabaa"
Consultas = [[0, 2], [1, 5]]
```

**Saída:**
```
[Verdadeiro, Falso]
```

#### 8. Subarrays possuindo Contagem de Elementos Distintos

**Descrição:** Calcular quantos subarrays possuem o mesmo número de elementos únicos contidos no array todo.

**Passo a passo:**
1. Use um Hash Set no array total para saber o número total de únicos (`k`).
2. Utilize dois ponteiros (Janela Deslizante) e um Hash Map para contagem.
3. Expanda à direita. Se atingir `k` únicos no mapa, então todo subarray fechando dali em diante até o fim do array é válido. Encolha pela esquerda e repita.

**Entrada:**
```
arr = [2, 1, 3, 2, 3]
```

**Saída:**
```
5
```

#### 9. Array Máximo a partir de Dois Arrays

**Descrição:** De dois arrays e um valor limite comum, monte um único array resultante com os maiores elementos possíveis preservando suas ordens relativas originais.

**Passo a passo:**
1. Use um Hash Set associado a filas de prioridade e/ou ordenação combinada das tabelas para selecionar os `K` maiores elementos únicos.
2. Construa a estrutura final mapeando se o item escolhido pertencia ao array 1 ou 2, inserindo de forma estável.

**Entrada:**
```
A = [7, 4, 8, 0, 1, 2]
B = [9, 7, 2, 3, 6]
tam = 6
```

**Saída:**
```
[9, 7, 8, 4, 3, 6]
```

#### 10. Soma de Todas as Somas Únicas de Subarrays

**Descrição:** Calcular a soma total de todos os subarrays, mas filtrando apenas as somas de subarrays que acontecem exatamente uma vez globalmente.

**Passo a passo:**
1. Itere em loop duplo para encontrar a soma de todos os subarrays individualmente.
2. Adicione os resultados a um Hash Map `(Soma -> Frequência de Ocorrência)`.
3. Percorra as chaves do Mapa: some ao resultado final todas as chaves em que o valor (frequência) seja 1.

**Entrada:**
```
arr = [1, 2, 3]
```

**Saída:**
```
14 (Somas são: 1, 2, 3, 3, 5, 6; Únicas: 1, 2, 5, 6. Total = 1+2+5+6 = 14)
```

#### 11. Sequência de Recamán

**Descrição:** Gerar os N primeiros números dessa sequência matemática. Regra: `a(n) = a(n-1) - n` se positivo e ainda não incluso, senão `a(n) = a(n-1) + n`.

**Passo a passo:**
1. Inicie a sequência num array. O primeiro termo é 0.
2. Crie um Hash Set para registrar se um valor já foi incluído na resposta.
3. Itere aplicando a regra. Use o Hash Set para a checagem em O(1) de "ainda não incluso".

**Entrada:**
```
n = 5
```

**Saída:**
```
[0, 1, 3, 6, 2]
```

#### 12. Maior Subsequência Bitônica Estrita

**Descrição:** Subsequência bitônica é crescente, atinge um pico, depois é decrescente. Queremos o tamanho da maior que é de progressão estrita.

**Passo a passo:**
1. Calcule a Subsequência Crescente Mais Longa (LIS) da esquerda pra direita, utilizando um dicionário (Hash Map) para otimizações O(n log n).
2. Calcule a Subsequência Decrescente (LDS) da direita pra esquerda.
3. Para cada elemento, a resposta é `(LIS[i] + LDS[i] - 1)`. Pegue o máximo.

**Entrada:**
```
arr = [1, 5, 2, 3, 4, 5, 3, 2]
```

**Saída:**
```
5 (Pode ser [1, 2, 3, 4, 3])
```

#### 13. Subárvores Duplicadas

**Descrição:** Encontrar a raiz de todas as subárvores que têm estrutura e valores idênticos.

**Passo a passo:**
1. Faça uma travessia pós-ordem, serializando a estrutura da árvore em formato de string (ex: "Esq,Raiz,Dir").
2. Armazene a string serializada em um Hash Map com sua contagem de aparição `(String -> Frequência)`.
3. Se, após o incremento na DFS, a contagem da subárvore for `2` (para não repetir log), adicione o nó atual a uma lista de saídas.

#### 14. Submatriz com Cantos Iguais a 1

**Descrição:** Dada uma matriz binária, checar se há algum retângulo invisível onde os quatro cantos possuem o valor `1`.

**Passo a passo:**
1. Itere linha por linha (de cima para baixo).
2. Dentro da mesma linha, avalie todas as combinações de colunas `i` e `j` onde a matriz seja igual a `1`.
3. Crie um Set/Hash Map guardando o par de colunas `(i, j)`. Se um par atual já existir no Map, quer dizer que uma linha acima também tinha 1 nestas mesmas colunas (logo, o retângulo se formou). Retorne Verdadeiro.

**Entrada:** Matriz contendo `1` nas posições (0,0), (0,2), (2,0) e (2,2)

**Saída:**
```
Verdadeiro
```

</details>
