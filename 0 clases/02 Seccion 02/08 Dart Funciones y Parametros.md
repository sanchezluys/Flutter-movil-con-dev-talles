Dart, Funciones y Parámetros
=========================

- [S2/L07](https://www.youtube.com/watch?v=PJ1pOxr3d8Q&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=13)

## Función main()

- es el punto de entrada de la aplicación
- es la función que se ejecuta primero
- es la función que se ejecuta al iniciar la aplicación
- con void main() {} se define la función main y no devuelve nada

## Funciones

- son bloques de código que se pueden reutilizar
- se definen con la palabra reservada void
- pueden recibir parámetros
- pueden devolver valores
- se definen con la palabra reservada return
- pueden ser funciones anónimas
- pueden ser funciones de flecha

```dart
void main() {
    print(greetEveryone());  // Hola everyone
}
String greetEveryone() {
    return 'Hola everyone';
}
String greetFlecha() => 'Hola con funcion flecha';

int addTwoNumbers(int a, int b) {
    return a + b;
    // si no declaro que a y b son enteros entonces serán dynamicos, no se recomienda
}

int addTwoNumbersFlecha(int a, int b) => a + b;
```

### Argumentos opcionales

- se declaran con []
- pueden ser null
- pueden ser obligatorios
- pueden ser opcionales
- pueden ser nombrados
- pueden ser posicionales

```dart
void main() {
    print(greetEveryone());  // Hola everyone
    print(greetFlecha());  // Hola con funcion flecha
    print(addTwoNumbers(1, 2));  // 3
    print(addTwoNumbersFlecha(1, 2));  // 3
    print(greet('Juan', 'Pérez'));  // Hola Juan Pérez
    print(greet('Juan'));  // Hola Juan null
}
String greet(String name, [String lastName]) {
    return 'Hola $name $lastName';
}

int addTwoNumbers(int a, int b, [int c]) {
    return a + b + (c ?? 0);
    // c es opcional y si no se pasa se le asigna 0
}

// opcional dynamico
int addTwoNumbersOptional(int a, int b, [int? c]) {
    return a + b + c;
    // c es opcional y es dinamico, tampoco se recomienda
    // se puede usar c ?? 0 // que coloca 0 si c es null
}

// establecer un valor por defecto en el argumento
int addTwoNumbersDefault(int a, int b, [int c = 0]) {
    return a + b + c;
    // c es opcional y se le asigna 0 por defecto
}
```