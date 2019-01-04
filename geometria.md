
<a href="https://colab.research.google.com/github/crdguez/aprendiendo_sympy/blob/master/geometria.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Si usas [https://colab.research.google.com/](https://colab.research.google.com/), necesitarás instalar los siguientes paquetes si quieres usar la función *parse_latex* que sirve para introducir expresiones directamente en $ \LaTeX $:


```python
# Descomentar si se quiere usar:
# !pip install sympy==1.3 antlr4-python3-runtime
```

    Collecting sympy==1.3
    [?25l  Downloading https://files.pythonhosted.org/packages/dd/f6/ed485ff22efdd7b371d0dbbf6d77ad61c3b3b7e0815a83c89cbb38ce35de/sympy-1.3.tar.gz (5.9MB)
    [K    100% |████████████████████████████████| 5.9MB 5.3MB/s 
    [?25hRequirement already satisfied: antlr4-python3-runtime in /usr/local/lib/python3.6/dist-packages (4.7.2)
    Requirement already satisfied: mpmath>=0.19 in /usr/local/lib/python3.6/dist-packages (from sympy==1.3) (1.1.0)
    Building wheels for collected packages: sympy
      Running setup.py bdist_wheel for sympy ... [?25l- \ | / - \ | / - \ | / - \ | / - \ | done
    [?25h  Stored in directory: /root/.cache/pip/wheels/6c/59/86/478e3c0f298368c119095cc5985dedac57c0e35a85c737f823
    Successfully built sympy
    Installing collected packages: sympy
      Found existing installation: sympy 1.1.1
        Uninstalling sympy-1.1.1:
          Successfully uninstalled sympy-1.1.1
    Successfully installed sympy-1.3


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





    N.i + 2*N.j



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



## Referencias


 *   [Documentación de SymPy](https://docs.sympy.org/latest/index.html#)



```python
!jupyter nbconvert geometria.ipynb --to=markdown
```
