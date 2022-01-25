### O Java fornece uma segunda forma de trabalhar com estrutura de dados tão importante quanto a primeira. São as classes e interfaces relacionadas a trabalhar com mapas. Veja o diagrama de classes e:

![Map](https://github.com/luanhroliveira/assets/blob/main/mestreDosCodigosDB1/java/escudeiro/map.png "Map")

- Demonstre, por algoritmos, a utilização de cada uma delas, ressaltando qual problema cada uma resolve e qual a
  importância de fazer a escolha certa.

---

### Map

- A interface Map tem como característica armazenar os seus itens em pares "chave/valor". E, através da chave, é
  possível obter o seu respetivo valor. E essa chave não pode ser repetida, se caso ocorrer de ter uma chave repetida,
  será substituída pela última chamada.

  Por essa característica de chave/valor, ela se torna ideal para cenários do tipo dicionário.

  Como, por exemplo, um mapa de turmas e alunos, onde cada turma (chave) está associada a uma lista de alunos (valor).

  Por ser uma interface, não é possível criar objetos do tipo map. Portanto, devemos utilizar uma classe que estenda
  esse Map.

  Veja um exemplo de aplicação:

````java
public class MapClass {

    public static void main(String args[]) {

        Map<String, Integer> stringIntegerMap = new HashMap<String, Integer>();

        // Inserindo chaves e valores utilizando o método put().
        stringIntegerMap.put("a", new Integer(100));
        stringIntegerMap.put("b", new Integer(200));
        stringIntegerMap.put("c", new Integer(300));
        stringIntegerMap.put("d", new Integer(400));

        // Percorrendo o mapa usando o for-each
        for (Map.Entry<String, Integer> me : stringIntegerMap.entrySet()) {

            // Imprimindo as chaves
            System.out.print(me.getKey() + ": ");
            System.out.println(me.getValue());
        }
    }
}
````

Saída:

    a: 100
    b: 200
    c: 300
    d: 400

### Hashtable

- A classe Hashtable implementa uma tabela hash, que faz o mapeamento de chaves para valores. E podemos usar qualquer
  objeto que não seja nulo como chave ou valor. E para se obter os objetos com sucesso, é necessário que os objetos
  mapeados como chave devem implementar o método hashCode e equals.

  Em Hashtable, especificamos um objeto que é usado como chave e o valor que queremos associar a essa chave. A chave é
  então criptografada e o código de hash resultante é usado como o índice onde o valor é armazenado na tabela.

  Veja um algoritmo de implementação do Hashtable:

````java
class HashtableClass {

    public static void main(String args[]) {

        Hashtable<Integer, String> hashtableOne = new Hashtable<>();

        Hashtable<Integer, String> hashtableTwo = new Hashtable<Integer, String>();

        // Inserindo elementos utilizando o método put().
        hashtableOne.put(1, "one");
        hashtableOne.put(2, "two");
        hashtableOne.put(3, "three");

        hashtableTwo.put(4, "four");
        hashtableTwo.put(5, "five");
        hashtableTwo.put(6, "six");

        // Imprimindo os valores no console
        System.out.println("Mapeamentos de hashtableOne : " + hashtableOne);
        System.out.println("Mapeamentos de hashtableTwo : " + hashtableTwo);
    }
}
````

Saída:

    Mapeamentos de hashtableOne: {3=three, 2=two, 1=one}
    Mapeamentos de hashtableTwo: {6=six, 5=five, 4=four}

### HashMap

- O HashMap implementa a interface Map, e fornece a implementação básica de Map. Da mesma forma, armazena os dados em
  pares de chave e valor. Um objeto é usado como chave para outro objeto valor. E se tentar adicionar chave duplicada, a
  última a ser inserida substituirá a primeira.

  HashMap é semelhante a HashTable, mas não é sincronizado. Ele também permite armazenar as chaves nulas, mas deve haver
  apenas um objeto de chave nula e pode haver qualquer número de valores nulos.

  Veja sua implementação:

````java
public class HashMapClass {

    public static void main(String[] args) {

        HashMap<String, Integer> map = new HashMap<>();

        // Inserindo elementos utilizando o método put().
        map.put("a", 10);
        map.put("b", 30);
        map.put("c", 20);

        // Exibindo no console o tamanho do map.
        System.out.println("O tamanho do map é: " + map.size());

        // Exibindo todos os elementos de map.
        System.out.println(map);

        //Verificando se uma chave existe no map, se existir, exibe o valor no console.
        if (map.containsKey("a")) {

            // Mapeamento
            Integer a = map.get("a");

            // Exibindo no console o valor de 'a'.
            System.out.println("valor para a chave \"a\" é: " + a);
        }
    }
}
````

Saída:

    O tamanho do map é: 3
    {c=20, a=10, b=30}
    valor para a chave "a" é: 10

### LinkedHashMap

- a classe LinkedHashMap implementa a interface Map e estende a classe HashMap, e herda a sua implementação. Tem o seu
  funcionamento muito semelhante a HashMap, com um diferencial de manter uma ordem de elementos inseridos nela.

  HashMap forneceu a vantagem de inserção, pesquisa e exclusão rápidas, mas nunca manteve o controle e a ordem de
  inserção que o LinkedHashMap fornece, onde os elementos podem ser acessados na sua ordem de inserção.

  Em sumo, é o mesmo que HashMap com um recurso adicional que mantém a ordem de inserção.

````java
public class LinkedHashMapClass {

    public static void main(String args[]) {

        LinkedHashMap<String, String> linkedHashMap = new LinkedHashMap<String, String>();

        // Adicionando elementos utilizando o método put().
        linkedHashMap.put("one", "1");
        linkedHashMap.put("two", "2");
        linkedHashMap.put("four", "4");

        // Exibindo os elementos no console.
        System.out.println(linkedHashMap);

        // Exibindo o valor especifico de uma chave.
        System.out.println("Obtendo valor para a chave 'one': " + linkedHashMap.get("one"));

        // Exibindo o tamanho com o método size().
        System.out.println("Tamanho do map: " + linkedHashMap.size());

        // Verificando se o map é vazio ou não.
        System.out.println("Map está vazio? " + linkedHashMap.isEmpty());

        // Verificando se uma chave já existe no map.
        System.out.println("Contém a chave 'two'? " + linkedHashMap.containsKey("two"));

        // Usando o método containsValue() para verificar se um valor existe.
        System.out.println("Contém o valor 'one'? " + linkedHashMap.containsValue("1"));

        // Usando o método remove() para remover um elemento.
        System.out.println("Excluir elemento 'one': " + linkedHashMap.remove("one"));

        // Exibindo no console todos os elementos de map.
        System.out.println("Mapeamento de LinkedHashMap: " + linkedHashMap);
    }
}
````

Saída:

    {one=1, two=2, four=4} 
    Obtendo valor para a chave 'one': 1 
    Tamanho do map: 3 
    Map está vazio? false 
    Contém a chave 'two'? true 
    Contém o valor 'one'? true 
    Excluir elemento 'one': 1 
    Mapeamentos de LinkedHashMap: {2, 4}

### SortedMap

- A interface SortedMap estende de Map, e fornece uma ordenação total de seus elementos, onde os elementos podem ser
  percorridos em ordem ordenada de chaves.

  Por ser interface, não se pode criar um objeto do tipo SortedMap, a classe que implementa essa interface é a TreeMap (
  veremos mais a frente).

  É Indicado usar o TreeMap quando não for permitido chave ou valor nulo e quando for necessário que as chaves sejam
  classificadas por ordenação natural ou por um Comparator específico.

````java
public class SortedMapClass {

    public static void main(String[] args) {

        SortedMap<Integer, String> sortedMap = new TreeMap<Integer, String>();

        // Inserindo elementos utilizando put().
        sortedMap.put(new Integer(2), "two");
        sortedMap.put(new Integer(3), "three");
        sortedMap.put(new Integer(5), "five");
        sortedMap.put(new Integer(4), "four");
        sortedMap.put(new Integer(1), "one");
        Set set = sortedMap.entrySet();

        // Usando iterator em SortedMap.
        Iterator iterator = set.iterator();

        // Map de travessia. Observe que a travessia produziu saída classificada (por chaves).
        while (iterator.hasNext()) {
            Map.Entry entry = (Map.Entry) iterator.next();

            int chave = (Integer) entry.getKey();
            String valor = (String) entry.getValue();

            System.out.println("Chave " + chave + "  valor : " + valor);
        }
    }
}
````

Saída:

    Chave : 1  valor : one
    Chave : 2  valor : two
    Chave : 3  valor : three
    Chave : 4  valor : four
    Chave : 5  valor : five

### NavigableMap

- A interface NavigableMap estende de SortedMap e fornece métodos de navegação convenientes como floorKey, ceilingKey e
  higherKey.

````java
public class NavigableMapClass {

    public static void main(String[] args) {

        NavigableMap<String, Integer> nm = new TreeMap<String, Integer>();

        // Inserindo elementos utilizando o método put().
        nm.put("C", 888);
        nm.put("Y", 999);
        nm.put("A", 444);
        nm.put("T", 555);
        nm.put("B", 666);
        nm.put("A", 555);

        // Exibindo elementos no console.
        System.out.println("Mapeamentos do NavigableMap : " + nm);

        System.out.printf("Descendente Set: %s%n", nm.descendingKeySet());
        System.out.printf("Floor Entry: %s%n", nm.floorEntry("L"));
        System.out.printf("First Entry: %s%n", nm.firstEntry());
        System.out.printf("Last Key: %s%n", nm.lastKey());
        System.out.printf("First Key: %s%n", nm.firstKey());
        System.out.printf("Original Map: %s%n", nm);
        System.out.printf("Reverse Map: %s%n", nm.descendingMap());
    }
}
````

Saída:

    Mapeamentos do NavigableMap: {A=555, B=666, C=888, T=555, Y=999}
    Descendente Set: [Y, T, C, B, A]
    Floor Entry: C=888
    First Entry: A= 555
    Last Key: Y
    First Key: A
    Original Map: {A=555, B=666, C=888, T=555, Y=999}
    Reverse Map: {Y=999, T=555, C=888, B =666, A=555}

### TreeMap

- A classe TreeMap implementa As interfaces Map, SortedMap e NavigableMap.

  A implementação de um TreeMap não é sincronizada no sentido de que se um Map for acessado por várias threads,
  concorrentemente e pelo menos uma das threads modificar o Map estruturalmente, ele deve ser sincronizado externamente.

  A ordem de armazenamento mantida pelo TreeMap deve ser consistente com equals como qualquer outro Map,
  independentemente dos comparadores explícitos.

  TreeMap não aceita chaves nulas, e se houver, lança uma NullPointerException, mas permite um ou mais valores nulos.

  Veja a sua implementação:

````java
public class TreeMapClass {

    public static void main(String[] args) {

        TreeMap<Integer, String> treeMap = new TreeMap<Integer, String>();

        // Inserindo elementos chave e valor com o método put().
        treeMap.put(10, "Dez");
        treeMap.put(15, "Quinze");
        treeMap.put(20, "Vinte");
        treeMap.put(25, "Vinte e cinco");
        treeMap.put(30, "Trinta");

        // Exibinto conteúdo de TreeMap no console.
        System.out.println("TreeMap: " + treeMap);
    }
}
````

Saída:

    TreeMap: {10=Dez, 15=Quinze, 20=Vinte, 25=Vinte e cinco, 30=trinta}

---

### Bibliografias:

<li><a href="https://www.devmedia.com.br/conhecendo-a-interface-map-do-java/37463">DEV MEDIA (MAP)</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/Hashtable.html">ORACLE (HASHTABLE)</a></li>
<li><a href="https://mauricio.github.io/2020/10/15/implementando-uma-hashtable-em-java.html">MAURICIO (HASHTABLE)</a></li>
<li><a href="https://www.devmedia.com.br/hashmap-java-trabalhando-com-listas-key-value/29811">DEV MEDIA (HASHMAP)</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/LinkedHashMap.html">ORACLE (LINKEDHASHMAP)</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/SortedMap.html">ORACLE (SORTEDMAP)</a></li>
<li><a href="https://stackoverflow.com/questions/7427758/how-to-use-sortedmap-interface-in-java">STACK OVERFLOW (SORTEDMAP)</a></li>
<li><a href="https://acervolima.com/interface-navigablemap-em-java-com-exemplo/">ACERVO LIMA (NAVIGABLEMAP)</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/TreeMap.html">ORACLE (TREEMAP)</a></li>
<li><a href="https://acervolima.com/como-criar-objetos-treemap-usando-interface-comparavel-em-java/">ACERVO LIMA (TREEMAP)</a></li>