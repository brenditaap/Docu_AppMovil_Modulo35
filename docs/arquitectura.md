# Arquitectura de PixelVault Store

## 1. Descripción general
PixelVault Store es una aplicación móvil desarrollada con React Native y JavaScript que simula una tienda digital de videojuegos.

La aplicación permite registrar usuarios, iniciar sesión, consultar un catálogo de videojuegos, visualizar detalles, agregar productos al carrito, realizar pagos simulados y consultar el historial de compras.

## 2. Tecnologías utilizadas
- React Native
- JavaScript
- Expo
- AsyncStorage
- Ionicons

## 3. Arquitectura de la aplicación
La aplicación utiliza una arquitectura basada en componentes, estados y almacenamiento local.

Los principales elementos son:
- Interfaz de usuario de React Native.
- Estados administrados mediante `useState`.
- Efectos mediante `useEffect`.
- Funciones JavaScript para procesar las operaciones.
- AsyncStorage para almacenar información localmente.

## 4. Almacenamiento de datos
PixelVault utiliza AsyncStorage para conservar información en el dispositivo.

Las principales claves utilizadas son:
- `@pixelvault_sesion`
- `@pixelvault_usuarios`
- `@pixelvault_compras`

## 5. Flujo principal
El funcionamiento general de la aplicación es:

1. El usuario abre la aplicación.
2. Se cargan los datos almacenados localmente.
3. Se verifica si existe una sesión activa.
4. El usuario puede iniciar sesión o registrarse.
5. Se muestra el catálogo de videojuegos.
6. El usuario puede consultar categorías y detalles.
7. Los videojuegos pueden agregarse al carrito.
8. Se calcula el total de la compra.
9. Se realiza un pago simulado.
10. Se genera un número de transacción.
11. La compra se almacena localmente.
12. El usuario puede consultar su historial.

## 6. Diagramas relacionados
La arquitectura del proyecto se complementa con los siguientes diagramas:

- Diagrama de casos de uso.
- Diagrama de secuencia.

Estos diagramas se encuentran almacenados en la carpeta `docs/assets/`.

## 7. Limitaciones
PixelVault es un proyecto académico y actualmente no utiliza un servidor backend ni una base de datos en la nube.
El proceso de pago es solamente una simulación y no se conecta con bancos o plataformas de pago reales.