# área class abs
// Definição da classe abstrata
abstract class Forma {
  // Método abstrato (sem implementação)
  void desenhar();
  
  // Método concreto (com implementação) que agora retorna double
  double area();
}

// Subclasse concreta que estende a classe abstrata
class Circulo extends Forma {
  double raio;

  Circulo(this.raio);

  @override
  void desenhar() {
    print("Desenhando um círculo com raio $raio.");
  }

  @override
  double area() {
    return 3.14159 * raio * raio;
  }
}

// Outra subclasse concreta que estende a classe abstrata
class Retangulo extends Forma {
  double comprimento;
  double altura;

  Retangulo(this.comprimento, this.altura);

  @override
  void desenhar() {
    print("Desenhando um retângulo com largura $comprimento e altura $altura.");
  }

  @override
  double area() {
    return comprimento * altura;
  }
}

// Subclasse concreta para o Triângulo
class Triangulo extends Forma {
  double base;
  double altura;

  Triangulo(this.base, this.altura);

  @override
  void desenhar() {
    print("Desenhando um triângulo com base $base e altura $altura.");
  }

  @override
  double area() {
    return (base * altura) / 2;
  }
}

void main() {
  // Criando instâncias das subclasses
  Forma circulo = Circulo(5.0);
  Forma retangulo = Retangulo(10.0, 20.0);
  Forma triangulo = Triangulo(6.0, 8.0);

  // Chamando métodos
  circulo.desenhar(); // "Desenhando um círculo com raio 5.0."
  print("Área do círculo: ${circulo.area()}"); // "Área do círculo: 78.53975"

  retangulo.desenhar(); // "Desenhando um retângulo com largura 10.0 e altura 20.0."
  print("Área do retângulo: ${retangulo.area()}"); // "Área do retângulo: 200.0"

  triangulo.desenhar(); // "Desenhando um triângulo com base 6.0 e altura 8.0."
  print("Área do triângulo: ${triangulo.area()}"); // "Área do triângulo: 24.0"
}
