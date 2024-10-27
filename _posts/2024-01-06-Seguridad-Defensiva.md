---
layout: single
title: Introducción a la Seguridad Defensiva
excerpt: "Presentamos la seguridad defensiva y temas relacionados, como Threat Intelligence, SOC, DFIR, Malware Analysys y SIEM"
date: 2024-10-17
classes: wide
header:
  teaser: /assets/images/
  teaser_home_page: true
categories:
  - Ciberseguridad 101
tags:
  - Sección 1
  - Seguridad Defensiva
---

![Portada](assets/images/)

## Introducción a la seguridad defensiva

En la sala anterior aprendimos sobre [seguridad ofensiva](), que tiene como objetivo identificar y explotar las vulnerabilidades del sistema para mejorar las medidas de seguridad. Esto incluye explotar errores de software, aprovechar configuraciones inseguras y aprovechar políticas de control de acceso no aplicadas, entre otras estrategias. Los equipos rojos y los probadores de penetración se especializan en estas técnicas ofensivas.

En esta sala examinaremos su contraparte, la seguridad defensiva. Se ocupa de dos tareas principales:

1. Evitar que se produzcan intrusiones
2. Detectar intrusiones cuando se producen y responder adecuadamente

Los equipos azules son parte del panorama de seguridad defensiva.

<div align="center">
<img src="/assets/images/Seguridad-Defensiva/Azul.png">
</div>

Algunas de las tareas que están relacionadas con la seguridad defensiva incluyen:

- `Concientización sobre la ciberseguridad del usuario`: capacitar a los usuarios sobre la ciberseguridad ayuda a protegerlos contra ataques dirigidos a sus sistemas.
- `Documentar y gestionar activos`: Necesitamos conocer los sistemas y dispositivos que debemos gestionar y proteger adecuadamente.
- `Actualización y parcheo de sistemas`: garantizar que las computadoras, servidores y dispositivos de red estén correctamente actualizados y parcheados contra cualquier vulnerabilidad (debilidad) conocida.
- `Configuración de dispositivos de seguridad preventivos`: el firewall y los sistemas de prevención de intrusiones ( IPS ) son componentes críticos de la seguridad preventiva. Los firewalls controlan qué tráfico de red puede entrar y qué puede salir del sistema o la red. IPS bloquea cualquier tráfico de red que coincida con las reglas actuales y las firmas de ataque.
- `Configuración de dispositivos de registro y monitoreo`: el registro y monitoreo de red adecuados son esenciales para detectar intrusiones y actividades maliciosas. Si aparece un nuevo dispositivo no autorizado en nuestra red, deberíamos poder detectarlo. 

La seguridad defensiva implica mucho más. Aparte de lo anterior, también cubriremos los siguientes temas relacionados:

- Centro de operaciones de seguridad ( SOC )
- Inteligencia de amenazas
- Análisis forense digital y respuesta a incidentes ( DFIR )
- Análisis de malware

### Responde las preguntas a continuación
- ¿Qué equipo se centra en la seguridad defensiva? `Blue Team`

## Áreas de Seguridad Defensiva
En esta tarea, cubriremos dos temas principales relacionados con la seguridad defensiva:

- Centro de Operaciones de Seguridad ( SOC ), donde cubrimos Inteligencia de Amenazas
- Análisis forense digital y respuesta a incidentes ( DFIR ), donde también cubrimos el análisis de malware

### Centro de operaciones de seguridad ( SOC )
Un Centro de Operaciones de Seguridad ( SOC ) es un equipo de profesionales de seguridad cibernética que monitorea la red y sus sistemas para detectar eventos de seguridad cibernética maliciosos. Algunas de las principales áreas de interés para un SOC son:

- `Vulnerabilidades`: Siempre que se descubre una vulnerabilidad (debilidad) del sistema, es esencial solucionarla instalando una actualización o parche adecuado. Cuando no hay una solución disponible, se deben tomar las medidas necesarias para evitar que un atacante la explote. Aunque remediar las vulnerabilidades es vital para un SOC , no necesariamente se les asigna.
- `Violaciones de políticas`: una política de seguridad es un conjunto de reglas necesarias para proteger la red y los sistemas. Por ejemplo, podría constituir una infracción de la política si los usuarios cargan datos confidenciales de la empresa en un servicio de almacenamiento en línea.
- `Actividad no autorizada`: considere el caso en el que se roban el nombre de inicio de sesión y la contraseña de un usuario y el atacante los utiliza para iniciar sesión en la red. Un SOC debe detectar y bloquear dicho evento lo antes posible antes de que se produzcan más daños.
- `Intrusiones en la red`: no importa qué tan buena sea su seguridad, siempre existe la posibilidad de que se produzca una intrusión. Puede ocurrir una intrusión cuando un usuario hace clic en un enlace malicioso o cuando un atacante explota un servidor público. De cualquier modo, cuando se produce una intrusión debemos detectarla lo antes posible para evitar daños mayores.

Las operaciones de seguridad cubren diversas tareas para garantizar la protección; Una de esas tareas es la inteligencia sobre amenazas. 

<div align="center">
<img src="/assets/images/Seguridad-Defensiva/SOC.png">
</div>

### Inteligencia de amenazas

En este contexto, la inteligencia se refiere a la información que recopilas sobre enemigos reales y potenciales. Una amenaza es cualquier acción que pueda alterar o afectar negativamente a un sistema. La inteligencia sobre amenazas recopila información para ayudar a la empresa a prepararse mejor contra posibles adversarios. El propósito sería lograr una defensa informada sobre las amenazas . Diferentes empresas tienen diferentes adversarios. Algunos adversarios podrían intentar robar datos de clientes de un operador de telefonía móvil; sin embargo, otros adversarios están interesados ​​en detener la producción en una refinería de petróleo. Los ejemplos de adversarios incluyen un ejército cibernético de un estado-nación que trabaja por razones políticas y un grupo de ransomware que actúa con fines financieros. Según la empresa (objetivo), podemos esperar adversarios. 

<div align="center">
<img src="/assets/images/Seguridad-Defensiva/Inteligencia.png">
</div>

La inteligencia necesita datos. Los datos deben recopilarse, procesarse y analizarse. Los datos se recopilan de fuentes locales, como registros de red, y fuentes públicas, como foros. El procesamiento de datos los organiza en un formato adecuado para el análisis. La fase de análisis busca encontrar más información sobre los atacantes y sus motivos; Además, su objetivo es crear una lista de recomendaciones y pasos viables.

Aprender sobre tus adversarios te permite conocer sus tácticas, técnicas y procedimientos. Como resultado de la inteligencia de amenazas, identificamos al actor de la amenaza (adversario) y predecimos su actividad. En consecuencia, podemos mitigar sus ataques y preparar una estrategia de respuesta.

### Análisis forense digital y respuesta a incidentes ( DFIR )
Esta sección trata sobre análisis forense digital y respuesta a incidentes ( DFIR ) y cubriremos:

- Forense digital
- Respuesta a incidentes
- Análisis de malware

#### Forense digital
La ciencia forense es la aplicación de la ciencia para investigar delitos y establecer hechos. Con el uso y la difusión de los sistemas digitales, como las computadoras y los teléfonos inteligentes, nació una nueva rama de la ciencia forense para investigar delitos relacionados: la ciencia forense informática, que luego evolucionó hacia la ciencia forense digital .

En seguridad defensiva, el enfoque de la ciencia forense digital se desplaza hacia el análisis de la evidencia de un ataque y sus perpetradores y otras áreas como el robo de propiedad intelectual, el ciberespionaje y la posesión de contenido no autorizado. En consecuencia, la ciencia forense digital se centrará en diferentes áreas, tales como:

- `Sistema de archivos`: el análisis de una imagen forense digital (copia de bajo nivel) del almacenamiento de un sistema revela mucha información, como programas instalados, archivos creados, archivos parcialmente sobrescritos y archivos eliminados.
- `Memoria del sistema`: si el atacante ejecuta su programa malicioso en la memoria sin guardarlo en el disco, tomar una imagen forense (copia de bajo nivel) de la memoria del sistema es la mejor manera de analizar su contenido y conocer el ataque.
- `Registros del sistema`: cada computadora cliente y servidor mantiene diferentes archivos de registro sobre lo que está sucediendo. Los archivos de registro brindan mucha información sobre lo que sucedió en un sistema. Incluso si el atacante intenta borrar sus rastros, algunos quedarán.
- `Registros de red`: los registros de los paquetes de red que han atravesado una red ayudarían a responder más preguntas sobre si se está produciendo un ataque y lo que implica.

### un incidente Respuesta a
Un incidente suele referirse a una violación de datos o un ciberataque; sin embargo, en algunos casos, puede ser algo menos crítico, como una mala configuración, un intento de intrusión o una infracción de política. Ejemplos de un ciberataque incluyen un atacante que hace que nuestra red o nuestros sistemas sean inaccesibles, desfigurar (cambiar) el sitio web público y una violación de datos (robar datos de la empresa). ¿Cómo responderías a un ciberataque? La respuesta a incidentes especifica la metodología que se debe seguir para manejar tal caso. El objetivo es reducir los daños y recuperarlos en el menor tiempo posible. Lo ideal sería desarrollar un plan que esté listo para la respuesta a incidentes.

Las cuatro fases principales del proceso de respuesta a incidentes son:

- `Preparación`: Esto requiere de un equipo capacitado y listo para manejar incidentes. Idealmente, se implementan varias medidas para evitar que ocurran incidentes en primer lugar.
- `Detección y Análisis`: El equipo cuenta con los recursos necesarios para detectar cualquier incidencia; además, es fundamental analizar más a fondo cualquier incidente detectado para conocer su gravedad.
- `Contención, Erradicación y Recuperación`: Una vez detectado un incidente, es crucial evitar que afecte a otros sistemas, eliminarlo y recuperar los sistemas afectados. Por ejemplo, cuando notamos que un sistema está infectado con un virus informático, nos gustaría detener (contener) la propagación del virus a otros sistemas, limpiarlo (erradicarlo) y garantizar una recuperación adecuada del sistema.
- `Actividad posterior al incidente`: después de una recuperación exitosa, se genera un informe y se comparte la lección aprendida para evitar incidentes similares en el futuro.

<div align="center">
<img src="/assets/images/Seguridad-Defensiva/Respuesta.png">
</div>

### Análisis de malware

Malware significa software malicioso. El software se refiere a programas, documentos y archivos que puede guardar en un disco o enviar a través de la red. El malware incluye muchos tipos, como por ejemplo:

- Un virus es un fragmento de código (parte de un programa) que se adjunta a un programa. Está diseñado para propagarse de una computadora a otra y funciona alterando, sobrescribiendo y eliminando archivos una vez que infecta una computadora. El resultado va desde que el ordenador se vuelve lento hasta inutilizable.
- Trojan Horse es un programa que muestra una función deseable pero oculta una función maliciosa debajo. Por ejemplo, una víctima podría descargar un reproductor de vídeo de un sitio web sospechoso que le dé al atacante control total sobre su sistema.
- El ransomware es un programa malicioso que cifra los archivos del usuario. El cifrado hace que los archivos sean ilegibles sin conocer la contraseña de cifrado. El atacante ofrece al usuario la contraseña de cifrado si está dispuesto a pagar un "rescate".

<div align="center">
  <img src="/assets/images/Seguridad-Defensiva/Malware.png">
</div>

El análisis de malware tiene como objetivo conocer dichos programas maliciosos utilizando varios medios:

- El análisis estático funciona inspeccionando el programa malicioso sin ejecutarlo. Esto suele requerir un conocimiento sólido del lenguaje ensamblador (el conjunto de instrucciones del procesador, es decir, las instrucciones fundamentales de la computadora).
- El análisis dinámico funciona ejecutando el malware en un entorno controlado y monitoreando sus actividades. Le permite observar cómo se comporta el malware cuando se ejecuta.

### Responde las preguntas a continuación
- ¿Cómo llamarías a un equipo de profesionales de seguridad cibernética que monitorea una red y sus sistemas en busca de eventos maliciosos? `Security Operations Center`
- ¿Qué significa DFIR? `Digital Forensics and Incident Response`
- ¿Qué tipo de malware requiere que el usuario pague dinero para recuperar el acceso a sus archivos? `ransomware`

## Ejemplo práctico de seguridad defensiva
**El escenario**

Supongamos que es un analista del Centro de operaciones de seguridad (SOC) responsable de proteger un banco. de este banco El SOC utiliza una herramienta de gestión de eventos e información de seguridad ( SIEM ), que recopila información y eventos relacionados con la seguridad de varias fuentes y los presenta en un panel. Si el SIEM encuentra algo sospechoso, se generará una alerta. 

<div align="center">
  <img src="/assets/images/Seguridad-Defensiva/Escenario.png">
</div>

Sin embargo, no todas las alertas son maliciosas. Depende del analista utilizar su experiencia en seguridad cibernética para investigar cuáles son perjudiciales.

Por ejemplo, puede encontrar una alerta en la que un usuario haya fallado en varios intentos de inicio de sesión. Si bien es sospechoso, este tipo de cosas suceden, especialmente si el usuario olvidó su contraseña y continúa intentando iniciar sesión.

Además, puede haber alertas relacionadas con conexiones de direcciones IP desconocidas. Una dirección IP es como la dirección particular de su computadora en Internet: le indica a otras computadoras dónde enviar la información que usted solicita. Cuando estas direcciones son desconocidas, podría significar que alguien nuevo está intentando conectarse o alguien está intentando acceder sin autorización .

### Simulando un SIEM

Hemos preparado una simulación interactiva y simplificada de un sistema SIEM para brindarle una experiencia práctica similar a la que encuentran los analistas de seguridad cibernética.

Para iniciar esta simulación, haga clic en el botón "Ver sitio" a continuación. 

Esta acción abrirá un "sitio estático" en el lado derecho de su pantalla. Siga las instrucciones paso a paso proporcionadas en la simulación para navegar a través de los eventos y localizar la "bandera". Una bandera es una serie de caracteres con un formato como este: "THM{RANDOM_WORDS}". Utilice esta bandera para responder preguntas de las salas aquí en TryHackMe, como la siguiente.

¿Qué sigue?
En esta sala, analizamos los diferentes subcampos (SOC, inteligencia de amenazas, análisis de malware y DFIR) y experimentamos de primera mano cómo lidiar con alertas en un entorno SIEM simulado. Si bien hemos cubierto mucho, la profundidad y complejidad de este campo significa que hay más para aprender y explorar. Las lecciones aprendidas aquí le servirán de base a medida que las amenazas cibernéticas evolucionen, exigiendo aprendizaje, vigilancia y adaptación continuos.

Continúe aprendiendo consultando la siguiente sala de esta serie, "Habilidades de búsqueda". Esta sala le enseñará técnicas valiosas para buscar información en línea que le ayudarán en sus investigaciones y aprendizaje.

Si desea avanzar y aprender más sobre los temas tratados en esta sala, se recomiendan las siguientes salas:

- [Introducción a SIEM](): introducción a la gestión de eventos e información de seguridad
- [Operaciones de seguridad](): obtenga más información sobre el Centro de operaciones de seguridad ( SOC ): sus responsabilidades, servicios y fuentes de datos.
- [DFIR : Introducción]()- Sala de introducción al DFIR módulo
- [Introducción al análisis de malware](): qué hacer cuando se encuentra con un malware sospechoso 

### Responde las preguntas a continuación
- ¿Cuál es la bandera que obtuviste al seguirme? `THM{THREAT-BLOCKED}`