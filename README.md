# exercicio_01-04

**1. Estrutura de Classes e Objetos**

a) Quais atributos são definidos na classe Animal? 

Os atributos presentes na classe são: nome, espécie e idade. 

b) Como a classe AnimalSelvagem amplia a estrutura de Animal?

Com o constructor, a classe AnimalSelvagem herda os métodos e atributos da classe base “Animal” e adiciona o novo atributo “habitat”.

**2. Herança**

c) O que significa a linha class AnimalSelvagem extends Animal? 

O comando "extendend", permite a herança de métodos e atributos entre a classe base “Animal” e a classe derivada “AnimalSelvagem”.

d) O que acontece internamente quando usamos o comando super(...) dentro do  construtor da subclasse?

O comando "super" puxa todas as definições herdadas da classe base, como “this.nome = nome",
"this.especie = especie;” evitando ter que defini-los novamente.

**3. Instanciação**

e) O que ocorre passo a passo quando o comando new AnimalSelvagem("Nala",  "Leoa", 5, "Savana Africana") é executado?

Ele cria um objeto (um animal selvagem) e define um valor de retorno para cada atributo, como nome sendo “nala”, espécie sendo “leoa”, idade sendo “5” anos e habitat sendo “Savana”.

f) Qual a diferença entre a criação dos objetos animal1 e animal2?

O animal1, pertence a classe base, ou seja, tem os atributos: "nome, idade e espécie", já o animal 2, pertencendo a classe derivada, contém além dos atributos da classe base, atributos novos, como “habitat”.

**4. Acesso a Métodos**

g) Por que o método exibirInformacoes() pode ser utilizado tanto em animal1 quanto  em animal2?

Ele pode ser utilizado em ambos os objetos, pois retorna atributos comuns entre os dois como "nome, idade e espécie".

h) O método exibirHabitat() está disponível em animal1? Justifique sua resposta. 

Não está disponível, pois o retorno de exibirHabitat(), referencia um atributo exclusivo da classe derivada, o “habitat”, o qual não está presente no objeto animal1.

**5. Reutilização de Código**

i) Como a herança contribui para evitar duplicação de código nesse exemplo?

Através da herança, podemos puxar declarações de outras classes, para evitar escrevê-las novamente, como por exemplo, o super puxa todas as definições herdadas da classe base, como “**this.nome = nome;, this.especie = especie;”** para a classe derivada.

 j) Se fosse necessário adicionar um novo comportamento a todos os animais, como  "dormir()", em qual classe ele deveria ser implementado? Por quê?

Seria implementada na classe base, assim, poderia ser herdada pela classe derivada.

**6. Retorno e Impressão**

k) Qual é a saída exata exibida no console ao executar o código apresentado?

Nome: Tico, Espécie: Macaco, Idade: 4
Nome: Nala, Espécie: Leoa, Idade: 5
Habitat natural: Savana Africana

 l) O que aconteceria se fosse removida a linha super(nome, especie, idade) do  construtor da classe AnimalSelvagem?

O código retornaria erro, pois os atributos “nome, idade e espécie” não teriam sua definição herdada da classe base, restando somente os atributos exclusivos da classe derivada.

**7. Prática de Extensão**

m) Crie uma nova subclasse chamada AnimalDomestico, que herda de Animal e inclui  um novo atributo chamado nomeDono.

n) Implemente um método chamado exibirDono() que retorne: "Dono de [nome do  animal]: [nome do dono]".

```javascript

// Classe base**

class Animal {

constructor(nome, especie, idade) {

this.nome = nome;

this.especie = especie;
this.idade = idade;

}

exibirInformacoes() {

return `Nome: ${this.nome}, Espécie: ${this.especie}, Idade: ${this.idade}`;  }

}

// Classe derivada**

class AnimalSelvagem extends Animal {

constructor(nome, especie, idade, habitat) {

super(nome, especie, idade);

this.habitat = habitat;

}

exibirHabitat() {

return `Habitat natural: ${this.habitat}`;

}

}

class AnimalDomestico extends Animal {
    constructor(nome, especie, idade, nomeDono) {
        super(nome,especie, idade)
        this.nomeDono = nomeDono;
    }
exibirDono () {
        return `Nome do dono: ${this.nomeDono}`;
    }
}

    

// Instâncias e retornos**

const animal1 = new Animal("Tico", "Macaco", 4);

const animal2 = new AnimalSelvagem("Nala", "Leoa", 5, "Savana Africana");
const animal3 = new AnimalDomestico("Shoyu", "Gato", 2, "Rayssa" )

console.log(animal1.exibirInformacoes());

console.log(animal2.exibirInformacoes());
console.log(animal2.exibirHabitat());

console.log(animal3.exibirInformacoes());

```
