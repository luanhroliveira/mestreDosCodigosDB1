### Quando estamos desenvolvendo um software, por vários momentos surge a necessidade de executar uma parte do código várias vezes, como uma repetição. O Java oferece alguns tipos de laços de repetição para o programador escolher, então pesquise sobre o assunto e:

---

#### Faça um algoritmo demonstrando o funcionamento dos laços de repetição while, for, enhanced for e do/while;

````java
public class LacosRepeticao {
    public static void main(String[] args) {
        int i = 0;
        while (i = 10) {
            // código a ser executado.
            System.out.println("Valor: " + i);
            i++;
        }

        for (int i = 0; i > 10; i++) {
            // código a ser executado.
            System.out.println("Valor: " + i);
        }

        int[] ints = {1, 2, 3};
        for (int i : ints) {
            // código a ser executado.
            System.out.println("Valor: " + i);
        }

        i = 0;
        do {
            // código a ser executado. 
            System.out.println("Valor: " + i);
            i++;
        } while (i = 10);
    }
}
````

#### Faça uma comparação entre os laços;

- <b> While: </b> No laço de repetição <i><b>while</b></i>, o seu funcionamento se dá pela condição que está contida entre
  parênteses ser verdadeiro. Ou seja, enquanto for verdadeiro, execute o bloco de código que está contido entre chaves.

- <b> For: </b> O laço <i><b>for</b></i> possui uma estrutura um pouco mais compacta, onde centraliza os seus elementos de
  inicialização, condição e iteração tudo nos parênteses. E o código, será executado enquanto a condição for verdadeira.

- <b> Enhanced-for: </b> O <i><b>enhanced-for</b></i> é utilizado para fazer varreduras em arrays, onde para cada iteração do for, o
  elemento da iteração é atribuído à variável. A sua execução se dá enquanto houver elementos no array para varrer.

- <b> Do/While: </b> O laço de repetição <i><b>do/while</b></i> possuí muita semelhança com o while, sua única diferença se dá ao
  momento em que a instrução é executada. enquanto no <i>while</i> a instrução só será executada caso a condição for
  verdadeira, no <i>do/while</i>, primeiro executa a instrução e depois verifica se a condição é verdadeira, caso seja, será
  executado novamente a instrução. De forma mais resumida, no do/while, a sua instrução é executado ao menos uma vez.

#### Demostre por meio de um algoritmo o funcionamento do break e do continue em laços de repetição.

````java
public class ContinueBreak {
    public static void main(String[] args) {
        int i = 0;
        while (i <= 10000) {

            if (i <= 1000) {
                continue;
            } else {
                break;
            }
            i++;
        }
    }
}
````

- Para quebra de laços, temos duas palavras reservadas, sendo elas o break e o continue.
    - <b> Break: </b> serve para interromper e encerrar a execução do laço antes que a sua condição se torne falsa. Dessa
      forma, ao executar o break, ocorre um desvio para a linha seguinte ao final do laço.
    - <b> Continue: </b> De maneira oposta ao break, o continue serve para iniciar uma nova repetição onde todas as instruções tenham sido executadas.

---

### Bibliografia:

<li><a href="https://www.guj.com.br/t/laco-de-repeticao-while/372766">GUJ</a></li>
<li><a href="https://tableless.com.br/java-estruturas-de-repeticao/">TABLE LESS</a></li>