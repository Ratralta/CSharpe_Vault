
# Armazenando dados :
## Sobre Variáveis :
### Criando variáveis :
* Para criar uma variável, é preciso definir seu tipo, o nome, E não obrigatoriamente um valor e sua visibilidade. **Assim que se define o tipo de uma variável não é mais possível muda-lo**.  
EX: 
> int hp_do_bixo = 12;
> float  speed_do_bixo = 3.6f;  ---- > *precisa do "f" no final*
> bool bixo_vivo = true;

* Você pode usar "var", que faz com que automaticamente defina o tipo de variável baseado no valor recebido. 
EX: 
> var sou_numero = 30; ---- > "30" é inteiro, então "sou_numero" é Int.
> var texto = "gugu dada"; ---- > "gugu dada" é string, então  "texto" é string.

* Variáveis normalmente não aceitam o valor ***null***, mais colocando um ponto de interrogação na definição do tipo, essa variável passa a aceitar valores *null*.
EX:
> char dale_tropa = *null*; ---> NÃO FUNCIONA 
> string? la_ele = *null*; ---> variável "la_ele" agora aceita valores ****null***. 

* Caso for criar variáveis em um [Class](link_Class.md), é recomendado usar as "propriedades" [{get;set;}](link_Class_get_e_set_propriedades.md) quando for criar qualquer variável, mesmo que você não for fazer uso dessas propriedades.
### Tipos de Variáveis : 
**São os tipos de valores que a variável pode receber, sendo eles :**
* **int** : Número inteiro.
EX: 
> int numero = 100;

* **Float** : Números reais. (Precisam ter o "f" quando for definir seu valor)
EX: 
>float numero = 13.69f;

* **String** : Texto sem propriedades matemáticas. 
EX: 
>string name = "Hog Ridder";

* **Char** : Similar a string, porem suporta somente **1** único caractere (*usar aspas simples \[''] para definir seu valor*).
EX: 
>char  inicial_do_blud = 'n';
### Palavras chaves de variáveis : 
Existem algumas palavras chaves que você pode adicionar a uma variável quando for cria-la, algumas delas são :
* **CONST** : Define que sua variável possui um valor **imutável**, que não pode ser alterado. 
>-- *Precisa ter algum valor definido quando criado*.
>-- *Não aceita variáveis para definir seu valor.*
>-- *Objetos não são capazes de retornar variáveis "Const".*

EX: 
```c#
const float gravidade = 9.8f;
gravidade = 20.5f; // ESSA LINHA DA ERRO
Console.Write("A força da gravidade do planeta é : " + gravidade + "m/s²");
```


### Pegando o tipo das variáveis : 
Para pegar o tipo da variável , basta colocar a variável, ponto e a função "GetType()", assim retorna o tipo de valor dela. 
EX : 
```cs
int variavel = 10;
Console.WriteLine("o tipo dessa variavel é " + variavel.GetType());
```

### "Mudando" tipo das Variáveis :
Através de uma variável, é possível **retornar** um valor com **um tipo diferente** do tipo original através da static classe "**Convert**". Essa static class guarda funções que mudam o tipo do retorno da variável, algumas dessas funções são : 

* **Convert.ToInt16(variavel)** : Retorna o valor de "variavel" como um "int" de "16 bytes". 
EX: 
```c#
float numero_real = 4.55f;
int numero_int = Convert.ToInt16(numero_real); // retornou o valor de "numero_real" como um "int".
Console.Write(numero_int);
```

* **Convert.ToString(variavel)** : Retorna o valor de "variavel" como uma "string". 
EX: 
```c#
bool pedra_usavel = true;
string pedra_usavel_string = Convert.ToString(pedra_usavel);
Console.Write("Essa pedra ela é " + pedra_usavel_string);
```


## Criando Array : 
* Array possui um tamanho definido, não pode ser aumentado nem diminuído após usa criação.
* [-- LINK --](https://www.w3schools.com/cs/cs_arrays_multi.php)
* Coloque o tipo de dado da array antes de colocar seu nome :
	```CS
	string[] nome_das_pedras = {"João", "Gustavo Lima", "Rauã"};
	``` 
* Para criar uma array vazia com um tamanho definido, siga essa sintaxe : 
	```CS
	string[] lista = new string[4]
	```

* Para criar array de 2 dimensões, siga essa exemplo : 
	```CS
	int[,] lista = {{1,2,3},{12,24,36}};
	Console.WriteLine(lista[1,2]); // printa "36"
	```

"array_name.Lenght" , retorna tantos itens a **array** tem.
## Criando List : 
* List diferente de Arrays, podem ter seu tamanho modificado após sua atribuição. 
* No C#, **list é um class**. 
* [-- LINK --](https://www.youtube.com/watch?v=vQzREQUhGSA)
* Para criar uma list, siga a sintaxe : 
	```CS
	List<int> lista = new List<int>();
	```
* Para adicionar elementos para a lista, use a função da class list **Add()**, ela adiciona um item no começo a lista , exemplo : 
	```CS
	List<int> lista = new List<int>();
	lista.Add(99);
	Console.WriteLine(lista[0])
	```
* Para remover elementos de uma lista, use a função da class list **Remove()**, essa função remove o que possui em seu parâmetro, exemplo : 
	```CS
	List<string> lista = new List<string>(){"AAAAAAA"};
	lista.Remove("AAAAAAA");
	Console.WriteLine(lista);
	```
 

"lista_name.Count" , retorna tantos itens a **lista** tem 
# Lações de Repetições 
## Foreach :
É tipo o for, só que o valor do *i* assume o valor da posição que ele está na coleção. (é tipo o for do pyton)
EX: 
> foreach (int i in array_de_int) {*codigo*}
> bool (bool i in lista_de_true_ou_false) {*codigo*}

## For :
Possui uma condição para ser repetido, e seu *i* retorna só um numero.
EX: 
> for(int i=0 ; i<5 ; i++)
> for(int i=0 ; i< array_de_int.Lenght ; i++)

## While : NÃO TEM NADA 
# Funções : 
Para criar funções, é preciso definir que tipo de dado ela vai retornar, caso queira criar parâmetros, é preciso definir o tipo de dados deles . (*Void* retorna nada)
EX: 
> void bixo_pule() {*codigo*} // não vai retornar nenhum valor
> int amostrar_vida_bixo() {*codigo*} // o tipo de dado que ela pode retornar é **somente inteiro** 
> float teste_de_lista(list\<float> \_lista) {*codigo*} // tem parâmetro uma lista do tipo float, **retorna um float**



# Class, Struct e Objetos : 
## Coisas sobre Class
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
* **Static :** Colocando isso na classe/variáveis ou funções, vai fazer com que elas sejam capazes de serem chamadas **através do Class**, sem precisar usar um objeto para chama-las. 
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
## Struct 
Extremamente similar ao class, o jeito que você cria um struct  e adiciona parâmetros é do mesmo de um class.
## Objeto 
Para criar um objeto, você precisa de uma "class" para ele se basear, então colocando o nome do class, nome do objeto recebendo **new** class(), você cria um objeto.
EX:
>Class_name objeto_1 = new Class_name(); // criou um objeto
```
class Pessoa
{
	string Nome = "Cauã Rocha Falcão";
	int Idade = 176; 
	public void acao_falar_nome() // pode ser acessada por um objeto baseado nele  
	{
	Console.WriteLine($"Meu nome é {Nome}");
	}
}

class Program // COMEÇANDO O PROGRAMA
{
    static void Main() // COMEÇANDO O PROGRAMA
    {
        Pessoa pessoa_new = new Pessoa(); // OBJETO
        pessoa_new.acao_falar_nome();
    }
}
```

Você também pode atribuir valores a um objeto quando for criar ele, caso já exista uma class pra ele se basear.
EX: 
```cs 
class Galinhas
{
    public string nome {get;set;}
    public int idade {get;set;}
    public bool compravel {get;set;}
}
class Program
{
    static void Main(string[] args)
    {
        Galinhas galinha_de_ouro = new Galinhas
        {
            nome = "Gustavo",
            idade = 9,
            compravel = true,
        };
        Console.WriteLine("Nome dessa galinha é " + galinha_de_ouro.nome);
    }
}
```


# Bibliotecas :
## O que é uma Biblioteca : 
* Biblioteca é uma biblioteca.

## Criando Bibliotecas : 
* Para criar uma biblioteca, você tem que criar **um novo projeto**, com o modelo **Biblioteca de Classes**, esse modelo permite criar uma pasta aonde você pode fazer uma biblioteca.   

* Para criar um projeto de modelo "Bibliotecas de Classes", use ==dotnet new classlib==. (use -n NomeDaPasta caso queira definir um nome pra pasta) 

* Tudo que poderá ser referenciado estão nos arquivos com a palavra chave **namespace**, o nome da sua biblioteca também será definida através do namespace. (só pode conter **UM** namespace em sua biblioteca)
EX:
```cs
namespace biblioteca; // nome da biblioteca 

static public class Variaveis // um class static. (não precisa criar um objeto para chamar essas variáveis)
{
    static public string texto = "El pepe";
    static public int inteito = 19;
    static public float real = 67.41f;
    static public char caractere = 'f';
}
```

* Agora com uma biblioteca criada, é preciso referencia-la para usa-la em seu projeto, para isso, abra um prompt de comando no seu projeto, e use o comando ==dotnet add reference local_da_pasta_da_biblioteca/arquivo.csproj==, referenciando o arquivo que possui **.csproj** do projeto **Biblioteca de Classes**. Assim você referencia a biblioteca criada em seu projeto e agora pode ser usada. (As bibliotecas do seu projeto podem ser vistas em seu arquivo **.csproj**)

* Agora com a biblioteca referenciada, você pode usa-la em seu projeto com a palavra chave **using** Nome_do_namespace, como no exemplo : 
```cs
using biblioteca;

Console.WriteLine("Isso é um texto :"+ Variaveis.texto);
Console.WriteLine("Isso é um numero real :"+ Variaveis.real);

```
## Adicionando bibliotecas externas : 
Para usar uma biblioteca externa, você precisa abaixar de um **Repositório de pacotes de bibliotecas**, os pacotes mais conhecidos são :
*  NuGet --> Repositório oficial do .Net 
### Instalando pacotes pelo NuGet : 
* Para instalar bibliotecas pelo NuGet, abra um prompt de comando no arquivo do seu projeto e use o comando ==dotnet add package NomeDaBiblioteca==, assim você instalará uma biblioteca e ela poderá ser usada em seu projeto.

* Agora para usar essa biblioteca, use a palavra chave **using** Nome_da_biblioteca, como no exemplo : 
```cs
// NO PROMPT DE COMANDO --> dotnet add package Newtonsoft.Json 
using Newtonsoft.Json;

class Program // exemplo do chat gpt
{
    static void Main()
    {
        var pessoa = new { Nome = "RatoPreto", Idade = 25 };
        string json = JsonConvert.SerializeObject(pessoa);

        Console.WriteLine(json);
    }
}
```

### Instalando pacotes via outros :
# Coisas : 
## TEMPLATE DE CÓDIGO C++++
```
class Program 
{
    static void Main(string[] args) 
    {
	Console.WriteLine("Hello World!");
    }
}
```
## Sobre a visibilidade das variáveis (NÃO TEM NADA)

## Memoria das Coisas
==[LINK SOBRE stack e heap](https://www.youtube.com/watch?v=95SkyJe3Fe0)==
### Stack : 
É um local de memoria onde o computador oferece uma quantia limitada de memoria, as coisas guardadas nele são guardadas diretamente. 
As coisas são :
- int.
- bools.
- floats.
- chars.
- structs.

Quando você cria uma variável, ela é armazenada no stack.
### Heap :
É um local de memoria onde o computador oferece quanta memoria o "heap" precisar, ele guarda os dados dele como um "apartamento", cada andar tem sua "ID", aonde cada *coisa* é guardada.
As coisas são : 
* classes.
* arrays.
* lists.
* coleções.
* string? 

Quando você cria um objeto duma Class, as informações deste objeto vão para um "andar" no "heap" , enquanto o objeto em si se torna uma "ID" para acessar seu "andar".
- ID do objeto é guardado no "stack".
- Informações do objeto é guardado em um "andar" no "heap".

EX:
```c#
class Pessoa
{
    public string nome;
    public int idade;
}

class Program
{
    static void Main(string[] args)
    {
        Pessoa pes1 = new Pessoa();
        Pessoa pes2 = new Pessoa();
          
        pes1.nome = "Ronaldo Prompt";
        pes1.idade = 120;

        pes2.nome = "Cropto Silva";
        pes2.idade = 20;

        Console.WriteLine(pes1.nome);
    }
}
```
![](heap_explicacao_1.png)
SE VOCÊ FIZER :
> pes1 = pes2;
   pes1.idade += 1;
   Console.WriteLine(pes2.idade);

Na teoria era pra retornar 20 , mais na pratica retorna 21. POR QUE pes1 recebeu a "ID" de pes2, tendo acesso ao seu "andar" do "apartamento", então quando mexe no valor de pes1, mexe também no de pes2, alias ambos estão agora no mesmo "andar". 
EX:
![](heap_explicacao_2.png)
## Conceitos Básicos :
### Criando arquivo C++++ :
Para criar um arquivo c#, você precisa ter abaixado:
[ -- ESPECIFICAÇÕES DO LINUX LINK --](https://learn.microsoft.com/pt-br/dotnet/core/install/linux?WT.mc_id=dotnet-35129-website)
> .net framework.
> 	No linux, precisa instalar o **SDK**, ele permite rodar e codar arquivos c#.
> extensão "C#" do Visual Studio Code.
> extensão "C# Dev Kit" do Visual Studio Code.

Com eles abaixados , vá no Cropto de Comando, e use o comando ==dotnet new console -n NomeDoFolder==, assim vai criar uma pasta aonde você pode mexer com o C#.

Você pode só colocar ==dotnet new console==, criando um projeto c# dentro da pasta que você abriu o prompt de comando.  
### Dicas
* Tem um site que emula c#, e nele tem umas features bem legais, o site é [SharpLab](https://sharplab.io/#v2:C4LgTgrgdgNAJiA1AHwPQCoCwAoABLgZQAsBDMABwBkSAjXYAewYBsBnXASylwCVpcAtgzgBTEDnz5ARAS4AbiWYQRAOgCSUVuREBjYAAoAlBMkz1mncGUAJESXJ6GNAFYWjeE7jNbdygsBLaANZ68ooibpK4MgACAEwArKFKAIwwcgpKsWmAZAQGuADCPKoAgrgAqgCyuABClADy+XW4dQByACIAorjFFXUEACo8pX2E/cX5ANK4XVYdxQAKOOioOHHJOKuxuNHJAOy4OADeOAAFuGc7AGzbACy4FSRcejsADADaALq4ZADmrHmnc64Y7YACQOwAnHoAEQ2ZjMBi4ADqDDAzDgAEJoQYANyAs4AXxwBKAA=)
*  "Sou_arquivo.cs" , assim cria um arquivo C#.
* Assim como as bibliotecas do pyton, o C# também possui, só que são tratados como "Classes", para usa-las, cheque [[link_Bibliotecas]]).
* Não é possível mudar o tipo de dado da variável, mais é possível **retornar** o valor dela em OUTRO tipo de dado, através do "Convert.ToString(variavel)".
* Constructors e Descontructors são métodos especiais de um class. Constructors executam seu código quando um objeto é criado, Descontructors executam seu código quando o objeto deixa de existir. 
