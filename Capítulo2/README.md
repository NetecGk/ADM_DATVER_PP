# Crear unidades,equipos y roles personalizados

## Objetivo de la práctica:
Al finalizar la práctica, serás capaz de:
- Aplicar la arquitectura de seguridad de Dataverse al crear y configurar Unidades de Negocio, Equipos y Roles de Seguridad personalizados, estableciendo así un modelo de permisos que defina la visibilidad y el acceso de los usuarios a los datos, y que refleje la estructura organizacional de la empresa.

## Objetivo Visual 
![diagrama1](../images/2.1.png)

## Duración aproximada:
- 60 minutos.

## Tabla de ayuda:
Acceso a tu cuenta Microsoft 365.

## Instrucciones 
### Tarea 1. Crear una Unidad de Negocio (Business Unit) en Dataverse
Las Unidades de Negocio definen la estructura organizacional dentro de Dataverse y controlan cómo se segmenta la seguridad y el acceso a los datos.

Paso 1. Ingresa a https://admin.powerplatform.microsoft.com y haz clic en el nombre de tu entorno.

Paso 2. Entra a la configuración del entorno, en la parte superior del panel del entorno, haz clic en Settings (Configuración) y se abre un menú con categorías.

Paso 3. Entra a Usuarios y Permisos, dentro de Settings, ve a: Users + permissions → Business units (Unidades de negocio)

Paso 4. Crear una nueva Unidad de Negocio, en la parte superior derecha, pulsa + New business unit y se un formulario.

Paso 5. Completa el formulario, verás varios campos. Los importantes son:
- Name (Nombre).
- Nombre de la unidad. Ejemplos: Ventas, Marketing, Región Norte, etc. Debe ser único dentro de la organización.
- Parent Business Unit (Unidad de negocio padre), aquí decides dónde va dentro de la jerarquía. Opciones típicas:
  - Si es la segunda unidad que creas → el padre será Root Business Unit (la unidad raíz que Dataverse crea automáticamente).
  - Si ya tienes varias unidades → selecciona la unidad superior correspondiente.
La jerarquía controla la herencia de permisos y visibilidad de datos, así que escógelo bien.
- Description (Descripción) Opcional, pero útil para documentar. Ejemplo: "Unidad responsable de gestionar ventas para Latam."

Paso 6. Haz clic en Save & Close para que la Unidad de Negocio quede creada.

### Tarea 2. Crear equipos dentro de una Unidad de Negocio en Dataverse
Paso 1. En el Centro de administración de Power Platform, haz clic en el nombre de tu entorno.

Paso 2. Abre configuraciones, dentro del entorno, haz clic en Settings (Configuraciones).

Paso 3. Abre la sección de administración de equipos, dentro de Settings Users + permissions → Teams. Aquí verás todos los equipos existentes en el entorno.

Paso 4. Crea un nuevo equipo en la parte superior derecha + New team. Se abrirá un formulario con varias opciones.

Paso 5. Completa los campos del equipo:
- Name (Nombre). Elige un nombre claro. Ejemplos: Equipo Ventas, Soporte Nivel 1 Marketing Digital
- Business Unit (Unidad de negocio). Selecciona la Unidad de Negocio donde quieres que viva el equipo. Ejemplo: Ventas Latam
- Team type (Tipo de equipo). Tipos más usados:
  - Owner Team:	Tiene propiedad de registros y seguridad fuerte. El más común y el recomendado para comenzar.
  - Azure AD Security Group Team:	Usa un grupo de Azure AD como miembros.
  - AAD Office Group (Microsoft 365 Group):	Equipo conectado a un grupo de Microsoft 365.
  - Access Team:	No posee registros; sirve para compartir acceso temporal.
- Administrator (Administrador del equipo). Selecciona un usuario responsable del equipo (Debe pertenecer a la misma Unidad de Negocio.)
- Description (Opcional). Puedes documentar propósito, funciones, etc.

Paso 6. Guardar el equipo, haz clic en Save & Close.

Paso 7. Agrega miembros al equipo. Una vez guardado ábrelo de nuevo, ve a la pestaña Member y haz clic en: + Add members. Selecciona los usuarios que pertenezcan a esa Unidad de Negocio.

Paso 8. Asigna roles de seguridad al equipo para tenga permisos:
- Dentro del equipo → pestaña Security roles
- Clic en Manage roles
- Selecciona los roles apropiados para su función. Esto define qué datos y acciones puede realizar el equipo. 

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
