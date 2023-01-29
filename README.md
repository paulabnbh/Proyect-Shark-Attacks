# Shark Attacks data cleaning project



#### Antes de empezar con la limpieza de datos, para asegurar cierta coherencia en los títulos de las columnas hice lo siguiente:

- cambiar todas las letras a minúsculas
- eliminar todos los posibles espacios a través del método strip()
- reemplazar los espacios y ':' entre palabras por '_'

Además, establecí un objetivo en el que se buscaría una relación de los ataques de tiburón y la época del año en que estos sucedían.

### Limpieza de filas con valores nulos

Antes de comenzar con la limpieza de datos en las oclumnas, eliminé todas las filas que tuviesen menos de 3 columnas con datos, puesto que son datos escases que nos vas a aportar muy poca información y no aportan valor a la base de datos. También comprobé si hubiera filas duplicadas, pero no fue el caso.

### Limpieza de columnas

Una vez retiradas las filas con pocos datos, rellené con 'unknown' aquellas columnas cuyos datos no pudieran ser obtenidos a través de otras columnas de la propia base de datos. Dichas columnas son las siguientes:
 #######
    - type
    - location
    - name
    - sex
    - species
    - injury
    - fatal (y/n)
    - investigator or source
    - pdf
    - href_formula
    - href
    - unnamed_22
    - unnamed_23

Por otro lado, hay ciertas columnas que rellené siguiendo otras técnicas.

En la columna 'age' hice una limpieza de esta para que todas las celdas tuviesen el mismo formato y convertí el tipo de dato a integer. De esta manera, pude completar las celdas con números nulos por la media de edad de la columna. Decidí rellenarlo con la media ya que, por un lado, no tendría sentido rellenarlo con '0' porque el número desvirtuaría por completo la base de datos. Sin emabrgo, a pesar de que la media no es un valor contrastado, es el que mejor se puede adecuar a una columna como esta.

La columna 'activity' fue rellenada con la moda de la columna. Como es información que no se puede obtener a través de investigación, rellenarlo con la actividad más repetida en ataques de tiburones es una forma lógica de rellenar la columna con datos.

La columna 'case_number' hace referencia a un número de seguimiento único para cada uno de los casos. Por ello, he reemplazado los números de esta columna con números únicos.

La columna 'date' se ha limpiado de manera que se mantuviese un mismo formato para toda la columna. Aquellas columnas que no cumplían con el formato de fecha por que estaban incompletas, han sido eliminadas. Esto se debe a que, sabiendo que el objetivo de esta limpieza de datos es la búsqueda de una relación entre ataques de tiburón y fechas en las que sucede, rellenar esta columna con datos que no son 100% reales, nos podría hacer llegar a una conclusión errónea.

La columna 'time' se ha editado y limpiado para que todas las celdas tuviesen el mismo formato: 'HH:MM'. Aquellas sin dato o cuyo dato o formato fuese impreciso o no se ajustase al genérico, fue sustituido por la moda: la hora más repetida en la que tuvieron lugar ataques de tiburones.

Finalmente, las columnas 'country' y 'location' fueron rellenadas en función de las columnas 'location' y 'area'. En varias ocasiones podíamos encontrar la ubicación y/o área definidas pero el país no. Por ello, esas celdas en concreto se han rellenado en función de las columnas siguientes y con algo de búsqueda. Todas aquellas de las que no se podía encontrar información investigando o en base a otra columna, se han rellenado con 'unknown'.




