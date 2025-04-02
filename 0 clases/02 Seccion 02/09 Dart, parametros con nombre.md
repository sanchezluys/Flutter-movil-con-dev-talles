Dart, Parametros con nombre
=========================

- [S2/L08](https://www.youtube.com/watch?v=kbxmwkUJeOI&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=14)

## Parámetros con nombre obligatorios y posicionales

- se declaran con {} // opcionales

```dart
void main() {
    print(greetEveryone());  // Hola everyone
    print(greetFlecha());  // Hola con funcion flecha
    print(addTwoNumbers(1, 2));  // 3
    print(addTwoNumbersFlecha(1, 2));  // 3
    print(greet('Juan', 'Pérez'));  // Hola Juan Pérez
    print(greet('Juan'));  // Hola Juan null

    print(greetSaludo(name: 'Juan', message: 'Hola'));  // Hola Juan
    print(greetSaludo(name: 'Juan'));  // hola, Juan
}
String greet(String name, {String lastName}) {
    return 'Hola $name $lastName';
}

String greetSaludo({required String name, String message ='hola, '}) {
    return '$message $name';
};
```