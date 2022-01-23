### Trabalhar com estrutura de dados utilizando arrays pode ser uma tarefa difícil, pois arrays não permitem o redimensionamento. É impossível buscar um determinado elemento cujo índice é desconhecido, não conseguimos saber quantas posições do array foram populadas sem criarmos métodos adicionais para isso, entre outros problemas. Assim, para facilitar a vida do programador, foi criado um conjunto de interfaces e classes conhecidas como Collections Framework, que se encontra no pacote java.util. Veja o diagrama de classes abaixo e:

![Collections](https://github.com/luanhroliveira/assets/blob/main/mestreDosCodigosDB1/java/escudeiro/collections.png "Collections")

#### Demonstre, por meio de algoritmos, a utilização de cada uma delas, ressaltando qual o tipo de problema cada uma resolve e qual a importância de fazer a escolha certa.

---

### Priority Queue:

- O priority queue é baseado no heap de prioridade. Onde os elementos da fila de prioridade são ordenados de acordo com
  a ordenação natural, ou por um Comparator fornecido no momento da construção da fila, dependendo de qual construtor
  for utilizado. Um priority queue é usado quando os objetos devem ser processados com base na prioridade.

Na imagem abaixo, um elemento com valor ASCII máximo terá a prioridade mais alta.

![Priority Queue](https://github.com/luanhroliveira/assets/blob/main/mestreDosCodigosDB1/java/escudeiro/Priority-Queue-min-1024x512.png "Priority queue")

Veja um exemplo de aplicação no código abaixo:

````java
class PriorityQueue {

    public static void main(String args[]) {
        // Criando fila de prioridade vazia
        PriorityQueue<Integer> pQueue = new PriorityQueue<Integer>();

        // Adicionando itens ao pQueue usando add()
        pQueue.add(10);
        pQueue.add(20);
        pQueue.add(15);

        // Printing the top element of PriorityQueue
        System.out.println(pQueue.peek());

        /*
         * Imprimindo o elemento superior e removendo-o
         * do contêiner PriorityQueue
         */
        System.out.println(pQueue.poll());

        // Imprimindo o elemento superior novamente
        System.out.println(pQueue.peek());

        //STRING
        PriorityQueue<String> pq = new PriorityQueue<>();

        pq.add("Geeks");
        pq.add("For");
        pq.add("Geeks");

        System.out.println("Initial PriorityQueue " + pq);

        // usando o método
        pq.remove("Geeks");

        System.out.println("Após a remoção - " + pq);

        System.out.println("Método de Enquete - " + pq.poll());

        System.out.println("Final PriorityQueue - " + pq);

    }
}
````

Saída:

    10
    10
    15
    Initial PriorityQueue [For, Geeks, Geeks]
    Após a remoção - [For, Geeks]
    Método de Enquete - For
    Final PriorityQueue - [Geeks]

### Linked List:

- A classe LinkedList é uma collections que pode conter muitos objetos do mesmo tipo, e podem adicionar itens, alterar,
  remover e limpar a lista, pois implementa a interface List.

  A linkedList armazena os seus itens em "containers" e a lista tem um link para o primeiro container e cada container
  tem um link para o próximo container da lista. Para adicionar um elemento na lista, o mesmo é colocado num novo
  container que, é vinculado a um dos outros containers da lista.

  De maneira geral, um LinkedList serve para manipular dados.

Veja um exemplo de uso da classe LinkedList:

````java
public class LinkedList {

    public static void main(String args[]) {

        // Criando objeto da classe LinkedList
        LinkedList<String> stringLinkedList = new LinkedList<String>();

        // Adicionando elementos à LinkedList
        stringLinkedList.add("A");
        stringLinkedList.add("B");
        stringLinkedList.addLast("C");
        stringLinkedList.addFirst("D");
        stringLinkedList.add(2, "E");

        System.out.println(stringLinkedList);

        stringLinkedList.remove("B");
        stringLinkedList.remove(3);
        stringLinkedList.removeFirst();
        stringLinkedList.removeLast();

        System.out.println(stringLinkedList);
    }
}
````

Saída:

    [D, A, E, B, C]
    [A]

### Vector:

- O Vector tem como principal característica ser thread safe, isso significa que executará pilhas diferentes sendo
  executados paralelamente uma mesma lista será usada.

  É recomendado que se uma implementação thread-safe não for necessária, utiliza-se o ArrayList no lugar do Vector.

  Um Vector tem o dobro do tamanho da lista, tornando mais custoso. Por exemplo, se têm um Vector de 10 elementos, o seu
  tamanho corresponderá a 20 elementos.

Veja um exemplo da sua implementação:

````java
public class VectorClass {

    public static void main(String args[]) {

        Vector vector = new Vector();
        vector.add(3);
        vector.add(2);
        vector.add(1);
        vector.add(4);
        vector.add(5);
        vector.add(6);
        vector.add(6);

        Iterator iter1 = vector.iterator();
        while (iter1.hasNext()) {
            System.out.println(iter1.next());
        }

        System.out.println(vector.get(2));
    }
}
````

Saída:

    3
    2
    1
    4
    5
    6
    6
    1

### ArrayList:

- Um ArrayList, não muito diferente das demais listas, serve para armazenar objetos. E, com a ajuda dos seus métodos,
  podem ser adicionados, removidos, editados, acessados, dentre outros possíveis métodos.

````java
public class ArrayListClass {

    public static void main(String args[]) {

        ArrayList integerArrayList = new ArrayList<Integer>();
        integerArrayList.add(3);
        integerArrayList.add(2);
        integerArrayList.add(1);
        integerArrayList.add(4);
        integerArrayList.add(5);
        integerArrayList.add(6);
        integerArrayList.add(6);

        Iterator iter1 = integerArrayList.iterator();
        while (iter1.hasNext()) {
            System.out.println(iter1.next());
        }

        System.out.println(integerArrayList.get(2));
    }
}


````

Saída:

    3
    2
    1
    4
    5
    6
    6
    1

Note que o algoritmo é muito semelhante ao do Vector, pois realmente só troquei a classe. Isso porque sua utilização são
muito parecidas, tendo como diferença o fato do Vector ser thread-safe, e o ArrayList não. Dessa forma, se precisar
utilizar uma lista que permite thread-safe, utilize Vector.

### Queue:

- A interface Queue é utilizada para conter elementos que estão prestes a serem processados na ordem FIFO (First In
  First Out). De maneira geral, é uma lista ordenada de objetos com o seu uso limitado a inserir elementos no final, e
  deletar elementos no início da lista, seguindo o princípio de FIFO. Em outras palavras, o primeiro que chega, será o
  primeiro a ser atendido.

  Veja um exemplo de implementação da Queue:

````java
public class QueueClass {

    public static void main(String[] args) {
        Queue<Integer> queue = new LinkedList<>();

        // Adiciona elementos na fila
        for (int i = 0; i < 5; i++) {
            queue.add(i);
        }

        // Exibe o conteúdo da fila.
        System.out.println("Elementos da fila: " + queue);

        // Remover o primeiro da fila
        System.out.println("Elemento removido: " + queue.remove());

        // Exibe o conteúdo da fila.
        System.out.println(queue);

        // Visualizar o início da fila
        System.out.println("Chefe da fila: " + queue.peek());

        // Visualizar o tamanho da fila
        System.out.println("Tamanho da fila: " + queue.size());
    }
}
````

Saída:

    Elementos da fila: [0, 1, 2, 3, 4]
    Elemento removido: 0
    [1, 2, 3, 4]
    Chefe da fila: 1
    Tamanho da fila: 4

### List:

- A classe List é uma interface implementada pela classe ArrayList, Vector, e LinkedList. E ela extend de Collection.

  O primeiro elemento de List é zero. E ele, assim como os demais, fornece uma série de métodos para manipular os
  elementos.

````java
public class ListClass {
    public static void main(String[] args) {
        List<Livro> livros = new ArrayList<Livro>();
        List<Livro> livrosNovos = new ArrayList<Livro>();

        Livro livro = new Livro();

        //adiciona um livro a nossa lista
        livros.add(livro);

        //adiciona um livro a uma posição exata da lista
        livros.add(10, livro);

        // Adicionando todos os livros novos na lista de livros de uma só vez.
        livros.addAll(livrosNovos);

        // Adiciona os livros novos a lista de livros de forma dinâmica.
        for (int i = 0; i < livrosNovos.size(); i++) {
            livros.add(livrosNovos.get(i));
        }

        //Verifica se o livro está na lista de livros.
        livros.contains(livro);

        //Remove todos os elementos da lista
        livros.clear();
    }
}
````

Como podem ver, foi instanciado duas listas com sintaxes semelhantes, porém, na sua inicialização, utilizei o
ArrayList (que por sua vez, implementa a interface List).

O intuito é gaarantir a flexibilidade da aplicação, da forma implementada, conseguimos garantir que o mesmo objeto pode
ser instanciado de maneiras distintas em pontos distintos da aplicação, dessa forma, eu tenho certeza dos métodos que o
objeto tem.

### Set:

- Utilizamos a interface Set, quando não desejamos que o array contenha valores duplicados. Pois, é uma excelente opção
  para quem deseja trabalhar com união, intersecção, diferença.

  Veja um exemplo de sua implementação:

````java
public class SetClass {

    public static void main(String args[]) {

        // Criando um objeto da classe Set, declarando o objeto do tipo Integer
        Set<Integer> a = new HashSet<Integer>();

        // Adicionando todos os elementos à lista
        a.addAll(Arrays.asList(new Integer[]{1, 3, 2, 4, 8, 9, 0}));

        Set<Integer> b = new HashSet<Integer>();

        b.addAll(Arrays.asList(new Integer[]{1, 3, 7, 5, 4, 0, 7, 5}));


        // Para encontrar união
        Set<Integer> union = new HashSet<Integer>(a);
        union.addAll(b);
        System.out.print("União dos dois Set: ");
        System.out.println(union);

        // Para encontrar a intersecção
        Set<Integer> intersection = new HashSet<Integer>(a);
        intersection.retainAll(b);
        System.out.print("Intersecção dos dois Set: ");
        System.out.println(intersection);

        // Para encontrar a diferença simétrica
        Set<Integer> difference = new HashSet<Integer>(a);
        difference.removeAll(b);
        System.out.print("Diferença dos dois Set: ");
        System.out.println(difference);
    }
}
````

Saída:

    União dos dois Set: [0, 1, 2, 3, 4, 5, 7, 8, 9]
    Intersecção dos dois Set: [0, 1, 3, 4]
    Diferença dos dois Set: [2, 8, 9]

### HashSet:

- O HashSet implementa a interface Set, e é o mais rápido dentre todos que implementam o Set, pois este, usa a HashTable
  e os seus elementos não são ordenados. Muito indicado onde se é necessário ter maior desempenho, caso a ordenação seja
  importante, o HashSet não é tão interessante.

  Veja:

````java
public class HashSetClass {

    public static void main(String[] args) {

        HashSet<Gato> gatoHashSet = new HashSet<Gato>();

        gatoHashSet.add(new Gato(2));
        gatoHashSet.add(new Gato(1));
        gatoHashSet.add(new Gato(3));
        gatoHashSet.add(new Gato(5));
        gatoHashSet.add(new Gato(4));

        Iterator<Gato> iterator = gatoHashSet.iterator();

        while (iterator.hasNext()) {
            System.out.print(iterator.next() + " ");
        }
    }
````

Saída:

    [5 3 2 1 4 ]

### LinkedHashSet:

- A classe LinkedHashSet estende de HashSet, trazendo consigo parte do desempenho e a ordenação, ausente no HashSet.
  Ideal para quem busca um array performatico e ordenado.

  Ao percorrer o LinkedHashSet com um iterator, os elementos serão retornados na ordem em que foram inseridos.

  Veja sua implementação:

````java
public class LinkedHashSetClass {

    public static void main(String[] args) {

        LinkedHashSet<String> linkedHashSet = new LinkedHashSet<String>();

        // Adicionando elementos no LinkedHashSet utilizando o método add().
        linkedHashSet.add("A");
        linkedHashSet.add("B");
        linkedHashSet.add("C");
        linkedHashSet.add("D");

        // Nota: Isso não adicionará um novo elemento, pois o elemento 'A' já existe.
        linkedHashSet.add("A");
        linkedHashSet.add("E");

        // Obtendo o tamanho com o método size().
        System.out.println("Tamanho do LinkedHashSet: " + linkedHashSet.size());

        System.out.println("Original LinkedHashSet:" + linkedHashSet);

        // Removendo objeto existente 'D', utilizando o método remove(). 
        System.out.println("Removendo 'D' do LinkedHashSet: " + linkedHashSet.remove("D"));

        // Removendo um objeto inexistente no LinkedHashSet
        System.out.println("Tentando remover 'Z' que não existe no LinkedHashSet: " + linkedHashSet.remove("Z"));

        // Verificando se o elemento 'A' existe no array.
        System.out.println("Verificando se 'A' está contido no array: " + linkedHashSet.contains("A"));

        // Agora, exibindo o array atualizado.
        System.out.println("LinkedHashSet atualizado: " + linkedHashSet);
    }
}
````

Saída:

    Tamanho do LinkedHashSet: 5
    Original LinkedHashSet: [A, B, C, D, E]
    Removendo 'D' do LinkedHashSet: true
    Tentando remover 'Z' que não existe no LinkedHashSet: false
    Verificando se 'A' está contido no array: = true
    LinkedHashSet atualizado: [A, B, C, E]

### SortedSet:

- A interface SortedSet estende a interface Set. Esta interface contém os métodos de Set e adiciona um recurso que
  armazena todos os elementso desta interface para serem armazenadas de forma ordenada.

````java
public class SortedSetClass {

    public static void main(String[] args) {

        SortedSet<String> sortedSet = new TreeSet<String>();

        // Adicionando elementos
        sortedSet.add("India");
        sortedSet.add("Australia");
        sortedSet.add("África do Sul");

        // Adicionando elemento duplicado.
        sortedSet.add("India");

        // Exibindo.
        System.out.println(sortedSet);

        // Removendo itens usando o método remove().
        sortedSet.remove("Australia");
        System.out.println("Definido após a remoção da Austrália: " + sortedSet);

        // Iterando sobre itens do conjunto de árvores.
        System.out.println("Iterando sobre o conjunto:");

        Iterator<String> i = sortedSet.iterator();

        while (i.hasNext()) {
            System.out.println(i.next());
        }
    }
}
````

Saída:

    [Australia, India, Africa do Sul]
    Definido após a remoção da Austrália: [India, Africa do Sul]
    Iterando sobre o conjunto:
    India
    Africa do Sul

É importante ressaltar que todos os elementos de um SortedSet devem implementar a interface Comparable.

### NavigableSet:

- A interface NavigableSet estende a SortedSet, e também herda o comportamento de um SortedSet com a exceção de que
  temos métodos de navegação disponíveis.

  Um NavigableSet pode ser acessado e percorrido em ordem crescente e decrescente.

````java
public class NavigableSetClasse {

    public static void main(String[] args) {

        NavigableSet<Integer> ns = new TreeSet<>();

        ns.add(0);
        ns.add(1);
        ns.add(2);
        ns.add(3);
        ns.add(4);
        ns.add(5);
        ns.add(6);

        // Obtendo uma visão inversa do conjunto navegável
        NavigableSet<Integer> reverseNs = ns.descendingSet();

        // Imprime as visualizações normal e inversa
        System.out.println("Ordem normal: " + ns);
        System.out.println("Ordem inversa: " + reverseNs);

        NavigableSet<Integer> threeOrMore = ns.tailSet(3, true);

        System.out.println("3 or more:  " + threeOrMore);
        System.out.println("lower(3): " + ns.lower(3));
        System.out.println("floor(3): " + ns.floor(3));
        System.out.println("higher(3): " + ns.higher(3));
        System.out.println("ceiling(3): " + ns.ceiling(3));

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("Navigable Set: " + ns);

        System.out.println("pollLast(): " + ns.pollLast());
        System.out.println("Navigable Set: " + ns);

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("Navigable Set: " + ns);

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("Navigable Set: " + ns);

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("Navigable Set: " + ns);

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("pollLast(): " + ns.pollLast());
    }
}
````

Saída:

    Ordem normal: [0, 1, 2, 3, 4, 5, 6]
    Ordem inversa: [6, 5, 4, 3, 2, 1, 0]
    3 or more: [3, 4, 5, 6]
    lower(3): 2
    floor(3): 3
    higher(3): 4
    ceiling (3): 3
    pollFirst(): 0
    Navigable Set: [1, 2, 3, 4, 5, 6]
    pollLast(): 6
    Navigable Set: [1, 2, 3, 4, 5]
    pollFirst(): 1
    Navigable Set: [2, 3, 4, 5]
    pollFirst(): 2
    Navigable Set: [3, 4, 5]
    pollFirst(): 3
    Navigable Set: [4, 5]
    pollFirst(): 4
    pollLast(): 5

### TreeSet:

- O TreeSet implementa a interface SortedSet e consequentemente a interface Set, herdando assim todos os métodos já
  descritos.

  A ordenação dos elementos é mantida por um conjunto usando sua ordenação natural, independentemente de um comparador
  explícito ser fornecido ou não. Isso deve ser consistente com equals para implementar corretamente a interface Set.

  Ele também pode ser ordenado por um Comparator fornecido no momento da criação do conjunto, dependendo de qual
  construtor é usado.

![TreeSet](https://github.com/luanhroliveira/assets/blob/main/mestreDosCodigosDB1/java/escudeiro/Set-TreeSet-SortedSet-In-Java-Collection.png "TreeSet")

Como podemos ver na imagem acima, o NavigableSet estende a interface do Set. A interface do NavigableSet fornece a
implementação para navegar pelo Set, como visto no tópico acima. A classe que implementa o NavigableSet fornece uma
maneira de navegar por esta árvore.

````java
public class TreeSetClass {

    public static void main(String[] args) {

        Set<String> treeSet = new TreeSet<>();

        // Adicionando elementos utilizando o método add().
        treeSet.add("A");
        treeSet.add("B");
        treeSet.add("C");

        // Duplicatas não serão inseridas
        treeSet.add("C");

        // Os elementos são armazenados na ordem de classificação natural padrão (ascendente)
        System.out.println(treeSet);
    }
}
````

Saída:

    [A, B, C]

### Collection:

- A interface Collection é absoluta na hierarquia de coleções, dela descendem todas as interfaces que foram descritas
  neste documento, que formam a base das coleções genéricas de Java.

  E com ela, podemos manipular os dados como já visto nas demais interfaces utilizando os métodos de adicionar, remover,
  obter, entre outros.

  Veja alguns exemplos:

````java
public class CollectionClass {

    public static void main(String[] args) {

        Collection<String> nomes = new ArrayList();

        nomes.add("João");
        nomes.add("Maria");
        nomes.add("Eduardo");
        nomes.add("Silvana");
        nomes.add("Mário");

        System.out.println("Lista de nomes: " + nomes);

        nomes.remove("Mário");

        System.out.println("Lista de nomes após remoção: " + nomes);

        nomes.contains("Silvana");

        System.out.println("Contém o nome Silvana? " + nomes);

        for (String nome : nomes) {
            System.out.println("Nome: " + nome);
        }
    }
}
````

Saída:

    Lista de nomes: [João, Maria, Eduardo, Silvana, Mário]
    Lista de nomes após remoção: [João, Maria, Eduardo, Silvana]
    Contém o nome Silvana? true
    Nome: João
    Nome: Maria
    Nome: Eduardo
    Nome: Mário

### Iterator:

- A interface Iterator, como já visto em diversas implementações efetuadas neste documento, serve para percorrer as
  coleções.

  É chamado de Iterator porque "iterar" é o termo técnico para looping.

  Ao usar i Iterator, podemos executar operações de leitura e remoção. E é o único cursor disponível para toda a
  estrutura de coleção.

  Veja um exemplo da sua implementação:

````java
public class IteratorClass {

    public static void main(String[] args) {

        ArrayList<Integer> al = new ArrayList<Integer>();

        // Incrementando lista
        for (int i = 0; i < 10; i++)
            al.add(i);

        // Exibindo elementos da lista
        System.out.println(al);

        // no início itr(cursor) apontará para o índice logo antes do primeiro elemento em al.
        Iterator itr = al.iterator();

        // verificando o próximo elemento onde a condição é verdadeira
        // até que haja um único elemento na lista usando o método hasnext().
        while (itr.hasNext()) {
            //  Movendo cursor para o próximo elemento.
            int i = (Integer) itr.next();

            // Obtendo elementos pares um por um
            System.out.print(i + " ");

            // Removendo elementos ímpares.
            if (i % 2 != 0)
                itr.remove();
        }

        System.out.println();

        // Exibindo elementos dentro do objeto.
        System.out.println(al);
    }
}
````

Saída:

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    0 1 2 3 4 5 6 7 8 9
    [0, 2, 4, 6, 8]

---

### Bibliografias:

<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/PriorityQueue.html">ORACLE (PRIORITY QUEUE)</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/LinkedList.html"> ORACLE (LINKED LIST)</a></li>
<li><a href="https://www.educative.io/blog/data-structures-linked-list-java-tutorial">EDUCATIVE</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/Vector.html">ORACLE (VECTOR)</a></li>
<li><a href="https://www.devmedia.com.br/diferenca-entre-arraylist-vector-e-linkedlist-em-java/29162">DEV MEDIA</a></li>
<li><a href="https://www.w3schools.com/java/java_arraylist.asp">W3SCHOOLS</a></li>
<li><a href="https://www.devmedia.com.br/explorando-a-classe-arraylist-no-java/24298">DEV MEDIA</a></li>
<li><a href="http://www.linhadecodigo.com.br/artigo/3669/trabalhando-com-a-interface-set-no-java.aspx#:~:text=Considerada%20uma%20interface%20que%20faz,nenhum%20dado%20duplicado%20na%20cole%C3%A7%C3%A3o.">LINHA DE CÓDIGO</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/HashSet.html">ORACLE (HASH SET)</a></li>
<li><a href="https://www.w3schools.com/java/java_hashset.asp">W3SCHOOLS (HASH SET)</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/LinkedHashSet.html">ORACLE (LINKED HASH SET)</a></li>
<li><a href="https://www.devmedia.com.br/conjuntos-classificados-sortedset-em-java-gerando-jogos-para-mega-sena/26430">DEV MEDIA (SORTED SET)</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/NavigableSet.html">ORACLE (NAVIGABLE SET)</a></li>
<li><a href="https://www.devmedia.com.br/diferencas-entre-treeset-hashset-e-linkedhashset-em-java/29077">DEV MEDIA (TREE SET)</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/TreeSet.html">ORACLE (TREE SET)</a></li>
<li><a href="https://www.devmedia.com.br/visao-geral-da-interface-collection-em-java/25822">DEV MEDIA (COLLECTION)</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/Iterator.html">ORACLE (ITERATOR)</a></li>
<li><a href="https://www.w3schools.com/java/java_iterator.asp">W3SCHOOLS (ITERATOR)</a></li>