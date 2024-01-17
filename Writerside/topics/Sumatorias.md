# Sumatorias
Cheatsheet de sumatoria
1. Suma de una constante:
```tex
   \sum_{i=1}^{n} c = c \cdot n 
  ```

2. Propiedad distributiva:
Significa que puedes dividir la sumatoria en varias 
```tex
    \sum_{i=1}^{n} (a_i + b_i) = \sum_{i=1}^{n} a_i + \sum_{i=1}^{n} b_i 
```

3. Factor constante:
Significa que puedes extraer un coeficiente
```tex
    \sum_{i=1}^{n} c \cdot a_i = c \cdot \sum_{i=1}^{n} a_i 
```

4. Cambio de índice:
Se usa a veces para facilitar  la ejecucion de una operacion
```tex
    \sum_{i=a}^{b} f(i) = \sum_{j=a'}^{b'} f(j) 
   ( j = i - (a - a') 
```

5. Suma telescópica:
```tex
   \sum_{i=1}^{n} (a_i - a_{i-1}) = a_n - a_0 
```
6. Propiedad de separación:
```tex
   \sum_{i=m}^{n} f(i) = \sum_{i=m}^{k} f(i) + \sum_{i=k+1}^{n} f(i) 
```