### Um dos pilares da POO é o encapsulamento. Fazemos isso por meio da criação de classes, atributos e métodos, definindo uma restrição de acesso utilizando os modificadores de acesso. Então, demonstre por meio de algoritmos:

---

### Criação de métodos com argumentos e valores de retorno;

- Os métodos são as funcionalidades da classe. Para cada método, deve-se especificar uma assinatura com a segunte
  sintaxe:

        <modificadores> tipo_de_retorno <nome>(<argumentos>){
            //corpo do método
        }

  Exemplo:

````java
    public long soma(long num1, long num2){
    return num1 + num2;
    }
````

### Criação de métodos sem argumentos e valores de retorno;

- Para criar um método sem argumento e sem valor de retorno é muito simples, basta codificar seguindo as especificações
  e utilizar o tipo de retorno como 'void':

````java
    public void semRetorno(){
    //corpo vazio;
    }
````

### A aplicação da palavra-chave static em métodos e atributos, ressaltando a principal característica de um método static e um atributo static;

- O static é o modificador que torna os métodos ou atributos globais, ou seja, podem ser acessados sem a necessidade de
  um objeto da classe.

  O que é static, é compartilhado por todas as instâncias daquela determinada classe.

  Veja um exemplo de aplicação de método e atributo estáticos:

````java
public class RestauranteConfig {
    private static double taxaServico;

    static {
        taxaServico = 10.0;
    }

    public static double getTaxaServico() {
        return RestauranteConfig.taxaServico;
    }

    public static void setTaxaServico(double taxaServico) {
        RestauranteConfig.taxaServico = taxaServico;
    }

    public class TesteRestauranteConfig {
        public static void main(String[] args) {
            System.out.println("Taxa de serviço: " + RestauranteConfig.getTaxaServico());

            RestauranteConfig.setTaxaServico(11.0);

            System.out.println("Nova taxa de serviço: " + RestauranteConfig.getTaxaServico());
        }
    }
}
````

Conforme os princípios de encapsulamento, devem ser criados métodos para manipular esses atributos de classe static.

### A sobrecarga de métodos;

- Esse mecanismo do polimorfismo, consiste em definir, para uma mesma classe, vários métodos ou construtores de mesmo
  nome, mas com parâmetros diferentes.

  Veja um exemplo de overloading:

````java
public class Conta {

    private int numero;
    private double saldo;
    private double juros;
    private DateTime vencimento;

    // construtor padrão sobrecarregado.
    public Conta() {
        numero = 0;
        saldo = 0;
        juros = 0;
        vencimento = DateTime.now();
    }

    // contrutor com parâmetro sobrecarregado.
    public Conta(int numeroConta, double saldoInicial) {
        numero = numeroConta;
        saldo = saldoInicial;
        juros = 0;
        vencimento = DateTime.now();
    }

    // método sobrecarregado.
    public void debito(double valor) {
        // implementação...
    }

    // método sobrecarregado.
    public void debito(long valor) {
        // implementação...
    }
}
````

Conforme o elemento que estiver a ser definido, teremos overloading de métodos ou de parâmetros.

### A criação de construtores padrão, construtores com argumentos e a sobrecarga de construtores;

- Vide tópico acima.

### A aplicação de encapsulamento utilizando os modificadores de acesso.

- O encapsulamento serve para separar os dados do comportamento da aplicação, de modo a controlar como cada parte será
  usada pelo restante da aplicação.

  Em outras palavras, os atributos de um objeto podem ser escondidos de outros objetos por uma interface pública de
  métodos, de modo a impedir acessos indevidos.

  Veja um exemplo de encapsulamento:

````java
public class Pessoa {

    public String nome;
    public int idade;

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public int getIdade() {
        return idade;
    }

    public void setIdade(int idade) {
        this.idade = idade;
    }
}
````

---

### Bibliografias:

<li><a>MOREIRA NETO, Oziel. Entendendo e Dominando o Java. I.ed. São Paulo: Editora Books, 2004.</a></li>
<li><a>McLAUGHLIN, Brett. POLLICE, Gray. WEST, David. Análise e Projeto Orientado ao Objeto, Use a Cabeça!. I.ed. Rio de Janeiro: Editora Alta Books, 2007</a></li>