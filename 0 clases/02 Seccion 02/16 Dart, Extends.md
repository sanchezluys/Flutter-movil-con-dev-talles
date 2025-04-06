Dart, Extends
====================

- [S2/L15](https://www.youtube.com/watch?v=pX3j5ccq5t4&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=21)

## Diferencia entre extends e implements

- `extends`: se usa para heredar de una clase, es decir, para crear una subclase que hereda los métodos y propiedades de la clase padre. La subclase puede sobrescribir los métodos de la clase padre.
- `implements`: se usa para implementar una interfaz, es decir, para crear una clase que implementa los métodos de la interfaz. La clase que implementa la interfaz debe implementar todos los métodos de la interfaz.
- `extends` se usa para heredar de una clase, mientras que `implements` se usa para implementar una interfaz.

ejemplo con la planta de energía:

```dart
void main() {
    final windPlant = WindPlant(energyLeft: 100, type: PlantType.wind);
    print('Wind Plant Type: ${windPlant.type}');
}
enum PlantType {
    solar,
    wind,
    hydro,
    nuclear}

abstract class EnergyPlant {
    double energyLeft;
    PlantType type;

    EnergyPlant({
        required this.energyLeft, 
        required this.type
        });
    void consumeEnergy(double amount);
}

// extiende de EnergyPlant
class WindPlant extends EnergyPlant {

    WindPlant({
        required double energyLeft,
        required PlantType type
    }) : super(energyLeft: energyLeft, type: PlantType.wind);

    @override
    void consumeEnergy(double amount) {
        energyLeft -= amount;
    }
}
```

## Razones para crear una clase abstracta

- Para crear una clase base que no se puede instanciar, pero que se puede extender para crear subclases.
- Para definir un contrato que las subclases deben cumplir, es decir, para definir los métodos y propiedades que deben tener las subclases.
- Para crear una jerarquía de clases que comparten un comportamiento común, pero que tienen implementaciones diferentes.
- Para crear una clase que no tiene sentido instanciar, pero que se puede usar como base para crear otras clases.
- Para crear una clase que se puede usar como un molde para crear otras clases, es decir, para crear una clase que se puede usar como una plantilla para crear otras clases.
- Para crear una clase que se puede usar para aplicar patrones de diseño, es decir, para crear una clase que se puede usar para implementar un patrón de diseño.

