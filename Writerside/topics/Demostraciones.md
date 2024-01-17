# Demostraciones
Cuando empecé a estudiar ingeniería, debo de aceptar que no era el más versado en
matemáticas, y es más, sigo siendo medio tronco para el tema. Independientemente de eso, había un tema bastante molesto para mí; las demostraciones matemáticas. 

Ver semejante desmadre para poder demostrar que  una simple operación era correcta, me parecía absurdo. Sin embargo, estaba mal. Qué novedad. 

Las demostraciones matemáticas son bastante importantes para un@ ingenier@ en computación que se precie de serlo. ¿Por qué? Por varios motivos: 
* Permiten obtener una garantía de correctitud:
  En la ingeniería en computación, el desarrollo de software es una tarea crítica. Las demostraciones proporcionan una forma rigurosa de garantizar la corrección de algoritmos y programas. Al demostrar propiedades y teoremas, se puede establecer la certeza de que un algoritmo o sistema cumple con sus especificaciones y funciona correctamente en todos los casos.
* Análisis de Algoritmos:
Las demostraciones son esenciales para analizar la eficiencia y complejidad de los algoritmos. A través de la teoría de la computación y el análisis de algoritmos, se pueden demostrar propiedades como la complejidad temporal y espacial, proporcionando información crítica para la toma de decisiones sobre la elección de algoritmos en función de los requisitos del sistema.
* Seguridad:
  En campos como la seguridad informática y la criptografía, la demostración de la seguridad de algoritmos y protocolos es crucial. Las demostraciones proporcionan una base matemática para afirmar la resistencia de sistemas criptográficos contra ataques, asegurando la confidencialidad e integridad de la información.

Por eso, vamos a aprender un poco de demostraciones, sí señor. 

## Demostración por inducción

Esta demostración es (para mi) la más importante en el desarrollo de programas. Usualmente se utiliza seguido con recurrencias; nos permite saber si una recurrencia funciona para todos los casos. 

Básicamente la demostración por inducción se trata de imaginarse un número cualquiera y considerar verdadero el funcionamiento de tu hipótesis. Luego a ese número le añadimos un +1 para simular que es el número que le sigue y si coincide con tu propuesta, es que es verdadero para cualquier número.

Veamos con un ejemplo cómo funciona:

Vamos a utilizar la clásica demostración de
```tex
1 + 2 + \ldots + k = \frac{k(k+1)}{2}
```

y esa va a ser nuestra hipótesis. 

Ahora, queremos demostrar que la fórmula también es válida para lo que sigue después de cualquier número(k+1), así se vería la hipótesis con k+1, que es a lo que queremos llegar
```tex
1 + 2 + \ldots + (k+1) = \frac{(k+1)(k+2)}{2}
```

Entonces aplicamos la inducción. En la suma, también sumamos el número que seguiría a la secuencia:
```tex
1 + 2 + \ldots + (k+1) = (1 + 2 + \ldots + k) + (k + 1)
```

Como lo pusimos en la secuencia, ahora lo ponemos en la hipótesis
```tex
= \frac{k(k+1)}{2} + (k + 1)
```

Y ya solo es desarrollar
```tex
= \frac{k(k + 1)}{2} + \frac{2(k + 1)}{2}

= \frac{k(k + 1) + 2(k + 1)}{2}
= \frac{k^2 + k + 2k + 2}{2}
= \frac{k^2 + 3k + 2}{2}
= \frac{(k + 1)(k + 2)}{2}
```
 Bocatto di cardinale, llegamos justo a lo que queríamos encontrar. Eso señor@s es la demostración por inducción. 


