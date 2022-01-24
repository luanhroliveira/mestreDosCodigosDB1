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

---

### Bibliografias:

<li><a href="https://www.devmedia.com.br/conhecendo-a-interface-map-do-java/37463">DEV MEDIA (MAP)</a></li>