Dart, @override
=========================

- [S2/L10](https://www.youtube.com/watch?v=HGZ28wAYN8c&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=16)

## @override

- se utiliza para indicar que un método de una clase hija está sobrescribiendo un método de la clase padre

## Clases con el constructor y sus argumentos opcionales por nombre

```dart
void main() {
    final Hero wolverine = Hero(name: 'Logan', power: 'Regeneracion');
    print(wolverine.name); // Logan
    print(wolverine.power); // Regeneracion
}
class Hero {
    String name;
    String power;

    // Constructor
    Hero({ 
        required this.name, 
        required this.power });
}
```

- Ahora con un valor por defecto

```dart
void main() {
    final Hero wolverine = Hero(name: 'Logan');
    print(wolverine.name); // Logan
    print(wolverine.power); // Sin poder
}
class Hero {
    String name;
    String power;

    // Constructor
    Hero({ 
        required this.name, 
        this.power = 'Sin poder' });
}
```

- Ahora sobreescribiendo en el constructor el valor de toString() de la clase padre modificada con @override

```dart
void main() {
    final Hero wolverine = Hero(name: 'Logan');
    print(wolverine.name); // Logan
    print(wolverine.power); // Sin poder
    //*****
    print(wolverine); // Hero: Logan, Sin poder
}   
class Hero {
    String name;
    String power;

    // Constructor
    Hero({ 
        required this.name, 
        this.power = 'Sin poder' });

    @override
    String toString() {
        return 'Hero: $name, $power';
    }
}
```