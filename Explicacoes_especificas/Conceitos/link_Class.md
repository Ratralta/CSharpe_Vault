### Criando um Class
Para criar uma class, coloque o primeira letra do nome da sua class em maiúsculo. 
EX:
> Class Pessoa {
>  string Nome = "Cauã Rocha Falcão"; 
>  int Idade = 176; 
>  public void acao_falar_nome() // pode ser acessada por um objeto baseado nele  
> } // Assim você criou um class.

Você pode pedir alguns parâmetros na hora de criar um objeto usando um class/struct, **criando um constructor**, tem varias maneiras de criar um constructor, uma delas é : 
Crie um public com o nome da classe com parênteses, e dentro do parênteses especifique os valores que você quer pedir. (Não esqueça de colocar o tipo de variável)
EX_1:
```cs
class Pessoa
{
	string Nome; // não possue valor 
	
	public Pessoa(string _nome) // constructor com visibilidade public
	{
	Nome = _nome;
	}
	
	public void acao_falar_nome()
	{
	Console.WriteLine($"Meu nome é {Nome}");
	}
}
class Program // COMEÇANDO O PROGRAMA
{
    static void Main() // COMEÇANDO O PROGRAMA
    {
        Pessoa pessoa_new = new Pessoa("Falcão Lima"); // OBJETO, que tem como parametro um CLASS
        pessoa_new.acao_falar_nome();
    }
}
```

Da pra também usar uma logica de "função", colocando os valores que você quer entre coxetes, e guardando eles dentro de uma variável public da class/struct. 
EX_2 :  
```cs
class Pessoa(string _nome) // constructor 
{
	string Nome {get;set;} = _nome; // guardando os valores do parâmetro desse class
	
	public void acao_falar_nome() // função 
	{
	Console.WriteLine($"Meu nome é {Nome}");
	}
}
class Program // COMEÇANDO O PROGRAMA
{
    static void Main() // COMEÇANDO O PROGRAMA
    {
        Pessoa pessoa_new = new Pessoa("Falcão Lima"); // OBJETO, que tem como parametro um CLASS
        pessoa_new.acao_falar_nome();
    }
}
```

### Propriedades das variáveis em um class (get E set) : 
==[LINK SOBRE get/set](https://www.w3schools.com/cs/cs_properties.php) ==
\--- **O que é {get;set;}?** 
get e set permitem adicionar algumas "propriedades" na hora de definir um valor para uma variável de um class/stuct. **Recomenda-se usar isso mesmo que você não queira  nenhuma propriedade especial para sua variável.**

EXEMPLO USANDO SEM DEFINIR NENHUMA PROPRIEDADE ESPECIAL: 
```c# 
class Pessoa
{
	string nome {get;set;} // mesma coisa que "string nome;"
	float tamanho {get;set;} // mesma coisa que "float tamanho;"
}

class Program 
{
    static void Main(string[] args) 
    {
	Console.WriteLine("Hello World!");
    }
}
```

\--- **Usando get/set com propriedades**
get : Serve para pegar outra variável, e definir seu tipo(int float etc) igual ao da variável pega.  

set : Adiciona uma propriedade que acontece quando a variável recebe um valor. Usando "value", você pega o valor que atribuído a variável 

EXEMPLO DEFININDO UMA PROPRIEDADE ESPECIAL: 
```cs
class Galinhas
{
    public string nome { get; set;} // sem propriedade
    private int _idade; // valor "cobaia" que será usado na variavel "idade"
    public int idade
    {
        get { return _idade; } // mesma coisa que "int idade;"
        set // adicionando uma "propriedade" na hora de "setar" um valor a esta variavel, essa "propriedade" será lida quando a variavel receber um valor(value)
        {
            if (value < 0)
            {
               Console.WriteLine("Não existe idade menor que zero");
                _idade = 0;
            }
            else
            {
                Console.WriteLine("Idade ok");
                _idade = value;
            }
        }
    }
}
class Program
{
    static void Main(string[] args)
    {
        Galinhas galinha = new Galinhas();
        galinha.nome = "Felipe";
        galinha.idade = -30;
        Console.WriteLine("a idade dessa galinha é : " + galinha.idade);
        // vai aparecer no console :
        // > Não existe idade menor que zero
        // > a idade dessa galinha é : 0
    }
}
```
### Criando Classes derivadas de outras : 
Você consegue criar sub classes, que são classes que herdam variáveis e métodos/funções DA **classe base**. 
Para criar um sub class, coloque o nome da sub class, dois ponto (:) e a qual **class base** ela pertence. 
EX: 
```cs 
class classe_base
{
    public string var_class_base { get; set; } = "CLASS BASE"; // variavel da class base
    public void falar_oi() // função da class base
    {
        Console.Write("Oi");
    }
}
class sub_class : classe_base // "sub_class" DERIVA de "classe_base"
{
    public void falar_bomdia()
    {
        falar_oi(); // função de sua class base "classe_base"
        Console.WriteLine(", Bom dia!");
    }
}
// "sub_class" DERIVA de "classe_base", sub_class tem acesso a "var_class_base" E "falar_oi()"

class Program
{
    static void Main(string[] args)
    {
        sub_class obj = new sub_class();
        obj.falar_bomdia(); // RETORNA : Oi, Bom dia!
    }
}
```

Caso sua **classe base** tenha um "constructor", é OBRIGATÓRIO criar um constructor com a palavra chave "base()", para pegar os parâmetros da **classe base**. 
EX: 
```cs
class class_base // classe base
{
    public int variavel { get; set; }
    public class_base(int _variavel) // constructor public
    {
	variavel = _variavel;
    }
} 

class sub_class : class_base // "sub_class" DERIVA de "class_base"
{
public char variavel_de_subclass {get;set;} // variavel que só existe no class  "sub_class"
    public sub_class(int _variavel, char _variavel_de_subclass) : base(_variavel)
	{
	variavel_de_subclass = _variavel_de_subclass;
	}
	// criando constructor, POIS a class base "class_base" POSSUI UM CONSTRUCTOR, então a sub classe "sub_class", precisa também de um constructor.

    // esse constructor tem a palavra chave "base()", ele é OBRIGATORIO caso sua "class base" TENHA um constructor.
}

class Program
{
    static void Main(string[] args)
    {
        class_base ex1 = new class_base(10); // objeto do class "class_base"
        sub_class ex2 = new sub_class(1, 'z'); // objeto da class "sub_class", que é derivada de "class_base"
        Console.WriteLine(ex1.variavel);
        Console.WriteLine(ex2.variavel_de_subclass);
    }
}
```

Funções de **classes base** podem conter a palavra chave "virtual", ela faz com que **classes derivadas** possam reescrever as funções com "virtual", através da palavra-chave "override"
EX:
```cs
class Pessoa
{
    public string nome { set; get; }
    public int idade { set; get; }
    public Pessoa(string _nome, int _idade) // constructor public
    {
        nome = _nome;
        idade = _idade;
    }
    
    public virtual void falar_bom_dia() // função com palavra chave "virtual", para que ela possa ser reescrita.
    {
        Console.WriteLine("Oi bom dia");
    }
}

class Pessoa_dois : Pessoa
{
    public Pessoa_dois(string _nome, int _idade) : base(_nome, _idade) // pegando constructor da class "Pessoa"
    { }
  
    public override void falar_bom_dia() // usando a palavra chave "override", para reescrever a função "falar_bom_dia()" da class base "Pessoa"
    {
        Console.WriteLine("Ola bom dia, meu nome é " + nome + ", e tenho " + idade + " anos de idade");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Pessoa pes1 = new Pessoa("Didi", 67);
        Pessoa_dois pes2 = new Pessoa_dois("Ronaldo", 43);
        pes1.falar_bom_dia();
        pes2.falar_bom_dia();
    }
}
```

### Palavras chaves de um Class
Você pode adicionar algumas palavras chaves a sua class, deixando ela com algumas propriedades especiais, alguma dessas palavras chaves são :
* **Static :** Colocando isso na classe ou em suas variáveis, vai fazer com que essa seja **GLOBAL**, fazendo com que você não precise criar um objeto para acessar seus métodos/atributos E variáveis . Para criar uma class, coloque o primeira letra do nome da sua class em maiúsculo. 
EX Static: 
```cs
static class Falar
{
	static public void falar_com_raiva(string nome_da_pessoa)
	{
	Console.WriteLine("grrrrr to com raiva de " + nome_da_pessoa + ", grrrrrr");
	}
}

class Program 
{
    static void Main(string[] args) 
    {
	Falar.falar_com_raiva("Warick");
    }
}
// Conseguiu usar a função "falar_com_raiva" sem precisar criar um objeto e usar o objeto para rodar a função.
// static --> propriedade 
// public --> visibilidade 
// void --> tido de dado que retorna (void = nenhum)
```

* **Partial**: Ela serve para dividir o que você vai escrever em um class/struct, podendo definir um  class em varias áreas diferentes E até mesmo em arquivos diferentes, é útil principalmente para organização. (Quando o programa rodar, o compilador vai compilar primeiro todas as class "partial" que existem, *juntando elas em uma class só*)
EX Partial:
```cs
public partial class Pessoa // primeiro pedaço da class "Pessoa"
{
	public string nome = "Felipe Lá ele";
	public int idade = 25;
}

public partial class Pessoa // segundo pedaco da class "Pessoa"
{
	public void falar_nome()
	{
	Console.WriteLine("Meu nome é " + nome);
	} 
}

class Program
{
    static void Main(string[] args)
    {
        Pessoa pessoa1 = new Pessoa(); // criando objeto class de "Pessoa"
        pessoa1.falar_nome(); // usando função "falar_nome()" do objeto "pessoa1"
    }
}
```
### NameSpace : 
* **Namespaces** servem para organizar suas classes, podendo acessar classes de um namespace que estão em outros arquivos usando o **using**. É possível um arquivo possuir mais de um namespace e pode colocar um namespace dentro de outro namespace.

* Namespaces **não** são classes, pois eles simplesmente agrupam dados, não os armazenam, significando que não é possível instancia-los.

* **É muito recomendado** usa-los, pois eles são muito úteis pra organizar seus códigos de maneira mais logica.
EX:
Arquivo A : 
```cs 
namespace Pessoas; // esse arquivo inteiro é deste namespace
public class class_pessoa // class 
{
	public string nome = "ronaldo";
	public int idade = 19;
}
```
Arquivo B :
```cs
using Pessoas; // Usando namespace "Pessoas" de [Arquivo A]
class Program
{
    static void Main(string[] args)
    {
    class_pessoa humano = new class_pessoa(); // class_pessoa é um class do namespace "Pessoas"
    Console.WriteLine("meu nome é " + humano.nome + ", tenho " + humano.idade + " anos");
    }
}
```