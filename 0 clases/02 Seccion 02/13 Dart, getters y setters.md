Dart, Getters y Setters
=========================

- [S2/L12](https://www.youtube.com/watch?v=vOtw69YwofI&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=18)

- para hacer privadas las variables se usa el guion bajo (_) al inicio del nombre de la variable.
- se pueden crear getters y setters para acceder a las variables privadas de una clase.
- los getters y setters son métodos que permiten acceder y modificar las variables privadas de una clase de forma controlada.
- los getters se utilizan para obtener el valor de una variable privada, mientras que los setters se utilizan para modificar el valor de una variable privada.

```dart	
void main() {
    final mySquare = Square(side: 10);
    print('area: ${mySquare.area}');
}
class Square {
    double _side = 0.0; // variable privada

    Square({double side = 0}) {
        this._side = side;
    }

    double get area => _side * _side; // getter para obtener el área
    set side(double value) => _side = value; // setter para modificar el lado
}
```

- en el ejemplo anterior, la variable `_side` es privada y no se puede acceder directamente desde fuera de la clase `Square`. Sin embargo, se puede acceder a su valor a través del getter `area` y modificarlo a través del setter `side`.

## Usando el setter con throw y el if

```dart
void main() {
    final mySquare = Square(side: 10);
    print('area: ${mySquare.area}');
    mySquare.side = -5; // se lanza una excepción
}
class Square {
    double _side = 0.0; // variable privada

    Square({double side = 0}) {
        this._side = side;
    }

    double get area => _side * _side; // getter para obtener el área
    set side(double value) {
        if (value < 0) {
            throw Exception('El lado no puede ser negativo');
        }
        _side = value; // setter para modificar el lado
    }
}
```

## tambien se pueden usar aserciones para validar el setter

```dart
void main() {
    final mySquare = Square(side: 10);
    print('area: ${mySquare.area}');
    mySquare.side = -5; // se lanza una excepción
}   
class Square {
    double _side = 0.0; // variable privada

    Square({double side = 0}) {
        this._side = side;
    }

    double get area => _side * _side; // getter para obtener el área
    set side(double value) {
        assert(value >= 0, 'El lado no puede ser negativo'); // aserción para validar el lado
        _side = value; // setter para modificar el lado
    }
}
```
- las aserciones son una forma de validar condiciones en tiempo de ejecución y lanzar excepciones si la condición no se cumple. En este caso, se lanza una excepción si el valor del lado es negativo.