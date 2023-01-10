# dados-atletas
function comparacaoDasNotas(x,y) {return x - y;}

class Atleta {
    constructor(nome, idade, peso, altura, notas) {
        this.nome = nome;
        this.notas = notas;
        this.altura = altura;
        this.peso = peso;
        this.idade = idade;
    }
    calculaCategoria(){
        if (this.idade >= 16 & this.idade <= 30) {
            return "Adulto";
        }else if (this.idade >= 14 & this.idade <= 15) {
            return "Intermediário";
        }else if (this.idade >= 12 & this.idade <= 13) {
            return "Juvenil";
        }else if (this.idade >= 9 & this.idade <= 11) {
            return "Infantil";
        }
        else {
            return "demais idades"
        }
    }
    calculaIMC() {
            return this.peso / (this.altura * this.altura)
    }
    calculaMediaValida() {
        let total = 0;
        this.notas = this.notas.sort(comparacaoDasNotas).slice(1,4)
        this.notas.map(function(notas) {
            total = total + notas
        })
        return total / this.notas.length
    }
    obtemNomeAtleta() {
        return this.nome
    }
    obtemIdadeAtleta() {
        return this.idade
    }
    obtemPesoAtleta() {
        return this.peso
    }
    obtemAlturaAtleta() {
        return this.altura
    }
    obtemNotasAtleta(){
        return this.notas
    }
    obtemCategoria() {
        return this.calculaCategoria()
    }
    obtemIMC() {
        return this.calculaIMC()
    }
    obtemMediaValida() {
        return this.calculaMediaValida()
    }
}
// Declara o atleta
const atleta = new Atleta("Cesar Abascal",
    30, 80, 1.70,
    [10, 9.34, 8.42, 10, 7.88]);

console.log("Nome: " + atleta.obtemNomeAtleta())
console.log("Idade: " + atleta.obtemIdadeAtleta())
console.log("Peso: " + atleta.obtemPesoAtleta())
console.log("Altura" + atleta.obtemAlturaAtleta())
console.log("Notas: " + atleta.obtemNotasAtleta())
console.log("Categoria: " + atleta.obtemCategoria())
console.log("IMC: " + atleta.obtemIMC())
console.log("Média válida: " + atleta.obtemMediaValida())
