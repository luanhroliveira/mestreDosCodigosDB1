<html lang="pt-BR">
<h3>
    3. Para começarmos desenvolver em Java, precisamos de muito pouco. Basta um editor de texto, uma outra coisinha que você
       aprendeu na questão de número 2 e um terminal. Crie uma classe Java utilizando um editor qualquer. Esta classe deve
       ter um método main que imprima a frase “Hello World!”, para começarmos com o pé direito esta aventura de programação.
   <br>
    Agora faça uma explanação sobre:
    <ui>
        <li>O que você precisou para resolver esta questão;</li>
        <li>O comando que você usou para compilar;</li>
        <li>O comando que você usou para executar;</li>
        <li>Qual é a estrutura miníma de uma classe Java;</li>
        <li>O que é o método main e qual a sua importância;</li>
        <li>O que é e em que momento da resolução da questão foi gerado o BYTECODE;</li>
    </ui>
</h3>

---

### 3.1 O que você precisou para resolver esta questão?

Utilizei como editor de texto a IDE IntelliJ IDEA 2021.2.3 para a escrita do método 'main', para desenvolvimento,
utilizei o JDK e para a execução JRE.

### 3.2 O comando que você usou para compilar?

Para efetuar a compilação, utilizei o seguinte comando:

    javac Application.java

### 3.3 O comando que você usou para executar?

Para executar a aplicação, utilizei o comando:

    java Application.java

### 3.4 Qual é a estrutura miníma de uma classe Java?

A classe deve estar em um arquivo fonte e deve ir com um par de chaves "{}" (onde os métodos são implementados), e devem
sempre serem iniciadas com letra maiúscula.

Exemplo:

      public class NomeDaClasse{
      }

### 3.5 O que é o método main e qual a sua importância?

O método main determina o ponto de início de execução de uma aplicação Java. Todas as classes podem contér um método
main. Mas na hora de executar, deve-se definir, através do primeiro argumento, para o interpretador o main a ser
executado.

A JVM, quando executada, procura pela aplicação o método main para iniciar-se a execução do código implementado. Assim,
faz-se de extrema necessidade ao menos um método main para que a aplicação funcione.

Por ser um método padrão, deve seguir algumas regras, como: ser público, estático, sem retorno (void), com o nome <b>
main</b> e receber um argumento array do tipo string.

Exemplo:

      public class Application {
         public static void main(String[] args) {
            System.out.println("Hello World!");
         }
      }

### 3.6 O que é e em que momento da resolução da questão foi gerado o BYTECODE?

o <b>BYTECODE</b> é gerado no momento da compilação. No Java, é a forma como a JVM entende o programa desenvolvido. Na
compilação é gerado o BYTECODE e a JVM traduz para a máquina, fazendo com que ela executa os algorítimos implementado na
aplicação.

O grande diferencial do Java, é que o BYTECODE é gerado para que a JVM interprete, e não para o SO (sistema operacional)
. O que dá o poder da aplicação rodar em qualquer plataforma, basta apenas ter o suporte para a JVM.

---

### Bibliografia:

<ui>
    <li><a href="https://www.devmedia.com.br/entendendo-a-estrutura-de-um-codigo-java/24622#:~:text=Em%20java%20a%20classe%20deve,sempre%20inicia%20com%20letra%20mai%C3%BAscula.">DEVMEDIA</a></li>
    <li><a href="https://www.dca.fee.unicamp.br/cursos/PooJava/classes/met_main.html#:~:text=Toda%20classe%20pode%20ter%20um,execu%C3%A7%C3%A3o%20de%20qualquer%20aplica%C3%A7%C3%A3o%20Java.&text=O%20m%C3%A9todo%20main%20%C3%A9%20um,definido%20como%20um%20m%C3%A9todo%20est%C3%A1tico.">UNICAMP</a></li>
    <li><a href="https://pt.wikipedia.org/wiki/Bytecode_Java">WIKIPEDIA</a></li>
    <li><a href="https://www.devmedia.com.br/bytecode-escondendo-e-revelando/12302">DEVMEDIA (BYTECODE)</a></li>
</ui>
</html>