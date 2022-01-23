### Trabalhar com estrutura de dados utilizando arrays pode ser uma tarefa difícil, pois arrays não permitem o redimensionamento. É impossível buscar um determinado elemento cujo índice é desconhecido, não conseguimos saber quantas posições do array foram populadas sem criarmos métodos adicionais para isso, entre outros problemas. Assim, para facilitar a vida do programador, foi criado um conjunto de interfaces e classes conhecidas como Collections Framework, que se encontra no pacote java.util. Veja o diagrama de classes abaixo e:

---

![Collections](https://github.com/luanhroliveira/assets/blob/main/mestreDosCodigosDB1/java/escudeiro/collections.png "Collections")

#### Demonstre, por meio de algoritmos, a utilização de cada uma delas, ressaltando qual o tipo de problema cada uma resolve e qual a importância de fazer a escolha certa.

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

---

### Bibliografias:

<li><a href="https://docs.oracle.com/javase/7/docs/api/java/util/PriorityQueue.html">ORACLE (PRIORITY QUEUE)</a></li>
<li><a href="https://docs.oracle.com/javase/7/docs/api/java/util/LinkedList.html"> ORACLE (LINKED LIST)</a></li>
<li><a href="https://www.educative.io/blog/data-structures-linked-list-java-tutorial">EDUCATIVE</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/Vector.html">ORACLE (VECTOR)</a></li>
<li><a href="https://www.devmedia.com.br/diferenca-entre-arraylist-vector-e-linkedlist-em-java/29162">DEV MEDIA</a></li>
<li><a href="https://www.w3schools.com/java/java_arraylist.asp">W3SCHOOLS</a></li>
<li><a href="https://www.devmedia.com.br/explorando-a-classe-arraylist-no-java/24298">DEV MEDIA</a></li>
