### É comum a necessidade de armazenamento de variáveis em memória sequencial. O Java permite esta implementação com o uso de arrays. Mostre, por meio de algoritmos, utilizando no mínimo dois tipos primitivos e dois tipos não primitivos (classes wrappers), como podemos:

---

#### Declarar um array:

- Um array em Java pode ser declarada como qualquer outra variável, basta após declarar o tipo, adicionar colchetes '[]'
  .

````java
public class Declarar {
    public static void main(String[] args) {
        int[] ints;
        ints = new int[10];
        long[] longs;
        longs = new long[11];

        Integer[] integers = new Integer[10];
        Long[] longsWrapper = new Long[15];
    }
}
````

#### Inicializar:

- Para iniciliar um array, adicionamos uma lista de valores separados por vírgula entre chaves '{}'.

````java
public class Inicializar {
    public static void main(String[] args) {
        int[] ints = {10, 20, 30};
        long[] longs = {20, 30, 40};

        Integer[] integers = {30, 40, 50};
        Long[] longsWrapper = {10L, 20L, 40L};
    }
}
````

#### Acessar posições:

- Para acessarmos uma determinada posição num array, basta definirmos qual posição desejamos dentro dos colchetes
  variavel[].

````java
public class acessarPosicoes {
    public static void main(String[] args) {
        int[] ints = {10, 20, 30};
        System.out.println("Elemento 3 do ints: " + ints[2]);

        long[] longs = {20, 30, 40};
        System.out.println("Elemento 2 do longs: " + longs[1]);

        Integer[] integers = {30, 40, 50};
        System.out.println("Elemento 1 do integers: " + integers[0]);

        Long[] longsWrapper = {10L, 20L, 40L};
        System.out.println("Elemento 3 do longsWrapper: " + longsWrapper[2]);
    }
}
````

#### Percorrer um array:

- Para percorrer um array, podemos utilizar a instrução <i><b>for()</b></i>:

````java
public class Percorrer {
    public static void main(String[] args) {

        int[] ints = {10, 20, 30};
        for (int i : ints) {
            System.out.printf("Valor %d%n", i);
        }

        long[] longs = {20, 30, 40};
        for (long i : longs) {
            System.out.printf("Valor %d%n", i);
        }

        Integer[] integers = {30, 40, 50};
        for (Integer i : integers) {
            System.out.printf("Valor %d%n", i);
        }

        Long[] longsWrapper = {10L, 20L, 40L};
        for (Long i : longsWrapper) {
            System.out.printf("Valor %d%n", i);
        }
    }
}
````

---

### Bibliografia:

<li><a href="https://docs.oracle.com/javase/specs/jls/se8/html/jls-10.html#jls-10.6">ORACLE</a></li>
<li><a href="http://www.bosontreinamentos.com.br/java/como-acessar-os-elementos-de-um-array-unidimensional-em-java/#:~:text=Os%20elementos%20em%20um%20array,10%20%2D1%20%3D%20%C3%ADndice%209.">BÓSSON TREINAMENTOS</a></li>
<li><a href="https://www.delftstack.com/pt/howto/java/how-to-initialize-an-array-in-java/">DELFT STACK</a></li>
<li><a href="https://www.baeldung.com/java-initialize-array">BAELDUNG</a></li>
<li><a href="https://stackoverflow.com/questions/1938101/how-to-initialize-an-array-in-java">STACK OVERFLOW</a></li>
<li><a href="https://www.devmedia.com.br/trabalhando-com-arrays-em-java/25530">DEV MEDIA</a></li>
