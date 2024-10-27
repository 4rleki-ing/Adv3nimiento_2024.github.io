---
layout: single
title: Windows PowerShell
excerpt: "Descubra el Poder de PowerShell y aprenda los conceptos básicos."
date: 2024-10-10
classes: wide
header:
  teaser: /assets/images/
  teaser_home_page: true
categories:
  - Ciberseguridad 101
tags:
  - Sección 4
  - Windows
  - PowerShell
---

![Portada](assets/images/)

## Introducción

<div align="center">
  <img src="/assets/images/PowerShell/Power.png">
</div>

¡Ahí ahí! Si está aquí, es posible que haya escuchado susurros sobre las maravillas de PowerShell y quiera descubrir más, o haya navegado desde la primera sala del módulo Línea de comandos: [Línea de comandos de Windows](https://tryhackme.com/r/room/windowscommandline) . De cualquier manera, está a punto de embarcarse en un viaje para descubrir las maravillas de este poderoso shell y aprender a usarlo para descubrir los secretos de cualquier sistema Windows. Avast, entonces, ¡a bordo!

### Objetivos de aprendizaje

Esta es la segunda sala del [módulo Línea de comando](https://tryhackme.com/module/command-line). Es una sala de introducción a PowerShell, la segunda (históricamente) utilidad de línea de comandos creada para el sistema operativo Windows.

- Conozca qué es PowerShell y sus capacidades.
- Comprender la estructura básica del lenguaje de PowerShell. 
- Aprenda y ejecute algunos comandos básicos de PowerShell.
- Comprenda las numerosas aplicaciones de PowerShell en la industria de la seguridad cibernética.

### Requisitos previos de la habitación

Antes de acercarse a esta sala, se recomienda haber comprendido los conceptos del módulo [Fundamentos de Windows y AD](https://tryhackme.com/module/windows-and-active-directory-fundamentals) y de la sala de [línea de comandos de Windows](https://tryhackme.com/r/room/windowscommandline).

### Responde las preguntas a continuación
- Levantar ancla, izar velas: ¡es hora de zarpar! 

## ¿Qué es PowerShell? 

<div align="center">
  <img src="/assets/images/PowerShell/PowerShell2.png">
</div>

De la página oficial de [Microsoft](https://learn.microsoft.com/en-us/powershell/scripting/overview?view=powershell-7.4): *"PowerShell es una solución de automatización de tareas multiplataforma compuesta por un shell de línea de comandos, un lenguaje de secuencias de comandos y un marco de gestión de configuración".*

PowerShell es una poderosa herramienta de Microsoft diseñada para la automatización de tareas y la gestión de configuración. Combina una interfaz de línea de comandos y un lenguaje de secuencias de comandos creado en el marco .NET. A diferencia de las herramientas de línea de comandos más antiguas basadas en texto, PowerShell está orientado a objetos, lo que significa que puede manejar tipos de datos complejos e interactuar con los componentes del sistema de manera más efectiva. PowerShell, inicialmente exclusivo de Windows, últimamente se ha ampliado para admitir macOS y Linux, lo que lo convierte en una opción versátil para los profesionales de TI en diferentes sistemas operativos. 

### Una breve historia de PowerShell
PowerShell fue desarrollado para superar las limitaciones de las herramientas de línea de comandos y los entornos de secuencias de comandos existentes en Windows. A principios de la década de 2000, a medida que Windows se utilizaba cada vez más en entornos empresariales complejos, las herramientas tradicionales como `cmd.exe` y los archivos por lotes no lograron automatizar y administrar estos sistemas. Microsoft necesitaba una herramienta que pudiera manejar tareas administrativas más sofisticadas e interactuar con las API modernas de Windows.

Jeffrey Snover, un ingeniero de Microsoft, se dio cuenta de que Windows y Unix manejaban las operaciones del sistema de manera diferente: Windows usaba datos estructurados y API, mientras que Unix trataba todo como archivos de texto. Esta diferencia hizo que no fuera práctico portar herramientas de Unix a Windows. La solución de Snover fue desarrollar un enfoque orientado a objetos, combinando la simplicidad de las secuencias de comandos con el poder del marco .NET. Lanzado en 2006, PowerShell permitió a los administradores automatizar tareas de manera más efectiva mediante la manipulación de objetos, ofreciendo una integración más profunda con los sistemas Windows.

A medida que los entornos de TI evolucionaron para incluir varios sistemas operativos, creció la necesidad de una herramienta de automatización versátil. En 2016, Microsoft respondió lanzando PowerShell Core, una versión de código abierto y multiplataforma que se ejecuta en Windows, macOS y Linux.

### El poder en PowerShell
Para comprender plenamente el poder de PowerShell, primero debemos comprender qué es un objeto en este contexto.

En programación, un `objeto`representa un elemento con propiedades (características) y métodos (acciones). Por ejemplo, un `car` puede tener propiedades como `Color`, `Model`, `FuelLevel` y métodos como `Drive()`, `HonkHorn()`, y `Refuel()`.

De manera similar, en PowerShell, los objetos son unidades fundamentales que encapsulan datos y funcionalidades, lo que facilita la gestión y manipulación de la información. Un objeto en PowerShell puede contener nombres de archivos, nombres de usuario o tamaños como datos (`propiedades`) y llevar funciones (`métodos`), como copiar un archivo o detener un proceso.

Los comandos básicos del Command Shell tradicional están basados ​​en texto, lo que significa que procesan y generan datos como texto sin formato. Un `cmdlet` (pronunciado comando-let En cambio, cuando se ejecuta) en PowerShell, devuelve objetos que conservan sus propiedades y métodos. Esto permite una manipulación de datos más potente y flexible, ya que estos objetos no requieren análisis de texto adicional.

Exploraremos más sobre PowerShell y sus capacidades en las próximas secciones. los cmdlets de

### Responde las preguntas a continuación
- ¿Cómo llamamos al enfoque avanzado utilizado para desarrollar PowerShell? `object-oriented`

## Conceptos básicos de PowerShell
Antes de continuar con nuestro recorrido por *PowerShell*, conectémonos a nuestro entorno de laboratorio. Presione el `Start Machine`, luego inicie AttackBox presionando el botón `Start AttackBox` botón en la parte superior de esta página. La máquina AttackBox se iniciará en la vista de pantalla dividida . Si no es visible, use el azul. Show Split View botón en la parte superior de la página. 