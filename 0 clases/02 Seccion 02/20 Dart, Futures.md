Dart, Futures
=====================


- [S2/L19](https://www.youtube.com/watch?v=Oyabb8vTz-w&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=25)

- operación asíncrona
- se ejecuta en segundo plano
- no bloquea el hilo principal
- se debe manejar la excepción
- es una promesa


```dart
void main() async {
  print('Inicio');
  await Future.delayed(Duration(seconds: 2), () {
    print('Fin');
  });
  print('Fin2');
}
```

- otro ejemplo, simulando una petición a un servidor

```dart
void main(){
    print('Inicio del programa');
    //
    // simular una petición a un servidor
    getData().then((data) {
      print(data);
    }).catchError((error) {
      print('Error: $error');
    }).whenComplete(() {
      print('Fin de la petición');
    });


    print('Fin del programa');
}
//
Future<String> getData() async {
    await Future.delayed(Duration(seconds: 2), () {
      print('Fin de la petición');
    });
    return 'Datos de la petición';
  }
```