### O Java fornece uma segunda forma de trabalhar com estrutura de dados tão importante quanto a primeira. São as classes e interfaces relacionadas a trabalhar com mapas. Veja o diagrama de classes e:

![Map](https://github.com/luanhroliveira/assets/blob/main/mestreDosCodigosDB1/java/escudeiro/map.png "Map")

- Demonstre, por algoritmos, a utilização de cada uma delas, ressaltando qual problema cada uma resolve e qual a
  importância de fazer a escolha certa.

---

### Map:

- A interface Map tem como característica armazenar os seus itens em pares "chave/valor". E, através da chave, é
  possível obter o seu respetivo valor. E essa chave não pode ser repetida, se caso ocorrer de ter uma chave repetida,
  será substituída pela última chamada.

  Por essa característica de chave/valor, ela se torna ideal para cenários do tipo dicionário.

  Como por exemplo, um mapa de turmas e alunos, onde cada turma (chave) está associada a uma lista de alunos (valor).

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

  Em Hashtable, especificamos um objeto que é usado como chave e o valor que queremos associar a essa chave. A chaveé
  então criptografada e o código de hash resultante é usado como o índice no qual o valor é armazenado na tabela.

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

---

### Bibliografias:

<li><a href="https://www.devmedia.com.br/conhecendo-a-interface-map-do-java/37463">DEV MEDIA (MAP)</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/util/Hashtable.html">ORACLE (HASHTABLE)</a></li>
<li><a href="https://mauricio.github.io/2020/10/15/implementando-uma-hashtable-em-java.html">MAURICIO (HASHTABLE)</a></li>
<li><a href="https://www.devmedia.com.br/hashmap-java-trabalhando-com-listas-key-value/29811">DEV MEDIA (HASHMAP)</a></li>
