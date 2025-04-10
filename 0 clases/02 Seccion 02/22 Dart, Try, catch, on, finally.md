Dart, Try, catch, on, finally
=====================

# - [S2/L21](https://www.youtube.com/watch?v=-JCQKmZn8pI&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=27)


- se usa para errores que no se pueden controlar, como un error de red o un error de servidor.
- se usa para errores que se pueden controlar, como un error de validación o un error de formato.
- se usa para errores que se pueden manejar, como un error de conexión o un error de tiempo de espera.
- se usa para errores que se pueden ignorar, como un error de sintaxis o un error de tipo.


```dart
void main() async {

    try {
        final value = await httpGet("https://api.escuelajs.co/api/v1/products/1");
        print('exito: $value');
    } on Excepcion {
        print('tenemos una excepcion')
    } 
    catch (e) {
        print('oops!! algo terrible pasó, error: $e');
    }
    finally {
        print('fin del try catch');
    }
    print('fin del programa');
}
Future<String> httpGet(String url) {
  await Future.delayed(Duration(seconds: 2));
  throw Exception("no hay parametros en el url");
}
```
