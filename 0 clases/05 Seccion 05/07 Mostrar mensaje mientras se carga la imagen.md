Mostrar mensaje mientras se carga la imagen
===========================================

- [S5/L07](https://www.youtube.com/watch?v=1SHC65wC0lM&list=PLCKuOXG0bPi0sIn-nDsi7ma9OV6MEMkxj&index=63)

## Ajuste e de los mensajes de ella

```dart
import 'package:flutter/material.dart';

class HerMessageBubble extends StatelessWidget {
  const HerMessageBubble({super.key});

  @override
  Widget build(BuildContext context) {
    final colors = Theme.of(context).colorScheme;

    return Column(
      crossAxisAlignment: CrossAxisAlignment.start,
      children: [
        Container(
          decoration: BoxDecoration(
            color: colors.secondary,
            borderRadius: BorderRadius.circular(20),
          ),
          child: Padding(
            padding: const EdgeInsets.symmetric(horizontal: 20, vertical: 10),
            child: Text('Hola soy ella...', style: TextStyle(color: Colors.white)),
          ),
        ),
        SizedBox(height: 5),
        _ImageBubble(),
        SizedBox(height: 10,)
      ],
    );
  }
}

class _ImageBubble extends StatelessWidget {
  
  @override
  Widget build(BuildContext context) {

    final size = MediaQuery.of(context).size;
    
    return ClipRRect(
      borderRadius: BorderRadius.circular(20),
      child: Image.network('https://yesno.wtf/assets/yes/3-422e51268d64d78241720a7de52fe121.gif',
              width: size.width * 0.7,
              height: 150,
              fit: BoxFit.cover,
              loadingBuilder: (context, child, loadingProgress) {
                if(loadingProgress == null) return child;
                return Container(
                  width: size.width *0.7,
                  height: 150,
                  padding: EdgeInsets.symmetric(horizontal: 10, vertical: 5),
                  child: Text('mi amor esta escribiendo...'),
                );
              },
      ),
      
    );
      
  }
}
```

## Resultado

![alt text](image-7.png)

![alt text](image-8.png)