4. Durante muito tempo, uma das maiores dificuldades na hora de programar era o gerenciamento de memória. Os
   desenvolvedores eram responsáveis pela sua alocação e liberação manualmente, o que levava a muitos erros e memory
   leaks. Hoje, em todas as plataformas modernas (incluindo Java), temos gerenciamento de memória automático através de
   algoritmos de coleta de lixo. Pesquise sobre Garbage Collector e faça uma explanação de como este algoritmo funciona
   na plataforma Java. Também implemente dois algoritmos em Java: um que exemplifique um possível erro de
   OutOfMemoryError e outro que mostre os cuidados tomados para não acontecer este tipo de erro durante o
   desenvolvimento de software.

---
- O <b>Garbage collection</b> Java é um processo onde os programas desenvolvidos em Java executam seu gerenciamento
  automático de memória. Quando os programas são executados pela JVM, os objetos são criados na memória heap, que é uma
  parte da memória dedicada para o programa. E é aí onde o <b>Garbage collection</b> entra em ação. Eventualmente esses
  objetos acabam ficando sem utilização, e ocupando espaço em memória (heap). Ao contrário do que dizem, o <b>Garbage
  collection</b> não exclui esses objetos, o que realmente acontece é que o <b>Garbage collection</b> recupera essa
  memória subjacente e a reutiliza para uma futura alocação de objeto.

  Todos objetos são gerenciados pela JVM, alcando-os na memória heap. Enquanto o objeto está sendo referenciado, ele é
  considerado ativo, pela JVM. A partir do momento que o objeto não é mais referenciado, de modo a que não possa mais
  ser acessado pelo código da aplicação, o <b>Garbage collection</b> o remove e recupera a memória não utilizada.


- Um erro comum gerado pela memória heap, é o <b>OutOfMemoryError</b>. Essa mensagem indica que o objeto não pode ser
  alocado no heap Java.

  As possíveis causa desta exceção são:
    - problemas de configuração, onde o tamanho do heap especificado é inssuficiente para o aplicativo.
    - O aplicativo mantém as referências aos objetos, de forma não intencional, evitando assim que os Garbage Collection
      aja.
    - Uso excessivo de finalizadores.

Veja um código que causa a exceção <b>OutOfMemoryError</b>:

    public class App {
        public static void main(String args[]) throws Exception {
            Integer[] arrayInteger = new Integer[100000 * 100000];
        }
    }

Uma possível solução para o erro <b>OutOfMemoryError</b> é configurar um heap maior, através do -Xmx da JVM ou um código
mais estruturado. De modo a que valíde, basicamente, os cenários das possíveis causas descritas acima.

---

### Bibliografias:

<li><a href="https://stackify.com/what-is-java-garbage-collection/">STACKIFY</a></li>
<li><a href="https://www.dynatrace.com/resources/ebooks/javabook/how-garbage-collection-works/">DYNATRACE</a></li>
<li><a href="https://qastack.com.br/programming/37335/how-to-deal-with-java-lang-outofmemoryerror-java-heap-space-error#:~:text=A%20maneira%20mais%20f%C3%A1cil%20de,isso%20resolver%C3%A1%20imediatamente%20seu%20OutOfMemoryError.">QASTACK</a></li>
