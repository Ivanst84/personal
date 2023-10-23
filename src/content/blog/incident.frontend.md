---
title: 'Incident-frontend'
description: En el desarrollo de la interfaz de usuario de esta aplicación, hemos empleado React y JavaScript para crear un frontend atractivo y altamente interactivo. Esta parte del proyecto juega un papel crucial en la experiencia del usuario y proporciona una interfaz intuitiva para interactuar con la API RESTful que hemos construido en el backend de incidencias.'
pubDate: 'OCT 12 2023'
heroImage: 'https://i.imgur.com/6MhsLLx.png'
categories: ['JavaScript']
authors: ['ivanSosa']
tags: ['React', 'API']
---
  [Visitar el sitio web]( https://incident-front.vercel.app/ "{{title}}")

Documentación del Frontend de incidencias.

# Proyecto de Práctica en React

Este proyecto es el resultado de aplicar los conocimientos adquiridos en cursos de React, utilizando una API desarrollada en MongoDB y JavaScript. Una parte fundamental de la experiencia de desarrollo fue la implementación de esta API en un entorno específico conocido como "Render," una plataforma que desempeña un papel esencial en la optimización de la velocidad y el rendimiento de la aplicación.

## Sobre Render

Render es una plataforma de alojamiento y despliegue diseñada para mejorar la velocidad y la eficiencia en la gestión de aplicaciones. En este proyecto, aprovechamos Render para albergar y ofrecer nuestra API de MongoDB. La elección de Render se realizó con el propósito de abordar y mitigar posibles problemas de lentitud en el consumo de datos a través de la API.

A través de este proyecto, exploramos cómo la integración de tecnologías como React y MongoDB, junto con la elección de un alojamiento adecuado en Render, puede mejorar significativamente la experiencia del usuario final y optimizar la velocidad de respuesta de la aplicación.

Sigue leyendo para obtener más detalles sobre la implementación, los desafíos superados y los resultados obtenidos en esta emocionante aventura de desarrollo.
**Características destacadas del Frontend:**

1. **React:** Se opto por utilizar React, una popular biblioteca de JavaScript para la construcción de interfaces de usuario. React es conocido por su eficiencia, reactividad y facilidad de uso, lo que nos permite crear componentes reutilizables y mantener un código limpio y bien organizado.

2. **Interfaz de Usuario Atractiva:** Se ha diseñado una interfaz de usuario atractiva y fácil de usar que se adapta a las necesidades de los usuarios. Esto incluye una navegación intuitiva, presentación de datos clara y elementos visuales que mejoran la experiencia del usuario.
![Formulario](https://i.imgur.com/CId2y1P.png)

3. **Interacción en Tiempo Real:** Se ha implementado interacción en tiempo real utilizando React para que los usuarios puedan ver los cambios en las incidencias y la información en pantalla al instante, lo que mejora la eficiencia y la usabilidad de la aplicación.

4. **Conexión con el Backend:** La parte del frontend se comunica de manera efectiva con el backend a través de solicitudes HTTP a la API RESTful. Esto permite a los usuarios acceder y gestionar las incidencias de forma rápida y sencilla.

5. **JavaScript:** El frontend de la aplicación se desarrolla principalmente en JavaScript, lo que facilita la manipulación de datos y la interacción con la API en el lado del cliente.

El frontend de la aplicación es la cara visible de el proyecto, brindando a los usuarios la capacidad de interactuar con la funcionalidad proporcionada por la API RESTful en el backend. La elección de React y JavaScript garantiza una experiencia de usuario agradable y una base sólida para el crecimiento futuro de la aplicación.ç

## Componente `AddIncident`

El componente `AddIncident` es una parte esencial de esta aplicación de React. Este componente permite a los usuarios agregar nuevas incidencias y actualizar las existentes, lo que contribuye a la gestión eficaz de incidentes. Aquí hay una descripción general de sus principales características y funciones:

- **Funcionalidad de Agregar y Actualizar:** El componente ofrece la capacidad de agregar nuevas incidencias a través del formulario de incidencia. Además, los usuarios pueden actualizar incidencias existentes con los datos proporcionados.

- **Notificaciones de Estado:** Utiliza el componente `Notification` para informar a los usuarios sobre el resultado de sus acciones, ya sea para notificar el éxito en la actualización o la adición de una incidencia, o para informar sobre posibles errores.

- **Navegación Dinámica:** La función `navigate` de React Router se utiliza para redirigir a los usuarios a la página principal después de completar con éxito una acción, mejorando la experiencia de usuario.

- **Interacción con una API:** El componente se conecta a una API para llevar a cabo operaciones de creación y actualización de incidencias, utilizando las funciones `createIncident` y `updateIncident` proporcionadas en `incidentService`.

Este componente juega un papel crucial en la gestión de incidencias en la aplicación, proporcionando a los usuarios las herramientas necesarias para agregar y mantener un registro actualizado de las incidencias que deben ser atendidas.
<details>
<summary>Haz clic para ver el código completo</summary>
<div style="overflow: scroll; max-height: 300px;">
```javascript
function AddIncident() {
  const navigate = useNavigate();
  const [notification, setNotification] = useState({
    open: false,
    message: "",
    severity: "success",
  });

  const handleCloseNotification = () => {
    setNotification({ ...notification, open: false });
  };
  
  const handleUpdate = (formData) => {
    // Llama a la función de actualización con los datos actualizados
    updateIncident(formData)
      .then((response) => {
        setNotification({
          open: true,
          message: "Incidencia actualizada correctamente",
          severity: "success",
        });
    
        setTimeout(() => {
          navigate("/");
        }, 1000);
      })
      .catch((error) => {
        setNotification({
          open: true,
          message: "Error al actualizar la incidencia",
          severity: "error",
        });
      });
  };

  const handleFormSubmit = (formData) => {
    console.log('formData:', formData); // Agrega este mensaje de consola
    createIncident(formData)
      .then((response) => {
        setNotification({
          open: true,
          message: "Incidencia agregada correctamente",
          severity: "success",
        });
        
        setTimeout(() => {
          navigate("/");
        }, 2000);
      })
      .catch((error) => {
        setNotification({
          open: true,
          message: "Error al agregar la incidencia",
          severity: "error",
        });

        navigate("/");
      });
  };

  return (
    <div>
      <IncidentForm onSubmit={handleFormSubmit} onUpdate={handleUpdate} />

      <Notification
        open={notification.open}
        onClose={handleCloseNotification}
        message={notification.message}
        severity={notification.severity}
      />
    </div>
  );
}

export default AddIncident;
</div>
</deta



