Dart, clases abstractas y enumeraciones
==============================


- [S2/L14](https://www.youtube.com/watch?v=VesurDVHcoI&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=20)

- molde que sirve para crea otros moldes
- no se puede instanciar    
- se usa para aplicar patrones de diseño

```dart
void main() {
  // Vehiculo vehiculo = new Vehiculo(); // No se puede instanciar una clase abstracta
  var auto = new Auto();
  auto.acelerar();
  auto.frenar();
}
class Auto extends Vehiculo {
  @override
  void acelerar() {
    print('Acelerando el auto...');
  }

  @override
  void frenar() {
    print('Frenando el auto...');
  }
}
abstract class Vehiculo {
  void acelerar();
  void frenar();
}
```

- otro ejemplo de clase abstracta con EnergyPlant  

```dart 
void main() {
  var plantaSolar = new PlantaSolar();
  plantaSolar.producirEnergia();
  plantaSolar.apagarPlanta();

  var plantaEolica = new PlantaEolica();
  plantaEolica.producirEnergia();
  plantaEolica.apagarPlanta();
}
class PlantaSolar extends EnergyPlant {
  @override
  void producirEnergia() {
    print('Produciendo energia solar...');
  }

  @override
  void apagarPlanta() {
    print('Apagando planta solar...');
  }
}
class PlantaEolica extends EnergyPlant {
  @override
  void producirEnergia() {
    print('Produciendo energia eolica...');
  }

  @override
  void apagarPlanta() {
    print('Apagando planta eolica...');
  }
}
abstract class EnergyPlant {
  void producirEnergia();
  void apagarPlanta();
}
```

- si tenemos opciones especificas, podemos crear un tipo de dato enumerado
- enum es un tipo de dato que permite definir un conjunto de valores constantes
- se usa para representar un conjunto de opciones limitadas y predefinidas
- se usa para mejorar la legibilidad y la mantenibilidad del código
- se usa para evitar errores de escritura y mejorar la seguridad del tipo
- se usa para facilitar la comparación de valores
- se usa para mejorar la documentación del código

ejemplo:

```dart
void main() {
  enum PantType {nuclear, wind, solar, water, geothermal}
}
abstract class EnergyPlant {
  double energyLeft;
  PantType Type;  // nuclear, wind, solar, water, geothermal

  EnergyPlant({
    required this.energyLeft,
    required this.Type,
  });
}   
```