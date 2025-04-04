Dart, Aserciones
================


- [S2/L13](https://www.youtube.com/watch?v=s5HO2T7OoSA&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=19)

- Sirve para crear las reglas del negocio, es decir, las reglas que deben cumplirse para que el programa funcione correctamente.
- Se pueden usar para validar los parámetros de un método o constructor, o para validar el estado de un objeto.

```dart
void main() {
    final mySquare = Square(side: 10);
    print('area: ${mySquare.area}');
    mySquare.side = -5; // se lanza una excepción
}
class Square {
    double _side = 0.0; // variable privada

    Square({double side = 0}) {
        assert(side > 0, 'El lado no puede ser negativo'); // aserción para validar el lado
        this._side = side;
    }

    double get area => _side * _side; // getter para obtener el área
    set side(double value) {
        assert(value > 0, 'El lado no puede ser negativo'); // aserción para validar el lado
        _side = value; // setter para modificar el lado
    }
}
```

[]: # - En el ejemplo anterior, se lanza una excepción si el lado es negativo al crear el objeto o al modificarlo.
[]: # - Las aserciones son útiles para detectar errores en tiempo de desarrollo, pero no se deben usar para validar la entrada del usuario en tiempo de ejecución.
[]: # - Las aserciones se pueden desactivar en producción, por lo que no se deben usar para validar la entrada del usuario en tiempo de ejecución.
[]: # - En su lugar, se deben usar excepciones para validar la entrada del usuario en tiempo de ejecución.
