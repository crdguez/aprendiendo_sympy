
<a href="https://colab.research.google.com/github/crdguez/aprendiendo_sympy/blob/master/inecuaciones.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Si usas [https://colab.research.google.com/](https://colab.research.google.com/) , necesitarás instalar los siguientes paquetes si quieres usar la función *parse_latex* que sirve para introducir expresiones directamente en $ \LaTeX $:


```python
!pip install sympy==1.3 antlr4-python3-runtime
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

## Medidas de ángulos

Por defecto, las funciones de simpy trabajan en radianes. Por tanto es necesario pasar el ángulo a operar en radianes. 

Las funciones que permiten pasar de grados a radianes y viceversa son:

* rad(), pasa a radianes el ángulo en grados que pasemos por parámetro
* deg(), pasa a grados el ángulo en radianes

### Ejemplos

## Funciones trigonométricas

### Seno

Se utiliza la función *sin()*

#### Ejemplo

$\sin(\frac{\pi}{6})=\frac{1}{2}$

En simpy:


```python
sin(pi/6)
```




    1/2



$\sin(30)=\frac{1}{2}$

En simpy:


```python
sin(rad(30))
```




    1/2



### Coseno

Se utiliza la función *cos()*

#### Ejemplo

$\cos(\frac{\pi}{3})=\frac{1}{2}$

En simpy:


```python
cos(pi/3)
```




    1/2



$\cos(60)=\frac{1}{2}$

En simpy:


```python
cos(rad(60))
```




    1/2



### Tangente

Se utiliza la función *tan()*

#### Ejemplo

$\tan(\frac{\pi}{4})=1$

En simpy:


```python
tan(pi/4)
```




    1



$\tan(45)=1$

En simpy:


```python
tan(rad(45))
```




    1



### Secante

### Cosecante

### Cotangente

## Funciones trigonométricas inversas

### Arcoseno

### Arcocoseno

### Arcotangente

### Arcosecante

### Arcocosecante

### Arcocotangente


```python
!jupyter nbconvert trigonometria.ipynb --to=markdown
```

    [NbConvertApp] Converting notebook trigonometria.ipynb to markdown
    [NbConvertApp] Writing 1925 bytes to trigonometria.md

