# ==[-- LINK --](https://www.youtube.com/watch?v=95SkyJe3Fe0)==
# Stack : 
É um local de memoria onde o computador oferece uma quantia limitada de memoria, as coisas guardadas nele são guardadas diretamente. 
As coisas são :
- int.
- bools.
- floats.
- chars.
- structs.

Quando você cria uma variável, ela é armazenada no stack.
# Heap :
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

