# Guía de Instalación y Configuración del Entorno Móvil

## 1. Descripción
PixelVault Store es una aplicación móvil desarrollada con **React Native y JavaScript**, utilizando **Expo** como entorno para facilitar su ejecución y pruebas. La aplicación simula una tienda digital de videojuegos y utiliza **AsyncStorage** para guardar información localmente en el dispositivo.

La aplicación permite registrarse, iniciar sesión, consultar el catálogo de videojuegos, filtrar por categorías, consultar los detalles de los juegos, agregar productos al carrito, realizar un pago simulado y consultar el historial de compras.
---

## 2. Requisitos del Dispositivo / Entorno
Para ejecutar y probar PixelVault Store se necesitan los siguientes requisitos:

### Dispositivo móvil
* Dispositivo Android o iOS compatible con la aplicación.
* Espacio suficiente para instalar y ejecutar la aplicación.
* Conexión a Internet o Wi-Fi cuando sea necesaria para el entorno de desarrollo y pruebas.
* Permisos necesarios para instalar y ejecutar la aplicación.

### Entorno de desarrollo
* **React Native:** utilizado para desarrollar la interfaz de la aplicación.
* **JavaScript:** utilizado para programar la lógica y funcionamiento de PixelVault.
* **Expo:** utilizado como entorno para ejecutar y realizar pruebas de la aplicación.
* **AsyncStorage:** utilizado para almacenar información localmente en el dispositivo.

### Información almacenada localmente
PixelVault utiliza las siguientes claves de AsyncStorage:

* `@pixelvault_sesion` — Guarda la sesión actual.
* `@pixelvault_usuarios` — Guarda los usuarios registrados.
* `@pixelvault_compras` — Guarda las compras realizadas.
---

## 3. Procedimiento de Instalación y Ejecución
### Opción 1: Ejecución mediante Expo

1. Tener disponible el proyecto de PixelVault Store en el entorno de desarrollo.
2. Abrir el proyecto utilizando el entorno configurado para trabajar con React Native y Expo.
3. Iniciar el proyecto mediante Expo.
4. Utilizar un dispositivo móvil compatible o un emulador para realizar las pruebas.
5. Abrir la aplicación PixelVault Store.
6. Verificar que aparezca correctamente la pantalla de inicio de sesión o la pantalla principal si existe una sesión guardada.

Expo facilita el desarrollo y las pruebas de la aplicación móvil.
---

## 4. Configuración Inicial
Al iniciar la aplicación, PixelVault ejecuta un proceso de carga de información almacenada previamente.

La aplicación utiliza:
```javascript
useEffect(() => {
  cargarDatosGuardados();
}, []);
```

Este proceso permite recuperar información guardada mediante AsyncStorage, como:
* Usuarios registrados.
* Compras anteriores.
* Sesión activa.

Si existe una sesión válida, la aplicación puede restaurarla y permitir el acceso nuevamente sin que el usuario tenga que iniciar sesión.
---

## 5. Prueba de Funcionamiento
Después de ejecutar la aplicación, se recomienda comprobar las principales funciones:

1. Abrir PixelVault Store.
2. Crear una cuenta utilizando los datos solicitados.
3. Iniciar sesión con las credenciales registradas.
4. Comprobar que se muestre el catálogo de videojuegos.
5. Seleccionar una categoría.
6. Consultar los detalles de un videojuego.
7. Agregar un videojuego al carrito.
8. Comprobar que el total se calcule automáticamente.
9. Realizar el proceso de pago simulado.
10. Verificar que se genere el número de transacción.
11. Consultar el historial de compras.
12. Cerrar sesión.
13. Volver a iniciar la aplicación y comprobar la recuperación de los datos almacenados.
---

## 6. Consideraciones sobre el Almacenamiento
PixelVault utiliza almacenamiento local mediante AsyncStorage. Esto permite conservar información después de cerrar la aplicación.

Los principales datos almacenados son:

| Información          | Clave                  |
| -------------------- | ---------------------- |
| Sesión actual        | `@pixelvault_sesion`   |
| Usuarios registrados | `@pixelvault_usuarios` |
| Compras realizadas   | `@pixelvault_compras`  |

El funcionamiento de la aplicación depende de que estas claves se mantengan correctamente configuradas.
---

## 7. Solución de Problemas Básicos
### La sesión no se mantiene
Verificar que AsyncStorage esté correctamente configurado y que la clave:

```text
@pixelvault_sesion
```

se encuentre correctamente utilizada en el código.

### Los usuarios registrados no aparecen
Verificar la clave:

```text
@pixelvault_usuarios
```

y comprobar que los datos estén siendo guardados y recuperados correctamente mediante AsyncStorage.

### El historial de compras no aparece
Verificar la clave:

```text
@pixelvault_compras
```

y comprobar que las compras hayan sido guardadas correctamente.

### La aplicación presenta errores después de modificar el código
Se deben revisar las importaciones, los estados utilizados por los componentes y la configuración de AsyncStorage, ya que estos elementos son necesarios para el funcionamiento de PixelVault.
---

## 8. Limitaciones de la Versión Actual
PixelVault es un proyecto académico que utiliza almacenamiento local mediante AsyncStorage.

Actualmente:
* Las cuentas se almacenan localmente.
* Las contraseñas no utilizan un sistema de cifrado o hashing de servidor.
* El proceso de pago es únicamente una simulación.
* No existe conexión con un banco o una plataforma de pagos real.
* No se deben utilizar datos reales de tarjetas durante las pruebas.

Por lo tanto, la aplicación está diseñada principalmente para fines académicos y de demostración.
---

## 9. Recomendaciones para las Pruebas
Durante las pruebas de PixelVault se recomienda:

* Utilizar datos de prueba.
* No introducir información bancaria real.
* Comprobar que los formularios validen correctamente la información.
* Verificar el funcionamiento del registro e inicio de sesión.
* Comprobar el carrito y el cálculo automático del total.
* Confirmar que las compras aparezcan en el historial.
* Verificar que la sesión pueda mantenerse después de cerrar y volver a abrir la aplicación.
---

## 10. Resumen de Requisitos

| Requisito                | Utilizado en PixelVault |
| ------------------------ | ----------------------- |
| React Native             | Sí                      |
| JavaScript               | Sí                      |
| Expo                     | Sí                      |
| AsyncStorage             | Sí                      |
| Almacenamiento local     | Sí                      |
| API REST externa         | No                      |
| Servidor Backend         | No                      |
| Base de datos en la nube | No                      |
| Pago real                | No                      |
| Pago simulado            | Sí                      |

PixelVault Store puede ejecutarse y probarse utilizando el entorno de **React Native y Expo**, utilizando **AsyncStorage** para conservar los datos localmente en el dispositivo.