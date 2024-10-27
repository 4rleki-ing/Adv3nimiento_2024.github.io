---
layout: single
title: Conceptos básicos de Directorio Activo
excerpt: "Esta sala presentará los conceptos básicos y la funcionalidad proporcionada por Active Directory."
date: 2024-10-12
classes: wide
header:
  teaser: /assets/images/
  teaser_home_page: true
categories:
  - Ciberseguridad 101
tags:
  - Sección 3
  - Windows
  - Active Directory
---

![Portada](assets/images/)

## Introducción
`Active Directory` de Microsoft es la *columna vertebral* del mundo empresarial. Simplifica la gestión de dispositivos y usuarios dentro de un entorno corporativo. En esta sala, profundizaremos en los componentes esenciales de Active Directory.

### Objetivos de la habitación
En esta sala aprenderemos sobre Active Directory y nos familiarizaremos con los siguientes temas.

- ¿Qué es el Directorio Activo?
- Qué es un dominio de Active Directory
- ¿Qué componentes van en un dominio de Active Directory?
- Bosques y confianza de dominio
- ¡Y mucho más!

### Requisitos previos de la habitación

- `Familiaridad general con Windows`. Consulte el módulo Windows Fundamentals para obtener más información al respecto.

### Responde las preguntas a continuación
- ¡Haz clic y continúa aprendiendo! 

## Dominios de Windows
Imagínese administrando la red de una pequeña empresa con sólo cinco computadoras y cinco empleados. En una red tan pequeña, probablemente podrás configurar cada computadora por separado sin problemas. Iniciará sesión manualmente en cada computadora, creará usuarios para quien los usará y realizará configuraciones específicas para las cuentas de cada empleado. Si la computadora de un usuario deja de funcionar, probablemente irás a su casa y arreglarás la computadora en el sitio.

Si bien esto suena como un estilo de vida muy relajado, supongamos que su negocio crece repentinamente y ahora tiene 157 computadoras y 320 usuarios diferentes ubicados en cuatro oficinas diferentes. ¿Aún podría administrar cada computadora como una entidad separada, configurar políticas manualmente para cada uno de los usuarios de la red y brindar soporte en el sitio para todos? Lo más probable es que la respuesta sea no.

Para superar estas limitaciones, podemos utilizar un dominio de Windows. En pocas palabras, un `dominio de Windows` es un grupo de usuarios y computadoras bajo la administración de una empresa determinada. La idea principal detrás de un dominio es centralizar la administración de los componentes comunes de una red informática Windows en un único repositorio llamado `Active Directory (AD)`. El servidor que ejecuta los servicios de Active Directory se conoce como `controlador de dominio (DC)`.

<div align="center">
  <img src="/assets/images/Active-Directory/Domain.png">
</div>

Las principales ventajas de tener un dominio Windows configurado son:

- `Gestión de identidades centralizada`: todos los usuarios de la red se pueden configurar desde Active Directory con el mínimo esfuerzo.
- `Administrar políticas de seguridad`: puede configurar políticas de seguridad directamente desde Active Directory y aplicarlas a usuarios y computadoras en la red según sea necesario.

### Un ejemplo del mundo real
Si esto suena un poco confuso, es probable que ya hayas interactuado con un dominio de Windows en algún momento de tu escuela, universidad o trabajo.

En las redes escolares/universitarias, a menudo se le proporcionará un nombre de usuario y una contraseña que podrá utilizar en cualquiera de las computadoras disponibles en el campus. Sus credenciales son válidas para todas las máquinas porque cada vez que las ingresa en una máquina, reenviará el proceso de autenticación a Active Directory, donde se verificarán sus credenciales. Gracias a Active Directory, no es necesario que sus credenciales existan en cada máquina y están disponibles en toda la red.

Active Directory es también el componente que permite a su escuela/universidad restringirle el acceso al panel de control de sus máquinas de la escuela/universidad. Por lo general, las políticas se implementarán en toda la red para que usted no tenga privilegios administrativos sobre esas computadoras.

### Bienvenido a THM Inc.
Durante esta tarea, asumiremos el rol del nuevo administrador de TI en THM Inc. Como primera tarea, se nos pidió que revisemos el dominio actual "THM.local" y realicemos algunas configuraciones adicionales. ) preconfigurado Tendrá credenciales administrativas sobre un controlador de dominio ( DC para realizar las tareas.

Asegúrese de hacer clic en el botón Iniciar máquina que aparece a continuación ahora, ya que utilizará la misma máquina para todas las tareas. Esto debería abrir una máquina en su navegador. 

<div align="center">
  <img src="/assets/images/Active-Directory/Iniciar.png">
</div>

Si prefiere conectarse a través de RDP , puede utilizar las siguientes credenciales: 

<div align="center">
  <img src="/assets/images/Active-Directory/RDP.png">
</div>

**Nota:** Cuando se conecte a través de RDP, utilice `THM\Administrator` como nombre de usuario para especificar que desea iniciar sesión utilizando el usuario `Administrator` en el dominio `THM`.

Dado que nos conectaremos a la máquina de destino a través de RDP, este también es un buen momento para iniciar AttackBox (a menos que esté usando su propia máquina).

### Responde las preguntas a continuación
- En un dominio de Windows, las credenciales se almacenan en un repositorio centralizado llamado... `Active Directory`
- El servidor encargado de ejecutar los servicios de Active Directory se llama... `Domain Controller`

## Directorio activo
El núcleo de cualquier dominio de Windows es el `Servicio de dominio de Active Directory (ADDS)`. Este servicio actúa como un catálogo que contiene la información de todos los "objetos" que existen en su red. Entre los muchos objetos admitidos por AD, tenemos usuarios, grupos, máquinas, impresoras, recursos compartidos y muchos otros. Veamos algunos de ellos:

### Usuarios
Los usuarios son uno de los tipos de objetos más comunes en Active Directory. Los usuarios son uno de los objetos conocidos como `principios de seguridad`, lo que significa que pueden ser autenticados por el dominio y se les pueden asignar *privilegios sobre recursos* como archivos o impresoras. Se podría decir que una entidad de seguridad es un objeto que puede actuar sobre los recursos de la red.

Los usuarios se pueden utilizar para representar dos tipos de entidades:

- `Personas`: los usuarios generalmente representarán a personas de su organización que necesitan acceder a la red, como los empleados.
- `Servicios`: también puede definir usuarios que utilizarán servicios como IIS o MSSQL. Cada servicio requiere un usuario para ejecutarse, pero los usuarios del servicio son diferentes de los usuarios normales ya que solo tendrán los privilegios necesarios para ejecutar su servicio específico.

### Maquinas
Las máquinas son otro tipo de objeto dentro de Active Directory; Para cada computadora que se una al dominio de Active Directory, se creará un objeto de máquina. Las máquinas también se consideran "principales de seguridad" y se les asigna una cuenta como a cualquier usuario normal. Esta cuenta tiene derechos algo limitados dentro del propio dominio.

Las cuentas de la máquina en sí son administradores locales en la computadora asignada, generalmente nadie debe acceder a ellas excepto la computadora misma, pero como con cualquier otra cuenta, si tiene la contraseña, puede usarla para iniciar sesión.

```cmd
Nota: 

  Las contraseñas de las cuentas de máquina se rotan automáticamente y generalmente 
constan de 120 caracteres aleatorios.

```

Identificar cuentas de máquinas es relativamente fácil. Siguen un esquema de nomenclatura específico. El nombre de la cuenta de la máquina es el nombre de la computadora seguido de un signo de dólar. Por ejemplo, una máquina llamada `DC01` tendrá una cuenta de máquina llamada `DC01$`.

### Grupos de seguridad
Si está familiarizado con Windows, probablemente sepa que puede definir grupos de usuarios para asignar derechos de acceso a archivos u otros recursos a grupos completos en lugar de a usuarios individuales. Esto permite una mejor capacidad de administración, ya que puede agregar usuarios a un grupo existente y estos heredarán automáticamente todos los privilegios del grupo. Los grupos de seguridad también se consideran principios de seguridad y, por lo tanto, pueden tener privilegios sobre los recursos de la red.

Los grupos pueden tener tanto usuarios como máquinas como miembros. Si es necesario, los grupos también pueden incluir otros grupos.

De forma predeterminada, se crean varios grupos en un dominio que se pueden utilizar para otorgar privilegios específicos a los usuarios. A modo de ejemplo, estos son algunos de los grupos más importantes de un dominio: 

| Grupo de Seguridad         | Descripción                                                                                    |
|----------------------------|------------------------------------------------------------------------------------------------|
| Administradores de dominio | Tienen privilegios sobre todo el dominio; administran cualquier computadora del dominio.       |
| Operadores de servidores   | Los usuarios administran controladores de dominio.                                             |
| Operadores de respaldo     | Los usuarios pueden acceder a cualquier archivo, ignorando sus permisos; (copias de seguridad) |
| Operadores de cuentas      | Los usuarios de este grupo pueden crear o modificar otras cuentas en el dominio.               |
| Usuarios de dominio        | Incluye todas las cuentas de usuario existentes en el dominio.                                 |
| Computadoras de dominio    | Incluye todas las computadoras existentes en el dominio.                                       |
| Controladores de dominio   | Incluye todos los DC existentes en el dominio.                                                 |

Puede obtener la [lista completa de grupos](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/understand-security-groups) de seguridad predeterminados en la documentación de Microsoft.

### Usuarios y computadoras de Active Directory
Para configurar usuarios, grupos o máquinas en Active Directory, debemos *iniciar sesión en el Controlador de Dominio* y ejecutar "Usuarios y Computadoras de Active Directory" desde el menú de inicio: 

<div align="center">
  <img src="/assets/images/Active-Directory/User.png">
</div>

Esto abrirá una ventana donde podrá ver la *jerarquía de usuarios*, *computadoras* y *grupos* que existen en el dominio. Estos objetos están organizados en **Unidades Organizativas (OU)**, que son objetos contenedores que le permiten clasificar usuarios y máquinas. Las unidades organizativas se utilizan principalmente para definir conjuntos de usuarios con requisitos policiales similares. Es probable que las personas del departamento de Ventas de su organización apliquen un conjunto de políticas diferente al de las personas de TI, por ejemplo. Tenga en cuenta que un usuario solo puede ser parte de una única unidad organizativa a la vez.

Revisando nuestra máquina, podemos ver que ya existe una `OU` llamada **THM** con cuatro unidades organizativas secundarias para los departamentos de *TI*, *gestión*, *marketing* y *ventas*. Es muy típico ver que las unidades organizativas imitan la estructura empresarial, ya que permiten implementar de manera eficiente políticas básicas que se aplican a departamentos completos. Recuerde que, si bien este sería el modelo esperado la mayor parte del tiempo, puede definir unidades organizativas de forma arbitraria. Siéntase libre de hacer clic derecho en `THM OU` y *cree una nueva OU* debajo de ella llamada **Students** sólo por diversión. 

<div align="center">
  <img src="/assets/images/Active-Directory/OU.png">
</div>

Si abre alguna unidad organizativa, puede ver los usuarios que contiene y realizar tareas simples como crearlas, eliminarlas o modificarlas según sea necesario. También puede restablecer las contraseñas si es necesario (muy útil para el servicio de asistencia técnica): 

<div align="center">
  <img src="/assets/images/Active-Directory/Groups.png">
</div>

Probablemente ya hayas notado que existen otros contenedores predeterminados además de THM OU . Estos contenedores los crea Windows automáticamente y contienen lo siguiente:

- `Incorporado`: contiene grupos predeterminados disponibles para cualquier host de Windows.
- `Computadoras`: cualquier máquina que se una a la red se colocará aquí de forma predeterminada. Puedes moverlos si es necesario.
- `Controladores de dominio`: predeterminada unidad organizativa que contiene los controladores de dominio en su red.
- `Usuarios`: usuarios y grupos predeterminados que se aplican a un contexto de todo el dominio.
- `Cuentas de servicios administradas`: contiene cuentas utilizadas por los servicios en su dominio de Windows. 

### Grupos de seguridad frente a unidades organizativas
Probablemente se esté preguntando por qué tenemos grupos y unidades organizativas. Si bien ambos se utilizan para clasificar usuarios y computadoras, sus propósitos son completamente diferentes:

- Las `unidades organizativas` son útiles para aplicar políticas a usuarios y computadoras, que incluyen configuraciones específicas que pertenecen a conjuntos de usuarios según su función particular en la empresa. Recuerde, un usuario sólo puede ser miembro de una única unidad organizativa a la vez, ya que no tendría sentido intentar aplicar dos conjuntos diferentes de políticas a un solo usuario.
- Los `grupos de seguridad`, por otro lado, se utilizan para otorgar permisos sobre recursos . Por ejemplo, utilizará grupos si desea permitir que algunos usuarios accedan a una carpeta compartida o a una impresora de red. Un usuario puede ser parte de muchos grupos, lo cual es necesario para otorgar acceso a múltiples recursos. 

### Responde las preguntas a continuación
- ¿Qué grupo normalmente administra todas las computadoras y recursos de un dominio? `Domain Admin`
- ¿Cuál sería el nombre de la cuenta de la máquina asociada a una máquina llamada TOM-PC? `TOM-PC$`
- Supongamos que nuestra empresa crea un nuevo departamento de Garantía de Calidad. ¿Qué tipo de contenedores deberíamos utilizar para agrupar a todos los usuarios de Garantía de Calidad de modo que se les puedan aplicar políticas de manera consistente? `organizational unit`

## Administrar usuarios en AD
Su primera tarea como nuevo administrador de dominio es verificar las unidades organizativas y los usuarios de AD existentes , ya que se han producido algunos cambios recientes en la empresa. Se le ha proporcionado el siguiente organigrama y se espera que realice cambios en el AD para que coincida con él: 

<div align="center">
  <img src="/assets/images/Active-Directory/User-AD.png">
</div>

### Eliminar unidades organizativas y usuarios adicionales
Lo primero que debe notar es que hay una unidad organizativa de departamento adicional en su configuración actual de AD que no aparece en el gráfico. Nos dijeron que estaba cerrado debido a recortes presupuestarios y que debería eliminarse del dominio. Si intenta hacer clic derecho y eliminar la unidad organizativa , obtendrá el siguiente error: 

<div align="center">
  <img src="/assets/images/Active-Directory/eliminar.png">
</div>

De forma predeterminada, las unidades organizativas están protegidas contra la eliminación accidental. Para eliminar la unidad organizativa, debemos habilitar las `funciones avanzadas` en el menú Ver: 

<div align="center">
  <img src="/assets/images/Active-Directory/Funciones-Avanzadas.png">
</div>

Esto le mostrará algunos contenedores adicionales y le permitirá desactivar la protección contra eliminación accidental. Para hacerlo, haga clic derecho en la unidad organizativa y vaya a Propiedades. Encontrará una casilla de verificación en la pestaña `Objeto` para `desactivar la protección`: 

<div align="center">
  <img src="/assets/images/Active-Directory/Protec.png">
</div>

Asegúrese de desmarcar la casilla e intente eliminar la unidad organizativa nuevamente. Se le pedirá que confirme que desea eliminar la unidad organizativa y, como resultado, también se eliminarán todos los usuarios, grupos u unidades organizativas que se encuentren bajo ella.

Después de eliminar la unidad organizativa adicional, debería notar que para algunos de los departamentos, los usuarios en el AD no coinciden con los de nuestro organigrama. Cree y elimine usuarios según sea necesario para que coincidan.

### Delegación
Una de las cosas buenas que puedes hacer en AD es dar a usuarios específicos cierto control sobre algunas unidades organizativas. Este proceso se conoce como delegación y le permite otorgar a los usuarios privilegios específicos para realizar tareas avanzadas en unidades organizativas sin necesidad de que intervenga un administrador de dominio.

Uno de los casos de uso más comunes para esto es otorgar IT support los privilegios para restablecer las contraseñas de otros usuarios con pocos privilegios. Según nuestro organigrama, Phillip está a cargo del soporte de TI, por lo que probablemente querríamos delegarle el control de restablecer contraseñas en las unidades organizativas de Ventas, Marketing y Administración.

Para este ejemplo, delegaremos el control sobre la unidad organizativa de ventas a Phillip. Para delegar el control sobre una unidad organizativa , puede hacer clic derecho en ella y seleccionar Delegar control : 

<div align="center">
  <img src="/assets/images/Active-Directory/Delegar.png">
</div>

Esto debería abrir una nueva ventana donde primero se le preguntará qué usuarios desea delegar el control:

```cmd
Nota: 

  Para evitar escribir mal el nombre del usuario, escriba "phillip" y haga clic en el botón Verificar nombres. 
  
  Windows completará automáticamente el usuario por usted.
```

<div align="center">
  <img src="/assets/images/Active-Directory/Agregar.png">
</div>

Haga clic en Aceptar y, en el siguiente paso, seleccione la siguiente opción: 

<div align="center">
  <img src="/assets/images/Active-Directory/Permisos.png">
</div>

Haga clic en Siguiente un par de veces y ahora Phillip debería poder restablecer las contraseñas de cualquier usuario del departamento de ventas. Si bien probablemente quieras repetir estos pasos para delegar el restablecimiento de contraseñas de los departamentos de Marketing y Gestión, lo dejaremos aquí para esta tarea. Eres libre de continuar configurando el resto de las unidades organizativas si así lo deseas.

Ahora usemos la cuenta de Phillip para intentar restablecer la contraseña de Sophie. Aquí están las credenciales de Phillip para que inicie sesión a través de RDP : 

<div align="center">
  <img src="/assets/images/Active-Directory/RDP-Philip.png">
</div>

**Nota:** Cuando se conecte a través de RDP, utilice `THM\phillip` como nombre de usuario para especificar que desea iniciar sesión utilizando el usuario `phillip` en el dominio `THM`.

Si bien puede tener la tentación de ir a **Usuarios y computadoras** de `Active Directory` para probar los nuevos poderes de Phillip, él realmente no tiene los privilegios para abrirlo, por lo que tendrá que usar otros métodos para restablecer la contraseña. En este caso, usaremos `Powershell` para hacerlo: 

<div align="center">
  <img src="/assets/images/Active-Directory/PowerShell.png">
</div>

Como no queremos que Sophie siga usando una contraseña que conocemos, también podemos forzar un restablecimiento de contraseña en el siguiente inicio de sesión con el siguiente comando: 

<div align="center">
  <img src="/assets/images/Active-Directory/Change-pass.png">
</div>

<div align="center">
  <img src="/assets/images/Active-Directory/Shopie.png">
</div>

**Nota:** Cuando se conecte a través de RDP, utilice `THM\sophie` como nombre de usuario para especificar que desea iniciar sesión utilizando el usuario `sophie` en el dominio `THM`.

### Responde las preguntas a continuación
- ¿Cuál fue la bandera encontrada en el escritorio de Sophie? `THM{thanks_for_contacting_support}`
- El proceso de otorgar privilegios a un usuario sobre alguna unidad organizativa u otro objeto AD se llama... `delegation`

## Administrar computadoras en AD
De forma predeterminada, todas las máquinas que se unen a un dominio (excepto los DC) se colocarán en el contenedor llamado "Computers". Si revisamos nuestro DC , veremos que algunos dispositivos ya están allí: 

<div align="center">
  <img src="/assets/images/Active-Directory/Computers.png">
</div>

Podemos ver algunos servidores, algunos portátiles y algunos PC correspondientes a los usuarios de nuestra red. Tener todos nuestros dispositivos ahí no es la mejor idea ya que es muy probable que quieras políticas diferentes para tus servidores y las máquinas que los usuarios habituales utilizan a diario.

Si bien no existe una regla de oro sobre cómo organizar sus máquinas, un excelente punto de partida es segregar los dispositivos según su uso. En general, esperaría ver dispositivos divididos en al menos las tres categorías siguientes:

1. `Estaciones de trabajo`. Las estaciones de trabajo son uno de los dispositivos más comunes dentro de un dominio de Active Directory. Es probable que cada usuario del dominio inicie sesión en una estación de trabajo. Este es el dispositivo que utilizarán para realizar su trabajo o actividades normales de navegación. Estos dispositivos nunca deberían tener un usuario privilegiado que haya iniciado sesión.

2. `Servidores`. Los servidores son el segundo dispositivo más común dentro de un dominio de Active Directory. Los servidores se utilizan generalmente para proporcionar servicios a los usuarios u otros servidores.

3. `Controladores de dominio`. Los controladores de dominio son el tercer dispositivo más común dentro de un dominio de Active Directory. Los controladores de dominio le permiten administrar el dominio de Active Directory. Estos dispositivos a menudo se consideran los más sensibles dentro de la red, ya que contienen contraseñas hash para todas las cuentas de usuario dentro del entorno.

Ya que estamos ordenando nuestro AD, creemos dos unidades organizativas separadas para `Workstations` y `Servers` (Los controladores de dominio ya están en una unidad organizativa creada por Windows). Los crearemos directamente bajo el contenedor de dominio `thm.local`. Al final, deberías tener la siguiente estructura OU:

<div align="center">
  <img src="/assets/images/Active-Directory/Estructura.png">
</div>

Ahora, mueva las computadoras personales y portátiles a la OU Servidores Estaciones de trabajo y los servidores a la OU desde el contenedor Computadoras. Hacerlo nos permitirá configurar políticas para cada OU más adelante.

### Responde las preguntas a continuación
- Después de organizar las computadoras disponibles, ¿cuántas terminaron en la unidad organizativa Estaciones de trabajo? `7`
- ¿Es recomendable crear unidades organizativas separadas para servidores y estaciones de trabajo? (sí/no) `Si`

## Políticas de grupo
Hasta ahora, hemos organizado usuarios y computadoras en unidades organizativas simplemente porque sí, pero la idea principal detrás de esto es poder implementar diferentes políticas para cada unidad organizativa individualmente. De esa manera, podemos ofrecer diferentes configuraciones y líneas base de seguridad a los usuarios según su departamento.

Windows administra dichas políticas a través de `objetos de política de grupo (GPO)`. Los GPO son simplemente una *colección de configuraciones* que se pueden aplicar a las unidades organizativas. Los GPO pueden contener políticas dirigidas a usuarios o computadoras, lo que le permite establecer una línea de base en máquinas e identidades específicas.

Para configurar GPO, puede utilizar la herramienta de **administración de políticas de grupo**, disponible en el menú de inicio:

<div align="center">
  <img src="/assets/images/Active-Directory/Politica.png">
</div>

Lo primero que verá al abrirlo es su jerarquía OU completa, como se definió anteriormente. Para configurar las políticas de grupo, primero cree un GPO en Objetos de política de grupo y luego vincúlelo a la unidad organizativa donde desea que se apliquen las políticas. Como ejemplo, puede ver que ya existen algunos GPO en su máquina: 

<div align="center">
  <img src="/assets/images/Active-Directory/GPO.png">
</div>

Podemos ver en la imagen de arriba que se han creado `3 GPO`. De esos, el `Default Domain Policy` y `RDP Policy` están vinculados al dominio `thm.local` en su conjunto, y el `Default Domain Controllers Policy` está vinculado a la `Domain Controllers` Sólo unidad organizativa . Algo importante a tener en cuenta es que cualquier GPO se aplicará a la unidad organizativa vinculada y a cualquier subunidad organizativa que se encuentre debajo de ella. Por ejemplo, el `Sales OU` seguirá estando afectada por el `Default Domain Policy`.

Examinemos el `Default Domain Policy` para ver qué hay dentro de un GPO. La primera pestaña que verá al seleccionar un GPO muestra su alcance , que es donde está vinculado el GPO en el AD . Para la política actual, podemos ver que solo se ha vinculado al dominio `thm.local`:

<div align="center">
  <img src="/assets/images/Active-Directory/Scope.png">
</div>

Como puede ver, también puede aplicar filtrado de seguridad a los GPO para que solo se apliquen a *usuarios/computadoras específicas* bajo una unidad organizativa. De forma predeterminada, se aplicarán al grupo Usuarios autenticados, que incluye a todos los usuarios/PC.

La pestaña **Configuración** incluye el contenido real del GPO y nos permite saber qué configuraciones específicas aplica. Como se indicó anteriormente, cada GPO tiene configuraciones que se aplican solo a computadoras y configuraciones que se aplican solo a usuarios. En este caso, el *Default Domain Policy* solo contiene configuraciones de computadora: 

<div align="center">
  <img src="/assets/images/Active-Directory/Setting.png">
</div>

Siéntase libre de explorar el `GPO` y ampliar los elementos disponibles utilizando los enlaces "mostrar" en el lado derecho de cada configuración. En este caso, el *Default Domain Policy* indica configuraciones realmente básicas que deberían aplicarse a la mayoría de los dominios, incluidas las políticas de bloqueo de cuentas y contraseñas: 

<div align="center">
  <img src="/assets/images/Active-Directory/Config.png">
</div>

Dado que este GPO se aplica a todo el dominio, cualquier cambio afectaría a todas las computadoras. Cambiemos la política de longitud mínima de contraseña para exigir que los usuarios tengan al menos 10 caracteres en sus contraseñas. Para hacer esto, haga clic derecho en el GPO y seleccione `Editar`:

<div align="center">
  <img src="/assets/images/Active-Directory/Edit.png">
</div>

Esto abrirá una nueva ventana donde podremos navegar y editar todas las configuraciones disponibles. Para cambiar la longitud mínima de la contraseña, vaya a `Computer Configurations -> Policies -> Windows Setting -> Security Settings -> Account Policies -> Password Policy` y cambie el valor de política requerido:

<div align="center">
  <img src="/assets/images/Active-Directory/Politica-Pass.png">
</div>

Como puedes ver, en una GPO se pueden establecer multitud de políticas . Si bien explicar cada una de ellas sería imposible en una sola sala, siéntete libre de explorar un poco, ya que algunas de las políticas son sencillas. Si necesita más información sobre alguna de las políticas, puede hacer doble clic en ellas y leer la pestaña Explicar de cada una de ellas: 

<div align="center">
  <img src="/assets/images/Active-Directory/Explicar.png">
</div>

### Distribución de GPO
Los GPO se distribuyen a la red a través de un *recurso compartido* de red llamado `SYSVOL`, que se almacena en el `DC`. Normalmente, todos los usuarios de un dominio deberían tener acceso a este recurso compartido a través de la red para sincronizar sus GPO periódicamente. El recurso compartido SYSVOL apunta por defecto al `C:\Windows\SYSVOL\sysvol\` directorio en cada uno de los DC de nuestra red.

Una vez que se ha realizado un cambio en cualquier GPO, las computadoras pueden tardar hasta 2 horas en ponerse al día. Si desea forzar a una computadora en particular a sincronizar sus GPO inmediatamente, siempre puede ejecutar el siguiente comando en la computadora deseada: 

<div align="center">
  <img src="/assets/images/Active-Directory/Force.png">
</div>

### Creando algunos GPO para THM Inc.
Como parte de nuestro nuevo trabajo, se nos ha encomendado la tarea de implementar algunos GPO que nos permitan:

- Bloquee el acceso al Panel de control a usuarios que no sean de TI.
- Haga que las estaciones de trabajo y los servidores bloqueen su pantalla automáticamente después de 5 minutos de inactividad del usuario para evitar que las personas dejen sus sesiones expuestas.

Centrémonos en cada uno de ellos y definamos qué políticas debemos habilitar en cada GPO y dónde deben vincularse.

1. `Restringir el acceso al panel de control`. Queremos restringir el acceso al Panel de control en todas las máquinas solo a los usuarios que forman parte del departamento de TI. Los usuarios de otros departamentos no deberían poder cambiar las preferencias del sistema.

Creemos un *nuevo GPO* llamado `Restrict Control Panel Access` y ábrelo para editarlo. Como queremos que este GPO se aplique a usuarios específicos, buscaremos en **User Configuration** para la siguiente póliza: 

<div align="center">
  <img src="/assets/images/Active-Directory/Panel-Control.png">
</div>

Tenga en cuenta que hemos habilitado la política `Prohibir el acceso al panel de control` y a la `configuración de la PC`.

Una vez configurado el GPO, necesitaremos vincularlo a todas las cuentas OU correspondientes a usuarios que no deberían tener acceso al Panel de Control de sus PC. En este caso vincularemos el Marketing, Management y Sales OU arrastrando el GPO a cada una de ellas: 

<div align="center">
  <img src="/assets/images/Active-Directory/Restriccion.png">
</div>

### bloqueo de pantalla automático GPO
Para el primer GPO, relacionado con el bloqueo de pantalla para estaciones de trabajo y servidores, podríamos aplicarlo directamente sobre `Workstations`, `Servers` y `Domain Controllers OU` que creamos anteriormente.

Si bien esta solución debería funcionar, una alternativa consiste en simplemente `aplicar el GPO al dominio raíz`, ya que queremos que el GPO afecte a todos nuestros ordenadores. Desde el `Workstations`, `Servers` y `Domain Controllers` Todas las unidades organizativas son unidades organizativas secundarias del dominio raíz y heredarán sus políticas.

```cmd
Nota: 

  Es posible que observe que si nuestro GPO se aplica al dominio raíz, también lo heredarán 
otras unidades organizativas como Sales o Marketing.

Cualquier configuración de computadora en nuestro GPO . Dado que estas unidades organizativas contienen solo usuarios, ignorarán.
```

Creemos un nuevo GPO, llámelo `Auto Lock Screeny` edítelo. La política para lograr lo que queremos se ubica en la siguiente ruta: 

<div align="center">
  <img src="/assets/images/Active-Directory/Auto-Look.png">
</div>

Estableceremos el *límite de inactividad en 5 minutos* para que los ordenadores se bloqueen automáticamente si algún usuario deja su sesión abierta. Después de cerrar el editor de GPO, vincularemos el GPO al dominio raíz arrastrándolo hacia él : 

<div align="center">
  <img src="/assets/images/Active-Directory/Auto-Look-2.png">
</div>

Una vez que los GPO se hayan aplicado a las unidades organizativas correctas, podemos iniciar sesión como cualquier usuario en Marketing, Ventas o Administración para su verificación. Para esta tarea, conectemos vía RDP usando las credenciales de Mark: 

<div align="center">
  <img src="/assets/images/Active-Directory/RDP-MARK.png">
</div>

**Nota:** Cuando se conecte a través de RDP, utilice `THM\Mark` como nombre de usuario para especificar que desea iniciar sesión utilizando el usuario `Mark` en el dominio `THM`.

Si intentamos abrir el *Panel de control*, deberíamos recibir un mensaje indicando que el administrador rechaza esta operación. También puedes esperar 5 minutos para comprobar si la pantalla se bloquea automáticamente si lo deseas.

Dado que no aplicamos el GPO del panel de control en TI, aún debería poder iniciar sesión en la máquina como cualquiera de esos usuarios y acceder al panel de control.

```cmd
Nota:

  Si creó y vinculó los GPO, pero por alguna razón todavía no funcionan, recuerde que puede 
ejecutar gpupdate /force para forzar la actualización de los GPO.
```

### Responde las preguntas a continuación
- ¿Cuál es el nombre del recurso compartido de red utilizado para distribuir GPO a máquinas de dominio? `sysvol`
- ¿Se puede utilizar un GPO para aplicar configuraciones a usuarios y computadoras? (sí/no) `Sí`

## Métodos de autenticación
Cuando se utilizan dominios de Windows, todas las credenciales se almacenan en los controladores de dominio. Siempre que un usuario intente autenticarse en un servicio utilizando credenciales de dominio, el servicio deberá solicitarle al controlador de dominio que verifique si son correctas. Se pueden utilizar dos protocolos para la autenticación de red en dominios de Windows:

- `Kerberos`: Utilizado por cualquier versión reciente de Windows. Este es el protocolo predeterminado en cualquier dominio reciente.
- `NetNTLM`: Protocolo de autenticación heredado que se mantiene por motivos de compatibilidad. 

Si bien **NetNTLM** debería considerarse obsoleto, la mayoría de las redes tendrán ambos protocolos habilitados. Echemos un vistazo más profundo a cómo funciona cada uno de estos protocolos.

### Kerberos Autenticación
Es el protocolo de autenticación predeterminado para cualquier versión reciente de Windows. A los usuarios que inicien sesión en un servicio utilizando Kerberos se les asignarán *tickets*. Piensa en los billetes como prueba de una autenticación previa. Los usuarios con boletos pueden presentarlos a un servicio para demostrar que ya se han autenticado en la red anteriormente y, por lo tanto, están habilitados para usarlo.

1. Cuando se utiliza Kerberos para la autenticación, ocurre el siguiente proceso:

El usuario envía su nombre de usuario y una marca de tiempo cifrada mediante una clave derivada de su contraseña al Centro de distribución de claves (KDC), un servicio normalmente instalado en el controlador de dominio encargado de crear tickets Kerberos en la red.

El KDC creará y devolverá un Boleto de concesión de boletos (TGT), que permitirá al usuario solicitar boletos adicionales para acceder a servicios específicos. La necesidad de un ticket para obtener más tickets puede parecer un poco extraña, pero permite a los usuarios solicitar tickets de servicio sin pasar sus credenciales cada vez que quieran conectarse a un servicio. Junto con el TGT, se le entrega al usuario una clave de sesión , que necesitará para generar las siguientes solicitudes.

Observe que el TGT está cifrado utilizando el hash de contraseña de la cuenta krbtgt y, por lo tanto, el usuario no puede acceder a su contenido. Es esencial saber que el TGT cifrado incluye una copia de la clave de sesión como parte de su contenido, y el KDC no necesita almacenar la clave de sesión, ya que puede recuperar una copia descifrando el TGT si es necesario. 

<div align="center">
  <img src="/assets/images/Active-Directory/TGT.png">
</div>

2. Cuando un usuario desea conectarse a un servicio en la red, como un recurso compartido, un sitio web o una base de datos, utilizará su TGT para solicitar al KDC un Servicio de concesión de boletos (TGS) . Los TGS son boletos que permiten la conexión únicamente al servicio específico para el que fueron creados. Para solicitar un TGS, el usuario enviará su nombre de usuario y una marca de tiempo encriptada usando la Clave de Sesión, junto con el TGT y un Nombre Principal del Servicio (SPN), que indica el servicio y el nombre del servidor al que pretendemos acceder.

Como resultado, el KDC nos enviará un TGS junto con una clave de sesión de servicio , que necesitaremos para autenticarnos en el servicio al que queremos acceder. El TGS se cifra utilizando una clave derivada del Hash del propietario del servicio . El propietario del servicio es el usuario o la cuenta de máquina bajo la cual se ejecuta el servicio. El TGS contiene una copia de la Clave de sesión del servicio en su contenido cifrado para que el Propietario del servicio pueda acceder a ella descifrando el TGS. 

<div align="center">
  <img src="/assets/images/Active-Directory/TGS.png">
</div>

3. Luego, el TGS se puede enviar al servicio deseado para autenticar y establecer una conexión. El servicio utilizará el hash de contraseña de su cuenta configurada para descifrar el TGS y validar la clave de sesión del servicio. 

<div align="center">
  <img src="/assets/images/Active-Directory/SRV.png">
</div>

### Autenticación NetNTLM
NetNTLM funciona mediante un mecanismo de desafío-respuesta. Todo el proceso es el siguiente: 

<div align="center">
  <img src="/assets/images/Active-Directory/NET.png">
</div>


1. El cliente envía una solicitud de autenticación al servidor al que desea acceder.
2. El servidor genera un número aleatorio y lo envía como desafío al cliente.
3. El cliente combina su hash de contraseña NTLM con el desafío (y otros datos conocidos) para generar una respuesta al desafío y la envía de regreso al servidor para su verificación.
4. El servidor envía el desafío y la respuesta al controlador de dominio para su verificación.
5. El controlador de dominio utiliza el desafío para recalcular la respuesta y la compara con la respuesta original enviada por el cliente. Si ambos coinciden, el cliente queda autenticado; de lo contrario, se deniega el acceso. El resultado de la autenticación se envía de vuelta al servidor.
6. El servidor envía el resultado de la autenticación al cliente. 

Tenga en cuenta que la contraseña (o hash) del usuario nunca se transmite a través de la red por motivos de seguridad.

```cmd
Nota: 

  El proceso descrito se aplica cuando se utiliza una cuenta de dominio. Si se utiliza una 
cuenta local, el servidor puede verificar la respuesta al desafío sin necesidad de interacción 
con el controlador de dominio, ya que tiene el hash de contraseña almacenado localmente en su SAM.
```

### Responde las preguntas a continuación
- ¿La versión actual de Windows utilizará NetNTLM como protocolo de autenticación preferido de forma predeterminada? (sí/no) `nay`
- En cuanto a Kerberos, ¿qué tipo de ticket nos permite solicitar más tickets conocidos como TGS? `Ticket Granting Ticket`
- Cuando se utiliza NetNTLM, ¿se transmite la contraseña de un usuario a través de la red en algún momento? (sí/no) `nay`

## Trees, Forests and Trusts
Hasta ahora, hemos discutido cómo administrar un único dominio, el rol de un Controlador de Dominio y cómo une computadoras, servidores y usuarios. 

<div align="center">
  <img src="/assets/images/Active-Directory/DC-ROOT.png">
</div>

A medida que las empresas crecen, también lo hacen sus redes. Tener un único dominio para una empresa es suficiente para empezar, pero con el tiempo algunas necesidades adicionales pueden llevarte a tener más de uno.

### Trees
Imagina, por ejemplo, que de repente tu empresa se expande a un nuevo país. El nuevo país tiene diferentes leyes y regulaciones que requieren que usted actualice sus GPO para cumplirlas. Además, ahora tienes personal de TI en ambos países, y cada equipo de TI necesita gestionar los recursos que corresponden a cada país sin interferir con el otro equipo. Si bien se puede crear una estructura OU compleja y utilizar delegaciones para lograrlo, tener una estructura AD enorme puede ser difícil de administrar y propenso a errores humanos.

Afortunadamente para nosotros, Active Directory admite la integración de múltiples dominios para que pueda dividir su red en unidades que se puedan administrar de forma independiente. Si tiene dos dominios que comparten el mismo espacio de nombres (`thm.local` en nuestro ejemplo), esos dominios se pueden unir en un **Árbol**.

Si nuestro dominio `thm.local` se dividió en dos subdominios para las sucursales del Reino Unido y EE. UU., podría crear un árbol con un dominio raíz de `thm.local` y dos subdominios llamados `uk.thm.local` y `us.thm.local`, cada uno con su AD, computadoras y usuarios: 

<div align="center">
  <img src="/assets/images/Active-Directory/Sub-AD.png">
</div>

Esta estructura particionada nos brinda un mejor control sobre quién puede acceder a qué en el dominio. El personal de TI del Reino Unido tendrá su propio DC que gestionará únicamente los recursos del Reino Unido. Por ejemplo, un usuario del Reino Unido no podría gestionar usuarios de EE. UU. De esa manera, los Administradores de Dominio de cada sucursal tendrán control total sobre sus respectivos DC, pero no sobre los DC de otras sucursales. Las políticas también se pueden configurar de forma independiente para cada dominio del árbol.

Es necesario introducir un nuevo grupo de seguridad cuando se habla de árboles y bosques. El grupo de administradores empresariales otorgará a un usuario privilegios administrativos sobre todos los dominios de una empresa. Cada dominio todavía tendría sus administradores de dominio con privilegios de administrador sobre sus dominios individuales y los administradores empresariales que pueden controlar todo en la empresa. 

### Forests
Los dominios que administra también se pueden configurar en diferentes espacios de nombres. Supongamos que su empresa continúa creciendo y eventualmente adquiere otra empresa llamada `MHT Inc.` Cuando ambas empresas se fusionen, probablemente tendrá árboles de dominio diferentes para cada empresa, cada uno administrado por su propio departamento de TI. A la unión de varios árboles con distintos namespaces en una misma red se le conoce como bosque . 

<div align="center">
  <img src="/assets/images/Active-Directory/Bosque-AD.png">
</div>

### Trust Relationships
Tener múltiples dominios organizados en árboles y bosques le permite tener una buena red compartimentada en términos de gestión y recursos. Pero, en cierto momento, es posible que un usuario de THM UK necesite acceder a un archivo compartido en uno de los servidores de MHT ASIA. Para que esto suceda, los dominios dispuestos en árboles y bosques se unen mediante relaciones de confianza .

En términos simples, tener una relación de confianza entre dominios le permite autorizar a un usuario desde el dominio. `THM UK` para acceder a recursos desde el dominio `MHT EU`.

La relación de confianza más simple que se puede establecer es una **relación de confianza unidireccional**. En una confianza unidireccional, si `Domain AAA` fideicomisos `Domain BBB`, esto significa que un *usuario en BBB* puede tener autorización para acceder a *recursos en AAA*: 

<div align="center">
  <img src="/assets/images/Active-Directory/Bi-direccion.png">
</div>

La dirección de la relación de confianza unidireccional es contraria a la de la dirección de acceso.

También se pueden **establecer relaciones de confianza bidireccionales** para permitir que ambos dominios autoricen mutuamente a los usuarios del otro. De forma predeterminada, unir varios dominios bajo un árbol o bosque formará una relación de confianza bidireccional.

Es importante tener en cuenta que tener una relación de confianza entre dominios no otorga automáticamente acceso a todos los recursos de otros dominios. Una vez que se establece una relación de confianza, usted tiene la posibilidad de autorizar usuarios en diferentes dominios, pero depende de usted qué está realmente autorizado o no.

### Responde las preguntas a continuación
- ¿Cómo se llama un grupo de dominios de Windows que comparten el mismo espacio de nombres? `Tree`
- ¿Qué se debe configurar entre dos dominios para que un usuario del Dominio A acceda a un recurso del Dominio B? `A Trust Relationship`

## Conclusión
En esta sala hemos mostrado los componentes y conceptos básicos relacionados con Active Directories y Dominios de Windows. Tenga en cuenta que esta sala sólo debe servir como una introducción a los conceptos básicos, ya que hay mucho más que explorar para implementar un entorno Active Directory listo para producción.

Si está interesado en aprender cómo proteger una instalación de Active Directory, asegúrese de consultar la Sala de refuerzo de Active Directory (que se lanzará próximamente). Si, por otro lado, desea saber cómo los atacantes pueden aprovechar las configuraciones erróneas comunes de AD y otras técnicas de piratería de AD, el módulo [Compromering Active Directory](https://tryhackme.com/module/hacking-active-directory) es el camino a seguir.

### Responde las preguntas a continuación
- ¡Haz clic y continúa aprendiendo! 