---
layout: single
title: Introducción a la Seguridad Ofensiva
excerpt: "Hackea tu primer sitio web (legalmente en un entorno seguro) y experimenta el trabajo de un hacker ético."
date: 2024-10-17
classes: wide
header:
  teaser: /assets/images/Seguridad-Ofensiva/Logo.jpeg
  teaser_home_page: true
categories:
  - Ciberseguridad 101
tags:
  - Sección 1
  - Seguridad Ofensiva
---

![Portada](assets/images/Seguridad-Ofensiva/Portada.avif)

## ¿Qué es la seguridad ofensiva?
"Para ser más astuto que un hacker, es necesario pensar como tal".

<div align="center">
<img src="/assets/images/Seguridad-Ofensiva/Ofensiva.png">
</div>

Este es el núcleo de la "Seguridad Ofensiva". Implica irrumpir en sistemas informáticos, explotar errores de software y encontrar lagunas en las aplicaciones para obtener acceso no autorizado. El objetivo es comprender las tácticas de los piratas informáticos y mejorar las defensas de nuestro sistema. 

### Comenzando su viaje de aprendizaje

En esta sala TryHackMe, se le guiará para piratear su primer sitio web en un entorno legal y seguro. El objetivo es mostrarle cómo opera un hacker ético.

Pero antes de hacer eso, repasemos respondiendo las preguntas a continuación. Escriba su respuesta en el cuadro de texto después de la pregunta y haga clic en el botón "Enviar". Cuando haya terminado, continúe con la Tarea 2. 

### Responde las preguntas a continuación

¿Qué implica simular las acciones de un hacker para encontrar vulnerabilidades y obtener acceso no autorizado? `Offensive Security`

## Hackeando tu primera máquina

Aquí en TryHackMe utilizamos máquinas virtuales para crear entornos simulados que sirven como complementos prácticos de las salas.

En esta sala, hemos preparado una aplicación bancaria falsa llamada Fakebank que puedes piratear de forma segura. Para iniciar esta máquina, haga clic en el botón Iniciar máquina a continuación.

<div align="center">
<img src="/assets/images/Seguridad-Ofensiva/Iniciar.png">
</div>

Su pantalla debería estar dividida por la mitad, mostrando este contenido a la izquierda y la máquina recién iniciada a la derecha. Si lo oculta más tarde, siempre puede hacer clic en el botón Mostrar vista dividida en la parte superior para mostrarlo nuevamente. Debería ver una ventana del navegador que muestra el siguiente sitio web: 

<div align="center">
<img src="/assets/images/Seguridad-Ofensiva/FakeBank.png">
</div>

Si no ve el que se muestra arriba, use el botón "Mostrar vista dividida" en la parte superior de esta página.

<div align="center">
<img src="/assets/images/Seguridad-Ofensiva/Dividida.png">
</div>

### Tu primer truco

Usaremos una aplicación de línea de comandos llamada [Gobuster](https://github.com/OJ/gobuster) para aplicar fuerza bruta al sitio web de FakeBank para encontrar directorios y páginas ocultos. Gobuster tomará una lista de posibles nombres de páginas o directorios e intentará acceder a un sitio web con cada uno de ellos; si la pagina existe te lo dice.

- `Paso 1`. Abra una terminal

Una terminal, también conocida como línea de comandos, nos permite interactuar con una computadora sin utilizar una interfaz gráfica de usuario. En la máquina, abra la terminal haciendo clic en el icono de Terminal a la derecha de la pantalla.

<div align="center">
<img src="/assets/images/Seguridad-Ofensiva/Terminal.png">
</div>

- Paso 2. Utilice Gobuster para encontrar páginas web ocultas

La mayoría de las empresas tienen una página de portal de administración que brinda a su personal acceso a controles administrativos básicos para las operaciones diarias. En el caso de un banco, es posible que un empleado necesite transferir dinero hacia y desde las cuentas de los clientes. Debido a un error humano o negligencia, puede haber casos en los que estas páginas no se hagan privadas, lo que permite a los atacantes encontrar páginas ocultas que muestran o dan acceso a controles administrativos o datos confidenciales.

Para comenzar, escriba el siguiente comando en la terminal para encontrar páginas potencialmente ocultas en el sitio web de FakeBank usando Gobuster (una aplicación de seguridad de línea de comandos).

```cmd
gobuster -u http://fakebank.thm -w wordlist.txt dir
```

El comando se ejecutará y le mostrará un resultado similar a este:

<div align="center">
<img src="/assets/images/Seguridad-Ofensiva/Gobuster.png">
</div>

En el comando anterior, `-u` se utiliza para indicar el sitio web que estamos escaneando, `-w` toma una lista de palabras para recorrer y encontrar páginas ocultas.

Verás que Gobuster escanea el sitio web con cada palabra de la lista, encontrando páginas que existen en el sitio. Gobuster le habrá dicho las páginas en la lista de nombres de páginas/directorios (indicados por Estado: 200).

<div align="center">
<img src="/assets/images/Seguridad-Ofensiva/Estado.png">
</div>

Paso 3. Hackear el banco

Deberías haber encontrado una página secreta de transferencias bancarias que te permita transferir dinero entre cuentas bancarias `/bank-transfer`. Escriba la página oculta en el sitio web de FakeBank utilizando la barra de direcciones del navegador.

<div align="center">
<img src="/assets/images/Seguridad-Ofensiva/Transfer.png">
</div>

Desde esta página, un atacante tiene acceso autorizado y puede robar dinero de cualquier cuenta bancaria . Como hacker ético, usted (con permiso) podría encontrar vulnerabilidades en su aplicación y reportarlas al banco para solucionarlas antes de que un hacker las explote.

Tu misión es transferir $2000 de la cuenta bancaria 2276 a tu cuenta (número de cuenta 8881). Si su transferencia fue exitosa, ahora debería poder ver su nuevo saldo reflejado en la página de su cuenta.

¡Ve allí ahora y confirma que tienes el dinero! (Es posible que tengas que presionar Actualizar para que aparezcan los cambios)

### Responde las preguntas a continuación
- Sobre el saldo de su cuenta, ahora debería ver un mensaje que indica la respuesta a esta pregunta. ¿Puedes encontrar la respuesta que necesitas? `BANK-HACKED`

- Si fuera un evaluador de penetración o un consultor de seguridad, este es un ejercicio que realizaría para que las empresas prueben las vulnerabilidades en sus aplicaciones web y encuentren páginas ocultas para investigarlas. 

- Finalice la máquina haciendo clic en el botón rojo "Terminar" en la parte superior de la página. 

## Carreras en ciberseguridad
En esta sala, hablamos sobre seguridad ofensiva y lo guiamos para piratear su primer sitio web en un entorno seguro. Aprendió a utilizar Gobuster para encontrar páginas ocultas en el sitio web de destino y transfirió una cantidad considerable de dinero (falso) a su cuenta.

Esto es sólo un vistazo de los desafíos que puede esperar como miembro del equipo de seguridad ofensiva. Sin embargo, queremos reiterar que el objetivo de un hacker ético es identificar lagunas e informarlas para que el equipo de seguridad defensiva pueda solucionarlas.

Hablando de seguridad defensiva, Introducción a la seguridad defensiva es la siguiente sala de este módulo. Conozca lo que hace el otro equipo siguiendo este enlace aquí .

Si desea avanzar y aprender más sobre los temas tratados en esta sala, se recomiendan las siguientes salas:

- [Enumeración web](): aprenda la metodología de enumeración de sitios web mediante el uso de herramientas como Gobuster , Nikto y WPScan.
- [Conviértete en un hacker](): descubre cómo TryHackMe puede ayudarte a convertirte en un hacker. 

### Responde las preguntas a continuación
- ¡Adelante a más aprendizaje! 