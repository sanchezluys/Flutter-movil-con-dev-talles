Dart, Streams
=====================


- [S2/L22](https://www.youtube.com/watch?v=igbiVH8iLF0&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=28)

- puede ser un stream de un solo valor o de varios valores
- stream de un solo valor: Future
- stream de varios valores: Stream
- stream de un solo valor: StreamController
- stream de varios valores: StreamController.broadcast
- flujo de agua
- stream: flujo de datos
- stream: flujo de eventos
- stream: flujo de datos asíncronos
- stream: flujo de datos en tiempo real


- para que un strem emita resultados, se necesita alguien que lo escuche
- para que un stream emita resultados, se necesita un listener


```dart
void main() {
    emitNumbers().listen((event) {
        print('desde listen: $event');
    });
}
Stream<int> emitNumbers(){
    Stream.periodic(const Duration(seconds: 1), (value){
        // print('desde periodic: $value');
        return value;
    }).take(5);
}
```