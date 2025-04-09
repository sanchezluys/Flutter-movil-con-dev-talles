Dart, Async - await
=====================


- [S2/L20](https://www.youtube.com/watch?v=2TMuWJBtmc4&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=26)

- `async` y `await` son palabras reservadas de Dart que permiten trabajar con operaciones asíncronas de una manera más sencilla y legible.
- `async` se utiliza para marcar una función como asíncrona, lo que significa que puede contener operaciones asíncronas y devolver un `Future`.
- mejor legibilidad

```dart
void main() async {
  print('Inicio del programa');
  String data = await getData();
  print(data);
  print('Fin del programa');
}
// simular una petición a un servidor
// se puede usar el async y await para manejar la respuesta de una función asíncrona
Future<String> getData() async {
  await Future.delayed(Duration(seconds: 2), () {
    return print('tenemos un valor de la petición');
  });
}
```

- ahora usando try y catch para manejar la excepción

```dart
void main() async {
  print('Inicio del programa');
  try {
    String data = await getData();
    print(data);
  } catch (e) {
    print('Error: $e');
  } finally {
    print('Fin del programa');
  }
}
// simular una petición a un servidor
// se puede usar el async y await para manejar la respuesta de una función asíncrona
Future<String> getData() async {
  await Future.delayed(Duration(seconds: 2), () {
    return print('tenemos un valor de la petición');
  });
  throw Exception('Error en la petición');
}
```
- el `try` y `catch` se utilizan para manejar excepciones en el código, lo que permite capturar errores y evitar que el programa se detenga abruptamente.