---
title: "Control de Registro de Pacientes App: Creando Experiencias Web"
description: "Control de Registro de Pacientes es una aplicación básica para la gestión de pacientes en una veterinaria, desarrollada en React con el uso de context y reducer para práctica de conocimientos."
pubDate: "SEP 28 2023"
heroImage: "https://imgur.com/ExpUCgv"
categories: ["Programación"]
authors: ["Ist"]
tags: ["React", "Tailwind", "TypeScript", "Zustand"]
---

# Control de Registro de Pacientes App: Creando Experiencias Web

Esta aplicación básica permite el registro y gestión de pacientes en una veterinaria, desarrollada como proyecto de práctica utilizando React y otras tecnologías.

## Conocimientos Puestos en Práctica

En la creación de esta aplicación se aplicaron conocimientos adquiridos de Zustand, así como la implementación de dependencias que mejoran la experiencia de usuario, como React Toastify.

### Creación del Store con Zustand

El store define un estado inicial vacío para `patients` y un `activeId` nulo.

#### Funciones del Store:

- **`addPatient(data: DraftPatient): void`**:
  - Esta función agrega un nuevo paciente al estado.
  - Genera un nuevo paciente utilizando `createPatient(data)` que asigna un ID único utilizando `uuidv4()`.
  - Actualiza el estado `patients` agregando el nuevo paciente.

- **`deletePatient(id: Patient['id']): void`**:
  - Esta función elimina un paciente del estado según su ID.
  - Utiliza `state.patients.filter` para mantener solo los pacientes cuyo ID no coincide con el ID proporcionado.

- **`getPatientById(id: Patient['id']): void`**:
  - Esta función establece el `activeId` en el ID del paciente proporcionado.
  - Se utiliza para realizar un seguimiento del paciente activo seleccionado.

- **`updatePatient(data: DraftPatient): void`**:
  - Esta función actualiza los detalles de un paciente existente en el estado.
  - Utiliza `state.patients.map` para buscar y actualizar el paciente cuyo ID coincide con `state.activeId`.

#### Middleware Utilizado:

- **`devtools`**: Proporciona herramientas de desarrollo para depurar el estado del store.
- **`persist`**: Permite persistir el estado del store en el almacenamiento local del navegador para conservar los datos entre sesiones.

---

[Visita el sitio web de Control de Registro de Pacientes](https://pacientes-zustand-hook.netlify.app/)

[Repositorio en GitHub](https://github.com/Ivanst84/pacientes-zustand)
