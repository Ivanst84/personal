---
title: 'Api-Incident'
description: 'En este proyecto, se  desarrollo una API RESTful utilizando las tecnologías clave de Express, MongoDB y JavaScript. Esta API permite llevar a cabo operaciones básicas de Crear, Leer, Actualizar y Eliminar (CRUD) sobre una colección de datos relacionados con incidencias..'
pubDate: 'OCT 12 2023'
heroImage: 'https://i.imgur.com/eu8apsy.png'
categories: ['JavaScript']
authors: ['ivanSosa']
tags: ['express', 'API']
---

 Documentación de la API de Administración de Incidencias

## Introducción

La API de Administración de Incidencias es una aplicación RESTful que permite la gestión de incidencias. Puedes realizar operaciones como crear, leer, actualizar y eliminar incidencias a través de esta API.

## Tecnologías Utilizadas
- **Lenguaje:** JavaScript

- **Framework:** Express, React
- **Base de Datos:** MongoDB
- **Bibliotecas** Axios, MaterialUI


## Base URL

El punto de acceso principal para la API es: `https://incident-ap.onrender.com/api`

## Autenticación

Para utilizar la API, debes autenticarte. Actualmente, no se ha proporcionado información sobre el método de autenticación en el código proporcionado.

## Endpoints

### Crear una Incidencia

- **Ruta:** `/createIncident`
- **Método:** POST
- **Descripción:** Crea una nueva incidencia.

#### Parámetros de solicitud

- `title` (String, requerido): Título de la incidencia.
- `description` (String, requerido): Descripción de la incidencia.
- `user` (String, requerido): Usuario relacionado con la incidencia.
- `severity` (String, requerido): Gravedad de la incidencia.

#### Respuesta exitosa

Devuelve la incidencia creada.

#### Códigos de estado

- 200: Éxito
- 400: Error en la solicitud
- 500: Error interno del servidor

### Obtener todas las Incidencias

- **Ruta:** `/getIncidents`
- **Método:** GET
- **Descripción:** Obtiene todas las incidencias.

#### Respuesta exitosa

Devuelve un arreglo de incidencias.

#### Códigos de estado

- 200: Éxito
- 400: Error en la solicitud
- 500: Error interno del servidor

### Obtener Incidencias por Gravedad

- **Ruta:** `/getIncidentsBySeverity`
- **Método:** GET
- **Descripción:** Obtiene incidencias por gravedad.

#### Parámetros de consulta

- `severity` (String, requerido): Gravedad de la incidencia a filtrar.

#### Respuesta exitosa

Devuelve un arreglo de incidencias que coinciden con la gravedad especificada.

#### Códigos de estado

- 200: Éxito
- 400: Error en la solicitud
- 500: Error interno del servidor

### Obtener Incidencias por Estado

- **Ruta:** `/getIncidentsByState`
- **Método:** GET
- **Descripción:** Obtiene incidencias por estado.

#### Parámetros de consulta

- `completed` (Boolean, requerido): Estado de la incidencia a filtrar (completada o no completada).

#### Respuesta exitosa

Devuelve un arreglo de incidencias que coinciden con el estado especificado.

#### Códigos de estado

- 200: Éxito
- 400: Error en la solicitud
- 500: Error interno del servidor

### Actualizar una Incidencia

- **Ruta:** `/updateIncident`
- **Método:** PUT
- **Descripción:** Actualiza una incidencia existente.

#### Parámetros de solicitud

Debes proporcionar el `id` de la incidencia a actualizar y los campos que deseas modificar.

#### Respuesta exitosa

Devuelve un mensaje de éxito.

#### Códigos de estado

- 200: Éxito
- 400: Error en la solicitud
- 500: Error interno del servidor

### Eliminar una Incidencia

- **Ruta:** `/deleteIncident`
- **Método:** DELETE
- **Descripción:** Elimina una incidencia.

#### Parámetros de solicitud

Debes proporcionar el `id` de la incidencia a eliminar.

#### Respuesta exitosa

Devuelve un mensaje de éxito.

#### Códigos de estado

- 200: Éxito
- 400: Error en la solicitud
- 500: Error interno del servidor

## Ejemplos de Uso

### Crear una Incidencia

```http
POST /api/createIncident
Content-Type: application/json

{
  "title": "Incidencia de ejemplo",
  "description": "Descripción de la incidencia",
  "user": "UsuarioEjemplo",
  "severity": "Alta"
}
PUT /api/updateIncident
Content-Type: application/json

{
  "id": "ID_de_la_incidencia",
  "title": "Nuevo título"
}
DELETE /api/deleteIncident
Content-Type: application/json

{
  "id": "ID_de_la_incidencia"
}