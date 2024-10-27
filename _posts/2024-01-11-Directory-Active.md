---
layout: single
title: Conceptos básicos de Directorio Activo
excerpt: "Esta sala presentará los conceptos básicos y la funcionalidad proporcionada por Active Directory."
date: 2024-10-11
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

