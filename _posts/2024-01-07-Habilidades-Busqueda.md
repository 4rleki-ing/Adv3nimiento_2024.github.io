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