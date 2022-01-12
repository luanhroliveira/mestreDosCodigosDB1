### Um dos tipos mais utilizados na plataforma Java é o tipo String, com S maiúsculo. Strings em Java são objetos ou instâncias da classe java.lang.String que devem ser declaradas e instanciadas. Vamos, então, concentrar nossa energia no estudo deste tipo tão importante. Crie exemplos utilizando String mostrando:

---

#### Como criamos um objeto do tipo String?

- Para se criar um objeto do tipo String em Java, utilizamos o new String("TEXTO");

  Ficando da seguinte forma:

````java
    String texto = new String("TEXTO");
````

Dessa forma, a variável texto é um objeto do tipo String.

#### Como podemos concatenar uma String?

- Para unir duas ou mais strings, podemos utilizar o sinal de adição (+) ou utilizar o método .concat().

  Veja exemplos:

````java
    /* Com o sinal de adição (+) */
    String nomeSobrenome=nome+sobrenome;

    /* Com o método concat */
    String nomeSobrenome=nome.concat(sobrenome);
````

#### Quais os principais comportamentos de uma String?

- Uma String tem a característica de armazenar um caracter ou mais. Um objeto String é imutável, ou seja, o seu texto
  nunca é alterado.

  Sempre que a modificação for necessária, será utilizado mais espaço em memória para que uma nova String seja criada
  contendo a sua nova versão.

  Se uma variável for declarada sem a sua inicialização, o valor padrão a ser atribuído é null.

#### Como trabalhamos com String utilizando as classes StringBuilder e StringBuffer, pontuando a diferença entre elas e qual a importância de usá-las;

- Para se concatenar duas ou mais string, recomenda-se a utilização das classes StringBuilder ou StringBuffer.

  Ambas possuem funções semelhantes que é a de concatenar string, a diferença é que o StringBuffer é sincronizado, e o
  StringBuilder não é sincronizado. Portanto, para se garantir a consistência do código quando houver diversas threads,
  o ideal é utilizar o StringBuffer.

  Exemplos:

````java
    /* Utilizando StringBuilder */
    StringBuilder strBuilder = new StringBuilder();
    strBuilder.append(nome);
    strBuilder.append(sobreNome);

    /* Utilizando StringBuffer */
    StringBuffer strBuffer = new StringBuffer();
    strBuffer.append(nome);
    strBuffer.append(sobreNome);
````

#### Como transformamos String em outro tipo de dado?

- Como já vimos anteriormente, na [questão 01](Questao_01.md), podemos converter facilmente converter o tipo de dado
  utilizando os parses das classes Wrapper.

  Veja exemplo de conversão de String para int:

````java
    String numero = "23"
    int numeroConvertido = Integer.parseInt(numero);
````

No exemplo acima foi atribuído a String numero o valor 23 em forma de string, e, ao passar o valor da variável numero
para a variável numeroConvertido, foi utilizado o parse para alterar o tipo de dado. Dessa forma, a variável
numeroConvertido receberá o número 23 do tipo inteiro real.

#### Como podemos transformar qualquer tipo de dado em uma String.

- Da mesma forma descrita na questão acima, as classes Wrapper possuem métodos de conversão de dado. Sendo eles o
  CLASSE_WRAPPER.toString(), String.valueOf().

  Um exemplo do String.valueOf() seria:

````java
    String.valueOf(boolean b)
    String.valueOf(char c)
    String.valueOf(char[] data)
    String.valueOf(char[] data, int offset, int count)
    String.valueOf(double d)
    String.valueOf(float f)
    String.valueOf(int i)
    String.valueOf(long l)
    String.valueOf(Object obj) 
````

---

### Bibliografias:

<li><a href="https://www.devmedia.com.br/string-em-java-entendendo-e-utilizando-essa-classe/25503">DEV MEDIA</a></li>
<li><a href="https://dicasdejava.com.br/java-como-converter-string-para-int/#:~:text=Para%20converter%20uma%20String%20em,parseInt%20da%20class%20wrapper%20Integer%20.">DICAS DE JAVA</a></li>
<li><a href="https://www.devmedia.com.br/diferencas-entre-string-stringbuilder-e-stringbuffer-em-java/29865">DEV MEDIA</a></li>
<li><a href="https://pt.stackoverflow.com/questions/208388/qual-a-diferen%C3%A7a-entre-usar-object-tostring-e-string-valueof/208391">STACK OVERFLOW</a></li>
<li><a href="https://www.delftstack.com/pt/howto/java/how-to-convert-an-integer-to-a-string-in-java/">DELFT STACK</a></li>
