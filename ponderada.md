# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro ✅

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

Justificativa: a saída será definida como um erro pois 
 foi declarado com var. Isso acontece porque o JavaScript entende a declaração antes da execução do código e o valor só atribui depois 
Já o Y dá erro, porque foi declarado com  let, que não permite o uso da variável quando é declarada após o console.log.



**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

a) Substituir if (a || b === 0) por if (a === 0 || b === 0) ✅

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

Justificativa: Ao utilizar o operador lógico ||, o código retorna "Erro: número inválido" se qualquer um dos valores for zero, enquanto o operador && permite que a saída seja "Erro: número inválido”  só quando ambos os números são iguais a zero.

______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

b) O código imprime 200. ✅

c) O código imprime 50.

d) O código gera um erro.

Justificativa: O código entra no primeiro caso e vê que o tipo é "eletrônico", então define o preço como 1000. Porém não tem o break, então ele vai para o próximo caso, que é o de "vestuário", o preço é 200. Mas agora com o break sendo o preço final como 200.

______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

d) 24 ✅ 

Justificativa: 24, pois multiplica todos os números por 2, indo para 2, 4, 6, 8, 10, e depois elimina todos os valores abaixo de 5, ficando com 6, 8 e 10, que somados resultam em 24.
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"] ✅

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

Justificativa:  a lista declarada de frutas que são, banana, maça, uva e laranja, seguindo a ordem de 0 a 3, sendo o 1 e o 2 substituídos pelos declarados ("abacaxi" e "manga"), resultado em ["banana", "abacaxi", "manga", "laranja"].
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira. ✅

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

Justificativa: As duas alternativas são verdadeiras. Mas a segunda não justifica a primeira 
porque a segunda explica como a herança é aplicada em js e a primeira aborda o motivo pelo qual a herança é utilizada
______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

a) I e II são verdadeiras. ✅

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

Justificativa: A classe funcionário herda da classe pessoa, e o método super(nome, idade) chama o construtor da classe pai, inicializando os atributos nome e idade. O método apresentar () na classe funcionário sobrepõe o método da classe pai, e a linha super.apresentar() é responsável por chamar o método original da classe pessoa.

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa. ✅

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

Justificativa: O conceito de polimorfismo na POO permite que que objetos de classes diferentes respondam à mesma mensagem diferentemente, No entanto, em JavaScript, isso não é feito por sobrecarga de métodos, já que ele considera apenas a última declaração de um método com o mesmo nome. Em vez disso, o polimorfismo é implementado por sobrescrita de métodos e herança. Assim, a afirmação é verdadeira, mas a razão é falsa.

______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

**Resposta:**
```javascript
function somaArray(numeros) {

    var soma = 0; //erro 1: a soma não estava sendo declarada e não estava igual a zero
    
    for (i = 0; i < numeros.length; i++) { //erro 2: o size não é definido em js o certo é length
        soma = soma + 2*numeros[i]; //erro 3: o valor da soma não estava sendo acumulado
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

**Explicação:**
A herança, nesse caso, funciona porque a classe Livro reutiliza tudo o que a classe Produto já possui — como os atributos nome e preço — sem precisar reescrevê-los. Usamos extends Produto para indicar que Livro é uma versão mais específica de Produto. No construtor de Livro, o super() chama o construtor da classe pai para garantir que nome e preço sejam configurados corretamente.
Além disso, reescrevemos o método calcularDesconto() dentro da classe Livro para dar a ela um comportamento diferente — isso é chamado de sobrescrita de método. Com isso, o livro aplica um desconto de 20%, enquanto os demais produtos mantêm o desconto padrão de 10%. Esse exemplo ilustra bem como a herança permite reaproveitar código e, ao mesmo tempo, ajustar apenas o que for necessário.

```javascript
class Produto {
  //adiciona a classe produto
  constructor(nome, preco) {
    this.name = nome; // define o nome do produto
    this.preco = preco; // define o preço do produto
  }
  // método que calcula 10% de desconto
  calcularDesconto() {
    return this.preco * 0.9; //multiplica o preço por 0.9
  }
}
// cria a classe de livro que herda de produto com "extends"
class Livro extends Produto {
  //"extends" herda a classe do produto
  constructor(nome, preco) {
    super(nome, preco);
  }
  //sobescreve o método de caucular desconto da classe pai
  calcularDesconto() {
    // chama o método da classe pai e aplica 20% de deconto
    return this.preco * 0.8;
  }
}
// criação do produto
const produto = new Produto("celular", 2000);
// imprime o preço do produto
console.log("produto com 10% de desconto:", produto.calcularDesconto());

// criação do livro
const livro = new Livro("é assim que acaba", 50);
// imprime o preço do livro qe é 20%
console.log("livro com 20% de desconto:", livro.calcularDesconto());
``` 
