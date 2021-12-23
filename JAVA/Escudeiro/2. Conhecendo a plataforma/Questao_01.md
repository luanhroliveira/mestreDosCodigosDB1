### O Java possui vários tipos de dados primitivos para resolvermos diversos problemas e, para cada tipo primitivo, existe uma classe WRAPPER. Pontue:

---

#### Diferença entre os tipos primitivos e as classes Wrapper:

- <b>Wrapper:</b> Uma classe do tipo Wrapper em Java é usada para conversão de um determinado tipo de dado primitivo
  para objeto e de objeto para primitivo. E também armazenam seus dados na memória heap enquanto que as variáveis locais
  preservadas na pilha.
- <b>Primitivos:</b> As variáveis primitivas consomem menos memória, são mais rápidas e permitem operações mais
  complexas como conversão de tipo "key" em HashMap, por exemplo. E são muito eficientes em laços e expressões.

#### Quais são os tipos primitivos e suas classes Wrapper?

<table>
    <tbody>
        <tr>
            <th>Primitivo</th>
            <th>Classe Wrapper</th>
        </tr>
        <tr>
            <td>boolean </td>
            <td>Boolean </td>
        </tr>
        <tr>
            <td>Byte </td>
            <td>Byte </td>
        </tr>
        <tr>
            <td>Char </td>
            <td>Character </td>
        </tr>
        <tr>
            <td>double </td>
            <td>Double </td>
        </tr>
        <tr>
            <td>Float </td>
            <td>Float </td>
        </tr>
        <tr>
            <td>Int </td>
            <td>Integer </td>
        </tr>
        <tr>
            <td>Long </td>
            <td>Long </td>
        </tr>
        <tr>
            <td>short </td>
            <td>Short </td>
        </tr>
    </tbody>
</table>

#### Qual o valor default de cada tipo primitivo e de cada classe Wrapper?

- <b>Primitivos:</b> Nos casos de tipos numéricos são iniciados em 0 (zero). O boolean com false e o char é inicializado
  com ‘\u0000’ ou 0.
- <b>Wrapper:</b> O valor default para atributos de referência (objetos) é <b>null.</b>

#### Como consigo converter cada tipo primitivo em uma classe Wrapper e como consigo converter cada classe Wrapper em um tipo primitivo?
````java
    public class Application {
        public static void main(String[] args) {
    
            /* Declaração das variáveis do tipo primitivo */
            int primitivoInt = 0;
            float primitivoFloat = 0;
            long primitivoLong = 0L;
            short primitivoShort = 0;
            double primitivoDouble = 0;
            char primitivoChar = 0;
            byte primitivoByte = 0;
            boolean primitivoBoolean = false;
    
            /* Convertendo do primitivo para wrapper */
            Integer wrapperInteger = Integer.valueOf(primitivoInt);
            Float wrapperFloat = Float.valueOf(primitivoFloat);
            Long wrapperLong = Long.valueOf(primitivoLong);
            Short wrapperShort = Short.valueOf(primitivoShort);
            Double wrapperDouble = Double.valueOf(primitivoDouble);
            Character wrapperCharacter = Character.valueOf(primitivoChar);
            Byte wrapperByte = Byte.valueOf(primitivoByte);
            Boolean wrapperBoolean = Boolean.valueOf(primitivoBoolean);
    
            /* Convertendo de wrapper para primitivo */
            primitivoInt = wrapperInteger.intValue();
            primitivoLong = wrapperLong.longValue();
            primitivoShort = wrapperShort.shortValue();
            primitivoDouble = wrapperDouble.doubleValue();
            primitivoChar = wrapperCharacter.charValue();
            primitivoByte = wrapperByte.byteValue();
        }   
    }
````

#### Um exemplo de utilização de cada tipo durante o desenvolvimento de software.

- Exemplo de conversão ***Value() wrapper para tipo primitivo:
````java
      public class Application {
          public static void main(String[] args) {
              //cria um objeto wrapper
              Integer velocidade = new Integer(587);
    
              //converte a variável velocidade para tipo primitivo
              double total = velocidade.doubleValue();
              short total1 = velocidade.shortValue();
              byte total2 = velocidade.byteValue();

              Float pi = new Float(3.14f);
              int valorPi = pi.intValue();

              System.out.println("Valor de PI arredondado: " + valorPi);
              System.out.println("Total: " + total);
              System.out.println("Total1: " + total1);
              System.out.println("Total2: " + total2);
          } 
      }
````

- Conversão de uma String para o tipo primitivo:
````java
      double soma = Double.parseDouble("685.65");
      System.out.println("Soma: "+ soma);
````

- Exemplo do método valueOf() com a classe String:
````java
      Integer idade = new Integer(39);
      String idadeString = String.valueOf(idade);
      String velocidade = new String("568.55");
      Double velocidadeDouble = Double.valueOf(velocidade);

      System.out.println("Idade string: " + idadeString);
      System.out.println("Velocidade double: " + velocidadeDouble);
````

---

### Bibliografias:

<li><a href="https://pt.strephonsays.com/wrapper-class-and-vs-primitive-type-in-java-1235">STREPHONSAYS</a></li>
<li><a href="https://www.guj.com.br/t/diferenca-entre-primitivo-e-wrapper-classes/211354">GUJ</a></li>
<li><a href="https://www.devmedia.com.br/classes-wrapper-explorando-as-classes-que-empacotam-os-tipos-primitivos/24136">DEVMEDIA</a></li>
<li><a href="http://www.inf.ufes.br/~vitorsouza/archive/2020/wp-content/uploads/java-br-curso-basico-novo-slides04.pdf">UFES</a></li>
<li><a href="http://www.mauda.com.br/?p=1177">MAUDA</a></li>

