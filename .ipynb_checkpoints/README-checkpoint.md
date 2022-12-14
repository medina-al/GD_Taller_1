# GD_Taller_1


# AUTORES  
Andrés Leonardo Medina Quijano - Laura Carolina Tinjacá Cristancho


# OBJETIVO  
En el siguiente taller se muestran aquellos cuatro dataset elegidos para su debido perfilamiento (delitos sexuales, lesiones personales y accidentes de tránsito, hurto comercial y de vivienda y hurto a motocicletas y automotores). Describiendo los hallazgos encontrados, estructura de los datos y aspectos relevantes sobre la calidad de los mismos.

# DESARROLLO DEL TALLER

## 1 Análisis general

### Delitos sexuales

- Dimensiones: 59810 filas x 9 columnas
- Filas repetidas: 5
- Dimensiones finales: 59805 filas x 9 columnas

#### Campos

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

### Lesiones personales y accidentes de tránsito

### Hurto comercial y de viviendas

### Hurto a motocicletas y automotores

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
https://tabletomarkdown.com/convert-spreadsheet-to-markdown/