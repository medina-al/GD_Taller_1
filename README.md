# GD_Taller_1


# AUTORES  
Andrés Leonardo Medina Quijano - Laura Carolina Tinjacá Cristancho


# OBJETIVO  
En el siguiente taller se muestran los cuatro dataset elegidos para su debido perfilamiento (delitos sexuales, lesiones personales y accidentes de tránsito, hurto comercial y de vivienda y hurto a motocicletas y automotores). Describiendo los hallazgos encontrados, estructura de los datos y aspectos relevantes sobre la calidad de los mismos.

# DESARROLLO DEL TALLER

## 1 Análisis general

### Lesiones personales y accidentes de tránsito
Para este dataset se encuentran las siguientes características:
    - Dimensiones: 59810 filas x 9 columnas
    - Filas repetidas: 5
    - Dimensiones finales: 59805 filas x 9 columnas

#### Análisis encontrado

| Campo                | Tipo de dato    | Tipo de dato Pandas | Longitud máxima | Descripción                                                                                              | Debe ser lista cerrada | Media | Normalizado a lista | Valores nulos | Son congruentes los valores con el tipo de dato | Observaciones                                                                                                               |
| -------------------- | --------------- | ------------------- | --------------- | -------------------------------------------------------------------------------------------------------- | ---------------------- | ----- | ------------------- | ------------- | ----------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| DEPARTAMENTO         | Alfabético      | object              | 18              | Departamento en el cual ocurrió el hecho                                                                 | SI                     | N/A   | SI                  | NO            | SI                                              |                                                                                                                             |
| MUNICIPIO            | Alfabético      | object              | 27              | Municipio en el cual ocurrió el hecho                                                                    | SI                     | N/A   | SI                  | NO            | SI                                              |                                                                                                                             |
| CÓDIGO DANE          | Numérico entero | int64               | 8               | Código DANE del municipio en el que ocurrió el hecho                                                     | SI                     | N/A   | SI                  | NO            | SI                                              | Se detectan 3 ceros constantes al final respecto al código oficial del DANE, se reemplazan                                  |
| ARMAS MEDIOS         | Alfabético      | object              | 19              | Arma o medio con el que se cometió la lesión, o tipo vehículo en el que sucedió el accidente de tránsito | SI                     | N/A   | SI                  | NO            | SI                                              |                                                                                                                             |
| FECHA HECHO          | Fecha           | object              | 10              | Fecha en la ocurrió el hecho                                                                             | NO                     | N/A   | N/A                 | NO            | SI                                              |                                                                                                                             |
| GENERO               | Alfabético      | object              | 12              | Género de la persona involucrada en el hecho                                                             | SI                     | N/A   | NO                  | NO            | SI                                              | Se encuentra que hay dos valores con el mismo objetivo escritos de diferente manera (NO REPORTA Y NO REPORTADO), se corrige |
| GRUPO ETARÍO         | Alfabético      | object              | 12              | Clasificación cualitativa para la edad de la persona involucrada en el hecho                             | SI                     | N/A   | SI                  | NO            | SI                                              |                                                                                                                             |
| DESCRIPCIÓN CONDUCTA | Alfanúmerico    | object              | 63              | Encabezado del artículo según el tipo de delito cometido en el hecho                                     | SI                     | N/A   | SI                  | NO            | SI                                              |                                                                                                                             |
| CANTIDAD             | Numérico entero | int64               | 2               | Cantidad de hechos presentados para la agrupación de todos los datos anteriores                          | NO                     | 1,098 | N/A                 | NO            | SI                                              |                                                                                                                             |

### Delitos sexuales
Para este dataset se encuentran las siguientes características:
    - Dimensiones: 260323 filas x 9 columnas
    - Filas repetidas: 32466
    - Dimensiones sin repetidos: 241740 filas x 9 columnas
    - Dimensiones sin campos nulos: 241739 filas x 9 columnas

#### Análisis encontrado

| Campo        | Tipo de dato    | Tipo de dato Pandas | Longitud máxima | Descripción                                                                                              | Debe ser lista cerrada | Media    | Normalizado a lista | Valores nulos | Son congruentes los valores con el tipo de dato | Observaciones                                                                                                                                                                  |
| ------------ | --------------- | ------------------- | --------------- | -------------------------------------------------------------------------------------------------------- | ---------------------- | -------- | ------------------- | ------------- | ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| DEPARTAMENTO | Alfabético      | object              | 18              | Departamento en el cual ocurrió el hecho                                                                 | SI                     | N/A      | SI                  | NO            | SI                                              |                                                                                                                                                                                |
| MUNICIPIO    | Alfabético      | object              | 27              | Municipio en el cual ocurrió el hecho                                                                    | SI                     | N/A      | NO                  | SI            | SI                                              | Se encuentra que hay un valor nulo, se elimina la fila ya que no es representativa                                                                                             |
| CÓDIGO DANE  | Numérico entero | float64             | 10              | Código DANE del municipio en el que ocurrió el hecho                                                     | SI                     | N/A      | NO                  | SI            | SI                                              | Se encuentra que al final del código hay 3 ceros un punto y un espacio, se crea una función para eliminarlos y dejar el código limpio                                          |
| ARMAS MEDIOS | Alfabético      | object              | 27              | Arma o medio con el que se cometió la lesión, o tipo vehículo en el que sucedió el accidente de tránsito | SI                     | N/A      | NO                  | NO            | SI                                              | Se detecta que hay 3 campos que pueden unificarse. Se unifican en uno solo (ARMA BLANCA / CORTOPUNZANTE)<br>Se detectan valores con un guión, se reemplazan por "NO REPORTADO" |
| FECHA HECHO  | Fecha           | object              | 10              | Fecha en la ocurrió el hecho                                                                             | NO                     | N/A      | N/A                 | NO            | SI                                              |                                                                                                                                                                                |
| GENERO       | Alfabético      | object              | 12              | Género de la persona involucrada en el hecho                                                             | SI                     | N/A      | NO                  | SI            | SI                                              | Se detectan valores que se pueden unificar y campos nulos, se integran y unifican los valores                                                                                  |
| GRUPO ETARIO | Alfabético      | object              | 12              | Clasificación cualitativa para la edad de la persona involucrada en el hecho                             | SI                     | N/A      | NO                  | SI            | SI                                              | Se detectan valores que se pueden unificar y campos nulos, se integran y unifican los valores                                                                                  |
| CANTIDAD     | Numérico entero | int64               | 2               | Cantidad de hechos presentados para la agrupación de todos los datos anteriores                          | NO                     | 1,034035 | N/A                 | NO            | SI                                              |                                                                                                                                                                                |
| DELITO       | Alfanúmerico    | object              | 111             | Encabezado del artículo según el tipo de delito cometido en el hecho                                     | SI                     | N/A      | SI                  | NO            | SI                                              |                                                                                                                                                                                |

### Hurto comercial y de viviendas
Para este dataset se encuentran las siguientes características:
    - Dimensiones: 519388 rows × 9 columns
    - Filas repetidas: 35294
    - Dimensiones sin repetidos: 492967 rows × 9 columns
    - Filas con campos nulos: 123

#### Análisis encontrado
| Campo         | Tipo de dato    | Tipo de dato Pandas | Longitud máxima | Descripción                                                                  | Debe ser lista cerrada | Media  | Normalizado a lista | Valores nulos | Son congruentes los valores con el tipo de dato | Observaciones                                                                                                                                        |
| ------------- | --------------- | ------------------- | --------------- | ---------------------------------------------------------------------------- | ---------------------- | ------ | ------------------- | ------------- | ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| DEPARTAMENTO  | Alfabético      | object              | 18              | Departamento en el cual ocurrió el hecho                                     | SI                     | NA     |                     | NO            | SI                                              | Se observa que existe un registro como "No reportado" y existen caracteres como "CT" que pueden ser eliminados                                       |
| MUNICIPIO     | Alfabético      | object              | 27              | Municipio en el cual ocurrió el hecho                                        | SI                     | NA     |                     | NO            | SI                                              | Se observa que existen dos registros como "No reportado" y también presenta caracteres adicionales como "CD" que serán eliminados                    |
| CODIGO DANE   | Numérico entero | object              | 12              | Codígo DANE del municipio en el cual ocurrio el hecho                        | SI                     | NA     |                     | NO            | SI                                              |                                                                                                                                                      |
| ARMAS MEDIOS  | Alfabético      | object              | 27              | Arma o medio con el que se cometió la lesión                                 | SI                     | NA     |                     | NO            | SI                                              | Se observa que se pueden unificar dos categorías de esta variable como lo son "NO REPORTA" y "NO REPORTADO" dejando como único valor el "NO REPORTA" |
| FECHA HECHO   | Numérico entero | object              | 10              | Fecha en la que ocurrió el hecho                                             | NO                     | NA     |                     | NO            | SI                                              |                                                                                                                                                      |
| GENERO        | Alfabético      | object              | 12              | Género de la persona involucrada en el hecho                                 | SI                     | NA     |                     | NO            | SI                                              | Se observa que hay atributos que se pueden unificar como los géneros que no fueron reportados                                                        |
| GRUPO ETARIO  | Alfabético      | object              | 12              | Clasificación cualitativa para la edad de la persona involucrada en el hecho | SI                     | NA     |                     | SI            | SI                                              | Se observa que existen categorías que pueden ser unificadas y 123 campos vacíos a tratar                                                             |
| TIPO DE HURTO | Alfabético      | object              | 27              | Clasificación cualitativa para el tipo de hurto ocurrido                     | SI                     | NA     |                     | NO            | SI                                              |                                                                                                                                                      |
| CANTIDAD      | Numérico entero | int64               | 2               | Cantidad de hechos presentados para la agrupación de los datos anteriores    | NO                     | 1.4186 |                     | NO            | SI                                              |                                                                                                                                                      |

### Hurto a motocicletas y automotores
Para este dataset se encuentran las siguientes características:
    - Dimensiones: 298400 rows × 9 columns
    - Filas repetidas: 35314
    - Dimensiones sin repetidos: 276804 rows × 9 columns
    - DFilas con campos nulos: 0

#### Análisis encontrado
| Campo         | Tipo de dato    | Tipo de dato Pandas | Longitud máxima | Descripción                                                                  | Debe ser lista cerrada | Media  | Normalizado a lista | Valores nulos | Son congruentes los valores con el tipo de dato | Observaciones                                                                                                                                        |
| ------------- | --------------- | ------------------- | --------------- | ---------------------------------------------------------------------------- | ---------------------- | ------ | ------------------- | ------------- | ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| DEPARTAMENTO  | Alfabético      | object              | 18              | Departamento en el cual ocurrió el hecho                                     | SI                     | NA     |                     | NO            |                                                 |                                                                                                                                                      |
| MUNICIPIO     | Alfabético      | object              | 27              | Municipio en el cual ocurrió el hecho                                        | SI                     | NA     |                     | NO            |                                                 |                                                                                                                                                      |
| CODIGO DANE   | Numérico entero | int64               | 8               | Codígo DANE del municipio en el cual ocurrio el hecho                        | SI                     | NA     |                     | NO            |                                                 | Se observa que el tipo de la varible es númerico por lo que se ajusta a tipo alfabetico                                                              |
| ARMAS MEDIOS  | Alfabético      | object              | 27              | Arma o medio con el que se cometió la lesión                                 | SI                     | NA     |                     | NO            |                                                 | Se observa que se pueden unificar dos categorías de esta variable como lo son "NO REPORTA" y "NO REPORTADO" dejando como único valor el "NO REPORTA" |
| FECHA HECHO   | Alfabético      | object              | 10              | Fecha en la que ocurrió el hecho                                             | NO                     | NA     |                     | NO            |                                                 |                                                                                                                                                      |
| GENERO        | Alfabético      | object              | 9               | Género de la persona involucrada en el hecho                                 | SI                     | NA     |                     | NO            |                                                 | Se observa que sólo existen registros de "NO APLICA"                                                                                                 |
| GRUPO ETARIO  | Alfabético      | object              | 9               | Clasificación cualitativa para la edad de la persona involucrada en el hecho | SI                     | NA     |                     | NO            |                                                 | Se observa que sólo hay registros de tipo "NO APLICA"                                                                                                |
| TIPO DE HURTO | Alfabético      | object              | 18              | Clasificación cualitativa para el tipo de hurto ocurrido                     | SI                     | NA     |                     | NO            |                                                 |                                                                                                                                                      |
| CANTIDAD      | Numérico entero | int64               | 2               | Cantidad de hechos presentados para la agrupación de los datos anteriores    | NO                     | 1.4854 |                     | NO            |                                                 |                                                                                                                                                      |


## 2 Preguntas por dataset

### Delitos sexuales

### Lesiones personales y accidentes de tránsito

### Hurto comercial y de viviendas

### Hurto a motocicletas y automotores

## 3 Análisis de delitos últimos 5 años

## 4 Integración de datasets y análisis de delitos

## 5 URL del video

# LIBRERÍAS  
pandas
