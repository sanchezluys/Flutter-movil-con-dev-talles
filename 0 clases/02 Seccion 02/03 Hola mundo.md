Hola mundo
==========

Dart se puede ejecutar en el navegador, en el link [dartpad](https://dartpad.dev/).

```dart
void main() {
  print('Hola mundo');
}
```

![alt text](image-1.png)

## tipos de dato:

- void: no retorna nada

## crear variables

```dart
void main() {
  var nombre = 'Juan';
  print(nombre);
  print('hola $nombre');
}
```

### se recomienda definir de manera explicita el tipo de dato

```dart
void main() {
  String nombre = 'Juan';
  print(nombre);
  print('hola $nombre');
}
```

### comentarios con doble barra o con barra y asterisco

```dart
void main() {
  // comentario de una linea
  /*
  comentario
  multilinea
  */
  String nombre = 'Juan';
  print(nombre);
  print('hola $nombre');
}
```

### variable final, similar a una constante pero no es igual

```dart
void main() {
  final String nombre = 'Juan';
  print(nombre);
  print('hola $nombre');
}
```

### inicialización tardía *late*

```dart
void main() {
  late String nombre;
  nombre = 'Juan';
  print(nombre);
  print('hola $nombre');
}
```

### definir constantes

```dart
void main() {
  const String nombre = 'Juan';
  print(nombre);
  print('hola $nombre');
}
```

![note] constantes se agrega en tiempo de construcción: const
![note] final se agrega en tiempo de ejecución