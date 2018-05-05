Clase: Funciones

1. Dibujar 1 estrella usando 2 triángulos

```
noStroke();

fill(255, 0, 0);
triangle(100, 100, 110, 85, 120, 100);
triangle(100, 90, 110, 105, 120, 90);
```

2. Dibujar otra estrella igual en otro lugar de la pantalla

```
fill(0, 255, 0);
triangle(200, 100, 210, 85, 220, 100);
triangle(200, 90, 210, 105, 220, 90);
```

3. Dibjuar una tercera estrella. Qué podemos hacer para reducir la cantidad de código?

- Ejercicio

4. Crear una función que pinte una estrella. Cómo se puede mejorar?

```
var estrella = function() {
  fill(255, 0, 0);
  triangle(100, 100, 110, 85, 120, 100);
  triangle(100, 90, 110, 105, 120, 90);
}
```

5. Agregar el parámetro x a la función para poder pintar la estrella sobr el plano x

```
var estrella = function(x) {
  fill(255, 0, 0);
  triangle(x-10, 100, x, 85, x+10, 100);
  triangle(x-10, 90, x, 105, x+10, 90);
};

estrella(100);
estrella(120);
estrella(150);
```

6. Agregar parámetro y a la función para poder pintar la estrella en cualquier lugar

- Ejercicio

7. Crear una nueva función `sol` que sea más grande que dibuje una estrella más grande
   y dentro de esta dibuje una estrella usando la función creada anteriormente.

- Ejercicio
