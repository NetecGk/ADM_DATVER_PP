# Práctica 4. Exportar, importar y versionar soluciones

## Objetivo de la práctica:
Al finalizar la práctica, serás capaz de:
- Ejecutar el ciclo de vida de la aplicación (ALM) demostrando la capacidad de exportar una solución existente desde el entorno de desarrollo como administrador, para luego importarla y actualizarla en un entorno de destino, verificando la transferencia exitosa de componentes y el mantenimiento del control de versiones.

### Objetivo visual 
![diagrama1](../images/4.1.png)

### Duración aproximada:
- 85 minutos.

### Tabla de ayuda:
Acceso a tu cuenta Microsoft 365.

## Instrucciones 

### Tarea 1. Exportar de Power Apps.

**Paso 1.** Inicia sesión en Power Apps y selecciona `Soluciones` en el panel de navegación de la izquierda. Si no se encuentra en el panel lateral, selecciona `…Más` y, a continuación, el elemento que desees.

**Paso 2.** En la lista de soluciones, seleccione la solución no administrada que desea exportar y luego seleccione Exportar. Tenga en cuenta que no puede exportar soluciones administradas.

**Paso 3.** Aparece el panel derecho `Antes de exportar`.
  - Elige entre las siguientes opciones.
    - Publica todos los cambios. Ten en cuenta que, al exportar una solución no administrada, solo se exportan los componentes publicados.
    - **Recomendación.** Selecciona `Publicar todos los cambios` para asegurarte de que todos los componentes estén incluidos en la solución exportada.
  - Selecciona `Siguiente`.

**Paso 4.** Aparece el panel derecho `Exportar esta solución`.
  - Introduce o selecciona entre las siguientes opciones.
    - **Número de versión**: Power Apps incrementa automáticamente la versión de la solución mientras se muestra la versión actual. Puedes aceptar la versión predeterminada o introducir la propia.
    - **Exportar como**: selecciona el tipo de paquete, **Administrado** o **No administrado**.
    - **Ejecutar comprobador de soluciones al exportar**: ejecuta el comprobador de la solución en la solución para detectar problemas de rendimiento y estabilidad.
  - Selecciona `Exportar`.
  
![diagrama1](../images/4.2.png)

La exportación puede tardar varios minutos en completarse. Una vez finalizada, el archivo .zip de exportación está disponible en la carpeta de descarga especificada por el explorador web.

### Tarea 2. Importar soluciones.

**Paso 1.** Inicia sesión en Power Apps y selecciona `Soluciones` en el panel de navegación de la izquierda. Si el elemento no se encuentra en el panel lateral, selecciona `…Más` y, a continuación, el elemento que desees.

**Paso 2.** En la barra de comandos, selecciona `Importar solución`.

**Paso 3.** En la página **Importar una solución**, selecciona desde dónde desea importar la solución:
  - **Este dispositivo**. Selecciona `Examinar` para buscar el archivo comprimido (.zip o .cab) ubicado en el dispositivo que contiene la solución que a importar.
  - **Canalización**. Selecciona esta opción para importar una solución desde una canalización. Para usar esta opción, debes de haber configurado la solución dentro de una canalización.

**Paso 4.** Selecciona `Siguiente`.

**Paso 5.** <ins>Información sobre cómo se muestra la solución.</ins>
  - De forma predeterminada, en la sección **Configuración avanzada**, si los pasos del complemento (también conocidos como **pasos de procesamiento** de mensajes SDK) y los flujos existen en la solución, se importarán.
  - Desmarca la opción ***Habilitar pasos y flujos del complemento incluidos en la solución*** si no deseas que la importación intente activar cualquier paso del complemento que se importe en un estado inactivo. Los flujos no se desactivarán cuando la opción esté desactivada.

**Paso 6.** Si la solución contiene referencias de conexión, deberás seleccionar las conexiones que desees. Si aún **no** existe una conexión, crea una nueva. Selecciona `Siguiente`.

**Paso 7.** Si la solución contiene <ins>variables de entorno</ins>, deberás especificar <ins>valores</ins>. **No** verás esta pantalla si los valores ya están presentes en la solución o en el entorno de destino.

**Paso 8.** Si se detectan dependencias faltantes en el entorno de destino, se presentará una lista de las dependencias.

  - En entornos donde la versión del paquete requerida está disponible para su importación en el entorno de destino, se presenta un enlace para resolver la dependencia.
  - Seleccionar el vínculo te llevará al **Centro de administración de Power Platform**, donde puedes instalar la actualización de la aplicación. Una vez completada la actualización de la aplicación, puedes volver a iniciar la importación de la solución.

**Paso 9.** Selecciona `Importar`. La solución importa en segundo plano, puede tardar unos instantes.

---

### Tarea 3. Analizar el siguiente escenario y responder en consecuencia.

El desarrollador principal, por error, exportó la aplicación de nóminas como una **solución <ins>no</ins> administrada** y la importó en el entorno de **producción**. Tres meses después, el equipo de TI intenta desinstalar una característica obsoleta, pero el proceso falla y deja componentes huérfanos.

<ins>Selecciona la respuesta más adecuada para cada pregunta.</ins>

#### 1. ¿Cuál fue la principal consecuencia de importar una solución no administrada en el entorno de producción?

  * **A.** Se eliminaron todos los datos existentes en el entorno de producción.
  * **B.** Los componentes de la solución quedaron disponibles para ser modificados o eliminados directamente en el entorno de producción.
  * **C.** La aplicación dejó de funcionar inmediatamente porque los flujos de trabajo se rompieron.
  * **D.** La solución se revirtió automáticamente a la versión anterior instalada en el entorno.

#### 2. En el escenario donde se intentó desinstalar la característica obsoleta, ¿por qué el proceso falló y dejó componentes huérfanos?

  * **A.** Solo se pueden desinstalar soluciones si el entorno está en modo de administración.
  * **B.** Solo se eliminan las referencias a los componentes, dejando los componentes base como parte de la capa base (huérfanos).
  * **C.** La solución no tenía permisos de "eliminar" en el rol de seguridad.
  * **D.** El número de versión de la solución era demasiado alto para el entorno de producción.

#### 3. Si la solución se hubiera importado correctamente como Solución Administrada, ¿qué habría permitido que la desinstalación fuera exitosa y limpia?

  * **A.** Permite que todos los componentes sean editados manualmente por el equipo de TI antes de desinstalar.
  * **B.** Contiene un "candado" que fuerza a que el entorno elimine todos los componentes de la solución al mismo tiempo que la capa.
  * **C.** Crea automáticamente copias de seguridad de todos los componentes en Azure DevOps.
  * **D.** Requiere que se reinicie la instancia de Dataverse antes de la desinstalación.

#### 4. ¿Cuál es el principal beneficio de seguridad que una solución administrada ofrece al entorno de producción?

  * **A.** Asegura que los datos no puedan ser eliminados por usuarios con el rol de creador de entornos.
  * **B.** Impide que los usuarios (incluso los administradores) modifiquen directamente las propiedades de los componentes de la solución.
  * **C.** Permite auditar automáticamente todos los cambios realizados a la solución sin configuración adicional.
  * **D.** Bloquea el acceso a la aplicación para usuarios que no tienen licencia premium.

#### 5. ¿En qué tipo de entorno y con qué tipo de solución se deben realizar siempre los cambios y las correcciones de errores antes de la migración?

  * **A.** En el entorno de pruebas (TEST) usando una solución administrada.
  * **B.** En el entorno de producción (PROD) usando una solución no administrada.
  * **C.** En el entorno de desarrollo (DEV) usando una solución no administrada.
  * **D.** En el centro de administración de Power Platform (PPAC) usando el rol de administrador global.

#### 6. En el contexto de ALM, ¿a qué se refiere la frase "componentes huérfanos" que dejó la desinstalación fallida en producción?

  * **A.** Archivos temporales del sistema que deben eliminarse con la herramienta de limpieza de disco.
  * **B.** Componentes personalizados (tablas, campos, flujos) que permanecen en el entorno sin estar vinculados a ninguna solución que los 
rastree o gestione.
  * **C.** Cualquier componente que no haya sido tocado por el desarrollador durante los últimos 90 días.
  * **D.** Los datos de usuario que han quedado sin dueño en una tabla.

#### 7. Si el equipo de TI detecta que la aplicación necesita un cambio menor (un parche) después del despliegue exitoso de la v1.0, ¿cuál es la mejor práctica de ALM para aplicar la corrección?

  * **A.** Editar el componente directamente en producción y luego volver a exportarlo como administrada.
  * **B.** Crear una nueva versión de parche (ej. v1.0.0.1) en DEV y exportarla como administrada para actualizar PROD.
  * **C.** Desinstalar la v1.0 completamente e importar una solución no administrada con las correcciones.
  * **D.** Usar la función de **Hotfix** del centro de administración para aplicar el cambio sin versionar.

#### 8. ¿Qué sucede si el desarrollador intenta importar una nueva versión de la solución administrada que tiene una versión menor a la que ya está instalada en producción?

  * **A.** La importación sobrescribe automáticamente la versión actual con la versión más antigua.
  * **B.** La importación es rechazada por el sistema con un error de versión para proteger la estabilidad de la versión instalada.
  * **C.** El sistema permite la importación y fusiona las características de ambas versiones.
  * **D.** El entorno se desactiva hasta que el administrador apruebe la versión más baja.

#### 9. ¿Cuál es la herramienta o práctica de ALM que se recomienda para eliminar el riesgo de que una persona cometa el error de exportar el tipo de solución incorrecto (no administrada) a producción?

  * **A.** La función de auditoría del entorno.
  * **B.** Un rol de seguridad personalizado que prohíba la exportación.
  * **C.** La implementación de pipelines de Power Platform o Azure DevOps.
  * **D.** El uso de la Herramienta de comprobación de soluciones.

#### 10. En el contexto de una "actualización" (importar una nueva versión de una solución administrada), si el componente actualizado tiene una versión mayor (ej. de v1.0 a v2.0), ¿qué es <ins>verdad</ins> sobre el componente antiguo?

  * **A.** La versión antigua se mantiene como una capa superpuesta inactiva.
  * **B.** Los componentes de la versión antigua que no existen en la nueva versión se eliminan del entorno de destino.
  * **C.** El administrador debe desinstalar manualmente la versión v1.0 antes de importar la v2.0.
  * **D.** Los metadatos de la versión v1.0 se copian en el entorno de desarrollo para su custodia.
  
### Resultado esperado
![imagen resultado](../images/4.3.png)

