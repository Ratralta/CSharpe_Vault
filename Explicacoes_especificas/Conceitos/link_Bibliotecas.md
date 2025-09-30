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