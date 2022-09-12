HEALTHCHECK es un comando que se utiliza dentro de un dockerfile para verificar que 
el estado de ejecucion de ciertos contenedores. Ademas, puede servir para verificar
inhabilitaciones del container tanto propias como heredadas por sus imagenes base

ONBUILD sirve para agregar a la imagen instrucciones para ejecutarse luego de buildearse
Lo que hace es asignar una instruccion trigger que luego se ejecuta en el contenedor

VOLUME es una instruccion que permite elegir un punto de montaje determinado para la imagen
Suele utilizarse para exponer bases de datos, o para partes de imagenes que son modificadas
con frecuencia