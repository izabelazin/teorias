## Entendendo alguns conceitos... :brain:
Este repositório contém alguns conceitos teórico necessárias para a evolução profissional :woman_technologist:

### Teorias
 - [Escopo](#scope)
 - [Variáveis](#variables)
 - [Classes](#classes)
 - [Atributos](#attributes)


####  <a name="scope"></a>Escope
Escopo é a acessibilidade de objetos, variáveis e funções em diferentes partes do código.

- Escopo Global: uma variável global é definida quando declaramos uma variável fora de qualquer função, assim ela torna **acessível a qualquer parte** da nossa aplicação ou site, podendo ser lida e alterada.

- Escopo Local: uma variável se torna local quando ela é declarada dentro de uma função, de tal maneira a qual ela somente estará **acessível dentro dessa função**.	

- Escopo de bloco: não existia no JS escopo de bloco. Ou seja, for whiles e ifs não tinham escopo próprio. Porém com o ECMAScript 6 foi possível criar escopos de bloco usando as variáveis **let** e **const**, que são **acessíveis somente dentro do bloco.**

#### <a name="variables"></a> Variables (var, let e const)

- Var: 
	-    é içada
	-   tem escopo abrangente → se for declarada dentro de um bloco → vaza do escopo
	-   escopo global e função → n tem escopo de bloco
	- Praticamente não são mais usadas em aplicações modernas devidos aos problemas de escopo → **substituídas por const e lets**
  
```javascript
function varName (a) {
  var name = 'Sofia'
  
  function varAge () {
    var age = 23
    console.log(name) // Luca
    console.log(age) // 23
  }
  
  varAge() // Lucas - 23
  console.log(name) // Lucas
  console.log(age) // age is not defined
}
```

```javascript
if(true) {
    var global = 2; // vaza de dentro do bloco
}

function teste() {
    var global = 4;
    console.log(global); //4
}

console.log(global); //2 -> acessa a que vazou do if
``` 

 - Let e Const
	-   Tem escopo de **bloco** e de função
	-  Sofrem hoisting (são elevadas) para o topo do bloco que foram definidas → porém não é atribuido o valor de undefined como acontece com var  → continuam não inicializadas e dão erro caso sejam chamadas antes de suas declarações.
	- A grande diferença entre as duas é que consts não podem ser reatribuídas enquanto lets sim.
	
		 - Let: considera o bloco de código de sua origem. Isso significa que se a declararmos dentro de um **if( )**, **switch( )** ou **for( )**, ela será “vista” apenas dentro desta parte do código, dentro deste escopo específico.
		 - Const: usada para definir uma constante. Uma variável que não podemos sobrescrever o seu identificador. 

```javascript
function name() {
	console.log(name); // ❌ retorna erro porque ainda não foi inicializada
	let name = 'izabela';
	console.log(name); // 👍🏼 izabela
	name = 'izabela 2'; // 👍🏼 pode ser reatruída
}

const num = 6;
num = 8; // ❌ Não pode ser reatribuída porque é const

```

####  <a name="classes"></a>Classe
Classes nos dão uma sintaxe amigável que definem o estado e o comportamento de objetos que representam as abstrações que usamos diariamente.
Por exemplo, se necessitarmos de uma abstração para animais em que cada animal possui um nome, poderíamos implementar dessa forma:
```javascript

const animal = new Animal('dog')
animal.getName() // dog
animal.setName('cat')
animal.getName() // cat

```

####  <a name="attributes"></a>Atributo
Atributos são os elementos que definem a estrutura de uma classe. Um atributo é um dado para que cada objeto tenha seu próprio valor. Atributos são, basicamente, a estrutura de dados que vai representar a classe.
