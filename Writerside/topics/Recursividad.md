# Recursividad
Primero aprende demostración inductiva en [demostraciones](Demostraciones.md)


Si estás aquí, es porque ya mas o menos tienes un vago concepto de lo que es una recursividad. Vamos a tratar de aclarar los temas poco a poco. 

**Primero fantasear, despues delegar y luego ejecutar**. Así es como veo la recursividad. Imaginemos que tenemos la ardua labor de llevar 100 costales de cemento de un punto a a un punto b. 
No te gustaría hacerlo solo; es más, no te gustaría hacer nada. ¿Cómo podemos realizar la labor? Fácil, primero consigues a 10 chalanes, y les encargas lo siguiente: "Tu labor será conseguir 10 chalanes y que cada uno cargue un saco de cemento".

Hasta ahora todo bien, sin embargo te acaban de timar. Si prestas atención a nuestro encargo, veremos que nunca en ningún momento pones a cargar a los chalanes los bultos, entonces haces una modificación:
"Si observamos detenidamente nuestro encargo inicial, nos damos cuenta de que nunca especificamos que los chalanes debían cargar los bultos de cemento. Así que, hacemos una modificación y les comunicamos a los chalanes: 'Tu labor será conseguir 10 chalanes y que cada uno cargue un saco de cemento de un punto a otro, asegurándote de que todos los sacos lleguen al destino final'.

Ahora, cada chalán tiene una tarea clara y específica. Pero aquí está la magia de la recursividad: no queremos cargar directamente los 100 sacos nosotros mismos, y tampoco queremos que los 10 chalanes lo hagan uno por uno, ya que eso podría ser ineficiente.

Entonces, recurrimos nuevamente a la delegación y les decimos a los 10 chalanes: 'Ahora, cada uno de ustedes consiga 10 chalanes más y delegue la misma tarea: cargar un saco de cemento de un punto a otro'. Así, la carga se divide aún más, y todos tienen una tarea más manejable.

Este proceso continúa de manera recursiva hasta que llegamos a un nivel donde la tarea es lo suficientemente pequeña y manejable para cada individuo. En última instancia, cada chalán solo tiene que preocuparse por cargar un saco de cemento de un punto a otro.

Finalmente, ejecutamos el plan y observamos cómo se realiza la tarea de manera eficiente gracias a la recursividad y la delegación inteligente. Cada nivel de chalanes se encarga de coordinar a un grupo más pequeño, logrando que los 100 sacos de cemento lleguen a su destino de manera efectiva y sin que tengamos que cargar un solo saco nosotros mismos."

Básicamente eso es un algoritmo Recursivo. 

Para hacer un algoritmo recursivo debemos de cumplir ciertas normas: 

1. Debe ser posible descomponer el problema original en instancias más simples del mismo problema.
2. Una vez que se ha resuelto cada uno de estos subproblemas más simples, debe ser posible combinar estas soluciones para producir una solución al problema original.
3. A medida que el problema grande se descompone en subproblemas sucesivamente menos complejos, esos subproblemas deben volverse tan simples eventualmente que puedan resolverse sin más subdivisión.


¿Y cómo demostramos su correctitud?

La correctitud de un algoritmo recursivo se verifica demostrando dos propiedades fundamentales: la condición base y la relación recursiva.

    Condición base: Debe haber un caso base que sea sencillo de resolver y no requiera más llamadas recursivas. Es la condición que detiene la recursividad y permite que el algoritmo regrese valores sin más subdivisiones.

    Relación recursiva: La función recursiva debe progresar hacia el caso base, es decir, cada llamada recursiva debe acercar el problema a una solución. Además, la combinación de los resultados de las llamadas recursivas debe conducir a la solución del problema original.

A continuación, proporcionaré un ejemplo simple de un algoritmo recursivo junto con su explicación:
## Ejercicio
1. Demuestra que 
```tex
\frac{k(k+1)}{2}
```
Tiene como recurrencia
```tex
\text{subrutina } f(n) \\
\text{si } n = 0 \\
\quad \text{regresa } 0 \\
\text{ sino} \\
\quad \text{regresa } n + f(n - 1)

```

```tex
\text{1. Tenemos como base 0 y es válido, entonces debemos de aplicar la recurrencia:}

n + f(n-)

```
```tex
 \text{Resolvemos para f(n-1):          }

```
```tex
\frac{(n-1)(n-1+1))}{2}
```



```tex
\text{resolviendo queda:   }
```

```tex
\frac{n(n+1))}{2}
```

Entonces ya tenemos un esbozo simple de cómo ver la **correctitud de un algoritmo recursivo:**
1. Verificar el caso base
2. Resolvemos para el return de el algoritmo
3. Buscamos si nuestro planteamiento recursivo se parece a la fórmula que queremos reproducir.