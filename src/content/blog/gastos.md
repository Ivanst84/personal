---

title: 'Recetas de Bebidas: Explorando el Mundo de los Cócteles'
description: 'Una aplicación web desarrollada en React para explorar y descubrir recetas de bebidas utilizando una API externa de cócteles.'
pubDate: 'SEP 28 2023'
heroImage: 'https://example.com/hero-image.png'
categories: ['React', 'API', 'Frontend']
authors: ['Tu Nombre']
tags: ['React', 'Zustand', 'Zod', 'Axios', 'API', 'Bebidas']
---
                       
# Recetas de Bebidas: Descubre Nuevos Sabores

¡Bienvenido a la aplicación de Recetas de Bebidas! En este proyecto, se utilizo  React junto con otras tecnologías para crear una plataforma interactiva donde puedes explorar una amplia variedad de recetas de cócteles y bebidas.


- ## Herramientas utilizadas
React: La interfaz de usuario está construida utilizando React, permitiendo una experiencia fluida y receptiva para los usuarios.
Zustand: Empleamos Zustand como una librería ligera de gestión de estado para mantener la información de las recetas y otros datos importantes de manera eficiente.
Zod: Utilizamos Zod para definir y validar los tipos de datos que recibimos de la API de recetas de bebidas, garantizando la integridad de los datos en nuestra aplicación.
Axios: Realizamos peticiones HTTP a una API externa de cócteles utilizando Axios para obtener las recetas de bebidas y mostrarlas en nuestra aplicación

- **Características Principales:

*Página de Inicio (IndexPage):
Muestra una lista de recetas de bebidas.
Utiliza el hook useAppStore para obtener las bebidas del estado global.
Renderiza cartas de bebidas (DrinkCard) en función de los datos obtenidos.
Encabezado (Header):
Contiene un formulario de búsqueda para buscar recetas por nombre o ingredientes y categorías.
Utiliza el estado global (useAppStore) para realizar búsquedas de recetas y mostrar notificaciones.
Estado Global (useAppStore):
Utiliza Zustand para gestionar el estado global de la aplicación.
Define slices de estado para manejar las recetas (createRecipesSlice), favoritos y notificaciones.
Proporciona funciones para realizar búsquedas de recetas, obtener categorías y mostrar/ocultar notificaciones.
Funcionalidades Clave:

Búsqueda de Recetas:
Los usuarios pueden buscar recetas filtrando por nombre/ingredientes y categorías de bebidas.
Las recetas obtenidas se muestran dinámicamente en la página de inicio.
Gestión de Estado:
Utiliza slices de estado separados para diferentes aspectos de la aplicación (recetas, favoritos, notificaciones).
Las funciones definidas en los slices permiten actualizar y obtener datos del estado global de manera modular.
Notificaciones:
Muestra notificaciones para informar al usuario sobre acciones o errores (por ejemplo, campos obligatorios en el formulario de búsqueda).
Aspectos Técnicos:

Utiliza Axios para realizar peticiones HTTP a la API de recetas de bebidas.
Define tipos de datos utilizando Zod para garantizar la integridad y validez de los datos recibidos de la API.
Emplea React Router para la navegación entre diferentes vistas de la aplicación.

## Ejemplo de Código: Obtención de Categorías de Bebidas

En este fragmento de código, se muestra cómo utilizaste Axios y Zustand para obtener y almacenar las categorías de bebidas desde una API externa. Esto es esencial para permitir a los usuarios filtrar las recetas por categoría en tu aplicación.

```javascript
// En el servicio de recetas (RecipeService.js)
import axios from 'axios';
import { CategoryAPIResponseSchema } from '../utils/recipes-schema';

// Función para obtener las categorías de bebidas desde la API
export async function getCategories() {
  const url = 'https://www.thecocktaildb.com/api/json/v1/1/list.php?c=list';

  try {
    const { data } = await axios.get(url);
    const result = CategoryAPIResponseSchema.safeParse(data);

    if (result.success) {
      return result.data;
    } else {
      throw new Error('Error al obtener las categorías de bebidas');
    }
  } catch (error) {
    console.error('Error en la solicitud de categorías:', error);
    throw error;
  }
}


---

[Visita el sitio web de Planificador de gastos](https://control-gasto2.netlify.app/)

[Repositorio](https://github.com/Ivanst84/catalogoBebidas)