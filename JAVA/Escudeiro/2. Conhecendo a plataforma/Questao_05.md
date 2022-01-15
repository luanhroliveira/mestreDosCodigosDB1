### No Java 8 foi introduzida uma nova API para manipulação de datas e horas. Vamos entender quais classes e métodos foram incluídos. Faça uma pesquisa sobre as classes listadas abaixo e mostre, por meio de algorítimos, onde cada uma pode ser usada e como podemos criar objetos de datas, manipular datas, extrair partes de datas, realizar comparações entre datas, alterar datas e converter entre os diversos tipos de datas listadas:

---

#### LocalDate:

- Como visto na introdução, a nova API disponibiliza uma grande variedade de classes e métodos para se trabalhar com
  datas no Java. E a classe principal é a LocalDate (classe da qual falaremos a seguir).

  Veja um exemplo onde é possível recuperar diversos dados de uma data:

````java
    LocalDate localDate=LocalDate.now();
    System.out.println(localDate);
    System.out.println("Dia da semana: "+localDate.getDayOfWeek().name());
    System.out.println("Dia da semana: "+localDate.getDayOfWeek().ordinal());
    System.out.println("Mes: "+localDate.getMonthValue());
    System.out.println("Mes: "+localDate.getMonth().name());
    System.out.println("Ano: "+localDate.getYear());
````

A saída deste trecho de código deve corresponder a isso:

    2022-01-15  
    Dia da semana: SATURDAY
    Dia da semana: 5
    Mes: 1
    Mes: JANUARY
    Ano: 2022

Ainda sobre o LocalDate, temos alguns métodos que nos auxiliam nas comparações entre datas, como por exemplo:

````java
    LocalDate localDateAntigo=LocalDate.of(2010,3,7);
    LocalDate localDateNovo=LocalDate.of(2015,3,5);

    System.out.println(localDateAntigo.isAfter(localDateNovo));     //false
    System.out.println(localDateAntigo.isBefore(localDateNovo));    //true
    System.out.println(localDateAntigo.isEqual(localDateNovo));     //false
````

Utilizando mais alguns métodos, podemos manipular as datas da seguinte forma:

```` java
    LocalDate dataManipulacao = LocalDate.now();
    System.out.println("Mais 5 dias:" + dataManipulacao.plusDays(5));
    System.out.println("Mais 5 semanas:" + dataManipulacao.plusWeeks(5));
    System.out.println("Mais 5 anos:" + dataManipulacao.plusYears(5));
    System.out.println("Mais 2 meses:" + dataManipulacao.plusMonths(2));
    System.out.println("Menos 1 ano:" + dataManipulacao.minusYears(1));
    System.out.println("Menos 1 mês:" + dataManipulacao.minusMonths(1));
    System.out.println("Menos 3 dia: " + dataManipulacao.minusDays(3));
    System.out.println("Data Original:" + dataManipulacao);
````

O retorno deste trecho é igual a:

    Mais 5 dias: 2022-01-20
    Mais 5 semanas: 2022-02-19
    Mais 5 anos: 2027-01-15
    Mais 2 meses: 2022-03-15
    Menos 1 ano: 2021-01-15
    Menos 1 mês: 2021-12-15
    Data Original: 2022-01-15

Como descrito nos exemplos acima, é possível adicionar e subtrair dias, meses, anos, facilmente utilizando-se os métodos
disponíveis pela API.

#### LocalTime:

- O LocalTime é utilizado quando se é necessário manipular apenas horas.

  Para se criar um objeto do tipo LocalTime, instanciámos da seguinte forma:

````java
    LocalTime localTime=LocalTime.now();
````

Podemos assumir uma forma utilizando o DateTimeFormatter, veja:

````java
    String strLocalTime=LocalDateTime.now().format(DateTimeFormatter.ofPattern("HH:mm:ss"));
````

Uma possibilidade também, é a de parse de uma string em data:

````java
  LocalTime localTime=LocalTime.parse("11:40:02",DateTimeFormatter.ofPattern("HH:mm:ss"));

````

Muito semelhante ao LocalDate, podemos adicionar ou subtrair horas, ficando assim:

````java
    LocalTime plusLocalTime=LocalTime.now().plusHours(1);       // ADIÇÃO
    LocalTime minusLocalTime=LocalTime.now().minusHours(1);     // SUBTRAÇÃO
````

A classe LocalTime, possui construtores que auxiliam na criação do objeto, o LocalTime.of() é um exemplo disso:

````java
    LocalTime localTime=LocalTime.of(10,35,12);     //T10:35:12
````

#### LocalDateTime;

- A classe LocalDateTime, muito parecida com as classes já listadas, unindo a classe LocalDate com a classe LocalTime,
  serve para manipular data e hora.

A instanciação de um objeto do tipo LocalDateTime, pode ser feita das seguintes formas:

````java
    LocalDateTime localDateTime=LocalDateTime.now();
    LocalDateTime localDateTimeOf=LocalDateTime.of(2022,01,15,10,15,30);  //2022-01-15T10:15:30
````

Podemos adotar, também, uma formatação com o DateTimeFormatter para a classe LocalDateTime:

````java
    String strLocalDateTime=LocalDateTime.now().format(DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm:ss"));
````

Para adicionar e subtrair dias, meses, anos, e horas:

````java
    LocalDateTime localDateTime=LocalDateTime.now().plusDays(1).plusMonths(1).plusHours(2);
````

Para se fazer o parse de uma string para LocalDateTime, podemos utilizar o método parse() da classe, veja:

````java
  LocalDateTime localDateTime=LocalDateTime.parse("2018-07-22 10:35:10",DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss"));
````

E para recuperar parte especifica do objeto, temos uma série de métodos get para nos auxiliar a manipular o dado
desejado. Veja um exemplo:

````java
    Month month=LocalDateTime.now().getMonth();
````

Para manipulação de Tempos, temos a enum ChronoUnit. Com ela, podemos manipular os tempos de diferentes formas:

````java
    LocalDateTime localDateTime12=LocalDateTime.now();
    LocalDateTime localDateTime13=LocalDateTime.now().plusDays(2);

    long periodAsMinutes=ChronoUnit.MINUTES.between(localDateTime12,localDateTime13);
    long periodAsHours=ChronoUnit.HOURS.between(localDateTime12,localDateTime13);
    long periodAsDays=ChronoUnit.DAYS.between(localDateTime12,localDateTime13);
````

#### MonthDay:

- A classe MonthDay, representa um dia do mês, e é imutável. Pode-se obter qualquer campo que possa ser derivado de um
  mês e dia. Não armazena hora nem fuso horário.

  Devido a não ser possível definir se a data 02/29 é valida, não se pode implementar o plus/minus como nas classes
  acima.

  MonthDay fornece acesso apenas para consultar e definir os campos MONTH_OF_YEAR e DAY_OF_MONTH.

Para instanciar um objeto do tipo MonthDay, podemos fazer da seguinte forma:

````java
    MonthDay monthDay=MonthDay.now();
    MonthDay monthDayOf=MonthDay.of(Month.JANUARY,15);
````

Para se fazer o parse de uma string para MonthDay, façamos assim:

````java
    MonthDay monthDay=MonthDay.parse("01-15",DateTimeFormatter.ofPattern("MM/dd"));
````

Podemos fazer algumas comparações do tipo isAfter() e isBefore(), veja:

````java
    boolean isAfter=MonthDay.isAfter(MonthDay.now());
    boolean isBefore=MonthDay.isBefore(MonthDay.now());
````

#### YearMonth:

- De forma muito semelhante à classe MonthDay, o YearMonth representa um ano e mês, e também é imutável. Pode-se obter
  qualquer campo que possa ser derivado de um ano e mês. Não armazena hora nem fuso horário.

  Para instanciarmos um objeto do tipo YearMonth, podemos fazer da seguinte forma:

````java
    YearMonth yearMonth=YearMonth.now();
    YearMonth yearMonthOf=YearMonth.of(2021,Month.JANUARY);
````

Diferente do MonthDay, a classe YearMonth pode ser implementado com plus/minus, veja:

````java
    YearMonth monthPlus=YearMonth.plusMonths(3L);
    YearMonth yearPlus=YearMonth.plusYears(2L);

    YearMonth monthMinus=YearMonth.minusMonths(2L);
    YearMonth yearMinus=YearMonth.minusYears(3L);
````

De forma semelhante as demais classes, podemos fazer o parse de uma string para o tipo YearMonth, ficando desta forma:

````java
    YearMonth yearMonth=YearMonth..parse("2022-01",DateTimeFormatter.ofPattern("yy/MM"));
````

E para fazermos comparações, podemos utilizar os seguintes métodos:

````java
    // Verifica se este ano-mês é posterior ao ano-mês especificado.
    boolean isAfter=YearMonth.isAfter(YearMonth.now());

    // Verifica se este ano-mês é anterior ao ano-mês especificado
    boolean isBefore=YearMonth.isBefore(YearMonth.now());

    // Verifica se o ano é bissexto, conforme as regras do sistema de calendário proléptico ISO.
    boolean isLeapYear=YearMonth.isLeapYear();
````

Ainda nos métodos da classe YearMonth, temos diversos get() para obter dados isoladamente. Veja alguns exemplos:

````java
    int month = YearMonth.getMonth();
    int year = YearMonth.getYear();
````

#### Period:

Para se trabalhar com qualquer sistema, é essencial conhecer as principais classes de manipulação de data e hora. E
graças a API java.time, facilitou manipular esses tipos de dados.

---

### Bibliografia:

<li><a href="https://www.devmedia.com.br/como-manipular-datas-com-o-java-8/34135">DEV MEDIA</a></li>
<li><a href="https://blog.cvinicius.com.br/2018/08/utilizando-localdate-localdatetime-e.html">CVINICIUS</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html">ORACLE</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/time/class-use/MonthDay.html">ORACLE</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html#plusMonths-long-">ORACLE</a></li>
<li><a href="https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html">ORACLE</a></li>
