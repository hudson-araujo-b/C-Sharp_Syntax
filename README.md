# Sintaxe C# básica


## 1. Tipos de Dados e Operadores

No C#, as variáveis são **fortemente tipadas** (precisam ter um tipo definido).

```csharp
// Tipos Primitivos Básicos
int numero = 10;            // Números inteiros
double preco = 19.99;       // Números com ponto flutuante (decimais)
bool estaLogado = true;     // Verdadeiro ou Falso
char letra = 'A';           // Um único caractere (aspas simples)
string nome = "Gemini";     // Texto (aspas duplas)

// Operadores
// Aritméticos: +, -, *, /, % (resto)
// Comparação: >, <, >=, <=, == (igual), != (diferente)
// Lógicos: && (E), || (OU), ! (NÃO)
```


## 2. Estruturas de Controle

Controlam o fluxo de execução do código.

### Condicionais:

```csharp
// If / Else
if (numero > 5) {
    Console.WriteLine("Maior que 5");
} else {
    Console.WriteLine("Menor ou igual a 5");
}

// Switch (ótimo para muitas opções fixas)
switch (numero) {
    case 1: Console.WriteLine("Um"); break;
    case 10: Console.WriteLine("Dez"); break;
    default: Console.WriteLine("Outro"); break;
}
```

### Laços de Repetição (Loops):

```csharp
// For (define o indice direto)
for (int i = 0; i < 5; i++) {
    Console.WriteLine(i); 
}

// While (enquanto a condição for verdadeira)
while (numero < 20) {
    numero++;
}

// Do/While (executa pelo menos uma vez)
do {
    numero++;
} while (numero < 20);

// Foreach (Exclusivo para percorrer coleções/listas)
string[] nomes = { "Ana", "Beto" };
foreach (var n in nomes) {
    Console.WriteLine(n);
}
```


## 3. Funções (Métodos)

Blocos de código reutilizáveis.

```csharp
// <Retorno> <NomeDaFuncao>(<Parametros>)
int Somar(int a, int b) {
    return a + b;
}

// Função sem retorno (void)
void Saudacao(string nome) {
    Console.WriteLine("Olá " + nome);
}
```


## 4. Estruturas de Dados

Formas de organizar e armazenar informação para que um computador a possa utilizar de forma eficiente.

### Array (Vetores)

O Array tem tamanho fixo. Você define quantos itens ele terá na criação e não pode mudar depois. É ideal quando você sabe exatamente a quantidade de dados.

```csharp
// Declaração e Inicialização
int[] numeros = new int[5]; // Cria um array vazio para 5 números
string[] frutas = { "Maçã", "Banana", "Uva" }; // Cria já preenchido (tamanho 3)

// Acessar e Modificar (usa o índice, começando em 0)
Console.WriteLine(frutas[0]); // Imprime "Maçã"
frutas[1] = "Pera"; // Muda "Banana" para "Pera"
```

### List (Listas)

A Lista é dinâmica. Ela pode crescer ou diminuir conforme você adiciona ou remove itens. É a opção mais flexível.
Nota: Requer using System.Collections.Generic;

```csharp
// Declaração
List<string> nomes = new List<string>();

// Adicionar itens
nomes.Add("Ana");
nomes.Add("Bruno");

// Remover itens
nomes.Remove("Ana");

// Acessar (igual ao Array)
string nome = nomes[0]; 

// Tamanho atual
int quantidade = nomes.Count;
```


## 5. Comandos Básicos de Console

### Saída de Dados (Escrever na tela)

Console.WriteLine(): Escreve o texto e pula para a próxima linha (o mais usado).

Console.Write(): Escreve o texto e mantém o cursor na mesma linha.

### Entrada de Dados (Ler o teclado)

O comando principal é o Console.ReadLine().
Ele sempre lê o que o usuário digita como texto (string). Se você quiser um número, precisa converter.

```csharp
// Lendo Texto
Console.Write("Digite seu nome: ");
string nome = Console.ReadLine(); // O programa para e espera o enter

// Lendo Números (Conversão)
Console.Write("Digite sua idade: ");
string textoIdade = Console.ReadLine();
int idade = int.Parse(textoIdade); // Transforma em texto 

int numero;
bool conseguiu = int.TryParse("123", out numero); // Tenta transformar para texto
```
### Formatação (Interpolacão)

```csharp
Console.WriteLine("O cliente " + nome + " tem " + idade + " anos.");
Console.WriteLine($"O cliente {nome} tem {idade} anos.");
```

### Controle da Janela

```csharp
Console.Clear(); // Limpa toda a tela (útil para reiniciar loops)
Console.ReadKey(); // Espera o usuário apertar qualquer tecla para continuar
```
