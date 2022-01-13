### Trabalhar com sistemas que manipulam valores decimais é uma tarefa crítica e que deve exigir o máximo de atenção do desenvolvedor. Trabalhar com Double pode trazer uma certa dificuldade quando precisamos de precisão em operações matemáticas de valores decimais. Uma alternativa para resolver esse problema é utilizar a classe BigDecimal, que trabalha com pontos flutuantes de precisão arbitrária, conseguindo estipular o nível de precisão do valor. Diante disso, vamos aprender a trabalhar com esta classe. Faça exemplos de algoritmo que:

---

#### Converta uma String para BigDecimal:

- Para converter uma String em BigDecimal, podemos utilizar o construtor da classe BigDecimal.

  Exemplo:

````java
  String str = "100";
  BigDecimal varBigDecimal = new BigDecimal(str);
````

#### Converta um Double para BigDecimal:

- Para converter um Double em BigDecimal, podemos utilizar o método valueOf() da classe BigDecimal.

  Exemplo:

````java
  Double varDouble = 2.0;
  BigDecimal varBigDecimal = BigDecimal.valueOf(varDouble);
````

#### Execute as operações matemáticas de subtração, adição, divisão, multiplicação e potência de números decimais, demonstrando diferentes estratégias de arredondamento em todas as operações:

- Para efetuarmos as operações básicas de matemática, criei funções com nomes respectivos a sua ação para facilitar o
  entendimento.

  Já para os arredondamentos, utilizei a função <b>Math.round()</b> que tem como retorno o arredondamento para cima caso
  o número após a vírgula seja superior ou igual a cinco, ou arredondamento para baixo caso o número após a vírgula seja
  inferior a cinco. Em outras palavras, retorna o long mais próximo do valor real, ou seja, se colocarmos o número 5.2
  dentro da função, ele retornará o número 5.

  Ainda falando sobre o arredondamento, existem diversas formas de efetua-lo. Tomei a liberdade de criar duas funções
  semelhantes para arredondamento para cima, ou para baixo e que possuem apenas duas casas decimais, conforme o que o
  programador escolher.

````java
public class Calc {

    /* SUBTRAÇÃO */
    public Double subtracao(Double num1, Double num2) {
        return num1 - num2;
    }

    /* ADIÇÃO */
    public Double adicao(Double num1, Double num2) {
        return num1 + num2;
    }

    /* ADIÇÃO */
    public Double divisao(Double num1, Double num2) {
        return num1 / num2;
    }

    /* ADIÇÃO */
    public Double multiplicacao(Double num1, Double num2) {
        return num1 * num2;
    }

    /* ARREDONDAMENTO */
    public Long arredondamento(Double num1) {
        return Math.round(num1);
    }

    public String arredondamentoParaCima(Object obj) {
        DecimalFormat df = new DecimalFormat("0.00");
        df.setRoundingMode(RoundingMode.HALF_UP);
        return df.format(obj);
    }

    public String arredondamentoParaBaixo(Object obj) {
        DecimalFormat df = new DecimalFormat("0.00");
        df.setRoundingMode(RoundingMode.HALF_DOWN);
        return df.format(obj);
    }

    public static void main(String[] args) {
        Calc calc = new Calc();

        Double resultSubtracao = calc.subtracao(3.4, 2.1);
        Double resultAdicao = calc.adicao(1D, 2D);
        Double resultDivisao = calc.divisao(2.0, 5D);
        Double resultMultiplicacao = calc.multiplicacao(5.6, 6.5);

        Long result = calc.arredondamento(calc.adicao(1.56, 2.392));

        String resultadoArredondamentoParaCima = calc.arredondamentoParaCima(resultAdicao);
        String resultadoArredondamentoParaBaixo = calc.arredondamentoParaBaixo(resultDivisao);
    }
}
````

Como se pode observar, o retorno das funções arredondamentoParaCima() e arredondamentoParaBaixo() são do tipo String.

#### Faça a comparação entre 2 objetos do tipo BigDecimal.

- Para se comparar dois objetos do tipo BigDecimal, podemos utilizar o equals e o compareTo.

    - <b>equals()</b> verifica se dois objetos são iguais ou não;
    - <b>compareTo()</b> verifica qual dos dois é 'menor que', 'igual a' ou 'maior que' o outro.

````java
    BigDecimal obj1 = new BigDecimal("10");
    BigDecimal obj2 = new BigDecimal("x");

    Boolean resultEquals = obj1.equals(obj2);
    Integer resultCompareTo = obj1.compareTo(obj2);
````

Como podemos observar, o equals() retorna um boolean enquanto o compareTo() retorna um inteiro.

---
