Dart, Ejercicios con mixins
=====================


- [S2/L18](https://www.youtube.com/watch?v=OA7mOCOJNsE&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=24)

- se crea la clase abstracta, tomemos el ejemplo de la clase `Animal` y la clase `Perro` que hereda de `Animal`.


```dart
abstract class Animal {
  
}
abstract class Mamifero extends Animal {
  
}
abstract class Ave extends Animal {
  
}
abstract class Pez extends Animal {
  
}

abstract class Volador {
    void volar() => print('Estoy volando');
}
abstract class Caminante {
    void caminar() => print('Estoy caminando');
}
abstract class Nadador {
    void nadar() => print('Estoy nadando');
}

// comenzando a usar mixins, vamos a crear el delfin.
class Delfin extends Mamifero with Nadador {
    void nadar() => print('Soy un delfin nadando');
}

// con el murcielago, que es un mamifero volador.
class Murcielago extends Mamifero with Volador, Caminante {
    void volar() => print('Soy un murcielago volando');
}

// el gato, que es un mamifero caminante.
class Gato extends Mamifero with Caminante {
    void caminar() => print('Soy un gato caminando');
}

// paloma
class Paloma extends Ave with Volador, Caminante {
    void volar() => print('Soy una paloma volando');
}
// pato
class Pato extends Ave with Volador, Caminante, Nadador {
    void volar() => print('Soy un pato volando');
}
// tiburon
class Tiburon extends Pez with Nadador {
    void nadar() => print('Soy un tiburon nadando');
}
// pez volador
class PezVolador extends Pez with Volador, Nadador {
    void volar() => print('Soy un pez volador');
}

// usando los mixins
void main() {
    final flipper = Delfin();
    flipper.nadar(); // Soy un delfin nadando
 

    final batman = Murcielago();
    batman.caminar(); // Estoy caminando
    batman.volar(); // Soy un murcielago volando

    final gato = Gato();
    gato.nadar(); // Error, no puede nadar
    gato.caminar(); // Soy un gato caminando
    gato.volar(); // Error, no puede volar

    final paloma = Paloma();
    paloma.nadar(); // Error, no puede nadar
    paloma.caminar(); // Estoy caminando
    paloma.volar(); // Soy una paloma volando

    final namor = Pato();
    namor.nadar(); // Soy un pato nadando
    namor.caminar(); // Estoy caminando
    namor.volar(); // Soy un pato volando

    final tiburon = Tiburon();
    tiburon.nadar(); // Soy un tiburon nadando
    tiburon.caminar(); // Error, no puede caminar
    tiburon.volar(); // Error, no puede volar

    final pezVolador = PezVolador();
    pezVolador.nadar(); // Soy un pez volador nadando
    pezVolador.caminar(); // Error, no puede caminar
    pezVolador.volar(); // Soy un pez volador volando
}
```