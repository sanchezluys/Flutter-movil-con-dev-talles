Dart, Async* y await
======================


- [S2/L23](https://www.youtube.com/watch?v=CX9saA9W96M&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=29)


- la funcion async* se utiliza para indicar que una funcion es asincrona, lo que significa que puede realizar operaciones de larga duracion sin bloquear el hilo principal de la aplicacion. Esto es especialmente util en aplicaciones que requieren interaccion con el usuario o que realizan operaciones de red, como solicitudes HTTP o acceso a bases de datos.
- por defecto devuelve un stream, pero se puede cambiar el tipo de retorno a un iterable, lo que permite utilizar la funcion como un generador de datos.
- el uso de async* permite que la funcion devuelva datos a medida que se generan, en lugar de esperar a que se complete toda la funcion antes de devolver un resultado. Esto puede mejorar el rendimiento y la capacidad de respuesta de la aplicacion, ya que permite que el hilo principal siga ejecutandose mientras se generan los datos.
- el uso de async* es especialmente util en aplicaciones que requieren interaccion con el usuario o que realizan operaciones de larga duracion, como solicitudes HTTP o acceso a bases de datos. Al utilizar async*, se puede evitar que la aplicacion se congele o se vuelva inactiva mientras espera a que se completen estas operaciones.    
- el uso de async* permite que la funcion devuelva datos a medida que se generan, en lugar de esperar a que se complete toda la funcion antes de devolver un resultado. Esto puede mejorar el rendimiento y la capacidad de respuesta de la aplicacion, ya que permite que el hilo principal siga ejecutandose mientras se generan los datos.

- emisiones controladas

```dart
void main(){
    emitNumber()
    .listen((int value){
        print('stream value: $value');
    });
}
Stream<int> emitNumber() async* {
    for (int i = 0; i < 10; i++) {
        await Future.delayed(Duration(seconds: 1));
        yield i;
    }
}
```

- el uso de async* permite que la funcion devuelva datos a medida que se generan, en lugar de esperar a que se complete toda la funcion antes de devolver un resultado. Esto puede mejorar el rendimiento y la capacidad de respuesta de la aplicacion, ya que permite que el hilo principal siga ejecutandose mientras se generan los datos.