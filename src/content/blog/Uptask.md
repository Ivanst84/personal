---
title: 'UpTask Administrador de proyectos, tareas y etapas  para el desarrollo de software'
description: 'Uptask es un proyecto MERN Stack en donde se utilizo Headless Ui, JsonWebToken, context Api, axios, TaildwindCSS y TypeScript.'
pubDate: 'jun 15, 2024'
heroImage: 'https://i.imgur.com/j6HbwQk.png'
categories: ['TypeScript']
authors: ['Ivan']
tags: ['TaildwindCss', 'React', 'TypeScript', 'Zod']
---

[Visitar el sitio web](https://urcmxl.com/ "{{title}}")

## Descripción del Proyecto

El proyecto se divide en dos partes
#Rest API
Esta REST API es para administrar proyectos. Utiliza autorizacion para eliminar un proyecto, editarlo o agregar colaboradores En el caso que no seas el creador del proyecto y solo seas colaborador no podras ejecutar acciones como eliminar, actualizar o invitar a otro colaaborador Es la REST API mas grande que hice y me dio el conocimiento necesario para crear de todo.

MongoDB como base de datos y moongose para el manejo de la misma
Bcrypt para encriptar el password
JsonWebToken para guardar el ID y luego utilizarlo como referencia para saber quien esta autenticado y asi dar permisos
Nodemailer para simular el envio de Emails
CORS para permitir la conexion
Express

Frontend:
💠 Creación de proyectos: los usuarios pueden crear y administrar múltiples proyectos, cada uno con su propio conjunto de tareas.
💠 Gestión de tareas: dentro de cada proyecto, los usuarios pueden agregar tareas, editar, eliminar o cambiar el estado de cada tarea. 
💠 Colaboradores: los usuarios pueden agregar colaboradores a sus proyectos. Los colaboradores tendrán permisos limitados y solo podrán cambiar el estado de las tareas, pero no crear, editar ni eliminar tareas o proyectos.
💠 Diseño adaptable: Uptask está optimizado para su uso tanto en dispositivos de escritorio como móviles.
💠 Aplicación en tiempo real: cualquier cambio hecho en la aplicación lo podrán ver todos los usuarios instantáneamente, sin necesidad de recargar la págin

## Tecnologías Utilizadas
- TypeScript
- HTML5
- Tailwindcss
- Zod
- Axios
  - JsonWebToken 
  - HadlessUI
  - React
  

## Metodología Implementada
# Modelo MVC
En Upstak, el Modelo se encarga de la lógica de negocio y la gestión de datos. Utiliza MongoDB como base de datos para almacenar la información de las tareas de los usuarios.

# Estructura del Modelo: Los modelos se definen utilizando Mongoose, que proporciona una estructura clara y validación de datos para MongoDB.
Ejemplo de Modelo: Un modelo Tarea que incluye campos como título, descripción, fecha de vencimiento y estado de la tarea.
## Vista (View)
La Vista en Upstak está construida utilizando React. Es responsable de presentar los datos al usuario y capturar sus interacciones.

Componentes de la Vista: La aplicación utiliza componentes de React para mostrar listas de tareas, formularios de entrada y otros elementos de la interfaz de usuario.
Ejemplo de Componente: Un componente ListaDeTareas que muestra todas las tareas y permite a los usuarios interactuar con ellas.

## Controlador (Controller)
El Controlador actúa como intermediario entre el Modelo y la Vista. En Upstak, los controladores están implementados en el servidor utilizando Express.

Funciones del Controlador: Los controladores manejan las solicitudes HTTP, interactúan con los modelos para manipular los datos y devuelven las respuestas adecuadas a las vistas.
Ejemplo de Controlador: Un controlador tareasController que maneja las solicitudes para crear, leer, actualizar y eliminar tareas.
Integración MVC en Upstak
Al utilizar la metodología MVC en el proyecto Upstak, se logra una separación clara de responsabilidades:

Modelo gestiona los datos y la lógica de negocio.
Vista presenta los datos y captura la interacción del usuario.
Controlador maneja la lógica de la aplicación, gestionando las interacciones entre el Modelo y la Vista.
Esta estructura facilita el mantenimiento y la escalabilidad del proyecto, permitiendo que cada componente evolucione de manera independiente sin afectar los demás.

## Diagramas

### Vistas de autentificacion
![Login](https://i.imgur.com/ygSuOrb.png)
![Crear cuenta](https://i.imgur.com/S4CgIE6.png)


### Tareas
![Lista de tareas](https://i.imgur.com/A5RLutH.png)
![Historial de cambios y notas](https://i.imgur.com/tyOGlBx.png)

## Login usuario demo:
correo correo@correo.com
pass: Holas12345
segundo usuario :
correo2@correo.com
pass : Hola123456
![Backend Git Hub](https://github.com/Ivanst84/UpTask_backend)
![Frontend Git Hub](https://github.com/Ivanst84/UpTask_Frontend)
![Produccion](https://up-task-frontend-green.vercel.app/)

## Nota:
El servidor esta alojado en los servidores gratuitos de Render
Si creas una cuenta me llegara el nip  en el mailtrap


