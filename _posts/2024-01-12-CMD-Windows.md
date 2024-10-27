---
layout: single
title: Línea de comando de Windows
excerpt: "Aprenda los comandos esenciales de Windows."
date: 2024-10-11
classes: wide
header:
  teaser: /assets/images/
  teaser_home_page: true
categories:
  - Ciberseguridad 101
tags:
  - Sección 4
  - Windows
  - Línea de Comandos
---

![Portada](assets/images/)

## Introducción

<div align="center">
  <img src="/assets/images/CMD/Terminal.png">
</div>

Todo el mundo prefiere una *interfaz gráfica de usuario (GUI)* hasta que domine una *interfaz de línea de comandos (CLI)*. Hay muchas razones para ello; una razón es que las GUI suelen ser intuitivas. Si alguien le ofrece una interfaz GUI con la que no está familiarizado, puede hurgar rápidamente y descubrir una parte no trivial. Compare esto con tratar con una CLI, es decir, un mensaje.

Las interfaces CLI suelen tener una curva de aprendizaje; sin embargo, a medida que domines la línea de comandos, la encontrarás más rápida y eficiente. Considere este ejemplo trivial: ¿Cuántos clics necesita para encontrar su dirección IP utilizando el escritorio gráfico? Al utilizar la interfaz de línea de comandos, ni siquiera necesita levantar las manos del teclado. Digamos que desea volver a verificar su dirección IP. Debe emitir el mismo comando en lugar de mover el puntero del mouse a cada rincón de la pantalla.

Existen muchas otras ventajas al utilizar una CLI además de la velocidad y la eficiencia. Mencionaremos algunos:

- `Menor uso de recursos`: las CLI requieren menos recursos del sistema que las GUI con uso intensivo de gráficos. En otras palabras, puede ejecutar su sistema CLI en hardware o sistemas antiguos con memoria limitada. Si utiliza la computación en la nube, su sistema requerirá menos recursos, lo que a su vez reducirá su factura.
- `Automatización`: si bien puede automatizar las tareas de la GUI, es mucho más fácil crear un archivo por lotes o un script con los comandos que necesita repetir.
- `Administración remota`: CLI hace que sea muy conveniente usar SSH para administrar un sistema remoto, como un servidor, un enrutador o un IoT dispositivo . Este enfoque funciona bien en velocidades de red lentas y sistemas con recursos limitados.

### Objetivos de aprendizaje
El propósito de esta sala es enseñarle cómo usar el símbolo del sistema de MS Windows `cmd.exe`, el intérprete de línea de comandos predeterminado en el entorno Windows. Aprenderemos a utilizar la línea de comando para:

- Mostrar información básica del sistema
- Verificar y solucionar problemas de configuración de red
- Administrar archivos y carpetas
- Verificar procesos en ejecución

### Requisitos previos de la habitación

Antes de comenzar esta sala, debería haber terminado el de [módulo Fundamentos Windows y AD](https://tryhackme.com/module/windows-and-active-directory-fundamentals). Presione el botón Iniciar máquina a continuación.

<div align="center">
  <img src="/assets/images/CMD/Iniciar.png">
</div>

Inicie AttackBox presionando el botón `Iniciar AttackBox` en la parte superior de esta página. La máquina AttackBox se iniciará en la vista de pantalla dividida. Si no está visible, use el botón azul Mostrar vista dividida en la parte superior de la página.

Puede utilizar el cliente SSH en AttackBox para conectarse a 127.0.0.1 con las siguientes credenciales:

- `Nombre de usuario`: user
- `Contraseña`: Tryhackme123!

### Estableciendo una conexión SSH desde AttackBox
Si esta es la primera vez que inicia una `conexión SSH` desde AttackBox a un sistema de destino, los pasos se muestran en la captura de pantalla a continuación y son los siguientes:

1. Inicie el terminal de AttackBox haciendo clic en el icono del terminal marcado con 1.
2. Para conectarse a la máquina virtual de destino, emita el comando `ssh user@127.0.0.1` como **user** es el nombre de usuario en este caso.
3. Como es la primera vez que se conecta a esta máquina virtual de destino, se le pedirá que confíe en esta conexión. Responda sí como está marcado con 3.
4. Introduce tu contraseña `Tryhackme123!`. Tenga en cuenta que la contraseña no aparecerá cuando la escriba.

<div align="center">
  <img src="/assets/images/CMD/SSH-AttackBox.png">
</div>

### Responde las preguntas a continuación
- ¿Cuál es el intérprete de línea de comando predeterminado en el entorno Windows? `cmd.exe`

## Información básica del sistema

<div align="center">
  <img src="/assets/images/CMD/Hello.png">
</div>

Antes de emitir comandos, debemos tener en cuenta que solo podemos emitir comandos dentro de la ruta de Windows. Puedes emitir el comando `set` para verificar su ruta desde la línea de comando. La salida del terminal a continuación muestra la ruta donde MS Windows ejecutará los comandos, como lo indica la línea que comienza con `Path=`.

<div align="center">
  <img src="/assets/images/CMD/Set.png.png">
</div>

usemos el comando ver para determinar la versión del sistema operativo (OS). El siguiente terminal muestra un ejemplo de salida. 

<div align="center">
  <img src="/assets/images/CMD/ver.png">
</div>

Basta de calentamiento. Descubramos información más detallada sobre el sistema. Podemos ejecutar el comando `systeminfo` para enumerar diversa información sobre el sistema, como información del sistema operativo , detalles del sistema, procesador y memoria. La siguiente terminal muestra un fragmento del resultado mostrado. 

<div align="center">
  <img src="/assets/images/CMD/Systeminfo.png">
</div>

Antes de continuar, es bueno mencionar un par de trucos.

Primero, puedes canalizar `more` si la salida es demasiado larga. Luego, podrá verlo página tras página presionando el botón de la *barra espaciadora*. Para demostrar esto, intente ejecutar `driverquery` y compararlo con correr `driverquery | more`. En este último, puede mostrar la salida página por página y puede salir usando `CTRL + C`.

- `help` - Proporciona información de ayuda para un comando específico.
- `cls`  - Borra la pantalla del símbolo del sistema.

### Responde las preguntas a continuación
- ¿Cuál es la versión del sistema operativo de la máquina virtual de Windows? `10.0.20348.2655`
- ¿Cuál es el nombre de host de la máquina virtual de Windows? `WINSRV2022-CORE`

## Solución de problemas de red
La mayoría de nosotros estamos acostumbrados a buscar la *configuración de red* de MS Windows desde la interfaz GUI. La interfaz de línea de comandos proporciona muchos comandos relacionados con la red para buscar su configuración actual, verificar las conexiones en curso y solucionar problemas de red.

### Configuración de red
Puede verificar la información de su red usando `ipconfig`. La salida del terminal a continuación muestra nuestra dirección IP, máscara de subred y puerta de enlace predeterminada. 

<div align="center">
  <img src="/assets/images/CMD/Ipconfig.png">
</div>

También puedes usar `ipconfig /all` para obtener más información sobre la configuración de su red. Como se muestra en la terminal a continuación, podemos ver nuestros servidores DNS y confirmar que DHCP está habilitado.

<div align="center">
  <img src="/assets/images/CMD/Ipconfig-all.png">
</div>

### Solución de problemas de red
Una tarea común de solución de problemas es verificar si el servidor puede acceder a un servidor en particular en Internet. La sintaxis del comando es `ping example.com`. Inspirándonos en el ping-pong, enviamos un *paquete ICMP específico* y escuchamos una respuesta. Si se recibe una respuesta, sabemos que podemos alcanzar el objetivo y que el objetivo puede alcanzarnos a nosotros.

Averigüemos si llegamos `example.com`. En el resultado del terminal a continuación, podemos ver que hemos recibido cuatro respuestas con éxito. Además, obtuvimos algunas estadísticas; por ejemplo, el tiempo medio de ida y vuelta es de **78 milisegundos**. 

<div align="center">
  <img src="/assets/images/CMD/ping-example.png">
</div>

Otra herramienta valiosa para la resolución de problemas es `tracert` *(ruta de seguimiento)*. El comando `tracert example.com` rastrea la ruta de la red atravesada para llegar al objetivo. Sin entrar en más detalles, espera que los enrutadores en la ruta nos notifiquen si descartan un paquete porque su tiempo de vida (TTL) ha llegado a cero. El resultado del terminal a continuación muestra que pasamos por *15 enrutadores* antes de alcanzar nuestro objetivo. 

<div align="center">
  <img src="/assets/images/CMD/tracert-example.png">
</div>

### Más comandos de red
Un comando de red que vale la pena conocer es `nslookup`. Busca un host o dominio y *devuelve su dirección IP*. la sintaxis `nslookup example.com` mirará hacia arriba utilizando el servidor de nombres predeterminado; sin embargo, `nslookup example.com 1.1.1.1` utilizará el servidor de nombres de cloudflare. La siguiente terminal muestra el resultado de ambos comandos. Los resultados son idénticos; sin embargo, puede ver que las respuestas se recuperaron de diferentes servidores de nombres. 

<div align="center">
  <img src="/assets/images/CMD/nslookup-example.png">
</div>

<div align="center">
  <img src="/assets/images/CMD/nslookup-example-2.png">
</div>

El último comando de red que cubriremos en esta sala es `netstat`. Este comando muestra las conexiones de red actuales y los puertos de escucha. Un comando *básico netstat* sin argumentos le mostrará las conexiones establecidas, como se muestra a continuación. En este caso sólo disponemos de una SSH conexión ; descubrimos que es SSH porque está vinculado al puerto 22. 

<div align="center">
  <img src="/assets/images/CMD/netstat.png">
</div>

Si tiene curiosidad acerca de las otras opciones, puede ejecutar `netstat -h`, dónde `-h` muestra la página de ayuda. Optamos por las siguientes opciones:

- `-a`: muestra todas las conexiones establecidas y puertos de escucha
- `-b`: muestra el programa asociado a cada puerto de escucha y conexión establecida
- `-o`: revela el ID del proceso ( PID ) asociado con la conexión
- `-n`: utiliza una forma numérica para direcciones y números de puerto

Combinamos estas cuatro opciones y ejecutamos el `netstat -abon example.com`. El resultado es bastante largo, pero mostramos las primeras líneas en la terminal a continuación. Ahora está claro que el ejecutable `sshd.exe` es responsable de escuchar las conexiones entrantes en el puerto 22, como se muestra en la primera línea. También podemos ver el ID de proceso (PID) asociado a cada conexión.

<div align="center">
  <img src="/assets/images/CMD/netstat-2.png">
</div>

### Responde las preguntas a continuación
- ¿Qué comando podemos usar para buscar la dirección física del servidor (dirección MAC)? `ipconfig /all`
- ¿Cuál es el nombre del proceso que escucha en el puerto 3389? `TermService`
- ¿Cuál es la dirección IP de su puerta de enlace? `10.10.0.1`

## Gestión de archivos y discos
Ha aprendido a buscar información básica del sistema y comprobar la configuración de la red. Ahora, descubramos cómo navegar por los directorios y mover archivos.

### Trabajar con directorios
Puedes usar `cd` sin parámetros para mostrar la unidad y el directorio actuales. Es el equivalente a preguntarle al sistema ¿dónde estoy?

<div align="center">
  <img src="/assets/images/CMD/cd.png">
</div>

Puede ver los directorios secundarios usando `dir`. 

<div align="center">
  <img src="/assets/images/CMD/dir.png">
</div>

Tenga en cuenta que puede utilizar las siguientes opciones con `dir`:

- `dir /a`: Muestra archivos ocultos y del sistema también.
- `dir /s`: Muestra archivos en el directorio actual y todos los subdirectorios.

Puedes escribir `tree` para representar visualmente los directorios y subdirectorios secundarios. 

<div align="center">
  <img src="/assets/images/CMD/Tree.png">
</div>

Puede cambiar a cualquier directorio usando el comando `cd directory`; Esto equivale a hacer doble clic en el directory en tu escritorio. Además, puedes utilizar `cd ..` para subir un nivel. Se muestra un ejemplo en la salida del terminal a continuación. 

<div align="center">
  <img src="/assets/images/CMD/cd-2.png">
</div>

Para crear un directorio, utilice `mkdir directory_name`; **mkdir (crear directorio)**. Para eliminar un directorio, utilice `rmdir directory_name`; `rmdir (eliminar directorio)`. La siguiente salida del terminal muestra la creación y eliminación de un directorio. 

<div align="center">
  <img src="/assets/images/CMD/mkdir.png">
</div>

<div align="center">
  <img src="/assets/images/CMD/rmdir.png">
</div>

### Trabajar con archivos
Estás trabajando con la línea de comando. Tiene curiosidad sobre el contenido de un archivo de texto en particular.

Puede ver fácilmente archivos de texto con el comando `type`. Este comando volcará el contenido del archivo de texto en la pantalla; esto es conveniente para archivos que caben en la ventana de su terminal.

Quizás quieras considerar `more` para archivos de texto más largos. Este comando mostrará suficiente contenido de archivo de texto para llenar la ventana de su terminal. En otras palabras, para archivos de texto largos, *more* mostrará una sola página y esperará a que presione Spacebar moverse una página (voltear la página) o Enter para moverse una línea.

El comando `copy` permite copiar archivos de una ubicación a otra. La siguiente salida del terminal proporciona un ejemplo. 

<div align="center">
  <img src="/assets/images/CMD/copy.png">
</div>

De manera similar, puede mover archivos usando el comando `move`. Se muestra un ejemplo en la salida del terminal a continuación. 

<div align="center">
  <img src="/assets/images/CMD/move.png">
</div>

Finalmente, podemos eliminar un archivo usando `del` o `erase`.

<div align="center">
  <img src="/assets/images/CMD/erase.png">
</div>

Podemos utilizar el carácter `comodín (*)` para hacer referencia a varios archivos. Por ejemplo, `copy *.md C:\Markdown` Copiará todos los archivos con la extensión `.md` al directorio `C:\Markdown`.

### Responde las preguntas a continuación
- ¿Cuál es el contenido del archivo en C:\Treasure\Hunt? `THM{CLI_POWER}`

## Gestión de tareas y procesos
Debe estar familiarizado con el Administrador de tareas de MS Windows y es posible que esté familiarizado con la eliminación de procesos que no responden. Descubramos cómo lograr una funcionalidad similar usando la línea de comando.

Podemos enumerar los procesos en ejecución usando `tasklist`.

<div align="center">
  <img src="/assets/images/CMD/tasklist.png">
</div>

Algunos filtros son útiles porque se espera que el resultado sea muy largo. Puede consultar todos los filtros disponibles mostrando la página de ayuda usando `tasklist /?`. Digamos que queremos buscar tareas relacionadas con `sshd.exe`, podemos hacerlo con el comando `tasklist /FI "imagename eq sshd.exe`". Tenga en cuenta que `/FI` se utiliza para establecer que el nombre de la imagen del filtro sea igual `sshd.exe`. 

<div align="center">
  <img src="/assets/images/CMD/tasklist-FI.png">
</div>

Con el ID del proceso (PID) conocido, podemos finalizar cualquier tarea usando `taskkill /PID target_pid`. Por ejemplo, si queremos matar el proceso con *PID 4567*, emitiríamos el comando `taskkill /PID 4567`.

### Responde las preguntas a continuación
- ¿Qué comando usaría para encontrar los procesos en ejecución relacionados con notepad.exe? `tasklist /FI "imagename eq notepad.exe"`
- ¿Qué comando puedes usar para finalizar el proceso con PID 1516? `taskkill /PID 1516`

## Conclusión
En esta sala, nos centramos en los comandos más prácticos para acceder a un sistema en red a través de la línea de comandos. Omitimos intencionalmente algunos comandos comunes porque no vimos un valor real para incluirlos en una sala para principiantes. Los mencionamos a continuación para que sepas que la línea de comando se puede utilizar para otras tareas.

- `chkdsk`: comprueba el sistema de archivos y los volúmenes del disco en busca de errores y sectores defectuosos.
- `driverquery`: muestra una lista de controladores de dispositivos instalados.
- `sfc /scannow`: analiza los archivos del sistema en busca de daños y los repara si es posible.

Es importante recordar todos los comandos cubiertos en las tareas anteriores; además, es igualmente importante saber que `/?` se puede utilizar con la mayoría de los comandos para mostrar una página de ayuda.

En esta sala, usamos el comando `more` de dos maneras:

- Mostrar archivos de texto: `more file.txt`
- Canalice la salida larga para verla página por página: `some_command | more`

Equipados con este conocimiento, ahora sabemos cómo mostrar la página de ayuda de un nuevo comando y cómo mostrar resultados largos una página a la vez. Ahora que conoce la línea de comandos de Windows, es hora de pasar a la [sala de Windows PowerShell](https://tryhackme.com/r/room/windowspowershell).

### Responde las preguntas a continuación
- el comando `shutdown /s` puede cerrar un sistema. ¿Cuál es el comando que puede utilizar para reiniciar un sistema? `shutdown /r`
- ¿Qué comando puede utilizar para cancelar un apagado programado del sistema? `shutdown /a`




