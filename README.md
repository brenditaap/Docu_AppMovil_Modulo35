# PixelVault Store
Aplicación móvil desarrollada con **React Native y JavaScript** que simula una tienda digital de videojuegos.

PixelVault Store permite a los usuarios registrarse, iniciar sesión, consultar un catálogo de videojuegos, filtrar por categorías, visualizar información de los juegos, agregar productos al carrito, realizar un pago simulado y consultar el historial de compras.

## Tecnologías utilizadas
* React Native
* JavaScript
* Expo
* AsyncStorage
* Expo Vector Icons / Ionicons

## Funcionalidades principales
* Registro de usuarios.
* Inicio y cierre de sesión.
* Recuperación de contraseña.
* Persistencia de sesión.
* Catálogo de videojuegos.
* Filtrado por categorías.
* Visualización de detalles de cada juego.
* Carrito de compras.
* Cálculo automático del total.
* Pago simulado.
* Generación de número de transacción.
* Historial de compras.
* Perfil del usuario.

## Documentación
La documentación técnica del proyecto se encuentra organizada en la carpeta `docs/`.

* [Arquitectura del proyecto](docs/arquitectura.md)
* [Casos de uso](docs/casos_de_uso.md)
* [Diagrama de secuencia](docs/secuencia.md)
* [Instalación móvil](docs/instalacion_movil.md)
* [API y servicios](docs/api_endpoints.md)
* [Manual de usuario](docs/manual_usuario.md)
* [Políticas de Seguridad](docs/seguridad.md)

## Diagramas
Los diagramas utilizados en la documentación se encuentran en:

`docs/assets/`

* `diagrama_casos_uso.drawio.png`
* `diagrama_secuencia.jpeg`

## Almacenamiento local
PixelVault utiliza **AsyncStorage** para conservar información localmente.

Principales claves utilizadas:
* `@pixelvault_sesion`
* `@pixelvault_usuarios`
* `@pixelvault_compras`

## Limitaciones
El proyecto es una aplicación académica y actualmente utiliza almacenamiento local.
El proceso de pago es únicamente una **simulación** y no utiliza una plataforma bancaria o una pasarela de pago real.
No se deben utilizar datos reales de tarjetas dentro de la aplicación.

## Versión
**v1.0.0**

Primera versión estable del proyecto.

## Autores
* Brenda Lisseth Córdova Vigil
* Maybelline Gabriela Marroquín Chávez

## Curso
**3° Desarrollo de Software**