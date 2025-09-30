# Bibliotecas :

## Bibliotecas Padrões : 

## Bibliotecas Extras : 
* RayLib -- > Serve pra fazer jogo. 


# Funções :
## Console ...
* **Console.Write("texto") / Console.WriteLine("texto")** :"Write" escreve no console, "WriteLine" escreve no console e depois dá uma quebra de linha.
EX: 
```c#
Console.Write("Hello World!"); // isso aparecerá no console
```

* *Console.ReadLine()** : Cria um input pro usuário, retornando o que o usuário escreveu. 
EX: 
```c#
Console.WriteLine("Qual seu nome?");
string nome = Console.ReadLine();
Console.WriteLine("Qual sua idade?");
int idade = Convert.ToInt16(Console.ReadLine()); // Convertendo o valor retornado em int POIS é o tipo que eu definir pra variável.

Console.Write("Olá " + idade + ", você tem " + nome + " anos!!!");
```


## Math ...
* **Math.Max(value_1,value_2...)** : Retorna o maior numero entre os fornecidos no parâmetro 
EX: 
```c#
int bixo_1_power = 1000;
int bixo_2_power = 3650;

Console.WriteLine("O maior poder registrado foi : " + Math.Max(bixo_1_power,bixo_2_power));
```
