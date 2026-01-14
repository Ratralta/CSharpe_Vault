# O que é : 
* É uma propriedade que pode ser adicionada a funções/classes, que um valor "\<T>",  aceita qualquer tipo de dado para ser usado. 
* [List\<T>](Conceitos_Básicos_do_C++++), é uma class genérica.
* [--LINK--](https://www.youtube.com/watch?v=YEHbjy3JBtE)

# Básico : 

## Criando um class genérico :
* Similar a criar um class normal, sendo : 
	```CS
	public class Jogos<T>	{
	public T data; // variável recebendo tipo que "<T>" for.
	}
	
	Jogos<string> teste = new Jogos<string>(); // "<T>" é uma string
	teste.data = "AAAAAAAAAAAAAA"; // atribuindo valor a "teste.data"
	Console.WriteLine(teste.data);
	```
## Criando uma função : 
* Similar a uma função normal, sendo : 
	```CS
	void Print<T>(T _dado)
	{
	Console.WriteLine(_dado); 
	}
	```
	
## Constraints/restrições :
* Ele é uma propriedade que você pode adicionar a um "generic", ele permite adicionar restrições ao tipo de dado que "\<T>" pode receber. 
* Essas restrições NÃO aceitam tipos primitivos como int e string, elas aceitam somente :
	* **Classes**.
	* **Structs**. 
	* **Interface**. 
	* **OUTROS**.
* Funciona quanto para classes , quanto para funções.
* EX  :
	* Função sem retorno :
		```CS
		class Vivo { // class pai
		public string nome;
		public int idade;
		}
		class Pessoa : Vivo { // class filho
		public string profissao;
		}
		class Animal : Vivo { // class filho
		public string raca;
		}
		public void Print<T>(T _dado) where T : Vivo , new(){
		Console.WriteLine(_dado);
		// constraints = "where T : Pessoa".
		// "new()" indica que aceita somente classes sem "constructor"
		// essa função aceita somente as classes "Pessoa" e "Animal".
		}
		Pessoa obj = new Pessoa() // criando obj
		obj.idade = 20;
		obj.nome = "Doido";
		obj.profissao = "Cabeleleiro";
		Print(obj); // usando função "Print()" 
		``` 
	* Função com retorno : 
		```CS
		class Vivo { // class pai
		public string nome;
		public int idade;
		}
		class Pessoa : Vivo { // class filho
		public string profissao;
		}
		class Animal : Vivo { // class filho
		public string raca;
		}
		
		public T Amostrar_tipo<T>(T _dado) where T : Vivo , new()
		{
		// "new()" indica que aceita somente classes sem "constructor"
		return _dado;
		} 
		var obj = new Animal();
		obj.nome = "Papazulu";
		obj.idade = 89;
		obj.raca = "Cachorro";
		Console.WriteLine(Amostrar_tipo<Vivo>(obj));
		```


