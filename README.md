# ¡Todas tus pruebas son una simulación! - HandsOnTesting 2025

¡Hola! Este repositorio contiene el material de apoyo para la presentación **"¡Todas tus pruebas son una simulación!"** en el evento **HandsOnTesting 2025**.

Aquí encontrarás un ejemplo práctico de un mock service RESTful creado con SoapUI. Simula un sistema de autenticación básico con endpoints para `login` y `logout`, y gestiona una `sessionId` para las operaciones.

También se incluye una colección de Postman para que puedas probar el mock service de forma rápida y sencilla, tal como lo veremos en la charla.

## Características

*   **Mock Service RESTful**: Construido con SoapUI para simular un backend real.
*   **Endpoints**:
    *   `POST /login`: Para autenticar un usuario y recibir una `sessionId`.
    *   `PUT /logout`: Para invalidar una `sessionId`.
*   **Colección de Postman**: Peticiones preconfiguradas para interactuar con los endpoints del mock.

## Cómo Empezar

Necesitarás [SoapUI](https://www.soapui.org/) para ejecutar el mock service y [Postman](https://www.postman.com/) para ejecutar la colección de pruebas.

### 1. Ejecutar el Mock Service en SoapUI

1.  Abre SoapUI e importa el proyecto desde el archivo [`Sample-REST-API-Project-soapui-project.xml`](Sample-REST-API-Project-soapui-project.xml).
2.  En el panel izquierdo que tiene un árbol de navegación, busca el MockService llamado `Mocking Works Sample`, su icono son un par de flechas en direcciones opuestas, una sin relleno y otra rellena de color azul.
3.  Haz clic derecho sobre él y selecciona "Restart" (o "Start Minimized" si ya estás familiarizado). Por defecto, el servicio se ejecutará en `http://localhost:8089`.

### 2. Probar con Postman

1.  Importa la colección [`Mocking Works.postman_collection.json`](Mocking%20Works.postman_collection.json) en Postman.
2.  La colección utiliza una variable `baseUrl`. Asegúrate de que su valor sea la dirección de tu mock service (por ejemplo, `http://localhost:8089`).
3.  Ejecuta la petición `LogIn`. La prueba automatizada capturará la `sessionId` y la guardará en una variable de la colección.
4.  Ejecuta la petición `LogOut`. Usará automáticamente la `sessionId` guardada para cerrar la sesión.

## Archivos del Proyecto

*   [`Sample-REST-API-Project-soapui-project.xml`](Sample-REST-API-Project-soapui-project.xml): El proyecto de SoapUI que contiene la definición y la lógica del mock service REST.
*   [`Mocking Works.postman_collection.json`](Mocking%20Works.postman_collection.json): La colección de Postman con las peticiones para `login` y `logout`.
