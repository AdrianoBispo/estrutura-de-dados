# Lista de Exercícios - Estruturas de Dados Linked List

Esta lista contém exercícios focados em manipular e resolver problemas clássicos usando Listas Encadeadas (Linked Lists). Eles estão divididos em níveis de dificuldade e foram elaborados para praticar a lógica de programação, permitindo a implementação na linguagem de sua escolha.

<details>
<summary>🟢 Nível 1 - Fácil</summary>

#### 1. Comprimento de uma Lista Encadeada

**Descrição:** Determine o número total de nós presentes em uma lista encadeada simples.

**Passo a passo:**
1. Inicialize uma variável `contador` com o valor 0.
2. Crie um ponteiro `atual` que aponte para o nó inicial (cabeça/head).
3. Enquanto `atual` não for nulo, incremente `contador` em 1 e mova `atual` para o próximo nó.
4. Retorne o valor de `contador`.

**Input:** `Lista: 1 -> 3 -> 1 -> 2 -> 1 -> nulo`  
**Output:** `5`

#### 2. Imprimir Lista Encadeada

**Descrição:** Percorra uma lista encadeada e exiba o valor de cada um dos seus nós.

**Passo a passo:**
1. Defina o ponteiro `atual` como o início da lista.
2. Utilize um laço para iterar enquanto `atual` não for nulo.
3. Imprima/armazene o valor do nó `atual`.
4. Mova `atual` para `atual.proximo`.

**Input:** `Lista: 10 -> 20 -> 30 -> 40 -> nulo`  
**Output:** `10 20 30 40`

#### 3. Buscar em uma Lista Encadeada

**Descrição:** Verifique se um determinado elemento (chave) existe dentro da lista.

**Passo a passo:**
1. Defina o ponteiro `atual` no início da lista.
2. Inicie a iteração até o fim da lista.
3. Se o valor de `atual` for igual à chave desejada, retorne `Verdadeiro`.
4. Mova para o próximo nó. Se o laço terminar, retorne `Falso`.

**Input:** `Lista: 14 -> 21 -> 11 -> 30 -> 10, Chave: 14`  
**Output:** `Verdadeiro`

#### 4. Inserção na Lista Encadeada

**Descrição:** Adicione um novo nó em uma posição específica da lista (início, fim ou após um nó existente). Vamos focar na inserção no final.

**Passo a passo:**
1. Crie um novo nó com o valor fornecido.
2. Se a lista estiver vazia (cabeça é nula), defina a cabeça como o novo nó.
3. Caso contrário, percorra a lista até que `atual.proximo` seja nulo.
4. Faça `atual.proximo` apontar para o novo nó.

**Input:** `Lista: 1 -> 2 -> 3 -> nulo, Novo valor: 4`  
**Output:** `Lista: 1 -> 2 -> 3 -> 4 -> nulo`

#### 5. Deletar uma chave específica

**Descrição:** Remova a primeira ocorrência de um nó que contenha um valor específico.

**Passo a passo:**
1. Se a lista estiver vazia, encerre a operação.
2. Se a cabeça contém a chave, mude a cabeça para `cabeça.proximo` e delete o nó antigo.
3. Caso contrário, mantenha um ponteiro `anterior` e `atual`. Percorra procurando a chave.
4. Ao encontrar, faça `anterior.proximo` apontar para `atual.proximo`.

**Input:** `Lista: 1 -> 2 -> 3 -> 4 -> nulo, Chave: 3`  
**Output:** `Lista: 1 -> 2 -> 4 -> nulo`

#### 6. Deletar em uma posição específica

**Descrição:** Remova o nó localizado em um índice `N` (baseado em 0).

**Passo a passo:**
1. Se a lista for vazia, não faça nada.
2. Se a posição for 0, altere a cabeça para `cabeça.proximo`.
3. Percorra até a posição `N-1` mantendo controle do nó `anterior`.
4. Verifique se o nó a deletar existe; se sim, ajuste `anterior.proximo = anterior.proximo.proximo`.

**Input:** `Lista: 10 -> 20 -> 30 -> 40 -> nulo, Posição: 2`  
**Output:** `Lista: 10 -> 20 -> 40 -> nulo`

#### 7. Deletar uma Lista Encadeada

**Descrição:** Remova todos os nós de uma lista encadeada, liberando a memória alocada.

**Passo a passo:**
1. Defina `atual` como a cabeça.
2. Enquanto `atual` não for nulo, salve `atual.proximo` em uma variável temporária `proximo`.
3. Delete/libere o nó `atual`.
4. Mova `atual` para `proximo`.
5. Altere o ponteiro da cabeça para nulo.

**Input:** `Lista: 1 -> 2 -> 3 -> nulo`  
**Output:** `Lista Vazia (cabeça = nulo)`

#### 8. Enésimo nó a partir do início

**Descrição:** Recupere o valor do nó que está no índice fornecido.

**Passo a passo:**
1. Comece do primeiro nó (índice 0).
2. Use um laço com um contador para percorrer nó a nó até chegar ao índice desejado.
3. Retorne o dado contido neste nó. Se a lista for menor que o índice, retorne um erro ou nulo.

**Input:** `Lista: 1 -> 10 -> 30 -> 14 -> nulo, Índice: 2`  
**Output:** `30`

#### 9. Enésimo nó a partir do final

**Descrição:** Encontre o valor do enésimo nó contando de trás para frente.

**Passo a passo:**
1. Crie dois ponteiros: `referencia` e `principal`.
2. Mova o ponteiro `referencia` `N` vezes para a frente.
3. Se `referencia` ficar nulo antes de `N` passos, o tamanho é menor que `N` (retorne erro).
4. Mova ambos juntos, passo a passo, até que `referencia` alcance o último nó.
5. O `principal` estará apontando para a resposta.

**Input:** `Lista: 35 -> 15 -> 4 -> 20 -> nulo, N: 4`  
**Output:** `35`

#### 10. Tamanho da Lista Duplamente Encadeada

**Descrição:** Conte o número de nós numa lista que possui referências para o próximo e o anterior.

**Passo a passo:**
1. Crie um `contador` e inicie em zero.
2. Comece com `atual` apontando para a cabeça da lista.
3. Iterativamente vá para `atual = atual.proximo`, incrementando o contador.
4. Retorne o total.

**Input:** `DLL: nulo <- 1 <-> 2 <-> 3 <-> 4 -> nulo`  
**Output:** `4`

#### 11. Remover cada k-ésimo nó

**Descrição:** Percorra a lista e delete cada nó que for múltiplo de K (ex: k=2, remova o 2º, 4º, 6º...).

**Passo a passo:**
1. Se `K` for 1, a lista inteira é deletada. Se a lista for vazia, pare.
2. Use um ponteiro `atual` e um contador de nós percorridos.
3. Guarde a referência para o nó anterior.
4. Se `contador == K`, faça `anterior.proximo = atual.proximo`, delete `atual`, resete o `contador` para 0.

**Input:** `Lista: 1 -> 2 -> 3 -> 4 -> 5 -> 6 -> nulo, K: 2`  
**Output:** `Lista: 1 -> 3 -> 5 -> nulo`

#### 12. Meio de uma Lista Encadeada

**Descrição:** Encontre e retorne o elemento central. Se a lista for par, retorne o segundo nó do meio.

**Passo a passo:**
1. Use dois ponteiros: `lento` e `rapido`, ambos iniciando na cabeça.
2. A cada iteração, mova `lento` um nó para frente, e `rapido` dois nós.
3. Quando `rapido` ou `rapido.proximo` chegar ao fim (nulo), `lento` estará exatamente no meio.

**Input:** `Lista: 1 -> 2 -> 3 -> 4 -> 5 -> nulo`  
**Output:** `3`

#### 13. Contar ocorrências em uma Lista Encadeada

**Descrição:** Retorne a quantidade de vezes que um número aparece na lista.

**Passo a passo:**
1. Inicialize um `contador` em zero.
2. Percorra todos os nós desde a cabeça até o final.
3. Se o valor do nó atual for igual à chave de busca, incremente `contador`.
4. Retorne `contador`.

**Input:** `Lista: 1 -> 2 -> 1 -> 2 -> 1 -> 3 -> 1, Chave: 1`  
**Output:** `4`

#### 14. Percorrer Lista Encadeada Circular

**Descrição:** Imprima os nós de uma lista onde o último nó aponta novamente para o primeiro.

**Passo a passo:**
1. Se a cabeça for nula, a lista está vazia.
2. Defina o nó `atual` igual à cabeça.
3. Usando um loop tipo "do-while", imprima `atual.valor` e avance `atual = atual.proximo`.
4. A condição de parada é quando `atual` for novamente igual à cabeça.

**Input:** `Lista Circular: 1 -> 2 -> 3 -> 4 -> (volta para 1)`  
**Output:** `1 2 3 4`

#### 15. Verificar se a Lista é Circular

**Descrição:** Determine se a lista encadeada termina em nulo ou forma um ciclo de volta ao início.

**Passo a passo:**
1. Se a cabeça for nula, considere como não circular (ou circular vazia, dependendo da convenção; geralmente falso).
2. Inicie `atual` como `cabeça.proximo`.
3. Enquanto `atual` for diferente de nulo e diferente de `cabeça`, mova `atual` para o próximo.
4. Se `atual == cabeça`, retorne `Verdadeiro`. Se alcançar um `nulo`, `Falso`.

**Input:** `Lista: 10 -> 12 -> 14 -> (volta para 10)`  
**Output:** `Verdadeiro`

#### 16. Contar nós na Lista Circular

**Descrição:** Conte a quantidade de elementos numa lista encadeada circular.

**Passo a passo:**
1. Inicialize um contador em zero. Se a lista for nula, retorne 0.
2. Comece de `atual = cabeça`.
3. Use um laço "do-while" incrementando o contador e avançando `atual`.
4. Pare quando `atual == cabeça` novamente. Retorne o contador.

**Input:** `Lista Circular: 1 -> 2 -> 3 -> 4 -> 5 -> (volta para 1)`  
**Output:** `5`

#### 17. Deleção em uma Lista Encadeada Circular

**Descrição:** Deletar um nó dado um valor, mantendo a estrutura circular intacta.

**Passo a passo:**
1. Encontre o nó a ser deletado junto com seu nó anterior.
2. Se a lista possui apenas 1 nó que deve ser deletado, libere-o e torne a cabeça nula.
3. Se for a cabeça, encontre o último nó para ajustar o ponteiro para a `nova cabeça`, mova a cabeça e delete.
4. Se estiver no meio, apenas faça `anterior.proximo = atual.proximo`.

**Input:** `Lista: 2 -> 5 -> 7 -> 8 -> 10 -> (volta 2), Deletar: 5`  
**Output:** `Lista: 2 -> 7 -> 8 -> 10 -> (volta 2)`

#### 18. Conversão de Lista Simples para Circular

**Descrição:** Pegue uma lista comum (termina em nulo) e a transforme numa lista circular.

**Passo a passo:**
1. Verifique se a cabeça é nula. Se for, retorne.
2. Inicie em `atual = cabeça` e percorra até o último nó (`atual.proximo == nulo`).
3. Faça o ponteiro `proximo` do último nó apontar para a cabeça.

**Input:** `Lista: 10 -> 20 -> 30 -> nulo`  
**Output:** `Lista: 10 -> 20 -> 30 -> (volta para 10)`

#### 19. Trocar o primeiro e o último nó em Lista Circular

**Descrição:** Modifique a lista trocando as posições do primeiro com o último elemento.

**Passo a passo:**
1. Se houver 1 ou menos nós, não faça nada.
2. Percorra até achar o último e o penúltimo nós.
3. Se houver apenas 2 nós, eles trocam de posição naturalmente movendo a cabeça.
4. Caso contrário, ajuste `ultimo.proximo` para `cabeça.proximo`, ajuste `penultimo.proximo = cabeça`, e `cabeça.proximo = ultimo`. Por fim, `cabeça = ultimo`.

**Input:** `Lista: 1 -> 2 -> 3 -> 4 -> (volta para 1)`  
**Output:** `Lista: 4 -> 2 -> 3 -> 1 -> (volta para 4)`

#### 20. Deletar em uma Lista Duplamente Encadeada

**Descrição:** Remova um nó de uma DLL onde os nós conhecem o anterior e o próximo.

**Passo a passo:**
1. Identifique o nó a ser removido (vamos chamar de `alvo`).
2. Se for a cabeça, mova a cabeça para o `proximo` e defina `novo.anterior` como nulo.
3. Se houver nó anterior, defina `anterior.proximo = alvo.proximo`.
4. Se houver nó seguinte, defina `proximo.anterior = alvo.anterior`.

**Input:** `DLL: 1 <-> 2 <-> 3, Deletar: 2`  
**Output:** `DLL: 1 <-> 3`

#### 21. Inverter uma Lista Encadeada Simples

**Descrição:** Inverta a direção de todos os ponteiros, fazendo o último nó se tornar o primeiro.

**Passo a passo:**
1. Mantenha três ponteiros: `anterior` (inicialmente nulo), `atual` (cabeça) e `proximo` (nulo).
2. Percorra a lista; salve `atual.proximo` na variável `proximo`.
3. Altere `atual.proximo` apontando-o para `anterior`.
4. Mova `anterior` para `atual` e `atual` para `proximo`.
5. Ao fim, atualize a cabeça com o último valor de `anterior`.

**Input:** `Lista: 1 -> 2 -> 3 -> 4 -> nulo`  
**Output:** `Lista: 4 -> 3 -> 2 -> 1 -> nulo`

#### 22. Inverter uma Lista Duplamente Encadeada

**Descrição:** Reverta uma lista que tem ambos os ponteiros (`anterior` e `proximo`).

**Passo a passo:**
1. Defina um ponteiro `temp = nulo` e `atual = cabeça`.
2. Em um loop, para o nó `atual`, troque os ponteiros `proximo` e `anterior` entre si.
3. Salve a referência do `atual` antes de avançar.
4. Ao final, atualize a cabeça para o último nó válido processado.

**Input:** `DLL: 1 <-> 2 <-> 3 <-> nulo`  
**Output:** `DLL: 3 <-> 2 <-> 1 <-> nulo`

</details>

<details>
<summary>🟠 Nível 2 - Médio</summary>

#### 23. Trocar nós em pares

**Descrição:** Inverta posições de nós adjacentes consecutivamente.

**Passo a passo:**
1. Se a lista estiver vazia ou com 1 nó, retorne a cabeça.
2. Inicialize um nó "fictício" (dummy) apontando para a cabeça para facilitar a troca no início.
3. Usando ponteiros para gerenciar pares, conecte o ponteiro de trás ao segundo nó do par, ajuste o ponteiro do segundo para apontar para o primeiro, e o do primeiro para o próximo da lista.
4. Mova adiante em pares.

**Input:** `Lista: 1 -> 2 -> 3 -> 4 -> 5 -> 6 -> nulo`  
**Output:** `Lista: 2 -> 1 -> 4 -> 3 -> 6 -> 5 -> nulo`

#### 24. Detectar ciclo em uma lista encadeada

**Descrição:** Identifique se há um loop infinito onde um nó aponta para um nó anterior na lista.

**Passo a passo:**
1. Use o algoritmo da lebre e da tartaruga (Floyd's Cycle-Finding).
2. Ponteiro `lento` anda 1 passo, `rapido` anda 2 passos de cada vez.
3. Se, em algum momento, `lento == rapido`, existe um loop.
4. Se `rapido` ou `rapido.proximo` for nulo, não há loop.

**Input:** `Lista: 1 -> 2 -> 3 -> 4 -> 5 -> (aponta para o nó 3)`  
**Output:** `Verdadeiro`

#### 25. Comprimento do ciclo na lista encadeada

**Descrição:** Se a lista tem um ciclo, retorne quantos nós formam o ciclo.

**Passo a passo:**
1. Detecte o ciclo usando ponteiros rápido e lento.
2. Quando se encontrarem, mantenha o ponteiro `lento` parado e mova um novo ponteiro a partir deste ponto, contando os nós.
3. Pare quando o ponteiro contador alcançar o ponteiro fixo. O total será o tamanho do loop.

**Input:** `Lista: 1 -> 2 -> 3 -> 4 -> 5 -> (aponta para o 2)`  
**Output:** `4 (os nós 2, 3, 4, 5 formam o ciclo)`

#### 26. Projetar Histórico de Navegador

**Descrição:** Crie um sistema com as funções visitar(url), voltar(passos) e avançar(passos).

**Passo a passo:**
1. Use uma Lista Duplamente Encadeada para representar o histórico.
2. Ao visitar nova URL, crie um nó apontado pelo atual, zere o restante à frente e mova o atual para ele.
3. Na função voltar(N), itere via ponteiros `anterior` até N vezes ou até o início.
4. Na função avançar(N), itere via `proximo` até N vezes ou até o fim.

**Input:** `visita("a.com"), visita("b.com"), visita("c.com"), voltar(1), visita("d.com")`  
**Output:** `Histórico após ações: "a.com" <-> "b.com" <-> "d.com" (o nó "c" foi descartado)`

#### 27. Remover duplicatas de uma lista encadeada ordenada

**Descrição:** Elimine nós consecutivos que tenham o mesmo valor (visto que a lista está ordenada).

**Passo a passo:**
1. Comece de `atual = cabeça`.
2. Enquanto `atual` e `atual.proximo` existirem, compare seus valores.
3. Se forem iguais, modifique `atual.proximo` pulando o nó repetido (`atual.proximo = atual.proximo.proximo`), e libere memória.
4. Se não forem iguais, apenas mova `atual` para a frente.

**Input:** `Lista: 11 -> 11 -> 11 -> 21 -> 43 -> 43 -> 60 -> nulo`  
**Output:** `Lista: 11 -> 21 -> 43 -> 60 -> nulo`

#### 28. Remover duplicatas de uma lista encadeada não ordenada

**Descrição:** Remova elementos repetidos de uma lista fora de ordem.

**Passo a passo:**
1. Use um `HashSet` (conjunto de busca rápida) para rastrear os valores já vistos.
2. Traverse usando um ponteiro `atual` e `anterior`.
3. Se o valor de `atual` já existir no conjunto, pule-o ajustando `anterior.proximo`.
4. Se for novo, adicione no conjunto e atualize `anterior = atual`.

**Input:** `Lista: 12 -> 11 -> 12 -> 21 -> 41 -> 43 -> 21 -> nulo`  
**Output:** `Lista: 12 -> 11 -> 21 -> 41 -> 43 -> nulo`

#### 29. Interseção de duas listas encadeadas ordenadas

**Descrição:** Crie uma terceira lista contendo os elementos presentes em ambas as listas fornecidas (apenas os comuns).

**Passo a passo:**
1. Use dois ponteiros: um no início da Lista1 e outro na Lista2.
2. Se `valor1 == valor2`, adicione esse valor à nova lista resultante e avance ambos os ponteiros.
3. Se `valor1 < valor2`, avance o ponteiro da Lista1.
4. Caso contrário, avance da Lista2. Pare quando qualquer uma chegar ao fim.

**Input:** `L1: 1->2->3->4->6, L2: 2->4->6->8`  
**Output:** `Resultado: 2 -> 4 -> 6 -> nulo`

#### 30. Particionar uma Lista

**Descrição:** Particione de modo que os nós com valores < X venham antes dos nós com valores >= X, mantendo a ordem original relativa de ambos.

**Passo a passo:**
1. Crie duas listas "fictícias": uma para `menores` e outra para `maiores/iguais`.
2. Itere sobre a lista original. Se `atual.valor < X`, adicione na lista `menores`. Se não, na lista `maiores`.
3. Ao fim, junte o final da lista `menores` no início da lista `maiores` (removendo o nó fictício inicial).
4. Feche o último nó apontando para nulo.

**Input:** `Lista: 1 -> 4 -> 3 -> 2 -> 5 -> 2, X = 3`  
**Output:** `Lista: 1 -> 2 -> 2 -> 4 -> 3 -> 5 -> nulo`

#### 31. QuickSort em Lista Encadeada Simples

**Descrição:** Implemente o famoso algoritmo QuickSort trocando e rearranjando referências (ponteiros).

**Passo a passo:**
1. Defina um pivô (ex: o último nó).
2. Particione a lista ao redor do pivô; mantenha nós menores ou iguais em uma sublista e maiores em outra.
3. Ordene recursivamente ambas as metades geradas.
4. Mescle (junte) o lado esquerdo ordenado + nó do pivô + lado direito ordenado e retorne a nova cabeça.

**Input:** `Lista: 30 -> 3 -> 4 -> 20 -> 5 -> nulo`  
**Output:** `Lista: 3 -> 4 -> 5 -> 20 -> 30 -> nulo`

#### 32. Dividir uma Lista Encadeada Circular em duas metades

**Descrição:** Reparta uma única lista circular inteira em duas sublistas menores, também circulares.

**Passo a passo:**
1. Encontre o meio da lista usando os ponteiros da lebre e tartaruga (`lento` e `rapido`).
2. Se o número de nós for ímpar, `rapido.proximo` chegará na cabeça. Se par, `rapido.proximo.proximo` baterá na cabeça.
3. Marque o meio, corte em duas listas fazendo a 1ª metade apontar do meio de volta ao começo, e a 2ª metade do fim ao item `meio.proximo`.

**Input:** `Lista: 1->2->3->4->(volta ao 1)`  
**Output:** `L1: 1->2->(volta 1) e L2: 3->4->(volta 3)`

#### 33. Mesclar Duas Listas Encadeadas Ordenadas

**Descrição:** Receba duas listas ordenadas e retorne uma única grande lista também em ordem.

**Passo a passo:**
1. Crie um nó "fictício" (dummy) como início da lista resultante e um ponteiro `cauda` sobre ele.
2. Compare as cabeças das duas listas; a de menor valor é adicionada após `cauda`. Avança-se o respectivo ponteiro.
3. Repita até uma das listas esvaziar. Emende o restante da lista que sobrou à `cauda`.

**Input:** `L1: 1->3->5, L2: 2->4->6`  
**Output:** `1 -> 2 -> 3 -> 4 -> 5 -> 6 -> nulo`

#### 34. União e Interseção

**Descrição:** Construa listas que representem, respectivamente, todos os itens únicos de ambas as listas (união) e apenas os itens presentes nas duas simultaneamente (interseção).

**Passo a passo (usando HashMap):**
1. Percorra L1 e insira todos os valores numa Tabela Hash.
2. Para a **União**: percorra L2, se o valor não estiver na Hash, adicione nele. Gere a lista a partir das chaves da Hash.
3. Para a **Interseção**: itere novamente em L2. Se o nó existir na Hash (preenchida apenas com L1), ele é interseção; coloque na lista de saída e remova da Hash para evitar duplicatas.

**Input:** `L1: 10->20->4->15, L2: 15->2->10`  
**Output:** `União: 10,20,4,15,2 | Interseção: 10,15`

#### 35. Merge Sort para Lista Duplamente Encadeada

**Descrição:** O método de ordenação Merge Sort adaptado para DLL (que se torna eficiente pois os nós podem ser divididos sem mover dados da memória).

**Passo a passo:**
1. Se for nulo ou ter apenas 1 nó, retorne a lista.
2. Divida a DLL em duas metades usando ponteiros rápido e lento. O meio da lista quebra as ligações `proximo` e `anterior` separando as duas partes.
3. Chame a função recursivamente nas metades.
4. Mescle as listas ordenadas em uma nova DLL (ajustando sempre `proximo` e `anterior` em cada conexão) e retorne a cabeça correspondente.

**Input:** `DLL: 5 <-> 3 <-> 1 <-> 4 <-> 2`  
**Output:** `DLL: 1 <-> 2 <-> 3 <-> 4 <-> 5`

#### 36. Pares com soma em lista duplamente encadeada

**Descrição:** Dada uma lista DLL ordenada, ache pares que somados dão um valor alvo numérico.

**Passo a passo:**
1. Como está ordenada, aponte um ponteiro `inicio` para a cabeça e `fim` para a cauda (último nó).
2. Verifique a soma: `atual = inicio.valor + fim.valor`.
3. Se for igual ao alvo, imprima, avance `inicio` e recue `fim`.
4. Se for menor, suba `inicio.proximo`. Se maior, desça `fim.anterior`.

**Input:** `DLL: 1 <-> 2 <-> 4 <-> 5 <-> 6 <-> 8 <-> 9, Alvo: 7`  
**Output:** `(1, 6), (2, 5)`

#### 37. Inserir de forma ordenada em lista duplamente encadeada

**Descrição:** Insira um novo nó na posição correta num fluxo que garanta que a DLL permaneça crescente.

**Passo a passo:**
1. Crie o novo nó. Se a lista estiver vazia, apenas o defina como a cabeça.
2. Se seu valor for menor que o da cabeça, insira no início (atualize `anterior` e `cabeça`).
3. Caso não, itere com um `atual` até `atual.proximo` ser nulo ou o dado ser maior que o do nó inserido.
4. Ajuste os ponteiros em torno de `atual` para intercalar o novo nó.

**Input:** `DLL: 1 <-> 3 <-> 5, Novo valor: 4`  
**Output:** `DLL: 1 <-> 3 <-> 4 <-> 5`

#### 38. Remover duplicatas de uma lista duplamente encadeada não ordenada

**Descrição:** Limpe números que aparecem repetidos numa DLL bagunçada.

**Passo a passo:**
1. Inicialize um conjunto Hash.
2. Comece da cabeça. Antes de mover, verifique se o valor de `atual` está na Hash.
3. Se sim, ajuste o `anterior` e o `proximo` do nó, desconectando-o e liberando a memória.
4. Se não, adicione o valor e avance.

**Input:** `DLL: 1 <-> 2 <-> 1 <-> 2 <-> 3`  
**Output:** `DLL: 1 <-> 2 <-> 3`

#### 39. Rotacionar uma Lista Encadeada

**Descrição:** Desloque os nós k posições anti-horário. Ex: a cabeça vira a cauda e o resto escorrega para trás.

**Passo a passo:**
1. Se k for 0 ou lista nula, retorne.
2. Itere para conhecer o tamanho da lista e achar a cauda (`ultimo` nó).
3. Conecte `ultimo.proximo = cabeça` para formar um ciclo contínuo.
4. Itere K passos contando desde o início (dependendo do sentido, k passos leva ao novo final).
5. Defina `nova_cabeca = corte.proximo`, corte o ciclo `corte.proximo = nulo` e retorne `nova_cabeca`.

**Input:** `Lista: 10->20->30->40->50->60, K=4`  
**Output:** `Lista: 50->60->10->20->30->40`

#### 40. Rotacionar Lista Duplamente Encadeada em N nós

**Descrição:** Semelhante a rotacionar listas simples, mas deve-se garantir que ponteiros de "ida e volta" se mantenham corretos na reconexão.

**Passo a passo:**
1. Traverse ao fim, encontrando o último elemento e o comprimento.
2. Conecte `fim.proximo = cabeca` e `cabeca.anterior = fim`.
3. Avance N passos partindo da cabeça. O nó onde parar será a nova cabeça.
4. O anterior da nova cabeça passa a ser o fim. Rompa o laço atualizando os ponteiros para nulo.

**Input:** `DLL: a<->b<->c<->d<->e<->nulo, N=2`  
**Output:** `DLL: c<->d<->e<->a<->b<->nulo`

#### 41. Deletar um nó com apenas o seu ponteiro fornecido

**Descrição:** O método não recebe o início da lista, apenas uma referência direta para o nó em si, e pede para apagá-lo. (Garantido que não é o último nó).

**Passo a passo:**
1. Acesse o conteúdo do próximo nó: `proximo_no = no_atual.proximo`.
2. Copie os dados: `no_atual.valor = proximo_no.valor`.
3. Modifique o encadeamento: `no_atual.proximo = proximo_no.proximo`.
4. Delete/libere memória de `proximo_no`.

**Input:** `Nó em mãos contendo o valor "B" na lista A->B->C->D`  
**Output:** `Lista passará a ser A->C->D`

#### 42. Segregar nós pares e ímpares

**Descrição:** Separe a lista para que todos os nós com valores numéricos ímpares fiquem no final, e os pares primeiro (ou o oposto), mantendo a ordem de aparição intacta.

**Passo a passo:**
1. Crie ponteiros para Início_Pares, Fim_Pares, Início_Ímpares, Fim_Ímpares.
2. Percorra os nós. Verifique `valor % 2 == 0`.
3. Atribua e cresça as respectivas listas Pares ou Ímpares.
4. Finalizado o laço, se existirem pares e ímpares, una `Fim_Pares` em `Início_Ímpares` e encerre com nulo.

**Input:** `Lista: 17 -> 15 -> 8 -> 12 -> 10 -> 5 -> 4`  
**Output:** `Lista: 8 -> 12 -> 10 -> 4 -> 17 -> 15 -> 5`

</details>

<details>
<summary>🔴 Nível 3 - Difícil</summary>

#### 43. Mesclar K Listas Ordenadas

**Descrição:** Dada uma array com `K` Listas Encadeadas, já ordenadas internamente, junte-as numa lista mestre única.

**Passo a passo:**
1. Utilize uma estrutura de **Min-Heap (Fila de Prioridade)**.
2. Insira as `K` cabeças das listas na Heap. A Heap organizará de forma a colocar o nó com menor valor numérico no topo.
3. Extraia o valor mínimo e jogue na lista resultante mestre.
4. Adicione à Heap o nó seguinte associado àquele que acabou de ser extraído. Repita até exaurir.

**Input:** `[ 1->4->5, 1->3->4, 2->6 ]`  
**Output:** `1 -> 1 -> 2 -> 3 -> 4 -> 4 -> 5 -> 6 -> nulo`

#### 44. Ponto de interseção de duas Listas Encadeadas

**Descrição:** Identificar em qual "nó memória" duas ramificações se unem em forma de um "Y".

**Passo a passo:**
1. Calcule o número de nós na Lista1 (`C1`) e Lista2 (`C2`).
2. Descubra o delta: valor absoluto da diferença `abs(C1 - C2)`.
3. Inicie um ponteiro no início da lista maior e avance o delta vezes (igualando as pontas finais das duas no plano linear).
4. Avance sincronizadamente um em cada lista, parando quando ambos apontarem para o **mesmo nó na memória**.

**Input:** `L1: (cabeçalho) -> [3]->[6]->[9]->[15]->[30]; L2: (cabeçalho diferente) -> [10]->[15]->[30]`  
**Output:** `Nó contendo o valor 15`

#### 45. Implementar Cache LRU

**Descrição:** Least Recently Used Cache. Desenvolva as funções estritas O(1) de colocar e capturar dados num cache dinâmico restrito por tamanho máximo.

**Passo a passo:**
1. Estruture um HashMap contendo a Chave como identificador e o Valor como ponteiro para um Nó numa **Lista Duplamente Encadeada**.
2. A DLL manterá os elementos recentes próximos à "cabeça" e os velhos no fim.
3. Operação Get(chave): ache no Map e traga o Nó para o topo da DLL, retorne o dado.
4. Operação Put(chave, dado): Se cheio, remova o rabo da DLL e da Hash. Em seguida, adicione como o elemento mais recente da DLL.

**Input:** `Capacidade 2; Put(1, 1); Put(2, 2); Get(1) => 1; Put(3, 3) (desaloca chave 2); Get(2) => Não achou`  
**Output:** `Retorna 1, depois Erro/Nulo/Vazio`

#### 46. Clonar uma lista encadeada com ponteiro aleatório

**Descrição:** Fazer um "Deep Copy" de uma lista em que cada nó possui o ponteiro `proximo` padrão e um `aleatorio` para qualquer lugar.

**Passo a passo:**
1. Itere infundindo um clone entre os passos normais: `A -> A_clone -> B -> B_clone -> ...`
2. No segundo loop, conecte os ponteiros aleatórios: `A_clone.aleatorio = A.aleatorio.proximo`.
3. No último loop, desconecte a engrenagem (separe as duas Listas): aponte os ponteiros `A_clone.proximo` para os próximos clones e restaure a lista pai.

**Input:** `Lista: A -> B -> C, onde A_aleatório aponta C`  
**Output:** `Cópia Exata num endereço diferente da memória, A' apontando C'`

#### 47. Árvore Binária para Lista Duplamente Encadeada

**Descrição:** Converta estruturalmente uma Árvore Binária de Busca na própria posição da memória em uma DLL ordenada in-place (esquerda vira `anterior` e direita vira `proximo`).

**Passo a passo:**
1. Crie uma variável rastreadora global para guardar o `ultimo_processado` da lista (inicialmente nulo) e uma rastreadora global para a nova cabeça.
2. Realize uma recursão em **In-Order** (Esquerda, Raiz, Direita).
3. Na chamada raiz, se `ultimo_processado` for nulo, marque a cabeça como o nó atual.
4. Caso contrário, defina `ultimo_processado.direita = raiz` e `raiz.esquerda = ultimo_processado`. Em seguida, desloque `ultimo_processado = raiz`.

**Input:** `Árvore BST onde 10 é raiz, L:5 e R:20`  
**Output:** `DLL: 5 <-> 10 <-> 20`

#### 48. Inverter uma Lista Encadeada Simples em Grupos

**Descrição:** Separe a lista em porções de K e inverta cada uma individualmente.

**Passo a passo:**
1. Dentro de uma função recursiva, inicialize um laço para avançar exatamente `K` vezes que inverte o elo como numa reversão padrão, mantendo um `atual`, `proximo` e `anterior`.
2. O último de seu sub-grupo se tornará o novo primeiro; o antigo primeiro pontará para o restante da recursão.
3. Chame `cabeca.proximo = InverterEmGrupos(proximo_no_livre, k)` e retorne `anterior` como nova cabeça do bloco.

**Input:** `Lista: 1->2->3->4->5->6->7->8, K = 3`  
**Output:** `Lista: 3->2->1->6->5->4->7->8`

#### 49. Inverter uma Lista Duplamente Encadeada em Grupos

**Descrição:** O mesmo do passo acima, mas é preciso reajustar adequadamente o ponteiro de ida e o ponteiro de volta de cada um dos blocos.

**Passo a passo:**
1. A função usa `atual` movendo e invertendo os ponteiros `proximo` e `anterior` para os primeiros `K` nós.
2. Concluído o lote, se o ponteiro `proximo_bloco` ainda existir, defina `cabeca.proximo = Recursive(proximo_bloco, K)`.
3. Garanta que o elo `anterior` da cabeça do subproblema retornando aponte para a base da pilha atual recursiva.

**Input:** `DLL: 1 <-> 2 <-> 3 <-> 4, K=2`  
**Output:** `DLL: 2 <-> 1 <-> 4 <-> 3`

#### 50. Busca de Sublista

**Descrição:** Encontrar uma sequência exata menor "Sub" dentro do corpo de uma lista maior "Master".

**Passo a passo:**
1. Marque um nó em Master como ponto de início de partida usando um loop externo.
2. Inicie outro loop interno com dois ponteiros, um apontado à cabeça de Sub e outro comparando com o ponto base de Master.
3. Vá movendo e comparando. Se ambos forem idênticos até que Sub acabe de iterar (bata no nulo), a sublista existe (retorne `Verdadeiro`).
4. Se um item quebrar, pare o sub-laço e avance a âncora no loop externo em 1.

**Input:** `Sub: 1->2->3, Master: 5->4->1->2->3->6`  
**Output:** `Verdadeiro`

#### 51. Lista encadeada a partir de matriz 2D

**Descrição:** Imagine uma grade (Grid) M x N, onde cada bloco converte-se num nó com 2 ponteiros de navegação espacial: um apontando à `direita` e um apontando para `baixo`.

**Passo a passo:**
1. Defina uma matriz Node base. Utilize uma função recursiva `Construct(matriz, i, j, max_i, max_j)`.
2. Se `i` ou `j` ultrapassarem os limites das linhas/colunas da grade, retorne `nulo`.
3. Crie `novo_no = construtor( matriz[i][j] )`.
4. Defina as rotas encadeadas: `novo_no.direita = Construct(matriz, i, j+1)` e `novo_no.baixo = Construct(matriz, i+1, j)`.

**Input:** `Matriz = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]`  
**Output:** `Nó contendo o número 1, de onde você pode seguir nó.direita (2) ou nó.baixo (4) interconectados globalmente`

#### 52. Rotacionar Lista Encadeada em blocos

**Descrição:** A tarefa é inverter os dados de nós subespaçados. Rotacionar ciclicamente subseções (blocos) de tamanho D com distância ou offset fixo.

**Passo a passo:**
1. A complexidade deste problema demanda varredura parcial. Pegue um ponteiro e agrupe a contagem D.
2. Ao selecionar uma porção, desconecte ela temporariamente, invoque o algoritmo normal de reversão local ou rotação clássica sob a pequena faixa.
3. Quando finalizado, emende o nó modificado final de volta nos que aguardam.

**Input:** `Lista base: 1->2->3->4->5->6->7->8->9, Bloco=3`  
**Output:** `Processará (1,2,3), depois (4,5,6), rearranjando ou rodando em suas localizações baseadas nas regras da entrada`

#### 53. Multiplicar dois números como Listas

**Descrição:** Uma conta matemática de M x N operada node a node (onde 100 vem como `1 -> 0 -> 0`).

**Passo a passo:**
1. Como gerenciar memória infinita é a meta aqui, use duas variáveis rastreadoras em inteiros bem grandes ou lide numericamente.
2. Inicie a variável global como 0. Extraia Lista1 multiplicando pela base (`var_L1 = (var_L1 * 10) + atual_L1.valor`).
3. Repita o loop completo de acumulação e shift decimal na Lista2 (`var_L2`).
4. Multiplique o resultado `(var_L1 * var_L2)` e você pode construir ou iterar para retornar a soma se desejado.

**Input:** `L1: 3 -> 2 (valor 32), L2: 2 (valor 2)`  
**Output:** `64`

#### 54. Deletar N nós após M nós

**Descrição:** Percorra uma listagem, mantenha e ignore `M` nós, depois disso delete ativamente os `N` nós subsequentes, retornando a pular.

**Passo a passo:**
1. Defina um ponteiro `atual = cabeca`.
2. Abra um laço infinito. Use um mini laço para percorrer mantendo-se `M-1` passos à frente.
3. Se o limite acabar batendo em nulo, quebre o programa (não resta mais nada).
4. Do contrário, abra um segundo mini laço percorrendo e apagando ativamente referências de `N` nós, religando então o `protegido_limite.proximo` na continuidade do processo.

**Input:** `Lista: 1->2->3->4->5->6->7->8, M = 2, N = 2`  
**Output:** `Lista: 1->2->5->6-> nulo`

</details>
