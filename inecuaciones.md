
<a href="https://colab.research.google.com/github/crdguez/aprendiendo_sympy/blob/master/inecuaciones.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Lo primero que necesitamos hacer es importar la librerias de *Python* que necesitaremos


```
from sympy import *
from IPython.display import Markdown as md
from IPython.display import display
from sympy import reduce_abs_inequality
from __future__ import division
from sympy import *
x, y, z, t = symbols('x y z t')
k, m, n = symbols('k m n', integer=True)
f, g, h = symbols('f g h', cls=Function)
init_printing(use_latex=False)
```

## Resolviendo inecuaciones

#### Inecuaciones de primer grado

Son las más sencillas de resolver. Solo hay que resolverlas como si fueran ecuaciones de primer grado pero con las reglas de equivalencia correspondientes: multiplicar ambos miembros de la inecuación por un número negativo invierte el sentido de la inecuación. Ídem para la división puesto que no es más que multiplicar por el inverso.

#### polinómicas de grado mayor que dos

Se descompone el polinomio en factores. Se estudia el signo de cada uno para determinar el signo del producto.

### Inecuaciones con fracciones algebraicas

Se pueden reducir a una del siguiente tipo o similar:
$$\frac{P(x)}{Q(x)} \leq 0$$

Su resolución se reduce a estudiar el signo del numerador y del denominador para estudiar el cociente.




### Inecuaciones con  valores absolutos
Para poder resolver inecuaciones con valores absolutos hay que utilizar la función *reduce_abs_inequality*.

La función recibe tres parámetros resuelve inecuaciones con el miembro de la derecha 0 (por lo tanto hay que ):


*   La expresión algebraica del miembro de la izquierda
*   El símbolo de la desigualdad
*   La variable, normalmente x





#### Ejemplo:

Resuelve la inecuación $$\lvert x-2 \rvert \leq 1 $$



> La inecuación anterior es equivalente a $\lvert x-2 \rvert -1 \leq 0$  y se resuelve con el siguiente código:




```
reduce_abs_inequality(Abs(x-2)-1,'<=',x).as_set()
```




    [1, 3]




```
!jupyter nbconvert inecuaciones.ipynb --to=markdown
```

## Referencias


 *   [Documentación de SymPy](https://docs.sympy.org/latest/index.html#)