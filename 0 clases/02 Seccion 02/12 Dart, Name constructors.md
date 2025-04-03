Dart, Name constructors
=========================

- [S2/L11](https://www.youtube.com/watch?v=WxUNKrzZ6_I&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=17)

- se pueden tener multiples constructores en una clase, pero no se pueden tener dos constructores con el mismo nombre.
- y dependiendo de los argumentos que se pasen, se ejecutara un constructor u otro.


```dart
class Persona {
  String nombre;
  int edad;

  // Constructor por defecto
  Persona(this.nombre, this.edad);

  // Constructor nombrado
  Persona.conNombre(this.nombre) : edad = 0;

  // Constructor nombrado con un valor por defecto
  Persona.conEdad(this.edad) : nombre = 'Sin nombre';

  // Constructor nombrado con un valor por defecto y un valor por defecto
  Persona.conNombreYEdad(this.nombre, [this.edad = 0]);
}
```

- con los heroes

```dart
void main(){

    final ironman = 
        Hero(
            name: 'Tony Stark', 
            power: 'Money',
            isAlive: false
            );
}
class Hero {

    String name;
    String? power;
    bool isAlive = true;

    Hero({
        required this.name, 
        required this.power,
        required this.isAlive
        }); 

    @override
    String toString() {
        // usando un ternario
        // return 'Hero: $name, Power: ${power ?? 'No power'}, Alive: $isAlive';
        // return 'Hero: $name, Power: $power, Alive: $isAlive';
        return 'Hero: $name, Power: $power, isAlive: ${ isAlive ? 'Yes!!' : 'Nope' }';
    }
}
```

## Constructor para un dato recibido como Json de una API por ejemplo

```dart
class Hero {
    String name;
    String? power;
    bool isAlive = true;

    Hero({
        required this.name, 
        required this.power,
        required this.isAlive
        }); 

    // Constructor para un dato recibido como Json de una API
    Hero.fromJson(Map<String, dynamic> json) : 
        name = json['name'] ?? 'Sin nombre',
        power = json['power'] ?? 'Sin poder',
        isAlive = json['isAlive'] ?? true;

    @override
    String toString() {
        return 'Hero: $name, Power: $power, Alive: $isAlive';
    }
}
```