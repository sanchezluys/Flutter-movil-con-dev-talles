Dynamic type
============

[S2/L04](https://www.youtube.com/watch?v=AnyON-cr0S4&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=10)

- se recomienda no usar el tipo dynamic, ya que es un tipo de dato que puede ser cualquier cosa, y no se recomienda usarlo en producción.
- se recomienda usar un balance de donde usarlo y donde no usarlo.
- dynamic por defecto es null

```dart
void main() {
  dynamic nombre = 'Juan';
  print(nombre);
  nombre = 52;
  print(nombre);
}
```

- inclusive puede ser una funcion.
    
```dart 
    void main() {
        dynamic nombre = 'Juan';
        print(nombre);
        nombre = 52;
        print(nombre);
        nombre = () => 'Hola';
        print(nombre());
    }
```