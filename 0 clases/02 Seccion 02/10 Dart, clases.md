Dart, Clases
==============

- [S2/L09](https://www.youtube.com/watch?v=DMiw6xP8gPY&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=15)

## Clases   

- Flutter maneja clases
- Dart obliga a que inicialicen las variables dentro de la clase, existen varias formas de inicializar las variables

```dart
void main(){
    final Hero wolverine = Hero ('Logan','Regeneracion');
    print(wolverine.name); // Logan
    print(wolverine.power); // Regeneracion
}

class Hero {
    String name;
    String power;

    // Constructor
    Hero(this.name, this.power);
}

// otra forma de inicializar las variables es con el constructor

class Hero2 {
    String name;
    String power;

    // Constructor version 2
    Hero(String pName, String pPower)
        : name = pName,
          power = pPower;
}

class Person {
    String name;
    int age;
    String email;
    String phone;
    String address;

    // Constructor
    Person(this.name, this.age, this.email, this.phone, this.address);
}
```