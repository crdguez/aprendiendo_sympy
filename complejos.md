
<a href="https://colab.research.google.com/github/crdguez/aprendiendo_sympy/blob/master/complejos.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Si usas [https://colab.research.google.com/](https://colab.research.google.com/) , necesitarás instalar los siguientes paquetes si quieres usar la función *parse_latex* que sirve para introducir expresiones directamente en $ \LaTeX $:


```python
# !pip install sympy==1.3 antlr4-python3-runtime
```

Lo primero que necesitamos hacer es importar la librerias de *Python* que necesitaremos


```python
from sympy import *
from IPython.display import Markdown as md
from IPython.display import display
from sympy import solve_poly_inequality, reduce_abs_inequality
from sympy.solvers.inequalities import solve_univariate_inequality, reduce_rational_inequalities
from sympy.parsing.latex import parse_latex

from __future__ import division
from sympy import *
x, y, z, t = symbols('x y z t')
k, m, n = symbols('k m n', integer=True)
f, g, h = symbols('f g h', cls=Function)
init_printing(use_latex=False)
```

## El número *i*

En *Sympy* existe el símbolo *I* mayúscula reservado para el número *i*:


```python
I
```




    ⅈ



**Ejemplos:**


```python
2 + 3*I, 2*I, 1+I
```




    (2 + 3⋅ⅈ, 2⋅ⅈ, 1 + ⅈ)



## Documentación oficial

La documentación oficial están en [https://docs.sympy.org/latest/modules/functions/elementary.html](https://docs.sympy.org/latest/modules/functions/elementary.html#sympy-functions-elementary-complexes)


## Funciones

Veamos las funciones que aparecen:

### Parte real de un número complejo

Se usa la función *re*

**Ejemplo: **



```python
a = 2 + 3*I

re(a)
```




    2



### Parte imaginaria de un número complejo

Se usa la función *im*

**Ejemplo: **


```python
a = 2+3*I

im(a)


```




    3



### Módulo de un vector

Se usa la función *Abs*, (ojo con mayúscula la primera)

**Ejemplo: **


```python
a = 2+3*I

Abs(a)


```




    √13



### Argumento

Se usa la función *arg*. El ángulo lo da en radianes, por lo que si queremos que lo pase a grados tendremos que usar la función *deg*

**Ejemplo: **


```python
a = 2+3*I

deg(arg(a)).evalf()


```




    56.3099324740202



### Conjugado

Se usa la función *conjugate*. 

**Ejemplo: **


```python
a = 2+3*I

conjugate(a)


```




    2 - 3⋅ⅈ



### Paso a coordenadas polares

Podemos definir una función sencilla que lo haga: 




```python
def a_polar(binomico) :
    return [abs(binomico), arg(binomico)]
```

**Ejemplo:**


```python
a = 2+3*I

a_polar(a)
```




    [√13, atan(3/2)]



### Paso a coordenadas binómicas

Podemos definir una función sencilla que lo haga: 




```python
def a_binomico(polar) :
    return(polar[0]*cos(polar[1])+polar[0]*sin(polar[1])*I)
```

**Ejemplo:**


```python
b=[sqrt(13), atan(3/2)]
a_binomico(b).evalf()
```




    2.0 + 3.0⋅ⅈ




```python
!jupyter nbconvert complejos.ipynb --to=markdown
```
