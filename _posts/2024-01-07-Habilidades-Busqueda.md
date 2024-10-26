---
layout: single
title: Habilidades de Búsqueda
excerpt: "Aprenda a realizar búsquedas eficientes en Internet y a utilizar motores de búsqueda especializados y documentos técnicos."
date: 2024-10-15
classes: wide
header:
  teaser: /assets/images/
  teaser_home_page: true
categories:
  - Ciberseguridad 101
tags:
  - Sección 1
  - Habilidades de Búsqueda
---

![Portada](assets/images/)

## Introducción

<div align="center">
  <img src="/assets/images/Habilidades-Busqueda/Buscar.png">
</div>

Una búsqueda rápida en Google de "aprender seguridad cibernética" arrojó alrededor de 600 millones de resultados, mientras que una búsqueda de "aprender piratería" arrojó más del doble de esa cifra. Es posible que el número haya aumentado aún más cuando pases por esta sala.

Estamos rodeados de información. ¿Prefieres rendirte ante la sobrecarga de información y aceptar los primeros resultados que obtengas? ¿O te gusta adquirir las habilidades de búsqueda necesarias para encontrar y acceder a lo que buscas? Esta sala tiene como objetivo ayudarte con esto último.
Objetivos de aprendizaje

El objetivo de esta sala es enseñar:

- Evaluar fuentes de información.
- Utilice los motores de búsqueda de manera eficiente
- Explora motores de búsqueda especializados
- Leer documentación técnica
- Haz uso de las redes sociales
- Consultar medios de comunicación

### Responde las preguntas a continuación
- Comprueba cuántos resultados obtienes al buscar `aprender a hackear`. Al momento de escribir este artículo, obtuvimos 1.500 millones de resultados al realizar búsquedas en Google. 

<div align="center">
  <img src="/assets/images/Habilidades-Busqueda/Evaluacion.png">
</div>

En Internet todo el mundo puede publicar sus escritos. Puede ser en forma de publicaciones de blog, artículos o publicaciones en redes sociales. Puede ser incluso de formas más sutiles, como editando una página wiki pública. Esta capacidad hace posible que cualquiera pueda expresar sus afirmaciones infundadas. Todos pueden expresar su opinión sobre las mejores prácticas de seguridad cibernética, las tendencias de programación futuras y cómo prepararse mejor para una de DevSecOps . entrevista

Es nuestro trabajo, como lectores, evaluar la información. Mencionaremos algunas cosas a considerar al evaluar la información:

- `Fuente`: Identifique el autor u organización que publica la información. Considere si tienen buena reputación y autoridad en el tema. Publicar una publicación de blog no lo convierte a uno en una autoridad en el tema.
- `Evidencia y razonamiento`: verifique si las afirmaciones están respaldadas por evidencia creíble y razonamiento lógico. Buscamos hechos concretos y argumentos sólidos.
- `Objetividad y sesgo`: Evaluar si la información se presenta de manera imparcial y racional, reflejando múltiples perspectivas. No estamos interesados ​​en que los autores impulsen agendas turbias, ya sea para promocionar un producto o atacar a un rival.
- `Corroboración y coherencia`: Validar la información presentada mediante la corroboración de múltiples fuentes independientes. Compruebe si varias fuentes confiables y acreditadas están de acuerdo con las afirmaciones centrales.

### Responde las preguntas a continuación
- ¿Cómo se llama un método o producto criptográfico considerado falso o fraudulento? `snake oil` [Wikipedia](https://en.wikipedia.org/wiki/Snake_oil_(cryptography))
- ¿Cuál es el nombre del comando que reemplaza? netstat en sistemas Linux? `ss`

## Motores de búsqueda
Cada uno de nosotros ha utilizado un motor de búsqueda en Internet; sin embargo, no todo el mundo ha intentado aprovechar todo el poder de un motor de búsqueda en Internet. Casi todos los motores de búsqueda de Internet permiten realizar búsquedas avanzadas. Considere los siguientes ejemplos:

- [Google](https://www.google.com/advanced_search)
- [Bing](https://support.microsoft.com/en-us/topic/advanced-search-options-b92e25f1-0085-4271-bdf9-14aaea720930)
- [DuckDuckGo](https://duckduckgo.com/duckduckgo-help-pages/results/syntax/)

Consideremos los operadores de búsqueda compatibles con Google.

- `"exact phrase"`: Las comillas dobles indican que estás buscando páginas con la palabra o frase exacta. Por ejemplo, se podría buscar `"passive reconnaissance"` para obtener páginas con esta frase exacta.
- `site:`: Este operador le permite especificar el nombre de dominio al que desea limitar su búsqueda. Por ejemplo, podemos buscar historias de éxito en TryHackMe usando `site:tryhackme.com success stories`.
- `-`: El signo menos le permite omitir los resultados de búsqueda que contienen una palabra o frase en particular. Por ejemplo, es posible que le interese aprender sobre las pirámides, pero no desee ver sitios web de turismo; Un enfoque es buscar `pyramids -tourism` o `-tourism pyramids`.
- `filetype:`: Este operador de búsqueda es indispensable para encontrar archivos en lugar de páginas web. Algunos de los tipos de archivos que puede buscar con Google son el formato de documento portátil (PDF), el documento de Microsoft Word (DOC), la hoja de cálculo de Microsoft Excel (XLS) y la presentación de Microsoft PowerPoint (PPT). Por ejemplo, para encontrar presentaciones sobre seguridad cibernética, intente buscar `filetype:ppt cyber security`.

Puede consultar controles más avanzados en varios motores de búsqueda en esta [lista de operadores de búsqueda avanzada](https://github.com/cipher387/Advanced-search-operators-list); sin embargo, lo anterior proporciona un buen punto de partida. Consulte su motor de búsqueda favorito para conocer los operadores de búsqueda admitidos.

### Responde las preguntas a continuación
- ¿Cómo limitaría su búsqueda en Google a archivos PDF que contengan los términos informe de guerra cibernética ? `filetype:pdf cyber warfare report`
- Que frase manda el linux `ss` ¿representar? `socket statistics`

## Motores de búsqueda especializados
Está familiarizado con los motores de búsqueda de Internet; Sin embargo, ¿qué tan familiarizado estás con los motores de búsqueda especializados? Con esto nos referimos a los motores de búsqueda utilizados para encontrar tipos específicos de resultados.

### Shodan
Empecemos por [Shodan](https://www.shodan.io/), un buscador de dispositivos conectados a Internet. Le permite buscar tipos y versiones específicos de servidores, equipos de red, sistemas de control industrial y dispositivos IoT. Es posible que desee ver cuántos servidores todavía ejecutan Apache 2.4.1 y la distribución entre países. Para encontrar la respuesta, podemos buscar `apache 2.4.1`, que devolverá la lista de servidores con la cadena "apache 2.4.1" en sus encabezados. 

<div align="center">
  <img src="/assets/images/Habilidades-Busqueda/Shodan.png">
</div>

Considere visitar [Ejemplos de consultas de búsqueda de Shodan](https://www.shodan.io/search/examples) para ver más ejemplos. Además, puede consultar las [tendencias de Shodan](https://trends.shodan.io) para obtener información histórica si tiene una suscripción. 

### censys
A primera vista, [Censys](https://search.censys.io/) parece similar a Shodan. Sin embargo, Shodan se centra en dispositivos y sistemas conectados a Internet, como servidores, enrutadores, cámaras web y dispositivos IoT. Censys, por otro lado, se centra en hosts, sitios web, certificados y otros activos de Internet conectados a Internet. Algunos de sus casos de uso incluyen enumerar dominios en uso, auditar puertos y servicios abiertos y descubrir activos no autorizados dentro de una red. Es posible que desee consultar los [casos de uso de búsqueda de Censys](https://support.censys.io/hc/en-us/articles/20720064229140-Censys-Search-Use-Cases).

<div align="center">
  <img src="/assets/images/Habilidades-Busqueda/Censys.png">
</div>

### VirusTotal

[VirusTotal](https://www.virustotal.com/gui/) es un sitio web en línea que proporciona un servicio de escaneo de virus para archivos que utilizan múltiples motores antivirus. Permite a los usuarios cargar archivos o proporcionar URL para escanearlos con numerosos motores antivirus y escáneres de sitios web en una sola operación. Incluso pueden ingresar hashes de archivos para verificar los resultados de archivos cargados anteriormente.

La siguiente captura de pantalla muestra el resultado de comparar el archivo enviado con 67 motores antivirus. Además, se pueden consultar los comentarios de la comunidad para obtener más información. En ocasiones, un archivo puede estar marcado como virus o troyano; sin embargo, es posible que esto no sea exacto por varias razones, y es entonces cuando los miembros de la comunidad pueden brindar una explicación más detallada. 

<div align="center">
  <img src="/assets/images/Habilidades-Busqueda/Virustotal.png">
</div>

### Have I Been Pwned

[Have I Been Pwned (HIBP)](https://haveibeenpwned.com/) hace una cosa; le indica si una dirección de correo electrónico ha aparecido en una filtración de datos. Encontrar el correo electrónico dentro de los datos filtrados indica información privada filtrada y, lo que es más importante, contraseñas. Muchos usuarios usan la misma contraseña en múltiples plataformas; si se viola una plataforma, su contraseña en otras plataformas también queda expuesta. De hecho, las contraseñas suelen almacenarse en formato cifrado; sin embargo, muchas contraseñas no son tan complejas y se pueden recuperar mediante una variedad de ataques. 

<div align="center">
  <img src="/assets/images/Habilidades-Busqueda/pwned.png">
</div>

### Responde las preguntas a continuación
- ¿Cuál es el principal país con servidores lighttpd ? `United States`
- ¿Qué detecta BitDefenderFalx con el hash  `2de70ca737c1f4602517c555ddd54165432cf231ffc0e21fb2e23b9dd14e7fb4`?  `Android.Riskware.Agent.LHH`

## Vulnerabilidades y exploits
### CVE
Podemos pensar en el programa Common Vulnerabilities and Exposures ( CVE ) como un diccionario de vulnerabilidades. Proporciona un identificador estandarizado para vulnerabilidades y problemas de seguridad en productos de software y hardware. A cada vulnerabilidad se le asigna un CVE con un formato estandarizado como ID `CVE-2024-29988`. Este identificador único (CVE ID) garantiza que todos, desde investigadores de seguridad hasta proveedores y profesionales de TI, se refieran a la misma vulnerabilidad, [CVE -2024-29988](https://nvd.nist.gov/vuln/detail/CVE-2024-29988) en este caso.

La Corporación MITRE mantiene el sistema CVE. Para obtener más información y buscar CVE existentes, visite el [sitio web](https://www.cve.org/) del programa CVE. Alternativamente, visite el [sitio web]((https://nvd.nist.gov/)) de la Base de datos nacional de vulnerabilidad (NVD). La siguiente captura de pantalla muestra CVE -2014-0160, también conocido como Heartbleed. 

<div align="center">
  <img src="/assets/images/Habilidades-Busqueda/CVE.png">
</div>

### Explotar base de datos

Hay muchas razones por las que querrías explotar una aplicación vulnerable; uno estaría evaluando la seguridad de una empresa como parte de su equipo rojo. No hace falta decir que no deberíamos intentar explotar un sistema vulnerable a menos que se nos dé permiso, generalmente mediante un acuerdo legalmente vinculante.

Ahora que tenemos permiso para explotar un sistema vulnerable, es posible que necesitemos encontrar un código de explotación que funcione. Un recurso es la [base de datos de explotación](https://www.exploit-db.com/). La base de datos de exploits enumera códigos de exploits de varios autores; Algunos de estos códigos de explotación se prueban y se marcan como verificados. 

<div align="center">
  <img src="/assets/images/Habilidades-Busqueda/Exploit.png">
</div>

[GitHub](https://github.com/), una plataforma web para el desarrollo de software, puede contener muchas herramientas relacionadas con CVE, junto con códigos de prueba de concepto (PoC) y de explotación. Para demostrar esta idea, consulte la captura de pantalla siguiente de los resultados de búsqueda en GitHub relacionados con la vulnerabilidad Heartbleed. 

<div align="center">
  <img src="/assets/images/Habilidades-Busqueda/Github.png">
</div>

### Responde las preguntas a continuación
¿A qué utilidad se refiere CVE-2024-3094? `xz`

## Documentación técnica
Una habilidad vital que se debe adquirir es buscar documentación oficial. Cubriremos algunos ejemplos de páginas de documentación oficial.

### Páginas del manual de Linux
Mucho antes de que Internet estuviera en todas partes, ¿cómo obtendría ayuda para utilizar un comando en un sistema tipo Linux o Unix? La respuesta sería consultar la página del manual, para abreviar la página de manual. En Linux y en todos los sistemas tipo Unix, se espera que cada comando tenga una página de manual. De hecho, también existen páginas de manual para llamadas al sistema, funciones de biblioteca e incluso archivos de configuración.

Digamos que queremos consultar la página del manual para el comando `ip`. Emitimos el comando `man ip`. La siguiente captura de pantalla muestra la página que recibimos. Es posible que desee iniciar AttackBox y ejecutar `man ip` en la terminal. Prensa `q` para dejar de leer.

<div align="center">
  <img src="/assets/images/Habilidades-Busqueda/ip.png">
</div>

Si prefieres leer la página de manual de `ip` en su navegador web, simplemente escriba `man ip` en tu buscador favorito. Esta [página](https://linux.die.net/man/8/ip) puede estar en la parte superior de los resultados.

AttackBox accesible es un sistema Linux desde su navegador. Al hacer clic en el botón Iniciar AttackBox se mostrará AttackBox en una pantalla dividida, lo que hace que sea conveniente leer el texto de la tarea y aplicar las instrucciones dentro de la misma ventana del navegador. Si oculta la ventana de AttackBox, puede volver a mostrarla haciendo clic en el botón azul Mostrar vista dividida en la parte superior. En esta tarea, puede iniciar AttackBox y usarlo para probar comandos de Linux como `man`.

### Windows
Microsoft proporciona una [página](https://learn.microsoft.com/en-us/) de documentación técnica oficial para sus productos. La siguiente captura de pantalla muestra los resultados de la búsqueda del comando `ipconfig`.

<div align="center">
  <img src="/assets/images/Habilidades-Busqueda/Windows.png">
</div>

### Documentación del producto
Se espera que cada producto popular tenga documentación bien organizada. Esta documentación proporciona una fuente oficial y confiable de información sobre las características y funciones del producto. Los ejemplos incluyen la [documentación oficial de Snort](https://www.snort.org/documents), [Apache HTTP la documentación del servidor](https://httpd.apache.org/docs/), [de PHP la documentación](https://www.php.net/manual/en/index.php) y [la documentación de Node.js](https://nodejs.org/docs/latest/api/).

Siempre es gratificante consultar la documentación oficial, ya que es la más actualizada y ofrece la información más completa del producto.

### Responde las preguntas a continuación
- ¿Qué descripción manda el comando `cat` en Linux? `concatenate`
- ¿Con `netstat` cuál es el parámetro en MS Windows que muestra el ejecutable asociado con cada conexión activa y puerto de escucha? `-b`

## Redes Sociales

<div align="center">
  <img src="/assets/images/Habilidades-Busqueda/Red.svg">
</div>

Hay miles de millones de usuarios registrados en plataformas de redes sociales como [Facebook](https://www.facebook.com/people/Tryhackme/100069557747714/), [Twitter](https://x.com/RealTryHackMe) y [LinkedIn](https://www.linkedin.com/company/tryhackme/). Esperamos que esté familiarizado con las plataformas populares. Sin embargo, si conoce alguna plataforma con la que no está familiarizado, le recomendamos que la consulte y conozca más sobre ella. Idealmente, uno querría explorar una plataforma sin crear una cuenta; sin embargo, esto limita gravemente su experiencia. En cambio, una recomendación es utilizar una dirección de correo electrónico temporal para descubrir estas plataformas sin vincularlas a sus direcciones de correo electrónico reales; Una vez hecho esto, puede cancelar las cuentas y las direcciones de correo electrónico asociadas. Una razón para no usar tu cuenta principal es que no quieres que tus contactos comiencen a conectarse contigo allí cuando solo estás explorando una plataforma temporalmente.

El poder de las redes sociales es que le permiten conectarse con empresas y personas que le interesan. Además, las redes sociales ofrecen una gran cantidad de información para los profesionales de la seguridad cibernética, ya sea que estén buscando personas o información técnica. ¿Por qué es importante buscar personas?

Al proteger una empresa, debe asegurarse de que las personas que protege no compartan demasiado en las redes sociales. Por ejemplo, sus redes sociales podrían revelar la respuesta a sus preguntas secretas, como "¿A qué escuela fuiste cuando eras niño?". Esta información podría permitir a los adversarios restablecer sus contraseñas y hacerse cargo de sus cuentas sin esfuerzo.

Además, como profesional de la seguridad cibernética, desea mantenerse actualizado con las nuevas tendencias, tecnologías y productos de seguridad cibernética. Seguir los canales y grupos adecuados puede proporcionar un entorno adecuado para aumentar su experiencia técnica.

Además de mantenernos actualizados a través de canales y grupos de redes sociales, debemos mencionar los medios de comunicación. Cientos de sitios web de noticias ofrecerían valiosas noticias relacionadas con la ciberseguridad. Prueba diferentes y quédate con los que más te gusten.

### Responde las preguntas a continuación
- Lo contratan para evaluar la seguridad de una empresa en particular. ¿Qué es un sitio web popular de redes sociales que usaría para aprender sobre los aspectos técnicos antecedentes de uno de sus empleados? `LinkedIn`
- Continuando con el escenario anterior, estás intentando encontrar la respuesta a la pregunta secreta: “¿A qué escuela fuiste cuando eras niño?”. Qué sitio web de redes sociales, ¿consideraría consultar para encontrar la respuesta? ¿Preguntas tan secretas? `Facebook`

## Conclusión
Esta sala se centró en las fuentes de información más habituales para los profesionales de la ciberseguridad. Hay muchos más. A medida que el panorama de la información sigue cambiando, es imposible abarcar todas las fuentes. Sin embargo, al suscribirse a grupos de seguridad cibernética relevantes, uno puede mantenerse a la vanguardia y estar al tanto siempre que surjan nuevas fuentes interesantes.

### Responde las preguntas a continuación
- Asegúrese de haber tomado nota de los distintos motores de búsqueda y recursos mencionados. en esta sala, ya que serán convenientes en cualquier camino de seguridad cibernética que seguir. 