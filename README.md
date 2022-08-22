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
| DEPARTAMENTO  | Alfabético      | object              | 18              | Departamento en el cual ocurrió el hecho                                     | SI                     | NA     | NO                  | NO            | SI                                              | Se observa que existe un registro como "No reportado" que puede ser eliminados                                                                       |
| MUNICIPIO     | Alfabético      | object              | 27              | Municipio en el cual ocurrió el hecho                                        | SI                     | NA     | NO                  | NO            | SI                                              | Se observa que existen dos registros como "No reportado" y también presenta caracteres adicionales como "CD" que serán eliminados                    |
| CODIGO DANE   | Numérico entero | object              | 12              | Codígo DANE del municipio en el cual ocurrio el hecho                        | SI                     | NA     | NO                  | NO            | SI                                              | Se observa que los últimos 3 digitos del código no hacen parte de la nomenclatura                                                                    |
| ARMAS MEDIOS  | Alfabético      | object              | 27              | Arma o medio con el que se cometió la lesión                                 | SI                     | NA     | NO                  | NO            | SI                                              | Se observa que se pueden unificar dos categorías de esta variable como lo son "NO REPORTA" y "NO REPORTADO" dejando como único valor el "NO REPORTA" |
| FECHA HECHO   | Numérico entero | object              | 10              | Fecha en la que ocurrió el hecho                                             | NO                     | NA     | SI                  | NO            | SI                                              |                                                                                                                                                      |
| GENERO        | Alfabético      | object              | 12              | Género de la persona involucrada en el hecho                                 | SI                     | NA     | NO                  | NO            | SI                                              | Se observa que hay atributos que se pueden unificar como los géneros que no fueron reportados                                                        |
| GRUPO ETARIO  | Alfabético      | object              | 12              | Clasificación cualitativa para la edad de la persona involucrada en el hecho | SI                     | NA     | NO                  | SI            | SI                                              | Se observa que existen categorías que pueden ser unificadas y 123 campos vacíos a tratar para remplazar con la categoría "no reporta"                |
| TIPO DE HURTO | Alfabético      | object              | 27              | Clasificación cualitativa para el tipo de hurto ocurrido                     | SI                     | NA     | SI                  | NO            | SI                                              |                                                                                                                                                      |
| CANTIDAD      | Numérico entero | int64               | 2               | Cantidad de hechos presentados para la agrupación de los datos anteriores    | NO                     | 1.4186 | SI                  | NO            | SI                                              |                                                                                                                                                      |
                                       

### Hurto a motocicletas y automotores
Para este dataset se encuentran las siguientes características:
    - Dimensiones: 298400 rows × 9 columns
    - Filas repetidas: 35314
    - Dimensiones sin repetidos: 276804 rows × 9 columns
    - DFilas con campos nulos: 0

#### Análisis encontrado
| Campo         | Tipo de dato    | Tipo de dato Pandas | Longitud máxima | Descripción                                                                  | Debe ser lista cerrada | Media  | Normalizado a lista | Valores nulos | Son congruentes los valores con el tipo de dato | Observaciones                                                                                                                                        |
| ------------- | --------------- | ------------------- | --------------- | ---------------------------------------------------------------------------- | ---------------------- | ------ | ------------------- | ------------- | ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| DEPARTAMENTO  | Alfabético      | object              | 18              | Departamento en el cual ocurrió el hecho                                     | SI                     | NA     | SI                  | NO            |                                                 |                                                                                                                                                      |
| MUNICIPIO     | Alfabético      | object              | 27              | Municipio en el cual ocurrió el hecho                                        | SI                     | NA     | SI                  | NO            |                                                 | Se observa que hay municipos con caracteres adicionales como "(ct)" que deben ser eliminados                                                         |
| CODIGO DANE   | Numérico entero | int64               | 8               | Codígo DANE del municipio en el cual ocurrio el hecho                        | SI                     | NA     | NO                  | NO            |                                                 | Se observa que los últimos 3 digitos del código no hacen parte de la nomenclatura                                                                    |
| ARMAS MEDIOS  | Alfabético      | object              | 27              | Arma o medio con el que se cometió la lesión                                 | SI                     | NA     | NO                  | NO            |                                                 | Se observa que se pueden unificar dos categorías de esta variable como lo son "NO REPORTA" y "NO REPORTADO" dejando como único valor el "NO REPORTA" |
| FECHA HECHO   | Alfabético      | object              | 10              | Fecha en la que ocurrió el hecho                                             | NO                     | NA     | SI                  | NO            |                                                 |                                                                                                                                                      |
| GENERO        | Alfabético      | object              | 9               | Género de la persona involucrada en el hecho                                 | SI                     | NA     | SI                  | NO            |                                                 | Se observa que sólo existen registros de "NO APLICA"                                                                                                 |
| GRUPO ETARIO  | Alfabético      | object              | 9               | Clasificación cualitativa para la edad de la persona involucrada en el hecho | SI                     | NA     | SI                  | NO            |                                                 | Se observa que sólo hay registros de tipo "NO APLICA"                                                                                                |
| TIPO DE HURTO | Alfabético      | object              | 18              | Clasificación cualitativa para el tipo de hurto ocurrido                     | SI                     | NA     | SI                  | NO            |                                                 |                                                                                                                                                      |
| CANTIDAD      | Numérico entero | int64               | 2               | Cantidad de hechos presentados para la agrupación de los datos anteriores    | NO                     | 1.4854 | SI                  | NO            |                                                 |                                                                                                                                                      |                                                


## 2 Preguntas por dataset

### Lesiones personales y accidentes de tránsito

#### Top 3  

Cundinamarca (5,90%), Antioquia (5,63%) y Valle (4,74%) presentan en los últimos 5 años la mayor cantidad de delitos por lesiones personales y accidentes de tránsito. Como es de esperarse, las ciudades con un número mayor de habitantes presentan más este tipo de delito.


#### Arma o medio más común

Se evidencia que el medio más común en el caso de accidentes de tránsito son vehículos automotores, seguidos por motocicletas con 34319 y 18230 casos respectivamente.

#### Proporción por género y grupo etario  

Como lo muestra la gráfica anterior, se puede observar que los hombres son aquellos que reciben una mayor cantidad de accidentes de tránsito y como es de esperarse se encuentran dentro del grupo etario de adultos.

#### Tendencia de delitos por mes

Gráficamente se evidencia que los meses en los que más casos se presentan son en enero y diciembre sin embargo, no se puede decir que hay una tendencia claro en esos meses, ya que otros como marzo y octubre se acercan bastante, y la desviación estándar de todos los meses es de 326.78 , un dato bastante bajo teniendo en cuenta que son más de 59000 registros.

#### Descripciones más comunes

Hay dos descripciones y una representa más del 99% de los datos (Artículo 109. Homicidio culposo en accidente de tránsito) vs menos del 1% (Artículo 110 Homicidio culposo, circunstancias de agravación)

### Delitos sexuales

#### Top 3  

Cundinamarca (11,26%), Antioquia (7,28%) y Valle (4,65%) presentan en los últimos 5 años la mayor cantidad de delitos sexuales registrados. Como es de esperarse, las ciudades con un número mayor de habitantes presenta mas robos.

#### Arma o medio más común

Se evidencia que la mayoría de casos se dieron sin el uso de armas con 114948, siendo casi 2.7 veces, respecto al uso de armas contundentes (43712)

#### Proporción por género y grupo etario  

Como es de esperarse, la mayor cantidad de delitos sexuales cometidos son hacia las mujeres representando un pico alto de incidencias a lo largo de los años. En este caso, el grupo etario con mayor cantidad de delitos sexuales son las menores de edad.

#### Tendencia de delitos por mes

Gráficamente se evidencia que no hay una tendencia definida por mes para estos casos, sin embargo, si es notable que en diciembre es evidente una reducción en los casos, pero no es significativa en general, ya que la desviación estándar entre meses es de 2261,3 en un total de 241739.

#### Descripciones más comunes

Las descripciones de delitos más comunes para este caso son: ARTÍCULO 209. ACTOS SEXUALES CON MENOR DE 14 AÑOS y ARTÍCULO 208. ACCESO CARNAL ABUSIVO CON MENOR DE 14 AÑOS, entre ambos representando más del 60% de los casos totales

### Hurto comercial y de viviendas

#### Top 3  

Cundinamarca (31,02%), Antioquia (13,19%) y Valle (8,76%) presentan en los últimos 5 años la mayor cantidad de delitos registrados en  hurtos cometidos a viviendas y comercio. Como es de esperarse, las ciudades con un número mayor de habitantes presenta mas robos.

#### Arma o medio más común

Se evidencia que al igual que en delitos sexuales en el hurto a comercios y residencias, no emplear armas es el medio más común (220069), seguido por poco más de la mitad de casos, el uso de armas contundentes (127567). 

#### Proporción por género y grupo etario  

Se puede evidenciar que entre el 2017 y 2019 se presenta la mayor cantidad de hurtos a comercios y viviendas en los que no se especifica el género ni el grupo etario a la que pertence la persona agredida.

#### Tendencia de delitos por mes

En un total de 492963 datos con una desviación estándar entre los datos de casos por mes de ocurrencia de 3336,72 se evidencia que no hay una tendencia clara para este tipo de delitos, aunque en el mes de enero es cuando más se presentan estos casos, pero sin marcar una gran diferencia. Por último, se puede inferir que de agruparlos tres primeros meses representan el 27,91% del total de hurtos cometidos, cabe resaltar que es la epoca en la que mucha gente sale de vacaciones.

#### Descripciones más comunes

Se presentan dos tipos de delitos que son a comercios y a residencias, siendo el segundo el más común con un 55,9% de los casos.

### Hurto a motocicletas y automotores

#### Top 3  

Cundinamarca (20,94%), Antioquia (20,40%) y Valle (14,14%) presentan en los últimos 5 años la mayor cantidad de delitos registrados a automotores y motocicletas. Como es de esperarse, las ciudades con un número mayor de habitantes presenta mas robos.

#### Arma o medio más común

Gráficamente se evidencia claramente que 3 armas o medios son los más comunes en este tipo de delitos siendo los siguientes los más comunes:
- Llave maestra (1)
- Arma de fuedo (2)
- Sin empledo de armas (3)

#### Proporción por género y grupo etario  

Como se puede observar en la gráfica anterior no hay alguna discriminación por género o grupo etario, lo que hace díficil realizar una interpretación puntual por dichas características, sin embargo, se puede observar que la mayoría de hurtos a motos y autos se realizaron durante el 2019 oscilando a los mil husrtos de más según el año que le precede.

#### Tendencia de delitos por mes

Se evidencia una uniformidad en los datos de los casos por mes con una desviación estándar de 1268,23 contra un total de 276804 casos. No hay un mes con grandes picos o diferencias respecto a los demás. Por último, se refleja que la mayor cantidad de hurtos cometidos a automóviles y motocicletas son realizados en los tres primeros meses representando el 26,94% de los hurtos registrados. Cabe mencionar que es una temporada usual en el que se incrementan los robos debido a la mayoría de visitantes a diferentes lugares de Colombia pues es una fecha usual en la que la mayoría se encuentra en vacaciones.

#### Descripciones más comunes

Se presentan dos tipos de casos, primero de hurto a automóviles, y segundo de hurto a motocicletas, siendo este último el de mayor ocurrencia con un 75.7% del total de los casos, Es evidente que hay una mayor facilidad de llevarse la motocicleta con una llave maestra por el tipo de medio de transporte y los lugares de parqueo no son muy seguros.

## 3 Análisis de delitos últimos 5 años

## 4 Integración de datasets y análisis de delitos

En este ítem se realizaron los siguientes pasos:
- Cargar cada uno de los documentos ya depurados en el punto 1
- Organizar y renombrar las columnas para que fueran homogeneas en cada dataset
- Unificar en un solo dataframe todos los datasets
- Validar los datos de nombres de municipios que podían referirse al mismo pero tenían alguna diferencia
- Cargar el archivo que contenía los habitantes de cada municipio para el año 2022
- Filtrar solo los municipios con más de un millón de habitantes
- Dejar solo los datos correspondientes a los municipios filtrados en el dataset original
- Agrupar por departamento, municipio y código DANE, los datos realizando una operación de suma del campo de cantidad de casos, y el resultado almacenarlo en un nuevo dataframe
- Sobre el nuevo Dataframe añadir una nueva columna con la cantidad de habitantes del municipio correspondiente
- Calcular la cantidad de casos per capita por cada 100.000 habitantes
- Graficar los resultados

Finalmente se evidencia que son 5 municipios, en realidad ciudades, las que aplican al cálculo final con una media de 3328 casos por cada 100.000 habitantes. En la gráfica final se puede ver el detalle de cada uno de estos

## 5 URL del video

# LIBRERÍAS  
pandas
