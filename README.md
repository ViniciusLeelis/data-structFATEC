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
8º Algoritmos Rápidos de ordenação (Mergesort, Quicksort)  

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
  A lista encadeada solucionou problemas de desempenho, já que não é necessário percorrer toda uma lista já que a adição sempre é feita no início
 
    
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
    
 # Algoritmos rápidos de ordenação
 
   
    
   
   
