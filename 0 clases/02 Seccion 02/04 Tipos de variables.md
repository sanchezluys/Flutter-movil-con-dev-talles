Tipos de variables
==================

[S2/L03](https://www.youtube.com/watch?v=9ACoJV3xa38&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=9)

- se van a mostrar muchos warnings, pero no hay que preocuparse


## Enteros

```dart
void main() {
  int edad = 52;
  print(edad);
}
```

## Double

```dart
void main() {
  double pi = 3.141592;
  print(pi);
}
```

## String

```dart
void main() {
  String nombre = 'Juan';
  print(nombre);
}
```

## Boolean

```dart
void main() {
  bool activo = true;
  print(activo);
}
```

## List

```dart
void main() {
  List<String> frutas = ['manzana', 'pera', 'uva'];
  print(frutas);
}
```

## Set

```dart
void main() {
  Set<String> frutas = {'manzana', 'pera', 'uva'};
  print(frutas);
}
```

## Map

```dart
void main() {
  Map<String, dynamic> persona = {
    'nombre': 'Juan',
    'edad': 30,
    'soltero': true
  };
  print(persona);
}
```

## Runes

```dart
void main() {
  var simbolo = '\u{1F60D}';
  print(simbolo);
}
```

## Symbols

```dart
void main() {
  Symbol simbolo = #miSimbolo;
  print(simbolo);
}
```

## Null

```dart
void main() {
  var variableNula;
  print(variableNula);
}
```

## Dynamic

```dart
void main() {
  dynamic variableDinamica = 'Hola';
  print(variableDinamica);
}
``` 

## Constantes

```dart
void main() {
  const pi = 3.1416;
  print(pi);
}
``` 

## Final

```dart
void main() {
  final pi = 3.1416;
  print(pi);
}
```

## String interpolación

```dart
void main() {
  String nombre = 'Juan';
  String saludo = 'Hola $nombre';
  print(saludo);
}
```

## String concatenación

```dart
void main() {
  String nombre = 'Juan';
  String saludo = 'Hola ' + nombre;
  print(saludo);
}
``

## String raw

```dart
void main() {
  String ruta = r'C:\Program Files\Dart';
  print(ruta);
}
```


## String multilinea

```dart
void main() {
  String multilinea = '''
  Hola mundo
  ¿Cómo están?
  ''';
  print(multilinea);
}
```

## Null safety

```dart
void main() {
  String? nombre = null;
  print(nombre);
}
```

## Null safety con operador de cascada

```dart
void main() {
  String? nombre = null;
  print(nombre?.length);
}
```

## iterables

```dart
void main() {
  List<String> frutas = ['manzana', 'pera', 'uva'];
  frutas.add('sandía');
  print(frutas);
}
```