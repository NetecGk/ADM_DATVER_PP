# Exportar, importar y versionar soluciones

## Objetivo de la práctica:
Al finalizar la práctica, serás capaz de:
- Ejecutar el ciclo de vida de la aplicación (ALM) demostrando la capacidad de exportar una solución existente desde el entorno de desarrollo como Administrada, para luego importarla y actualizarla en un entorno de destino, verificando la transferencia exitosa de componentes y el mantenimiento del control de versiones.

## Objetivo Visual 
![diagrama1](../images/4.1.png)

## Duración aproximada:
- 60 minutos.

## Tabla de ayuda:
Acceso a tu cuenta Microsoft 365.

## Instrucciones 
### Tarea 1. Exportar de Power Apps
Paso 1. Inicie sesión en Power Apps y seleccione Soluciones en el panel de navegación de la izquierda. Si el elemento no se encuentra en el panel lateral, seleccione …Más y, a continuación, el elemento que desee.

2. En la lista de soluciones, seleccione la solución no administrada que desea exportar y luego seleccione Exportar. Tenga en cuenta que no puede exportar soluciones administradas.

3. Aparece el panel derecho Antes de exportar. Elija entre las siguientes opciones y, a continuación, seleccione Siguiente:
- Publique todos los cambios. Tenga en cuenta que, al exportar una solución no administrada, solo se exportan los componentes publicados. Le recomendamos que seleccione Publicar todos los cambios para asegurarse de que todos los componentes estén incluidos en la solución exportada.

4. Aparece el panel derecho Exportar esta solución. Introduzca o seleccione entre las siguientes opciones y, a continuación, seleccione Exportar:
- Número de versión: Power Apps incrementa automáticamente la versión de su solución mientras se muestra la versión actual. Puede aceptar la versión predeterminada o introducir la suya.
- Exportar como: seleccione el tipo de paquete, Administrado o No administrado. Más información: Soluciones administradas y no administradas
- Ejecutar comprobador de soluciones al exportar. Ejecute el comprobador de la solución en la solución para detectar problemas de rendimiento y estabilidad.
![diagrama1](../images/4.2.png)

La exportación puede tardar varios minutos en completarse. Una vez finalizada, el archivo .zip de exportación está disponible en la carpeta de descarga especificada por el explorador web.

### Tarea 2. Importar soluciones
Paso 1. Inicie sesión en Power Apps y seleccione Soluciones en el panel de navegación de la izquierda. Si el elemento no se encuentra en el panel lateral, seleccione …Más y, a continuación, el elemento que desee.

Paso 2. En la barra de comandos, seleccione Importar solución.

Paso 3. En la página Importar una solución , seleccione desde dónde desea importar la solución:
- Este dispositivo. Seleccione Examinar para buscar el archivo comprimido (.zip o .cab) ubicado en el dispositivo que contiene la solución que desea importar.
- Canalización. Seleccione esta opción para importar una solución desde una canalización. Para usar esta opción, debe haber configurado la solución dentro de una canalización. 

Paso 4. Seleccione Siguiente.

Paso 5. Información sobre cómo se muestra la solución. De forma predeterminada, en la sección Configuración avanzada, si los pasos del complemento (también conocidos como pasos de procesamiento de mensajes SDK) y los flujos existen en la solución, se importarán. Desmarque la opción Habilitar pasos y flujos del complemento incluidos en la solución si no desea que la importación intente activar cualquier paso del complemento que se importe en un estado inactivo. Los flujos no se desactivarán cuando la opción esté desactivada.

Paso 6. Si la solución contiene referencias de conexión, se le pedirá que seleccione las conexiones que desee. Si aún no existe una conexión, cree una nueva. Seleccione Siguiente.

Paso 7. Si su solución contiene variables de entorno, se le pide que especifique valores. No verá esta pantalla si los valores ya están presentes en su solución o en el entorno de destino.

Paso 8. Si se detectan dependencias faltantes en el entorno de destino, se presenta una lista de las dependencias. En entornos donde la versión del paquete requerida está disponible para su importación en el entorno de destino, se presenta un enlace para resolver la dependencia. Seleccionar el vínculo le lleva al Centro de administración de Power Platform donde puede instalar la actualización de la aplicación. Una vez completada la actualización de la aplicación, puede volver a iniciar la importación de la solución.

Paso 9. Seleccione Importar. La solución importa en segundo plano y puede tardar unos instantes.

### Tarea 3. Configurar la auditoría para una o varias tablas y columnas en Power Apps
Paso 1.
  
### Resultado esperado
![imagen resultado](../images/4.3.png)

