# Manual de Usuario - PixelVault Store

## 1. Introducción
PixelVault Store es una aplicación móvil que simula una tienda digital de videojuegos.
La aplicación permite al usuario crear una cuenta, iniciar sesión, consultar videojuegos, filtrar el catálogo por categorías, revisar información de cada producto, agregar videojuegos al carrito, realizar una compra simulada y consultar el historial de compras.
---

## 2. Inicio de la Aplicación
Al abrir PixelVault Store, la aplicación carga la información almacenada previamente en el dispositivo.
El sistema comprueba si existe una sesión activa.

* Si existe una sesión válida, el usuario puede acceder directamente a la aplicación.
* Si no existe una sesión, se muestra la pantalla de inicio de sesión.

La aplicación utiliza almacenamiento local para conservar la sesión, los usuarios registrados y las compras realizadas.
---

## 3. Registro de Usuario
Si el usuario todavía no posee una cuenta, puede utilizar la opción de registro.
Para crear una cuenta se solicitan los siguientes datos:

* Nombre.
* Correo electrónico.
* Número de teléfono.
* Contraseña.

Antes de crear la cuenta, la aplicación realiza diferentes validaciones.
También comprueba que el correo electrónico no haya sido registrado anteriormente.
El correo se convierte a minúsculas para evitar problemas entre direcciones escritas con mayúsculas y minúsculas.
Una vez completado correctamente el registro, la cuenta queda almacenada localmente.
---

## 4. Inicio de Sesión
Para iniciar sesión, el usuario debe introducir:

* Correo electrónico.
* Contraseña.

La aplicación comprueba que las credenciales coincidan con una cuenta registrada.
Si los datos son correctos:

1. Se identifica al usuario.
2. Se guarda la sesión.
3. Se establece el usuario como conectado.
4. Se recuperan sus datos.
5. Se muestra la pantalla principal.

Si los datos son incorrectos, la aplicación muestra un mensaje indicando que las credenciales no son válidas.
---

## 5. Mostrar u Ocultar Contraseña
Los campos de contraseña cuentan con una opción para mostrar u ocultar el contenido.
El usuario puede presionar el icono del ojo para cambiar entre:

* Contraseña oculta.
* Contraseña visible.

Esta función está disponible durante el inicio de sesión y utiliza iconos de Ionicons.
---

## 6. Recuperación de Contraseña
PixelVault incluye una opción para recuperar la contraseña.

El usuario debe proporcionar:
* Correo electrónico registrado.
* Nueva contraseña.
* Confirmación de la nueva contraseña.

La aplicación comprueba que el correo exista y que las dos contraseñas coincidan.
Si la información es correcta, la contraseña se actualiza y los datos se guardan nuevamente.
---

## 7. Catálogo de Videojuegos
Después de iniciar sesión, el usuario puede consultar el catálogo de videojuegos disponibles.

Cada videojuego contiene información como:
* Nombre.
* Categoría.
* Precio.
* Disponibilidad.
* Calificación.
* Descripción.
* Imagen.

El catálogo contiene actualmente **68 videojuegos**.
---

## 8. Filtrar por Categoría
El usuario puede utilizar las categorías disponibles para encontrar videojuegos específicos.

Las categorías son:
* Todos.
* Acción.
* Aventura.
* Disparos.
* Estrategia.
* Rol.
* Simulación.
* Deportes y Conducción.

Al seleccionar una categoría, la aplicación muestra únicamente los videojuegos correspondientes.
La opción **Todos** permite volver a visualizar el catálogo completo.
---

## 9. Consultar los Detalles de un Videojuego
El usuario puede seleccionar un videojuego para consultar información más detallada.
Los datos que pueden visualizarse son:

* Imagen.
* Nombre.
* Categoría.
* Calificación.
* Precio.
* Descripción.
* Disponibilidad.

La información se muestra mediante un modal sin necesidad de abandonar la pantalla principal.
---

## 10. Agregar un Videojuego al Carrito
Para comprar un videojuego, el usuario puede agregarlo al carrito.
Antes de agregar el producto, la aplicación comprueba que se encuentre disponible.
Si el producto está disponible, se agrega al carrito.
El usuario puede agregar uno o varios videojuegos.
---

## 11. Revisar el Carrito
El carrito permite consultar los videojuegos seleccionados antes de realizar la compra.

El usuario puede:
* Ver los productos seleccionados.
* Eliminar productos.
* Consultar el total de la compra.

El total se calcula automáticamente sumando el precio de todos los videojuegos incluidos en el carrito.

Por ejemplo:

```text
Juego A     $10
Juego B     $20
Juego C     $15
----------------
Total       $45
```

El usuario no necesita introducir manualmente el total.
---

## 12. Proceso de Pago
PixelVault cuenta con un proceso de pago simulado.
El usuario debe introducir los datos solicitados en el formulario de pago.

La aplicación realiza validaciones para comprobar:
* Que los campos requeridos estén completos.
* Que el número de tarjeta tenga una longitud válida.
* Que el CVV tenga la longitud necesaria.

El proceso **no corresponde a un pago bancario real**.
Por seguridad, durante las pruebas no deben utilizarse datos reales de tarjetas.
---

## 13. Confirmación de Compra
Después de superar las validaciones del proceso de pago, el usuario puede confirmar la compra.
La aplicación genera automáticamente un número de transacción de **8 dígitos**.

La compra registra información como:
* Productos comprados.
* Total.
* Fecha.
* Mes.
* Año.
* Número de transacción.
---

## 14. Historial de Compras
El usuario puede consultar las compras realizadas anteriormente.
Las compras se almacenan localmente y están relacionadas con el usuario que realizó la operación.
El historial permite consultar las compras registradas y utiliza la fecha actual para identificar las compras correspondientes al mes y año actuales.
---

## 15. Perfil del Usuario
PixelVault cuenta con una sección de perfil.
En esta sección se pueden visualizar los datos asociados con la cuenta que actualmente tiene la sesión iniciada.
La información mostrada corresponde al usuario activo.
---

## 16. Cerrar Sesión
El usuario puede cerrar su sesión desde la aplicación.

Al cerrar sesión:
1. Se elimina la sesión activa almacenada.
2. La aplicación deja de identificar al usuario como conectado.
3. El usuario regresa a la pantalla correspondiente para iniciar sesión nuevamente.

Cerrar sesión **no elimina la cuenta ni las compras registradas**.
---

## 17. Flujo General de Uso
El funcionamiento normal de PixelVault puede resumirse de la siguiente manera:

```text
Abrir aplicación
       ↓
Comprobar sesión
       ↓
Iniciar sesión o registrarse
       ↓
Acceder al catálogo
       ↓
Seleccionar categoría
       ↓
Consultar videojuego
       ↓
Agregar al carrito
       ↓
Revisar carrito
       ↓
Calcular total
       ↓
Realizar pago simulado
       ↓
Confirmar compra
       ↓
Generar transacción
       ↓
Guardar compra
       ↓
Consultar historial
       ↓
Cerrar sesión
```
---

## 18. Recomendaciones de Uso
Para utilizar correctamente PixelVault Store se recomienda:

* Utilizar datos de prueba durante las demostraciones.
* No utilizar información bancaria real.
* Verificar los datos antes de confirmar una compra.
* Comprobar que los videojuegos seleccionados estén disponibles.
* Cerrar sesión cuando termine la utilización de la aplicación en un dispositivo compartido.
---

## 19. Limitaciones
PixelVault es un proyecto académico.

Actualmente:
* Utiliza almacenamiento local.
* No utiliza un servidor Backend.
* No utiliza una base de datos en la nube.
* El sistema de pago es simulado.
* No existe conexión con una plataforma bancaria real.

Estas características podrían ampliarse en futuras versiones del proyecto.
---

## 20. Resumen
PixelVault Store permite al usuario gestionar una cuenta, consultar un catálogo de videojuegos, filtrar productos, revisar sus detalles, administrar un carrito, realizar una compra simulada y consultar su historial.

La aplicación utiliza React Native, JavaScript y AsyncStorage para proporcionar estas funcionalidades y conservar información localmente en el dispositivo.