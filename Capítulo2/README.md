# Crear unidades, equipos y roles personalizados

## Objetivo de la práctica:
Al finalizar la práctica, serás capaz de:
- Aplicar la arquitectura de seguridad de Dataverse al crear y configurar unidades de negocio, equipos y roles de seguridad personalizados, estableciendo así un modelo de permisos que defina la visibilidad y el acceso de los usuarios a los datos y que refleje la estructura organizacional de la empresa.

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

### Tarea 3. Crear un rol personalizado
Paso 1. En el Centro de administración de Power Platform, haz clic en el nombre de tu entorno.

Paso 2. Seleccione Ver todo en Roles de seguridad, en la panel Acceso a la derecha.

Paso 3. Seleccione Nuevo rol en la barra de menú superior, lo que abrirá el diseñador de roles de seguridad.

Paso 4. Introduzca un nombre, como "Mi nuevo rol de seguridad", para su rol de seguridad en el campo Nombre del rol.

Paso 5. Seleccione una Unidad de negocio (es posible que solo tenga una, de forma predeterminada, pero esta es una entrada obligatoria).

Paso 6. Seleccione Guardar. Tras unos momentos, el nuevo rol de seguridad aparecerá en una pantalla de configuración, con una lista de las tablas en el entorno. Puede buscar la tabla en el campo de búsqueda, en la parte superior derecha de la pantalla de configuración.

![diagrama1](../images/2.2.jpg)

Paso 7. Cuando encuentre la tabla en la lista, selecciónela. Como puede ver, aparecen menús desplegables bajo los distintos privilegios que puede asignar para este rol de seguridad, como Crear, Leer, Escribir, Eliminar, Anexar, Anexar a, Asignar y Compartir. Seleccione el ámbito para realizar esa acción seleccionando el nombre de la tabla. El ámbito determina la profundidad o altura en la jerarquía del entorno en la que el usuario puede realizar una acción en particular. Utilice los menús desplegables a fin de asignar privilegios para este grupo de seguridad y para esta tabla en particular. Para nuestro nuevo rol, vamos a hacer algo sencillo: vamos a dejar que Organización pueda crear, leer, escribir, eliminar, asignar y compartir un registro en esta tabla.

Paso 8. Seleccione Guardar y cerrar en la barra de comandos.

### Tarea 4. Asignar usuarios a su rol de seguridad
Tras guardar y cerrar su nuevo rol de seguridad, estará en la pantalla Roles de seguridad. (Si no sabe dónde está, vaya a Configuración > Usuarios + permisos > Roles de seguridad).

Paso 1. Busque el rol de seguridad que hemos creado desplazándose hacia abajo en la lista o introduciendo el nombre de su nuevo rol en el campo "Buscar por nombre" de la parte superior derecha de la pantalla.

Paso 2. Seleccione el rol y seleccione el botón Más acciones (...) > Miembros. Si selecciona por error el nombre del rol, regresará a la pantalla de configuración de este; si regresa a la pantalla Roles de seguridad, seleccione el botón Más acciones.

Paso 3. Su nuevo rol de seguridad tendrá un botón Agregar personas. Selecciónelo.

Paso 4. Aparecerá un panel Agregar personas en el lado derecho de la pantalla. Tiene un campo de búsqueda donde puede introducir el nombre de una persona, el correo electrónico o el nombre de un equipo. Busque y agregue varios usuarios seleccionando su nombre en los resultados de búsqueda.

Paso 5. Cuando tenga varias personas en la lista, seleccione el botón Agregar en la parte inferior del panel Agregar personas.

Paso 6. Tras unos momentos, los usuarios para su nuevo rol de seguridad aparecerán debajo de Miembros. Si necesita eliminar un usuario, puede seleccionar el nombre de la persona; al hacerlo, aparecerá un botón de acción Eliminar en la parte superior izquierda de la barra de comandos. Si necesita agregar otro usuario, compruebe que no haya ningún usuario seleccionado; verá un botón "Agregar personas" en la parte superior izquierda de la barra de comandos.

### Resultado esperado
![imagen resultado](../images/2.3.jpg)
