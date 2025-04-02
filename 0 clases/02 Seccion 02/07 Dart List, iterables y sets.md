List, Iterables y Sets
================

[S2/L06](https://www.youtube.com/watch?v=pd5hBsuv1QE&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=12)

## iterables

- es un dato que puede ser recorrido
- se reconoce por los paréntesis en el resultado ()
- en cambio la lista se reconoce por los corchetes []

```dart
void main() {
    final numbers = [1, 2, 3, 4, 5,5,5,6,7,7,8,9,9,9,10];
    print('List original: $numbers'); // [1, 2, 3, 4, 5, 5, 5, 6, 7, 7, 8, 9, 9, 9, 10]
    print('Length: ${numbers.length}'); // 15
    pint('Index 0: ${numbers[0]}'); // 1
    print('First: ${numbers.first}'); // 1
    print('Last: ${numbers.last}'); // 10
    print('Reversed: ${numbers.reversed}'); // (10, 9, 9, 9, 8, 7, 7, 6, 5, 5, 5, 4, 3, 2, 1) *parentesis es un iterable
}
```

### algunas propiedades interesantes de los iterables son:

- toList(): convierte un iterable a una lista, [1,2,3,4,5,6,7,8,9,10]
- toSet(): convierte un iterable a un set, elimina los duplicados solo muestra los únicos {1,2,3,4,5}
- toString(): convierte un iterable a una cadena de texto, [1, 2, 3, 4, 5]

## Listados

- tiene metodos como el where, map, forEach, reduce, fold
- el where filtra los elementos de una lista, devuelve un iterable
- el map transforma los elementos de una lista, devuelve un iterable
- el forEach recorre los elementos de una lista, devuelve un void
- el reduce reduce los elementos de una lista a un solo elemento, devuelve un solo elemento
- el fold reduce los elementos de una lista a un solo elemento, devuelve un solo elemento

```dart
void main() {
    final numbers = [1, 2, 3, 4, 5,5,5,6,7,7,8,9,9,9,10];
    final numbersGreaterThanFive = numbers.where((number) => number > 5); 
}
```