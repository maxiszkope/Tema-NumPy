![](numpy.png)
### Numpy Arrays

Los arrays son los principales objetos que dispone NumPy, y sobre los cuales se pueden implementar multitud de algoritmos vía vectorización. En muchos casos, utilizaremos arrays de dimensión 1 (vectores) y 2 (matrices), aunque no es infrecuente encontrarse casos en los que tenga dimensión mayor, dependiendo del contexto de nuestro problema (por ejemplo, procesamiento de imágenes).

#### Crear NumPy Arrays

**A partir de una lista:**

Una de las maneras más habituales de inicializar un `numpy.array` es a través de una lista de Python, entendiéndose la concatenación de las mismas como un aumento progresivo en la dimensionalidad.

```python
my_list = [1,2,3]
np.array(my_list)
```

**A partir de una lista anidada:**

```python
my_matrix = [[1,2,3],[4,5,6],[7,8,9]]
np.array(my_matrix)
```

#### Métodos implementados

Si, por el contrario, necesitamos construir arrays con una dimensionalidad específica (para inicializar algoritmos, ...), es muy habitual recurrir a métodos ya implementados que nos permiten esta flexibilidad.

- **arange:** Devuelve un vector equiespaciado entre dos números.

```python
np.arange(0,10)
```

- **zeros y ones:** Generamos arrays de ceros y unos respectivamente, con la forma especificada en una tupla.

```python
np.zeros(3)
np.zeros((5,5))

np.ones(3)
np.ones((3,3))
```

- **linspace:** Devuelve un vector de números comprendidos entre el dato inicial y final, tan amplio como un parámetro especificado.

```python
np.linspace(0,10,3)
np.linspace(0,10,50)
```

- **eye:** Crea una matriz identidad.

```python
np.eye(4)
```

**Random:**

NumPy también tiene una gran variedad de métodos para generar números aleatorios:

- **rand:** Genera un array de la forma especificada, con valores aleatorios uniformemente distribuidos en el intervalo [0, 1).

```python
np.random.rand(2)
np.random.rand(5,5)
```

- **randn:** Devuelve una muestra de números normalmente distribuidos.

```python
np.random.randn(2)
np.random.randn(5,5)
```

- **randint:** Devuelve enteros desde el valor low (incluido) hasta high (excluido).

```python
np.random.randint(1,100)
np.random.randint(1,100,10)
```

Para más distribuciones, puedes consultar la documentación con el comando `help(np.random)`.

#### Atributos y métodos

Veamos cuáles son algunos de los más importantes en el día a día para trabajar con arrays:

```python
arr = np.arange(25)
ranarr = np.random.randint(0,50,10)

arr.max()
arr.argmax()
arr.min()
arr.argmin()
arr.shape
arr.reshape(5,5)
```

### NumPy indexado y filtrado

#### Bracket Indexing

La manera más sencilla es filtrar a través de los índices, como en las listas.

```python
arr[8]
arr[1:5]
```

#### Broadcasting

Estos objetos se diferencian de las listas en que podemos asignar valores a elementos del array mediante filtros.

```python
arr[0:5]=100
```

Recuerda, para obtener una copia y trabajar sobre ella de forma independiente, debemos especificarlo.

```python
arr_copy = arr.copy()
```

#### Indexado de matrices (arrays 2-dimensionales)

El formato general es

 arr_2d[fila][col] o arr_2d[fila,col].

```python
arr_2d[1]
arr_2d[1][0]

arr_2d[1,0]
```

### Selección condicional

NumPy también permite realizar filtrados condicionales muy potentes.

```python
arr > 5
arr[arr>5]
```

### Operaciones con NumPy

Existen muchas funciones universales disponibles para realizar operaciones en los arrays de NumPy. Algunas de las más comunes incluyen:

- **sqrt:** Raíz cuadrada de cada elemento.

```python
np.sqrt(arr)
```

- **exp:** Exponencial (e^x) de cada elemento.

```python
np.exp(arr)
```

- **sin, cos, tan:** Funciones trigonométricas.

```python
np.sin(arr)
```

- **log:** Logaritmo natural de cada elemento.

```python
np.log(arr)
```

- **sum:** Suma de todos los elementos del array.

```python
arr.sum()
```

- **std:** Desviación estándar de los elementos del array.

```python
arr.std()
```

- **mean:** Media aritmética de los elementos del array.

```python
arr.mean()
```

Estas son solo algunas de las muchas funcionalidades que ofrece NumPy. Para obtener más detalles, consulta la [documentación oficial de NumPy](https://numpy.org/doc/).

---
