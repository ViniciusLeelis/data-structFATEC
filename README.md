# data-structFATEC
Um repositório básico que encontra-se uma parte do resumo de Estrutura de Dados (lembrando que foi escrito com meu conhecimento, caso exista falhas, favor corrigir xD)


# Revisão |   
 OBS: Esta revisão tem como intuito principal treinar aquilo aprendido em aula e também, promover o conhecimento.  
 OBS²: Tal repositório não possui código-fonte daquilo aprendido em aula (ainda)  
   
A divisão do conteúdo encontra-se neste README !  

Iremos seguir a seguinte ordem de conteúdo  
1° Recursividade;  
2° Problemas dos vetores em C;  
3° Listas encadeadas sem cabeça;  
4° Listas encadeadas com cabeça;  
6° Pilhas  
7° Filas.  
8º Buscas em vetores ordenados
9º Algoritmos Rápidos de ordenação (Mergesort, Quicksort)  

# Recursividade
O conceito de recursividade é extremamente interessante e devemos levar em consideração se a implementação do mesmo é viável.
Basicamente a ideia principal é chamar a função dentro da própria função sucessivamente, assim fazendo que uma ação cuja necessidade
seja a repetição, seja chamada sem códigos gigantescos.
Mas nem sempre ela é viavel, um bom exemplo é no uso do famoso algoritmo de Fibonnacci, chegando um momento que não é viável, já que
é feito a chamada várias vezes de algo já calculado:  
 Exemplo em python:  

 > def fib(n):  
   print ('fib(%d)' %n)  
   if n <= 2:  
     return 1  
   #bad O(2**n)  
     return fib(n-1) + fib(n-2)  
  
  Para corrigir tal problema, é interessante utilizar um dicionário, no qual armazena os valores já utilizados, fazendo que não tenha repetição do mesmo valor já calculado.
   Exemplo em python:
   
   > dic = {}
     def fib(n):
       print ('fib(%d)' %n)
       if n <= 2:
         return 1
       else:
         if n not in dic:
            dic[n] = fib(n - 1) + fib(n - 2)
         return dic[n]
  
 # Problema de vetores em C
   Os vetores em C possui inúmeros problemas, dentre eles: Após definir um tamanho especifico, ele não pode ser alterado(só se for
   criado outro vetor), desempenho reduzido após a adição de mais elementos, aceitam um padrão por vez (um tipo, exemplo: Inteiro).
   Esses problemas fizeram que Estruturas de Dados fossem criadas, dentre elas podendo ser citado: Lista Encadeada, Mergesort e afins.
   Algumas linguagens resolveram tal problema, como exemplo as linguagens híbridas.  
   
   
 # Listas encadeadas (CONCEITO)
  Uma lista encadeada  (= linked list = lista ligada)  é uma seqüência de células; cada célula contém um objeto de algum tipo e o endereço da célula seguinte.   Suporemos nesta página que os objetos armazenados nas células são do tipo int.  A estrutura de cada
célula de uma tal lista pode ser definida assim:  
   >  struct cel {  
       int         conteudo;  
       struct cel *prox;  
    } ;  
  A lista encadeada solucionou problemas de desempenho, já que não é necessário percorrer toda uma lista já que a adição sempre é feita no início.
  Com esta estrutura não há mais o problema de alocações estáticas, já que é permitido aqui a alocação dinâmica de memória;
  O desempenho para a adição e remoção em listas encadeadas é muito melhor que em Arrays, isso porque não é necessário percorrer toda a lista para a adição e nem para a remoção.
 
    
  # Listas encadeadas com cabeça:
   "Lista com cabeça.  O conteúdo da primeira célula é irrelevante: ela serve apenas para marcar o início da lista.  A primeira célula é a cabeça (= head cell = dummy cell) da lista.  A primeira célula está sempre no mesmo lugar na memória, mesmo que a lista fique vazia. O endereço da primeira célula nunca muda.  Digamos que ini é o endereço da primeira célula. Então  ini->prox == NULL  se e somente se a lista está vazia. Para criar uma lista vazia, basta dizer." . Paulo Feofiloff IME- USP
   Vantagens:
   * Não testa lista vazia  
   * Não é tão complexo  
   * Bem mais eficiente  
   * Sem necessidade de ponteiro pra ponteiro  
   

 # Listas encadeadas sem cabeça:
   Lista sem cabeça.  O conteúdo da primeira célula é tão relevante quanto o das demais. Nesse caso, a lista está vazia se o endereço de sua primeira célula é NULL.  Para criar uma lista vazia basta fazer
   > celula *ini;  
     ini = NULL;  
     
   Desvantagens:  
     * Bem mais complexo de implementar  
     * Não é tão eficiente (apesar de ter programadores que preferem tal)  
     
 
 # Filas
   O conceito de filas pode ser comparado ao conceito FIFO (O primeiro que entra, é o primeiro que sai), já que é utilizado como array.
   Uma pilha é fixa, ou seja não aumenta e nem diminui, possuindo um valor fixo. O problema de ser fixa pode ser resolvido com as listas
   encadeadas, tornando a estrutura dinâmica, só que a complexidade de implementação é grande.
   
 # Pilhas
   O conceito de pilhas é chamado assim devido a sua semelhancia com uma pilha de pratos, sua caracteristica é baseada no LIFO (último a entrar, primeiro a sair)
    ?  ? ? /
  
 # Buscas em vetores ordenados
   * Busca sequêncial:   
      * No pior caso serão dados N passos  
      * Busca demorada;  
      * Não leva em conta a estrutura dos dados;  
      * Passa elemento a elemento do vetor  
  * Busca binária:  
      * Rápida;  
      * Leva em consideração a estrutura dos dados;  
      * No caso de um valor 2 ^ 1000000  
      * O algoritimo leva apenas 13 passos, isso porque trabalha dividindo cada passo em 2  
  Anotações retiradas do repositório Gigers.
 
# Algoritimos de busca


* Algoritimos bons:
    * Algoritimos bons utilizam, n * log(base 2) n, isso porque a cada divisão (por 2), terei o log(base 2) de n.  

* Algoritimos ruins:
    * Algoritimos ruins acabam trabalhando com N ^ 2, onde N é o tamanho do vetor, assim a busca passa duas vezes, pelo mesmo elemento.
    * 1° Exemplo de um algoritimo ruim de ordenação (Inserção):
        <code> 
   
                 1° Passo: 0, 3, 6, 1, 5, 4, 2, 7
                 2° Passo: 0, 1, 3, 6
                 3° Passo: 0, 1, 3, 5, 6
                 4° Passo: 0, 1, 3, 4, 5, 6
                 5° Passo: 0, 1, 3, 4, 5, 6, 7
                 
        </code>
        * Algoritimo ruim pois tem de passar por todos os elementos várias vezes para funcionar
    * Abaixo mais um exemplo:
        <code>
   
                1° Passo: 6, 3, 4, 5, 1, 0, 7, 2
                2° Passo: 3, 6
                3° Passo: 3, 4, 5
                4° Passo: 3, 4, 5, 6
                5° Passo: 1, 3, 4, 5, 6
                6° Passo: 0, 1, 3, 4, 5, 6
                7° Passo: 0, 2, 1, 3, 4, 5, 6
                8° Passo: 0, 2, 1, 3, 4, 5, 6, 7
        </code>
    * 2° Exemplo de algoritimo ruim de ordenação (Método de seleção):
        <code>
   
                1° Passo: 6, 3, 4, 5, 1, 0, 7, 2
                2° Passo: 0, 3, 4, 5, 1, 6, 7, 2
                3° Passo: 0, 1, 4, 5, 3, 6, 7, 2
                4° Passo: 0, 1, 2, 5, 3, 6, 7, 4
                5° Passo: 0, 1, 2, 3, 5, 6, 7, 4
                6° Passo: 0, 1, 2, 3, 4, 6, 7, 5
                7° Passo: 0, 1, 2, 3, 4, 5, 7, 6
                8° Passo: 0, 1, 2, 3, 4, 5, 6, 7
                
        </code>
    * Comparar os dois algoritimos. Quem é o pior ?
        * R: O de seleção, isso porque ele não leva em consideração o lado esquedo (Já ordenado), apenas o lado direito, e o algoritmo de inserção, considera o lado esquerdo.
    
    * Todos os algoritimos mostrados até aqui, são algoritimos n ^ 2
    
    
    Anotações retiradas do repositório Gigers.
    



# Aula - 26/09/2017  // link do repositório de onde foi tirado: https://github.com/Gigers/data-struct   ----------

# Algoritimos rápidos de ordenação - Mergesort

O processo de intercalar demora N (Sendo ordem de grandeza N/2)

Este é um processo mais rápido que o processo de inserção e de comparação

É um algoritmo bom para vetores pequenos, mas para grandes vetores terá problemas
As metades são independentes, podendo ser feitas em paralelo

* Abstração

0° - Receba o vetor
    [6, 7, 4, 0, 2, 1, 5, 3]
1° - Divide o vetor recebido na metade
    [6, 7, 4, 0]  [2, 1, 5, 3]
2° - Divide novamente os campos gerados na divisão anterior
    [6, 7] [4, 0] [2, 1] [5, 3]
3° - Divide novamente os campos gerados na divisão anterior
    [6] [7] [4] [0] [2] [1] [5] [3]
4° - Junta em pares de dois sorteando os menores
    [6,7] [0, 4] [1,2] [3,5]
5° - 0, 4 ,6 , 7



6,3,0,7,5,1, 2, 4


# Considerações que caem na prova

A - origem
B - Destino

Este algoritimo é bom porém consome o dobro de memória


Para um programa ser bom deve se levar em consideração dois tópicos:

* Quantidade de passos feitas pelo programa
* Espaço de memória utilizado

* Considerações sobre o algoritimo Mergesort
    * 1° - Muito mais rápido que os algoritimos de inserção e seleção (N/log(n) < n ^ 2)
    * 2° - Ocupa o dobro do espaço;
    * 3° - As metades são independentes, posso fazer em paralelo (Com threads, multiplos processadores)

# Heapsort (NÂO CAI NA PROVA)

log(n) / 2 

# Quicksort

Se este processo for feito recursivo, no final hávera o dobro de elementos no vetor
No entanto, na prática Quicksort é muito rápido, pois ninguem ordena um vetor já ordenado


1 2 (2 ^ 2) (2 ^ 4) (2 ^ 8)  (2 ^ 16) == log/2(n)

Aqui não há vetores auxiliares

* Considerações importantes

    * 1° - Se o vetor estiver ordenado, quicksort demora n ^ 2 passos
        * Exemplo de um passo: [0, 1, 2, 3, 4]; pivô = 0
        <code>
            menores = [] 
            maiores = [1,2,3,4]
        </code>
        * Este é o pior caso, onde todos os elementos ficam do mesmo lado
    * 2° - No entanto o Quicksort é muito rápido. Ninguém ordena um vetor ordenado
    * No pior caso n ^ 2, na media log/2(n)

# Conteúdo da prova

* Ordenar por mergesort sem ver o código
* Heapsort não cai na prova
* Quicksort
* Explicar os conceitos do quicksort

   
    
   
   

# Questões rápidas úteis (retirado do arquivo Estrutura de Dados.pdf criado por Kelvin)

* Problema de remoção.  
Remover elementos no início do vetor  
* Problema de Inserção.  
Inserir elementos no início do vetor  
* Problema de busca  
Lado ruim: Necessita de um dobro de
espaço

* ALGORITIMO DE BUSCA BINÁRIA
  * Por que aumenta só um passo?
    R: Porque divide pela metade.


* Quando vale a pena ordenar uma lista
para aplicar a busca binária?
  R: Quando é possível aplicar n*logN2 após
a ordenação.

Divide o vetor em dois blocos. De acordo
com um "pivô" escolhido. A cada vez que
voce faz esse processo, ele divide o vetor
em dois. Fazendo um lado ficar certo e o
outro errado.


* Comparar os dois algoritmos: Inserção e
  Seleção. Qual é pior?
   Seleção, pois, não leva em conta o lado
   esquerdo que já está ordenado.
   Diferentemente do Inserção, que aproveita
   o lado esquerdo.
Passagem por Valor e por referencia

* Por que é preciso usar ponteiros na
função troca?
  R: Porque eu não conseguiria acessar as
variáveis locais da main se não fosse
ponteiro.
