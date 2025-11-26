# Práctica 3. Habilitar auditoría, aplicar reglas de duplicados y eliminación

## Objetivo de la práctica:
Al finalizar la práctica, serás capaz de:
- Establecer la gobernanza y la integridad de los datos mediante la activación de la auditoría para el seguimiento de cambios, la configuración de reglas de detección de duplicados para mantener la calidad de los datos y la planificación de trabajos de eliminación masiva para optimizar el almacenamiento y asegurar el cumplimiento normativo.

### Objetivo visual 
![diagrama1](../images/3.1.png)

### Duración aproximada:
- 90 minutos.

### Tabla de ayuda:
Acceso a tu cuenta Microsoft 365.

## Instrucciones 
### Tarea 1. Configurar auditoría para un entorno.
La auditoría puede configurarse en tres niveles: un **entorno**, **tabla** y **columna**. La auditoría debe activarse primero en el nivel de **entorno**. Para registrar los cambios de datos en una tabla, la auditoría debe estar activada para la tabla y para la columna.

**Paso 1.** Inicia sesión en [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).

**Paso 2.** En el menú izquierdo, selecciona `Seguridad` > `Cumplimiento`.

**Paso 3.** Selecciona el mosaico `Auditoría`.

**Paso 4.** Selecciona el entorno para el que deseas configurar la auditoría.

**Paso 5.** Selecciona `Configurar auditoría`. En el cuadro de diálogo `Auditoría`, selecciona `Activar auditoría`.

**Paso 6.** Revisa la lista de entidades de datos de Dataverse y aplicaciones de Dynamics 365.

**Paso 7.** Revisa y actualiza la retención de registro de eventos seleccionando el <ins>menú desplegable</ins>.

**Paso 9.** Selecciona el periodo que cumpla su política de retención de datos.
  - Cuando el periodo de retención de auditoría se establece en **Siempre**, los registros no se eliminan.
  - Cuando el período de retención de auditoría se establece en cualquier otro valor, los registros se eliminan continuamente a partir del momento en que un registro de auditoría exceda el tiempo definido en la directiva de retención.

### Tarea 2. Iniciar/detener la auditoría de un entorno y establecer la directiva de retención.

**Paso 1.** Inicia sesión en [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).

**Paso 2.** En el panel de navegación, selecciona `Administrar`.

**Paso 3.** En el panel `Administrar`, selecciona `Entornos`. A continuación, elige un entorno.

**Paso 4.** Selecciona `Configuración` > `Auditoria` y `Registros` > `Configuración de auditoría`.

**Paso 5.** En `Conservar estos registros durante`, elige el periodo de tiempo en el que deseas conservar los registros.

**Paso 6.** Selecciona `Guardar`.

### Tarea 3. Configurar la auditoría para una o varias tablas y columnas en Power Apps.

**Paso 1.** Inicia sesión en Power Apps con tus credenciales de **Administrador** o **Personalizador del sistema**.

**Paso 2.** Selecciona el entorno para el que deseas configurar la auditoría.

**Paso 3.** Selecciona `Tablas`.

**Paso 4.** Selecciona una tabla.

![diagrama1](../images/3.2.png)

**Paso 5.** En la barra de comandos, selecciona `Editar`.

**Paso 6.** En la barra de comandos, selecciona `Editar propiedades de tabla`.

**Paso 7.** Expande `Opciones avanzadas`.

**Paso 8.** Selecciona la casilla `Cambios de auditoría en sus datos`.

![diagrama1](../images/3.3.png)

**Paso 9.** Selecciona `Guardar`.

**Paso 10.** En la barra de comandos, selecciona `<- Atrás`.

**Paso 11.** En **Esquema**, selecciona `Columnas`.

![diagrama1](../images/3.4.png)

**Paso 12.** Selecciona una columna que desees habilitar para auditoría y luego expande `Opciones avanzadas`.

![diagrama1](../images/3.5.png)

**Paso 13.** Selecciona la casilla `Habilitar auditoría`.

![diagrama1](../images/3.6.png)

**Paso 14.** Selecciona `Guardar`.

**Paso 15.** Repite los **pasos 3 a 10** para todas las tablas y columnas que desees editar.

### Tarea 4. Crear y activar una regla de duplicados.
**Paso 1.** Ingresa en: [https://make.powerapps.com](https://make.powerapps.com) y, en la parte superior derecha, selecciona el entorno donde trabajarás.

**Paso 2.** Abre el área de reglas de duplicados:
  - Selecciona el ícono de *Settings* `(⚙️)` en la esquina superior derecha.
  - Selecciona `Advanced settings`. Esto abre la interfaz clásica de Dynamics CRM.
  - Navega a `Settings` → `Data Management` → `Duplicate Detection Rules`.

**Paso 3.** Crea una nueva regla seleccionando `+ New` y completando los campos recomendados:
  - **Name**: regla contactos - nombres duplicados.
  - **Description**: detectar contactos con el mismo nombre y correo.
  - **Base table**: contact.
  - **Matching Criteria**:
    - First Name — Exact match.
    - Last Name — Exact match.
    - Email — Exact match.

**Paso 4.** Guarda la regla seleccionando `Save`.

**Paso 5.** Publica y activa la regla seleccionando `Publish` → `Activate`.

**Paso 6.** Prueba la regla.
  - Abre la tabla seleccionada (por ejemplo, **Contact**).
  - Crea un registro con datos de prueba.
  - Intenta crear otro registro con los mismos datos, **debe aparecer la advertencia de duplicado**.

### Tarea 5. Configurar trabajos de eliminación (Bulk Delete).
**Paso 1.** Abre la sección de **eliminación masiva**.
  - Ve `Settings` → `Advanced settings`.
  - Navega a `Settings` → `Data Management` → `Bulk Record Deletion`.

**Paso 2.** Crea un nuevo trabajo de eliminación.
  - Selecciona `+ New Bulk Delete job`.

**Paso 3.** <ins>Define criterios</ins>, por ejemplo: "eliminar contactos sin actividad creados hace más de 30 días".
  - Establece la tabla: `Contact`.
  - Configura el filtro:
    - <ins>Filtrar por</ins>: **Created On** → **Older than 30 days**.
    - <ins>Agregar condición</ins>: **Activities** → **No related activities**.

**Paso 4.** Configura la programación.
- Selecciona `Run this job` → `Once`.
- Define `Start time` → `Now`.
- Habilita o no `Email notifications` (opcional).

**Paso 5.** Confirma seleccionando `Next` → `Submit`.

**Paso 6.** Ve el progreso.
  - Revisa el estado del job (**Waiting** / **In progress** / **Succeeded**).
  - Actualiza la vista hasta observar la finalización.
  
### Resultado esperado
![imagen resultado](../images/3.7.png)

