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
