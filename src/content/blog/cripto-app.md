---
title: 'cripto-app'
description: 'CriptoApp utilizando React, TypeScript,Zustand,axios'
pubDate: 'nov 15, 2023'
heroImage: 'https://i.imgur.com/eu8apsy.png'
categories: ['TypeScript']
authors: ['ivanSosa']
tags: ['React', 'API','Zustand']
---



# Introducción

Bienvenido a la documentación de **CriptoApp**, una aplicación desarrollada para obtener información de cotización de criptomonedas mediante el consumo de una API. Esta documentación detalla los aprendizajes clave, la estructura del proyecto y la lógica de la aplicación.

## Aprendizajes

Durante el desarrollo de esta aplicación, adquirí conocimientos en las siguientes áreas:

- **React**: Utilicé React como biblioteca principal para construir la interfaz de usuario de la aplicación.
- **Zustand**: Empleé Zustand para gestionar el estado global de manera sencilla dentro de React.
- **Axios**: Implementé Axios para realizar peticiones HTTP y consumir datos de la API de criptomonedas.
- **Validación de Esquemas con Zod**: Utilicé Zod para definir y validar esquemas de datos, garantizando la integridad de los datos recibidos.
- **Uso de useEffect y useMemo**: Aproveché `useEffect` y `useMemo` para gestionar efectos secundarios y optimizar el rendimiento en componentes de React.
- **Estilización con CSS**: Aplicación de estilos CSS para mejorar la apariencia y la experiencia de usuario en la aplicación.

## Estructura del Proyecto

El proyecto está organizado de la siguiente manera:

### Componentes

- **App**: Componente principal que contiene la estructura principal de la aplicación.
- **CriptoSearchForm**: Componente que muestra un formulario para seleccionar un par de monedas.
- **CriptoPriceDisplay**: Componente que muestra la cotización de la criptomoneda seleccionada.

### Servicios

- **CryptoService**: Contiene funciones para interactuar con la API de criptomonedas utilizando Axios.

### Almacenamiento Global

- **store**: Utiliza Zustand para mantener y gestionar el estado global de la aplicación.

## Lógica de la Aplicación

### `App` Component

El componente `App` es la raíz de la aplicación. Aquí se realiza la carga inicial de las criptomonedas y se muestra el formulario de búsqueda y la visualización de precios.

### `CriptoSearchForm` Component

Este componente presenta un formulario que permite al usuario seleccionar un par de monedas (moneda y criptomoneda). Al enviar el formulario, se realiza una solicitud a la API para obtener el precio de la criptomoneda seleccionada.

### `CriptoPriceDisplay` Component

En este componente, se muestra la información de cotización de la criptomoneda seleccionada. Se utiliza `useEffect` para controlar la carga de la imagen de la criptomoneda y se aplican estilos CSS para mejorar la presentación de la información.

## Ejemplo de Código

### Ejemplo de Uso de Zustand y Axios

```typescript

import { create } from 'zustand';
import axios from 'axios';
import { CryptoPriceSchema } from './schema/crypto-schema';

type CryptoStore = {
  cryptocurrencies: Cryptocurrency[];
  result: CryptoPrice;
  fetchCryptos: () => Promise<void>;
  fetchData: (pair: Pair) => Promise<void>;
};

export const useCryptoStore = create<CryptoStore>((set) => ({
  cryptocurrencies: [],
  result: {} as CryptoPrice,
  fetchCryptos: async () => {
    const { data } = await axios.get('https://min-api.cryptocompare.com/data/top/mktcapfull?limit=20&tsym=USD');
    // Procesar los datos y actualizar el estado
  },
  fetchData: async (pair) => {
    const { data } = await axios.get(`https://min-api.cryptocompare.com/data/pricemultifull?fsyms=${pair.criptocurrency}&tsyms=${pair.currency}`);
    // Procesar los datos y actualizar el estado
  },
}));

```
###Ejemplo de Uso de Componente React con Estados

```typescript

import { useEffect, useState, useMemo } from 'react';
import { useCryptoStore } from '../store';

export default function CriptoPriceDisplay() {
  const result = useCryptoStore((state) => state.result);
  const hasResult = useMemo(() => Object.keys(result).length > 0, [result]);
  const [isLoaded, setIsLoaded]