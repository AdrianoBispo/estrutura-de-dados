# Lista de Exercícios - Estrutura de Dados Strings

Este documento serve como um guia de treinamento lógico para manipulação de Strings. O objetivo é que você implemente a solução para cada problema sem depender primariamente de funções prontas (built-ins) da sua linguagem de escolha, fortalecendo sua lógica de programação clássica.

<details>
<summary><strong>🟢 Problemas Fáceis</strong></summary>

### 1. Tamanho de uma String

- **Descrição:** Calcular o tamanho (quantidade de caracteres) de uma string.
- **Passo a Passo:**
  1. Inicialize uma variável contadora com valor 0.
  2. Percorra a string através de um laço de repetição.
  3. Incremente o contador a cada caractere lido até encontrar o final da string (caractere nulo `\0`).
- **Exemplo:**
  - **Input:** `"texto"`
  - **Output:** `5`

### 2. Verificar Igualdade

- **Descrição:** Verificar se duas strings são exatamente iguais.
- **Passo a Passo:**
  1. Compare o tamanho de ambas as strings. Se forem diferentes, retorne falso.
  2. Percorra ambas as strings simultaneamente em um laço.
  3. Compare o caractere da posição atual da primeira com a segunda. Se algum for diferente, retorne falso.
  4. Se o laço terminar sem diferenças, retorne verdadeiro.
- **Exemplo:**
  - **Input:** `str1 = "abc"`, `str2 = "abc"`
  - **Output:** `True`

### 3. Buscar um Caractere

- **Descrição:** Buscar a primeira ocorrência de um caractere específico em uma string.
- **Passo a Passo:**
  1. Receba a string e o caractere alvo.
  2. Percorra a string por índices numéricos.
  3. Ao encontrar o caractere alvo, retorne o índice atual.
  4. Caso o laço termine e não encontre, retorne -1.
- **Exemplo:**
  - **Input:** `"programacao"`, `'g'`
  - **Output:** `3`

### 4. Inserir um Caractere

- **Descrição:** Inserir um caractere em uma posição específica de uma string.
- **Passo a Passo:**
  1. Crie uma nova string ou array de caracteres com 1 espaço a mais.
  2. Copie os caracteres da string original para a nova até chegar ao índice alvo.
  3. Insira o novo caractere no índice alvo.
  4. Copie o resto da string original avançando um índice.
- **Exemplo:**
  - **Input:** `"helo"`, caractere `'l'`, índice `2`
  - **Output:** `"hello"`

### 5. Remover um Caractere

- **Descrição:** Remover um caractere de uma posição específica da string.
- **Passo a Passo:**
  1. Crie uma nova string (ou modifique a original deslocando dados).
  2. Percorra os caracteres, adicionando-os na nova string apenas se o índice atual não for o índice alvo a ser removido.
- **Exemplo:**
  - **Input:** `"hello"`, índice `1`
  - **Output:** `"hllo"`

### 6. Remover Todas as Ocorrências

- **Descrição:** Remover todas as instâncias de um caractere específico na string.
- **Passo a Passo:**
  1. Inicialize uma string de resultado vazia.
  2. Percorra a string original caractere por caractere.
  3. Se o caractere atual for diferente do alvo a ser removido, adicione-o ao resultado.
- **Exemplo:**
  - **Input:** `"banana"`, `'a'`
  - **Output:** `"bnn"`

### 7. Concatenar Duas Strings

- **Descrição:** Juntar (concatenar) uma string no final de outra.
- **Passo a Passo:**
  1. Crie uma nova string/array com o tamanho somado de ambas as strings.
  2. Copie todos os caracteres da primeira string para o início da nova string.
  3. Copie os caracteres da segunda string logo após o final da primeira.
- **Exemplo:**
  - **Input:** `"Hello, "`, `"World!"`
  - **Output:** `"Hello, World!"`

### 8. Inverter uma String

- **Descrição:** Inverter a ordem dos caracteres de uma string.
- **Passo a Passo:**
  1. Defina dois ponteiros/índices: um no início (`i=0`) e outro no final (`j = tamanho-1`).
  2. Enquanto `i < j`, troque o caractere da posição `i` com o da posição `j`.
  3. Incremente `i` e decremente `j`.
- **Exemplo:**
  - **Input:** `"abcd"`
  - **Output:** `"dcba"`

### 9. Gerar Todas as Substrings

- **Descrição:** Imprimir todas as substrings possíveis formadas a partir de uma string original.
- **Passo a Passo:**
  1. Utilize um laço `i` para marcar o índice inicial da substring.
  2. Utilize um laço interno `j` (iniciando de `i`) para marcar o final da substring.
  3. Imprima os caracteres de `i` até `j`.
- **Exemplo:**
  - **Input:** `"abc"`
  - **Output:** `"a"`, `"ab"`, `"abc"`, `"b"`, `"bc"`, `"c"`

### 10. Verificar String Binária

- **Descrição:** Validar se a string é composta exclusivamente por '0's e '1's.
- **Passo a Passo:**
  1. Percorra cada caractere da string.
  2. Se o caractere atual for diferente de '0' e diferente de '1', retorne falso imediatamente.
  3. Se chegar ao fim sem falhas, retorne verdadeiro.
- **Exemplo:**
  - **Input:** `"101011"`
  - **Output:** `True`

### 11. Conversão para Camel Case

- **Descrição:** Converter uma frase separada por espaços para o padrão `camelCase`.
- **Passo a Passo:**
  1. Crie uma string de resultado.
  2. Percorra a string original. Se encontrar um espaço, ative uma flag `próxima_letra_maiuscula`.
  3. Se não for espaço: se a flag estiver ativa, adicione o caractere convertido para maiúsculo e desative a flag. Caso contrário, adicione o caractere em minúsculo.
- **Exemplo:**
  - **Input:** `"hello world and universe"`
  - **Output:** `"helloWorldAndUniverse"`

### 12. Substrings com Extremos Iguais a 1

- **Descrição:** Contar quantas substrings de uma string binária começam e terminam com '1'.
- **Passo a Passo:**
  1. Conte a quantidade total de caracteres '1' na string inteira (chame de `k`).
  2. O número de substrings formadas por pares de '1's obedece a fórmula combinatória `k * (k - 1) / 2`.
  3. Retorne o resultado desse cálculo.
- **Exemplo:**
  - **Input:** `"10101"`
  - **Output:** `3` (substrings: "101", "10101", "101" a partir do segundo 1)

### 13. Verificar se é Pangrama

- **Descrição:** Verificar se uma frase contém todas as letras do alfabeto (inglês) pelo menos uma vez.
- **Passo a Passo:**
  1. Crie um array booleano ou Hash Set para registrar letras vistas (tamanho 26).
  2. Percorra a string. Para cada letra encontrada (ignorando espaços/pontuação), marque como `True` no índice correspondente.
  3. No final, verifique se todos os 26 espaços estão marcados como `True`.
- **Exemplo:**
  - **Input:** `"The quick brown fox jumps over the lazy dog"`
  - **Output:** `True`

### 14. Verificar se é Palíndromo

- **Descrição:** Verificar se uma string é a mesma quando lida de frente para trás e de trás para frente.
- **Passo a Passo:**
  1. Defina um ponteiro no início `i=0` e outro no final `j=tamanho-1`.
  2. Enquanto `i < j`, compare os caracteres. Se forem diferentes, retorne falso.
  3. Avance `i` e recue `j`. Retorne verdadeiro se acabar o laço.
- **Exemplo:**
  - **Input:** `"radar"`
  - **Output:** `True`

### 15. Verificar se é Substring

- **Descrição:** Descobrir se uma string "A" está contida integralmente dentro de uma string "B".
- **Passo a Passo:**
  1. Percorra a string principal "B" usando um índice `i`.
  2. Para cada posição de `i`, veja se os próximos caracteres correspondem à string "A".
  3. Se encontrar uma combinação completa sequencial, retorne verdadeiro.
- **Exemplo:**
  - **Input:** `B = "hello world"`, `A = "world"`
  - **Output:** `True`

### 16. Verificar se é Subsequência

- **Descrição:** Verificar se todos os caracteres da string "A" existem na string "B" mantendo a mesma ordem relativa (sem precisar ser contíguo).
- **Passo a Passo:**
  1. Use dois ponteiros: `i` para string "A" e `j` para string "B".
  2. Percorra "B". Se o caractere de `A[i]` for igual a `B[j]`, incremente `i`.
  3. Se `i` alcançar o final do tamanho de "A", retorne verdadeiro.
- **Exemplo:**
  - **Input:** `A = "ace"`, `B = "abcde"`
  - **Output:** `True`

### 17. Verificar se são Anagramas

- **Descrição:** Verificar se duas strings possuem os exatos mesmos caracteres com as mesmas quantidades, independentemente da ordem.
- **Passo a Passo:**
  1. Se os tamanhos forem diferentes, retorne falso.
  2. Crie um mapa de frequência (array de 256 posições).
  3. Para cada caractere em str1, incremente a posição. Para cada em str2, decremente a posição.
  4. Se ao final o array estiver zerado, é anagrama.
- **Exemplo:**
  - **Input:** `"listen"`, `"silent"`
  - **Output:** `True`

### 18. Verificar se são K-Anagramas

- **Descrição:** Verificar se é possível tornar duas strings anagramas mudando, no máximo, `K` caracteres.
- **Passo a Passo:**
  1. Se os tamanhos forem diferentes, retorne falso.
  2. Preencha um mapa de frequência para a primeira string.
  3. Percorra a segunda string, decrementando a frequência se o caractere existir no mapa. Se não existir (ou frequência zerar), incremente um contador de "diferenças".
  4. Se "diferenças" for menor ou igual a `K`, retorne verdadeiro.
- **Exemplo:**
  - **Input:** `"anagram"`, `"grammar"`, `K = 3`
  - **Output:** `True`

### 19. Transformar String em URL (URLify)

- **Descrição:** Substituir todos os espaços em branco de uma string pela cadeia de caracteres `"%20"`.
- **Passo a Passo:**
  1. Conte a quantidade de espaços em branco na string.
  2. Crie uma nova string alocando espaço extra (tamanho original + espaços × 2).
  3. Copie os dados iterando na original; se encontrar um espaço, insira `%`, `2`, `0` na nova string.
- **Exemplo:**
  - **Input:** `"Mr John Smith"`
  - **Output:** `"Mr%20John%20Smith"`

</details>

<details>
<summary><strong>🟡 Problemas Médios</strong></summary>

### 20. Primeiro Caractere Repetido

- **Descrição:** Encontrar a primeira letra que aparece mais de uma vez na string.
- **Passo a Passo:**
  1. Crie uma estrutura de dados de busca rápida (Hash Set) vazia.
  2. Percorra a string da esquerda para a direita.
  3. Para cada letra, verifique se ela já está no Set. Se sim, retorne-a imediatamente. Senão, adicione-a.
- **Exemplo:**
  - **Input:** `"geeksforgeeks"`
  - **Output:** `'e'`

### 21. Primeiro Caractere Não Repetido

- **Descrição:** Encontrar o primeiro caractere em uma string que não se repete nenhuma vez.
- **Passo a Passo:**
  1. Percorra a string e armazene a frequência de cada caractere em um array numérico ou Hash Map.
  2. Faça um segundo loop pela string original.
  3. O primeiro caractere cuja frequência registrada for igual a 1 será a resposta.
- **Exemplo:**
  - **Input:** `"swiss"`
  - **Output:** `'w'`

### 22. Verificar Rotação

- **Descrição:** Verificar se uma string `A` é rotação circular de uma string `B`.
- **Passo a Passo:**
  1. Se as strings tiverem tamanhos diferentes, retorne falso.
  2. Concatene a string `A` com ela mesma (`A + A`).
  3. Verifique se `B` é substring dessa nova string concatenada.
- **Exemplo:**
  - **Input:** `"abcd"`, `"cdab"`
  - **Output:** `True` (pois `"abcdabcd"` contém `"cdab"`)

### 23. K-ésimo Caractere Não Repetido

- **Descrição:** Encontrar o K-ésimo caractere que aparece apenas uma vez na string.
- **Passo a Passo:**
  1. Mapeie a frequência de todos os caracteres da string.
  2. Percorra a string novamente. Se a frequência do caractere for 1, incremente uma contagem temporária.
  3. Quando a contagem temporária for igual a `K`, retorne esse caractere.
- **Exemplo:**
  - **Input:** `"geeksforgeeks"`, `K = 2`
  - **Output:** `'o'`

### 24. Implementar atoi (String para Inteiro)

- **Descrição:** Converter uma representação string de um número em um tipo Inteiro, processando sinais.
- **Passo a Passo:**
  1. Ignore espaços em branco iniciais e verifique a presença de sinal (`+` ou `-`).
  2. Inicialize `resultado = 0`.
  3. Para cada caractere numérico ('0' a '9'), atualize: `resultado = resultado * 10 + (caractere - '0')`. Pare se encontrar letras.
  4. Aplique o sinal verificado no passo 1.
- **Exemplo:**
  - **Input:** `"-123"`
  - **Output:** `-123` (tipo inteiro)

### 25. Validar Endereço IP

- **Descrição:** Verificar se uma string representa um endereço IPv4 válido.
- **Passo a Passo:**
  1. Divida a string baseando-se nos pontos (`.`). Deve resultar em exatamente 4 partes.
  2. Para cada parte, garanta que seja composta apenas por dígitos numéricos e não tenha zeros à esquerda (ex: `01`).
  3. Converta cada parte para inteiro e verifique se o valor está entre 0 e 255.
- **Exemplo:**
  - **Input:** `"192.168.0.1"`
  - **Output:** `True`

### 26. Somar n Strings Binárias

- **Descrição:** Somar uma lista de múltiplas strings que representam números em notação binária.
- **Passo a Passo:**
  1. Crie uma função que soma duas strings binárias iterando de trás para frente, gerenciando o valor de "vai um" (carry).
  2. Utilize uma variável para guardar o resultado atual (inicialmente a primeira string).
  3. Percorra as demais strings do array passando o resultado atual e a próxima string pela sua função de soma.
- **Exemplo:**
  - **Input:** `["11", "1"]`
  - **Output:** `"100"`

### 27. Multiplicar Duas Strings

- **Descrição:** Multiplicar dois números gigantes representados como string para evitar overflow de tipos primitivos numéricos.
- **Passo a Passo:**
  1. Crie um array numérico de tamanho `len(num1) + len(num2)` para guardar o resultado provisório.
  2. Percorra num1 de trás pra frente e num2 de trás pra frente.
  3. Multiplique o dígito de num1 pelo de num2, adicione ao valor já existente no índice correspondente do array e gerencie a dezena (carry) para a posição anterior do array.
  4. Limpe os zeros à esquerda e transforme o array de volta em string.
- **Exemplo:**
  - **Input:** `"123"`, `"456"`
  - **Output:** `"56088"`

### 28. Strings Isomórficas

- **Descrição:** Verificar se os caracteres de uma string `A` podem ser substituídos para obter a string `B` com mapeamento único 1-para-1.
- **Passo a Passo:**
  1. Se os tamanhos divergirem, retorne falso.
  2. Utilize dois Hash Maps/Arrays para rastrear mapeamentos (ex: 'A' → 'B' e 'B' → 'A').
  3. Percorra as strings em paralelo; se um caractere já foi mapeado, ele deve apontar exatamente para o caractere esperado. Se a regra for quebrada, retorne falso.
- **Exemplo:**
  - **Input:** `"egg"`, `"add"`
  - **Output:** `True` (e → a, g → d)

### 29. Remover Adjacentes Duplicados

- **Descrição:** Remover recursivamente e exaustivamente caracteres duplicados que estejam lado a lado.
- **Passo a Passo:**
  1. Crie uma pilha (Stack). Alternativamente, use uma nova string gerenciando o último caractere.
  2. Ao iterar pela string: compare com o último inserido na pilha.
  3. Se for igual, em vez de adicionar, remova o item do topo da pilha (ou ignore-os recursivamente até parar de achar iguais).
- **Exemplo:**
  - **Input:** `"abbaca"`
  - **Output:** `"ca"` (bb removido → "aaca" → aa removido → "ca")

### 30. Romano para Inteiro

- **Descrição:** Converter um algarismo romano para número decimal correspondente.
- **Passo a Passo:**
  1. Mapeie os valores (I=1, V=5, X=10, L=50, C=100, D=500, M=1000).
  2. Percorra a string a partir da esquerda até a direita.
  3. Se o caractere atual for menor que o próximo caractere, ele deve ser subtraído do total.
  4. Se for maior ou igual ao próximo, adicione ao total.
- **Exemplo:**
  - **Input:** `"MCMIV"`
  - **Output:** `1904`

### 31. Strings Entrelaçadas

- **Descrição:** Verificar se uma terceira string `C` é formada pelo entrelaçamento das strings `A` e `B`, mantendo a ordem relativa dos caracteres.
- **Passo a Passo:**
  1. Verifique se o comprimento de `A + B` é igual a `C`.
  2. Utilize Recursão com Memoization ou Programação Dinâmica (matriz booleana 2D).
  3. O estado `dp[i][j]` é verdadeiro se `C[i+j-1]` é igual a `A[i-1]` e `dp[i-1][j]` é verdadeiro, OU se é igual a `B[j-1]` e `dp[i][j-1]` é verdadeiro.
- **Exemplo:**
  - **Input:** `A = "AB"`, `B = "CD"`, `C = "ACBD"`
  - **Output:** `True`

### 32. Permutações de uma String

- **Descrição:** Descobrir e imprimir todos os arranjos/combinações possíveis (permutações) com os caracteres da string.
- **Passo a Passo:**
  1. Utilize o padrão de Backtracking (recursão).
  2. Crie uma função que receba a string e os índices `left` e `right`.
  3. Itere do índice `left` até `right`, fazendo a troca (swap) do caractere atual com o inicial da recursão. Em seguida, chame a função recursivamente e então reverta a troca (backtrack).
- **Exemplo:**
  - **Input:** `"ABC"`
  - **Output:** `"ABC"`, `"ACB"`, `"BAC"`, `"BCA"`, `"CAB"`, `"CBA"`

### 33. Maior Substring Palindrômica

- **Descrição:** Encontrar a substring contígua mais longa que também seja um palíndromo.
- **Passo a Passo:**
  1. Iterar sob cada caractere da string considerando-o como "centro" do palíndromo.
  2. Para cada centro, use uma função para expandir para os lados (esquerda e direita) simultaneamente enquanto os caracteres forem iguais.
  3. Salve o maior palíndromo encontrado entre as expansões para centros ímpares (tamanho 1) e pares (tamanho 2).
- **Exemplo:**
  - **Input:** `"babad"`
  - **Output:** `"bab"` (ou `"aba"`)

### 34. Substrings Anagramas

- **Descrição:** Contar quantas substrings completas e independentes na string formam pares de anagramas uma da outra.
- **Passo a Passo:**
  1. Gere todas as substrings da string.
  2. Para cada substring, ordene alfabeticamente seus caracteres.
  3. Armazene a frequência de aparição de cada "substring ordenada" em um Hash Map.
  4. Some as combinações combinatórias `(frequencia * (frequencia - 1)) / 2` para obter a quantidade de pares.
- **Exemplo:**
  - **Input:** `"xyyx"`
  - **Output:** `4` (x, x / y, y / xy, yx / xyy, yyx)

### 35. Strings Binárias Sem 1s Consecutivos

- **Descrição:** Contar o número total de strings binárias de tamanho `N` nas quais não existam dois '1's adjacentes.
- **Passo a Passo:**
  1. Crie duas variáveis ou arrays DP: `termina_com_0` e `termina_com_1`.
  2. Para tamanho 1: `termina_com_0 = 1`, `termina_com_1 = 1`.
  3. Para um novo dígito inserido, a nova string terminada em 0 pode vir de strings anteriores finalizadas em 0 e em 1. A finalizada em 1 só pode vir de uma finalizada em 0. Some o final (Sequência de Fibonacci em essência).
- **Exemplo:**
  - **Input:** `3` (tamanho N)
  - **Output:** `5` (`"000"`, `"001"`, `"010"`, `"100"`, `"101"`)

### 36. Próxima String Lexicográfica

- **Descrição:** Encontrar a próxima string lógica na ordem alfabética que seja imediatamente maior (mantendo o mesmo tamanho se possível).
- **Passo a Passo:**
  1. Percorra a string do final para o início.
  2. Se o caractere atual for diferente de 'z', incremente este caractere em 1 letra. Transforme todos os caracteres à direita deste em 'a', e retorne.
  3. Se a string só possuir 'z', anexe 'a' no final.
- **Exemplo:**
  - **Input:** `"abc"`
  - **Output:** `"abd"`

### 37. Dividir String em Quatro Strings Distintas

- **Descrição:** Verificar se é possível particionar a string original em exatamente 4 substrings que sejam completamente diferentes entre si.
- **Passo a Passo:**
  1. Utilize três laços de repetição aninhados (for) dividindo a string em pontos de corte (índices `i`, `j`, `k`).
  2. Extraia os 4 pedaços criados pelos cortes (ex: `0..i`, `i..j`, `j..k`, `k..final`).
  3. Adicione as 4 strings em um HashSet. Se o tamanho do Set for 4, retorne verdadeiro.
- **Exemplo:**
  - **Input:** `"geeksforgeeks"`
  - **Output:** `True` (g, e, eks, forgeeks)

### 38. Problema de Quebra de Palavras

- **Descrição:** Dada uma string e um dicionário de palavras válidas, determine se a string pode ser inteiramente segmentada em palavras desse dicionário.
- **Passo a Passo:**
  1. Crie um array booleano de Programação Dinâmica `dp` do tamanho da string+1, sendo `dp[0] = true`.
  2. O índice representa que a string até aquele ponto consegue ser quebrada no dicionário.
  3. Use dois for aninhados (`i` de 1 até comprimento, `j` de 0 até `i`); caso `dp[j]` seja verdadeiro e a substring entre `j` e `i` exista no dicionário, marque `dp[i]` como verdadeiro.
- **Exemplo:**
  - **Input:** String = `"ilikesung"`, Dicionário = `["i", "like", "sun", "sung"]`
  - **Output:** `True`

### 39. Trocas Mínimas para Balanceamento de Chaves

- **Descrição:** Descobrir o número mínimo de trocas (swaps) necessárias para equilibrar uma sequência de chaves fechando/abrindo `[]`.
- **Passo a Passo:**
  1. Transforme em um problema de contagem. Percorra a string.
  2. Mantenha controle sobre o número de chaves abrindo não pareadas e uma variável de `desbalanço`.
  3. Se encontrar `[`, decremente desbalanço. Se encontrar `]`, incremente. Sempre que o desbalanço ficar positivo, a resposta global incrementará.
- **Exemplo:**
  - **Input:** `"]["
  - **Output:** `1`

### 40. String para Sequência de Teclado Numérico de Celular

- **Descrição:** Converter uma frase de texto na sequência exata de números que precisariam ser pressionados em um celular analógico antigo.
- **Passo a Passo:**
  1. Crie um array onde o índice representa a letra (`'A' = 0`) e o valor representa o botão numérico correspondente (ex: `'A' → "2"`, `'B' → "22"`).
  2. Percorra a string recebida de entrada iterando cada letra.
  3. Concatene os valores equivalentes do array em uma string final, incluindo o mapeamento do caractere de espaço (`"0"`).
- **Exemplo:**
  - **Input:** `"CAB"`
  - **Output:** `"222222"` (C=222, A=2, B=22)

### 41. Caminho Mais Curto para Imprimir uma String na Tela

- **Descrição:** Dado um teclado na tela com estrutura matricial, encontre os caminhos mais curtos (Cima, Baixo, Esquerda, Direita e "OK") para digitar a string.
- **Passo a Passo:**
  1. Posicione o cursor inicialmente em `
