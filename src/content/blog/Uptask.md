---
title: 'UpTask: Administrador de Proyectos, Tareas y Etapas para el Desarrollo de Software'
description: 'Uptask es un proyecto MERN Stack en donde se utilizó Headless UI, JSON Web Token, Context API, Axios, TailwindCSS y TypeScript.'
pubDate: 'jun 15, 2024'
heroImage: 'https://i.imgur.com/j6HbwQk.png'
categories: ['TypeScript']
authors: ['Ivan']
tags: ['TailwindCSS', 'React', 'TypeScript', 'Zod']
---

# UpTask: Administrador de Proyectos, Tareas y Etapas

![Hero Image](https://i.imgur.com/j6HbwQk.png)

[Visitar el sitio web](https://urcmxl.com/ "Visitar UpTask")

## Descripción del Proyecto

El proyecto se divide en dos partes:

### Rest API

Esta REST API es para administrar proyectos. Utiliza autorización para eliminar un proyecto, editarlo o agregar colaboradores. En el caso que no seas el creador del proyecto y solo seas colaborador, no podrás ejecutar acciones como eliminar, actualizar o invitar a otro colaborador. Es la REST API más grande que he hecho y me dio el conocimiento necesario para crear de todo.

- MongoDB como base de datos y Mongoose para el manejo de la misma.
- Bcrypt para encriptar las contraseñas.
- JSON Web Token para guardar el ID y luego utilizarlo como referencia para saber quién está autenticado y así dar permisos.
- Nodemailer para simular el envío de emails.
- CORS para permitir la conexión.
- Express como framework para el servidor.

### Frontend

- **Creación de proyectos**: Los usuarios pueden crear y administrar múltiples proyectos, cada uno con su propio conjunto de tareas.
- **Gestión de tareas**: Dentro de cada proyecto, los usuarios pueden agregar, editar, eliminar o cambiar el estado de cada tarea.
- **Colaboradores**: Los usuarios pueden agregar colaboradores a sus proyectos. Los colaboradores tendrán permisos limitados y solo podrán cambiar el estado de las tareas, pero no crear, editar ni eliminar tareas o proyectos.
- **Diseño adaptable**: Uptask está optimizado para su uso tanto en dispositivos de escritorio como móviles.
- **Aplicación en tiempo real**: Cualquier cambio hecho en la aplicación lo podrán ver todos los usuarios instantáneamente, sin necesidad de recargar la página.

## Tecnologías Utilizadas

- TypeScript
- HTML5
- TailwindCSS
- Zod
- Axios
- JSON Web Token
- Headless UI
- React

## Metodología Implementada

### Modelo MVC

En UpTask, el Modelo se encarga de la lógica de negocio y la gestión de datos. Utiliza MongoDB como base de datos para almacenar la información de las tareas de los usuarios.

- **Estructura del Modelo**: Los modelos se definen utilizando Mongoose, que proporciona una estructura clara y validación de datos para MongoDB.
- **Ejemplo de Modelo**: Un modelo Tarea que incluye campos como título, descripción, fecha de vencimiento y estado de la tarea.

### Vista (View)

La Vista en UpTask está construida utilizando React. Es responsable de presentar los datos al usuario y capturar sus interacciones.

- **Componentes de la Vista**: La aplicación utiliza componentes de React para mostrar listas de tareas, formularios de entrada y otros elementos de la interfaz de usuario.
- **Ejemplo de Componente**: Un componente `ListaDeTareas` que muestra todas las tareas y permite a los usuarios interactuar con ellas.

### Controlador (Controller)

El Controlador actúa como intermediario entre el Modelo y la Vista. En UpTask, los controladores están implementados en el servidor utilizando Express.

- **Funciones del Controlador**: Los controladores manejan las solicitudes HTTP, interactúan con los modelos para manipular los datos y devuelven las respuestas adecuadas a las vistas.
- **Ejemplo de Controlador**: Un controlador `tareasController` que maneja las solicitudes para crear, leer, actualizar y eliminar tareas.

### Integración MVC en UpTask

Al utilizar la metodología MVC en el proyecto UpTask, se logra una separación clara de responsabilidades:

- **Modelo**: Gestiona los datos y la lógica de negocio.
- **Vista**: Presenta los datos y captura la interacción del usuario.
- **Controlador**: Maneja la lógica de la aplicación, gestionando las interacciones entre el Modelo y la Vista.

Esta estructura facilita el mantenimiento y la escalabilidad del proyecto, permitiendo que cada componente evolucione de manera independiente sin afectar a los demás.

## Imágenes

### Vistas de Autenticación

![Login](https://i.imgur.com/ygSuOrb.png)
![Crear Cuenta](https://i.imgur.com/S4CgIE6.png)

### Tareas

![Lista de Tareas](https://i.imgur.com/A5RLutH.png)
![Historial de Cambios y Notas](https://i.imgur.com/tyOGlBx.png)

## Login Usuario Demo

- **Correo**: correo@correo.com
- **Contraseña**: Holas12345

- **Segundo Usuario**:
  - **Correo**: correo2@correo.com
  - **Contraseña**: Hola123456

## Enlaces

- [Backend GitHub](https://github.com/Ivanst84/UpTask_backend)
- [Frontend GitHub](https://github.com/Ivanst84/UpTask_Frontend)
- [Producción](https://up-task-frontend-green.vercel.app/)

## Nota

El servidor está alojado en los servidores gratuitos de Render. Si creas una cuenta, me llegará el NIP en Mailtrap..
