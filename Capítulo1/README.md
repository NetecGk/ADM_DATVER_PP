# Crear y configurar un entorno sandbox

## Objetivo de la práctica:
Al finalizar la práctica, serás capaz de:
- Demostrar la capacidad de crear y personalizar un Entorno Sandbox de Power Platform, y establecer sus configuraciones iniciales (tipo, región, base de datos) para usarlo como espacio seguro de desarrollo y prueba.

## Objetivo Visual 
![diagrama1](../images/1.1.png)

## Duración aproximada:
- 60 minutos.

## Tabla de ayuda:
Acceso a tu cuenta Microsoft 365.

## Instrucciones 
### Tarea 1. Crear y Configurar un Entorno Sandbox
Paso 1: Abre tu navegador y ve al Centro de administración de Power Platform (PPAC): admin.powerplatform.microsoft.com. Inicia sesión con tu cuenta de administrador que tenga los permisos necesarios (Admin del Servicio, Admin Global, o Admin de Power Platform).

Paso 2: Inicia la Creación del Entorno. 
- En el panel de navegación izquierdo, selecciona Entornos.
- En la barra de comandos superior, haz clic en el botón + Nuevo.

Paso 3: Configuración Básica del Entorno. En la primera ventana de configuración:
- Nombre: Asigna un nombre único y descriptivo, como Mi Entorno Sandbox de Prueba.
- Tipo: Selecciona Sandbox. Este es crucial para el aislamiento del trabajo de prueba.
- Región: Elige la región geográfica más cercana a tus usuarios para el mejor rendimiento.

Paso 4: Configuración de la Base de Datos. Haz clic en Siguiente o navega a la sección de configuración de la base de datos:
- Base de Datos: Asegúrate de que la opción para Crear una base de datos para este entorno esté activada (Sí).
- Idioma: Selecciona el idioma base para la interfaz de Dataverse (ej. Español).
- Moneda: Define la moneda predeterminada de la región (ej. EUR, USD).
- Aplicaciones Dynamics 365: Deja esta opción desactivada si solo usarás Dataverse y Power Apps (para ahorrar consumo de almacenamiento).

Paso 5: Finaliza la Creación, revisando todas las configuraciones y haz clic en el botón Guardar.

### Tarea 2. Configurar Seguridad Mínima
Paso 1: En el Centro de administración de Power Platform (PPAC), haz clic en el nombre de tu nuevo entorno.

Paso 2: En la barra de comandos superior del entorno, haz clic en Configuración. Se abrirá una nueva página. En el menú de navegación, selecciona Usuarios + permisos y luego haz clic en Usuarios.

Paso 3: Busca tu usuario (o un usuario de prueba). Haz clic en el usuario y luego en el botón ... (más acciones). Selecciona Administrar roles de seguridad.

Paso 4: Asigna el rol Administrador del Sistema a tu usuario.

### Tarea 3. Probar la configuración creando tablas mediante Copilot
Paso 1. En https://make.powerapps.com/ seleccione Tablas en el panel de navegación izquierdo.

Paso 2. Seleccione Empezar con Copilot.

Paso 3. En la pantalla Describir las tablas que creará Copilot, introduzca "Crea una tabla para administrar las donaciones recibidas. La tabla debe identificar el tipo de donación que se recibió, el importe, la fecha y el motivo, si se proporcionó".

Paso 4. Junto al botón Generar, seleccione Configuración de tabla y configure lo siguiente:
- Opciones de tabla: una tabla
- Tamaño de la tabla: pequeña
- NO incluya relaciones.

Paso 5. Seleccione el botón Generar. Copilot solo debería crear una tabla llamada Donation. Si se crearon más, puede eliminarlas diciéndole a Copilot el nombre de la tabla que desea eliminar.

Paso 6. En la barra de comandos de la parte superior, seleccione + Tabla existente.

Paso 7. En la pantalla Seleccionar tabla, cambie de Recomendadas a Todas las tablas.

Paso 8. En el campo de búsqueda, introduzca Contact y elija Agregar seleccionado.

Paso 9. En la barra de comandos, seleccione Crear relaciones.

Paso 10. Configure la relación como sigue:
- Tipo de relación: uno a varios
- Uno: Contact
- Varios: Donation
- Nombre para mostrar: Donor

![diagrama1](../images/1.2.png)

Paso 11. Seleccione Listo y de esta manera creamos un modelo que nos prueba que el entorno esta completamente funcional.

### Resultado esperado

![imagen resultado](../images/1.3.jpg)
