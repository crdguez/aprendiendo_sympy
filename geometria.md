
<a href="https://colab.research.google.com/github/crdguez/aprendiendo_sympy/blob/master/geometria.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Si usas [https://colab.research.google.com/](https://colab.research.google.com/), necesitarás instalar los siguientes paquetes si quieres usar la función *parse_latex* que sirve para introducir expresiones directamente en $ \LaTeX $:


```python
# Descomentar si se quiere usar:
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

from sympy.vector import CoordSys3D, vector

import numpy as np


from __future__ import division
from sympy import *
x, y, z, t = symbols('x y z t')
k, m, n = symbols('k m n', integer=True)
f, g, h = symbols('f g h', cls=Function)
#init_printing(use_latex=False)
```

## Usando el módulo Geometry


```python
from sympy.geometry import Point, Line
```

## Usando el modulo Vector

Podemos usar el módulo *Vector*. Es un poco más complicado de usar porque hay que genera un sistemar de coordenadas, pero es más potente.

Para generar el sistema de coordenadas:


```python
N = CoordSys3D('N') #instanciamos un sistema de coordenadas en R3

i, j, k = N.base_vectors()

display(N.base_vectors())

```


    (N.i, N.j, N.k)


Vamos a generar el vector $\overrightarrow{v}=(1,2)$. Como el módulo *vector* trabaja en 3 dimesiones, debemos pasar las 3 componentes:


```python
v = [1,2,0]
base = [i,j,k]
u=(np.array(v)*np.array(base)).sum()
type(u)
u.components
u
```




    N.i + 2*N.j



Podíamos haber obtenido lo mismo directamente:


```python
i+2*j
```




    N.i + 2*N.j



### Operaciones con vectores

#### Suma, producto por un número y combinaciones lineales

Se operan con los operadores habituales, solo hay que tener encuenta que los operando tienen que ser vectores. 
Dados los vectores $\overrightarrow{u}=(1,3)$ y $\overrightarrow{v}=(-3,5)$, y $m=3$ y $n=-2$


```python
u=i+3*j
v=-3*i+5*j
m=3
n=-2
```

 *  $\overrightarrow{u}+\overrightarrow{v}$


```python
u+v
```




    (-2)*N.i + 8*N.j



 *  $\overrightarrow{u}-v\overrightarrow{v}$

 *  $\overrightarrow{u}+\overrightarrow{v}$


```python
u-v
```




    4*N.i + (-2)*N.j



 *  $m\cdot\overrightarrow{u}$


```python
m*u
```




    3*N.i + 9*N.j



 *  $m\cdot\overrightarrow{u}+n\cdot\overrightarrow{v}$


```python
m*u+n*v
```




    9*N.i + (-1)*N.j



#### Módulo

* $|u|$


```python
u.magnitude()
```




$$\sqrt{10}$$



### Producto escalar



## Referencias


 *   [Documentación de SymPy](https://docs.sympy.org/latest/index.html#)



```python
!jupyter nbconvert geometria.ipynb --to=markdown
```

    [NbConvertApp] Converting notebook geometria.ipynb to markdown
    [NbConvertApp] Writing 3983 bytes to geometria.md

