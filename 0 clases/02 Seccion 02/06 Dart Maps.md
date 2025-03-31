Dart Maps
==========

[S2/L05](https://www.youtube.com/watch?v=tpgHBGRG1kQ&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=11)

- son pares de clave-valor, donde la clave es unica y el valor puede ser repetido.
- se puede acceder al valor a traves de la clave.
- se puede usar cualquier tipo de dato como clave, pero se recomienda usar String o int.
- son parecidos a los objetos de javascript.

```dart	

void main() {
    Map<String, String> persona = {
        'nombre': 'Juan',
        'apellido': 'Perez',
        'edad': '52'
    };
    print(persona['nombre']);
    print(persona['apellido']);
    print(persona['edad']);
}
```
- se puede usar el constructor Map() para crear un mapa.

```dart
void main() {
    Map<String, String> persona = Map();
    persona['nombre'] = 'Juan';
    persona['apellido'] = 'Perez';
    persona['edad'] = '52';
    print(persona['nombre']);
    print(persona['apellido']);
    print(persona['edad']);
}
```
- se puede usar el constructor Map() para crear un mapa con valores por defecto.

```dart
void main() {
    Map<String, String> persona = Map.from({
        'nombre': 'Juan',
        'apellido': 'Perez',
        'edad': '52'
    });
    print(persona['nombre']);
    print(persona['apellido']);
    print(persona['edad']);
};
```
- un caso que se recomienda tipar.
```dart
// no tipado
void main() {
   final pokemon= {
    'nombre': 'Pikachu',
    'tipo': 'Electrico',
    'nivel': 25,
    'habilidad': 'Impactrueno'
   };
}
```

```dart	
// tipado
void main() {
   final Map<String, dynamic> pokemon= {
    'nombre': 'Pikachu',
    'tipo': 'Electrico',
    'nivel': 25,
    'habilidad': 'Impactrueno'
   };
}
```
- para poder usar un dato de un mapa, se puede usar el operador de acceso a la propiedad (.) o el operador de acceso a la clave ([]).

```dart
void main() {
    final Map<String, dynamic> pokemon= {
        'nombre': 'Pikachu',
        'tipo': 'Electrico',
        'nivel': 25,
        'habilidad': 'Impactrueno',
        'sprite':{
            'frontal': 'https://pokeapi.co/media/sprites/pokemon/other/official-artwork/4.png',
            'trasero': 'https://pokeapi.co/media/sprites/pokemon/back/4.png'
        }
    };
    print(pokemon['nombre']);
    print(pokemon['tipo']);
    print(pokemon['nivel']);
    print(pokemon['habilidad']);
    print('Name: ${pokemon['nombre']}');
    //
    print('Back: ${pokemon['sprite']['trasero']}');
    print('Front: ${pokemon['sprite']['frontal']}');
}
```