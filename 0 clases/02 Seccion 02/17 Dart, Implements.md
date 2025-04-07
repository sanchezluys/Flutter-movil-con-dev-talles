Dart, Implements
=====================


- [S2/L16](https://www.youtube.com/watch?v=WSgcKk1symw&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=22)

en la implementación de una clase, se puede implementar una o varias interfaces, pero no se puede heredar de varias clases.

ejemplo con la planta de energía:

```dart
void main() {
  final windPlant = WindPlant(initialEnergy: 100);
  final nuclearPlant = NuclearPlant(initialEnergy: 1000);

  print('wind: ${ chargePhone(windPlant) }');
  print('nuclear: ${ chargePhone(nuclearPlant) }');
}

double chargePhone(EnergyPlant plant) {
  if( plant.energyLeft < 10>){
    throw Exception('Not enough energy');
  }
  return plant.energyLeft - 10;
}

enum PlantType {
  wind,
  nuclear,
  water
}

class WindPlant extends EnergyPlant {
  WindPlant({required double initialEnergy}) 
  : super(initialEnergy: initialEnergy, type: PlantType.wind);

  @override
  void consumeEnergy(double amount) {
    energyLeft -= amount;
  }
}

class NuclearPlant implements EnergyPlant {
  NuclearPlant({required double initialEnergy}) 
  : _energyLeft = initialEnergy, _type = PlantType.nuclear;

  @override
  double get energyLeft => _energyLeft;
  double _energyLeft;

  @override
  PlantType get type => _type;
  PlantType _type;

  @override
  void consumeEnergy(double amount) {
    _energyLeft -= amount;
  }
}
```

## Principio de inversión de dependencias

- Las clases de alto nivel no deben depender de las clases de bajo nivel. Ambas deben depender de abstracciones.
- Las abstracciones no deben depender de los detalles. Los detalles deben depender de las abstracciones.
- Esto significa que las clases de alto nivel no deben depender de las clases de bajo nivel, sino de interfaces o clases abstractas. Las clases de bajo nivel deben implementar estas interfaces o clases abstractas. Esto permite que el código sea más flexible y fácil de mantener, ya que se pueden cambiar las implementaciones sin afectar a las clases de alto nivel.
- Esto se puede lograr utilizando interfaces o clases abstractas para definir las dependencias entre las clases. Las clases de alto nivel deben depender de estas interfaces o clases abstractas, y las clases de bajo nivel deben implementar estas interfaces o clases abstractas. Esto permite que el código sea más flexible y fácil de mantener, ya que se pueden cambiar las implementaciones sin afectar a las clases de alto nivel.
- Esto se puede lograr utilizando interfaces o clases abstractas para definir las dependencias entre las clases. Las clases de alto nivel deben depender de estas interfaces o clases abstractas, y las clases de bajo nivel deben implementar estas interfaces o clases abstractas. Esto permite que el código sea más flexible y fácil de mantener, ya que se pueden cambiar las implementaciones sin afectar a las clases de alto nivel.