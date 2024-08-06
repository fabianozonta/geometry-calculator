# Geometry Calculator

A simple geometry calculator written in JavaScript that allows you to compute the area of various geometric shapes. This program provides an interactive console-based interface where users can choose between different shapes to calculate their area.

## Features

- Calculate the area of a triangle
- Calculate the area of a rectangle
- Calculate the area of a square
- Calculate the area of a trapezoid
- Calculate the area of a circle
- Option to exit the program

## How It Works

The program presents a menu with the following options:

1. **Calculate a Triangle**: Requires base and height. Computes the area using the formula: `base * height / 2`.
2. **Calculate a Rectangle**: Requires base and height. Computes the area using the formula: `base * height`.
3. **Calculate a Square**: Requires the length of a side. Computes the area using the formula: `side^2`.
4. **Calculate a Trapezoid**: Requires the lengths of the two bases and the height. Computes the area using the formula: `((baseMajor + baseMinor) * height) / 2`.
5. **Calculate a Circle**: Requires the radius. Computes the area using the formula: `π * radius^2`.
6. **Exit**: Terminates the program.

## Code

```javascript
let base;
let altura;
let lado;
let baseMaior;
let baseMenor;
let raio;
let opcao;

function triangulo(base, altura) {
    return (base * altura / 2);
}

function retangulo(base, altura) {
    return base * altura;
}

function quadrado(lado) {
    return lado ** 2;
}

function trapezio(baseMaior, baseMenor, altura) {
    return ((baseMaior + baseMenor) * altura) / 2;
}

function circulo(raio) {
    return Math.PI * raio ** 2;
}

do {
    opcao = prompt('Escolha uma opção:\n1 - calcular um triângulo\n2 - calcular um retângulo\n3 - calcular um quadrado\n4 - calcular um trapézio\n5 - calcular raio de um círculo\n6 - Sair');

    switch (opcao) {
        case '1':
            base = parseFloat(prompt('Digite a base do triângulo: '));
            altura = parseFloat(prompt('Digite a altura do triângulo: '));
            if (!isNaN(base) && !isNaN(altura)) {
                alert(`A área do triângulo é de ${triangulo(base, altura)}`);
            } else {
                alert('Valores inválidos. Por favor, insira números válidos.');
            }
            break;
        case '2':
            base = parseFloat(prompt('Digite a base do retangulo: '));
            altura = parseFloat(prompt('Digite a altura do retangulo: '));
            if (!isNaN(base) && !isNaN(altura)) {
                alert(`A área do retângulo é de ${retangulo(base, altura)}`);
            } else {
                alert('Valores inválidos. Por favor, insira números válidos.');
            }
            break;
        case '3':
            lado = parseFloat(prompt('Digite o lado do quadrado: '));
            if (!isNaN(lado)) {
                alert(`A área do quadrado é de ${quadrado(lado)}`);
            } else {
                alert('Valores inválidos. Por favor, insira números válidos.');
            }
            break;
        case '4':
            baseMaior = parseFloat(prompt('Digite a maior base do trapézio: '));
            baseMenor = parseFloat(prompt('Digite a menor base do trapézio: '));
            altura = parseFloat(prompt('Digite a altura do trapézio: '));
            if (!isNaN(baseMaior) && !isNaN(baseMenor) && !isNaN(altura)) {
                alert(`A área do trapézio é de ${trapezio(baseMaior, baseMenor, altura)}`);
            } else {
                alert('Valores inválidos. Por favor, insira números válidos.');
            }
            break;
        case '5':
            raio = parseFloat(prompt('Digite o raio do círculo: '));
            if (!isNaN(raio)) {
                alert(`A área do círculo é de ${circulo(raio)}`);
            } else {
                alert('Valor inválido. Por favor, insira um número válido.');
            }
            break;
        case '6':
            alert('Saindo do programa');
            break;
        default:
            alert('Opção inválida');
    }
} while (opcao !== '6');
