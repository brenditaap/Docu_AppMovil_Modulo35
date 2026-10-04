# Políticas de Seguridad - PixelVault Store

## 1. Introducción
PixelVault Store implementa diferentes medidas para proteger la información manejada por la aplicación y mantener un funcionamiento adecuado durante el uso de la tienda de videojuegos.

La aplicación utiliza almacenamiento local mediante AsyncStorage para conservar información relacionada con usuarios, sesiones y compras.

## 2. Gestión de Usuarios
PixelVault Store permite que los usuarios creen una cuenta utilizando sus datos personales y credenciales de acceso.

Durante el inicio de sesión, la aplicación verifica los datos introducidos por el usuario antes de permitir el acceso a las funciones principales de la aplicación.

Los usuarios registrados se almacenan localmente mediante:
`@pixelvault_usuarios`

## 3. Gestión de Sesiones
La aplicación utiliza:

`@pixelvault_sesion`

para identificar la sesión activa del usuario.

Cuando un usuario inicia sesión correctamente, la aplicación guarda la información necesaria para mantener la sesión.
Al seleccionar la opción de cerrar sesión, la sesión activa es eliminada.
Cerrar sesión no elimina la cuenta ni el historial de compras almacenado.

## 4. Protección de los Datos de Compra
Las compras realizadas se almacenan localmente mediante:
`@pixelvault_compras`

Cada registro de compra contiene información como:
- Productos adquiridos.
- Total de la compra.
- Fecha.
- Mes.
- Año.
- Número de transacción.

Las compras se relacionan con el usuario que realizó la operación.

## 5. Validación del Proceso de Pago
PixelVault Store cuenta con un proceso de pago simulado.
Antes de completar una compra, la aplicación valida los datos introducidos por el usuario.

Entre las validaciones realizadas se encuentran:
- Verificación de campos requeridos.
- Validación de la longitud del número de tarjeta.
- Validación de la longitud del código CVV.
- Procesamiento del formato de la fecha de expiración.

La aplicación no se conecta con una institución bancaria ni utiliza una pasarela de pagos real.

## 6. Número de Transacción
Cuando una compra es aprobada, la aplicación genera un identificador de transacción de 8 dígitos.
Este identificador permite diferenciar una compra de otra y forma parte de la información almacenada en el historial de compras.

## 7. Cierre de Sesión
El cierre de sesión permite finalizar la sesión activa del usuario.

Al realizar esta acción, la aplicación elimina la sesión almacenada y evita que el usuario continúe siendo identificado como conectado.

El cierre de sesión no elimina los datos de la cuenta ni las compras registradas.

## 8. Consideraciones de Seguridad
PixelVault Store es un proyecto móvil de carácter académico y utiliza almacenamiento local.

Por esta razón, no cuenta actualmente con:
- Servidor backend.
- Base de datos remota.
- Autenticación mediante servicios externos.
- Pasarela de pagos bancaria real.
- Sistema de tokens de autenticación remoto.

Las funciones de seguridad implementadas corresponden al funcionamiento local de la aplicación.

## 9. Recomendaciones para una Versión Futura
Si PixelVault Store fuera convertida en una aplicación comercial, podrían incorporarse mecanismos adicionales de seguridad, como:

- Autenticación mediante un servidor seguro.
- Base de datos remota protegida.
- Cifrado de información sensible.
- Uso de almacenamiento seguro para credenciales.
- Integración con una pasarela de pagos real y certificada.
- Comunicación mediante conexiones HTTPS.
- Gestión de sesiones mediante mecanismos de autenticación seguros.

Estas características representarían mejoras futuras y no forman parte de la implementación actual de PixelVault Store.

## 10. Resumen
PixelVault Store implementa controles básicos relacionados con la gestión de usuarios, sesiones, compras y validación del proceso de pago simulado.

La información se mantiene mediante almacenamiento local y el cierre de sesión permite finalizar la sesión activa.

Debido a que se trata de un proyecto académico, las funciones de seguridad se encuentran limitadas al entorno local de la aplicación.