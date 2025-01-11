
# Prueba tecnica Nequi para el cargo de Ingeniero de Datos

### Desarrollo hecho por Ricardo Antonio Arango Quiroz
#### Medellin - Colombia, 11/01/2025

## Contexto de los datos y del desafio
En el mundo financiero actual, las instituciones están constantemente expuestas a riesgos asociados con actividades fraudulentas. Estas actividades no solo impactan a las entidades financieras, sino que también pueden comprometer la seguridad y confianza de los clientes y del sistema financiero en general.
Las transacciones atípicas son aquellas que se desvían significativamente de los patrones habituales de comportamiento. Estas pueden incluir desde transferencias de montos inusualmente grandes o pequeños hasta movimientos de dinero que no se alinean con el historial financiero de los usuarios. Detectar estas transacciones representa un gran desafío debido a la inmensa cantidad de datos que las instituciones financieras procesan diariamente y a la complejidad de los patrones que pueden sugerir actividad fraudulenta.
Por ello, existe una necesidad creciente de desarrollar métodos más avanzados para identificar transacciones sospechosas. Al comprender los factores que influyen en el comportamiento de los clientes y emplear herramientas avanzadas, es posible mejorar la precisión y eficiencia en la detección de actividades atípicas, fortaleciendo así la seguridad del sistema financiero.

El actual reto consiste en la limpieza y preparación de datos de transacciones atípicas para la construcción de modelos de Machine Learning que eficazmente puedan detectar estos. También los datos deben de ser útiles para la construcción de reportes de visualización que permitan a los analistas conocer el estado actual del negocio.

## Especificaciones de los datos
Los datos suministrados consisten en aproximadamente 1.7 millones de transacciones reales realizadas en un tiempo específico. Cada transacción representa la creación de un crédito por parte de un cliente. Los datos incluyen diversas variables descriptivas, como la fecha de la transacción, el ID del almacén donde se generó el crédito, características del cliente, y otras variables adicionales. Los datos se entregarán en formato .csv.

## Diccionario de Datos
Lo siguiente muestra una explicacion para los campos de datos antes de entrar en el proceso de limpieza.

|VARIABLE|DEFINICIÓN|
|------|------|
|CreditoID|Código único para identificar un crédito|
|PersonaID|Código único para identificar un cliente|
|DepartamentoResidencia|Departamento de residencia del cliente, ingresado en el momento del enrolamiento|                         
|DepartamentoMayorFrecuenciaCompra|Moda del departamento de compra para cada cliente, es decir, el departamento donde más ha realizado compras|
|AlmacenMayorFrecuenciaPago|Moda del  Almacén de pago para cada cliente|       
|ValorPagosUltimosMes|Suma del total de pagos realizado por cada cliente en el último mes|
|AlmacenCredito|Código único para identificar al almacén donde se realiza el crédito|
|RiesgoAlmacen|Variable interna que identifica el grado de riesgo de un almacen (1: bajo, 7 medio, 9 alto)|
|DepartamentoCredito|Código del departamento del comercio donde se está realizando el crédito|
|FechaCredito|Fecha y hora en la que se crea el crédito|
|ValorCredito|Monto en pesos ($)  de la compra que se está realizando|                           
|CupoTotal|Cupo total  en pesos ($) que tiene el cliente justo antes de realizar la compra | 
|CupoDisponibleTotal|Cupo disponible en pesos ($) que tiene el cliente justo antes de realizar la compra (corresponde al cupo total -   monto de $ que tiene el cliente en el momento en uso)|
|storeIdEventoA|Código del almacén donde ocurrió el evento A|
|FechaEventoA|Fecha en la que sucedió el evento A|
|EventoA|Variable binaría, indica si sucedió el evento A|
|FechaEventoB|Fecha en la que sucedió el evento B|
|LocalizacionEventoB|Corresponde a la Latitud y Longitud del comercio donde se realizó el evento B|
|LocalizacionComercioCredito|Corresponde a la Latitud y Longitud del comercio donde se realiza el crédito|
|StatusComercioCredito|Codigo interno que permite identificar el estado del almacen, si está activo o inactivo|
|FrecuenciaCreditosSemana|Corresponde al calculo del promedio de créditos comprados por semana, calculado para las semanas en las que se ha realizado compras|
|CantidadCreditosUltimaSemana|Corresponde al conteo de los créditos sacados en la última semana|
|ValorAtipicoCliente|Variable calculada para medir cuando el valor de una transaccion es atípica para el monto comprado por un cliente|
|ValorAtipicoComercio|Variable calculada para medir cuando el valor de una transaccion es atípica para el monto vendido por el almacén|
|TipoAlmacen|Marcación de Fisico o virtual según el tipo de almacen donde se está realizando la compra|
|TipoCliente|Marcación de Antiguo o Nuevo, según el tipo de cliente que esta haciendo la transaccion|
|Atipico|Clasificación binaria, si una transacción fue considerada como atípica o no|

Nota:Los eventos A y B corresponden a sucesos poco frecuentes relacionados con una interacción del cliente en un comercio


## Pipeline construido
A continuación se muestra el pipeline construido.


Aquí, los datos que se reciben en S3 son procesados en cuanto se reciben. Estos se limpian mediante un ETL en AWS Glue para luego ser guardados en se respectiva tabla en AWS Redshift Serverless.

## Limpieza de datos
### Separación de datos de localizaciones
### Formatos de fechas
### Valores nulos


## Modelo de datos después de limpieza

## 


