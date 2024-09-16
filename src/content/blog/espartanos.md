---
title: 'Espartanos App - Sistema WEB de automatización para Marketing'
description: 'Aplicación desarrollada con React, Next.js y Tesseract.js para la automatización de procesos de captura de datos y envío de mensajes en el departamento de marketing.'
pubDate: 'sep 15, 2024'
heroImage: 'https://i.imgur.com/3xl0fm3.png'

categories: ['JavaScript', 'Next']
authors: ['Ivan Sosa']
tags: ['TailwindCSS', 'Next', 'JavaScript', 'Prisma']
---

[Visitar versión demo no oficial](https://espartanos.vercel.app/ "Espartanos App")

## Descripción del Proyecto

**Espartanos App** es una solución web diseñada para automatizar la captura de datos y el envío de mensajes en campañas de marketing. Desarrollada en **Next.js 14**, **React**, y **TailwindCSS**, esta aplicación permite procesar imágenes para extraer nombres y números de teléfono, generando archivos **Excel** y **TXT** con los datos capturados y automatizando el envío de mensajes a través de **WhatsApp Web**. El proyecto fue diseñado específicamente para casos de uso en el departamento de marketing de **Izzi en Mexicali**, orientado a mejorar la eficiencia de las campañas de contacto con clientes.

## Tecnologías Utilizadas

- **Next.js 14**
- **React**
- **TailwindCSS**
- **Prisma**
- **Tesseract.js** para el procesamiento de imágenes
- Librerías adicionales:
  - **Dropzone** para la carga de imágenes mediante arrastrar y soltar
  - **Toast** para notificaciones
  - **EmojiPicker** para personalización de mensajes

## Funcionalidades Clave

- **Carga y procesamiento de imágenes**: Los usuarios pueden arrastrar y soltar imágenes para extraer automáticamente nombres y números de teléfono utilizando **Tesseract.js**.
- **Generación de archivos Excel y TXT**: Los datos extraídos se pueden exportar fácilmente a archivos **Excel** con macros o **TXT**.
- **Automatización de mensajes**: Envío automático de mensajes personalizados a través de **WhatsApp Web**, permitiendo gestionar campañas de manera eficiente.
- **Preprocesamiento de imágenes**: Mejora de la precisión del OCR mediante la aplicación de técnicas de procesamiento previas.

![Interfaz de carga de imágenes en Espartanos App](https://i.imgur.com/EMtSOyz.png)

![Datos de nombres y números ficticios para demostración en Espartanos App](https://i.imgur.com/sXeIpdp.png)

![Formulario de demostración personalizado en Espartanos Web App v1.0 Beta](https://i.imgur.com/bac9kj6.png)

*Esta tabla muestra nombres y números de teléfono ficticios generados para fines de demostración en la Espartanos App. Los datos expuestos no representan información real, siendo utilizados únicamente para ilustrar el funcionamiento del sistema de captura de datos y envío automatizado de mensajes a través de WhatsApp.*

## Módulo de Filtrado de Datos

La aplicación incluye un módulo llamado `filterData` que permite procesar el texto extraído de imágenes y separar los nombres y números de teléfono. Este módulo utiliza técnicas de procesamiento para garantizar que solo se capturen números de teléfono válidos y evita duplicados mediante el uso de un conjunto para rastrear los números procesados.

### Características del módulo:

- **Validación de números de teléfono**: Asegura que los números tengan al menos 10 dígitos.
- **Eliminación de duplicados**: Rastrea y elimina números ya procesados.
- **Asignación de valores predeterminados**: Maneja casos donde los números no son válidos, asignando un valor predefinido.

Este proceso garantiza que los datos extraídos a partir de imágenes sean precisos y estén listos para su uso en la automatización del envío de mensajes.

## Módulo Generador de Mensajes

El **módulo generador de mensajes** de **Espartanos App** automatiza la creación de comunicaciones personalizadas para clientes y prospectos. Este módulo es fundamental para optimizar el flujo de mensajes en campañas de marketing a través de **WhatsApp**.

### Funcionalidades destacadas:

- **Mezcla aleatoria de promociones**: Genera combinaciones únicas de ofertas en cada mensaje, personalizando la experiencia del usuario.
- **Introducciones dinámicas**: Incluye introducciones personalizadas con el nombre del cliente y del asesor, variando el nombre de la marca.
- **Mensajes personalizados o predefinidos**: Permite tanto mensajes completamente personalizados como predefinidos, lo que facilita la comunicación en grandes volúmenes.
- **Despedidas variadas**: Los mensajes incluyen despedidas aleatorias para mantener un tono cordial y profesional.

### Consideraciones:

Este proyecto **no** utiliza las **APIs oficiales** de WhatsApp para el envío de mensajes. En su lugar, implementa técnicas que minimizan el riesgo de bloqueo por parte de WhatsApp, asegurando una operación eficiente dentro de los límites establecidos para el uso de **WhatsApp Web**.

Este enfoque garantiza que la aplicación pueda funcionar sin necesidad de integraciones directas con APIs oficiales, reduciendo los riesgos asociados al uso intensivo de mensajería masiva.