# Especificación de Servicios - PixelVault Store

## 1. Descripción
PixelVault Store es una aplicación móvil desarrollada con React Native y JavaScript.
La versión actual de la aplicación **no utiliza una API REST externa, servidor Backend ni una base de datos en la nube**. La información necesaria para el funcionamiento de la aplicación se administra localmente mediante **AsyncStorage**.

Por esta razón, no existen rutas HTTP como `GET`, `POST`, `PUT` o `DELETE` utilizadas actualmente por PixelVault.
---

## 2. Tecnología de Almacenamiento
PixelVault utiliza **AsyncStorage** para conservar información localmente en el dispositivo.

Los datos principales almacenados son:
* Sesión del usuario.
* Usuarios registrados.
* Compras realizadas.

Las claves utilizadas por la aplicación son:
```text
@pixelvault_sesion
@pixelvault_usuarios
@pixelvault_compras
```

Estas claves permiten guardar y recuperar la información necesaria para mantener el funcionamiento de la aplicación después de cerrarla.
---

## 3. Servicio de Sesión
### Función
Permite guardar y recuperar la sesión del usuario actual.

### Clave utilizada
```text
@pixelvault_sesion
```

### Información almacenada
Se guarda el correo electrónico correspondiente al usuario que inició sesión.

### Funcionamiento
Cuando el usuario inicia sesión correctamente:

1. Se comprueban sus credenciales.
2. Se identifica la cuenta correspondiente.
3. Se guarda el correo electrónico en AsyncStorage.
4. Se establece el usuario como conectado.
5. La aplicación puede recuperar la sesión posteriormente.

Cuando la aplicación vuelve a abrirse, se recupera la información almacenada para comprobar si existe una sesión válida.
---

## 4. Servicio de Usuarios
### Función
Permite conservar las cuentas registradas dentro de la aplicación.

### Clave utilizada
```text
@pixelvault_usuarios
```

### Datos principales
Cada usuario puede contener información como:

* Nombre.
* Correo electrónico.
* Número de teléfono.
* Contraseña.

### Funcionamiento
Cuando se registra una cuenta:

1. Se validan los datos introducidos.
2. Se comprueba que el correo no esté registrado anteriormente.
3. El nuevo usuario se agrega al arreglo de usuarios registrados.
4. La información actualizada se guarda mediante AsyncStorage.

---

## 5. Servicio de Compras
### Función
Permite almacenar las compras realizadas por los usuarios.

### Clave utilizada
```text
@pixelvault_compras
```

### Información almacenada
Cada compra puede contener:

* Productos comprados.
* Total de la compra.
* Fecha.
* Mes.
* Año.
* Número de transacción.

Las compras se relacionan con el usuario que realizó la operación.
---

## 6. Proceso de Compra
PixelVault cuenta con un proceso de pago simulado.

El funcionamiento general es:
```text
Seleccionar videojuego
        ↓
Agregar al carrito
        ↓
Revisar carrito
        ↓
Calcular total
        ↓
Introducir datos de prueba
        ↓
Validar información
        ↓
Confirmar compra
        ↓
Generar número de transacción
        ↓
Guardar compra
        ↓
Mostrar en historial
```

El total de la compra se calcula automáticamente utilizando los precios de los productos almacenados en el carrito.
---

## 7. Generación de Transacciones
Cuando una compra es aprobada, PixelVault genera un identificador de transacción de **8 dígitos**.
El registro de la compra incluye el número de transacción junto con los productos, total y fecha correspondiente.
Este identificador permite diferenciar una compra de otra.
---

## 8. Catálogo de Videojuegos
El catálogo de PixelVault se encuentra almacenado localmente en el arreglo:

```text
JUEGOS_DATOS
```

Cada videojuego contiene información como:

```text
id
titulo
categoria
precio
disponible
calificacion
descripcion
imagen
```

Actualmente el catálogo contiene **68 videojuegos** distribuidos en diferentes categorías.
Las categorías disponibles son:

* Todos
* Acción
* Aventura
* Disparos
* Estrategia
* Rol
* Simulación
* Deportes y Conducción
---

## 9. Operaciones Locales

Aunque PixelVault no utiliza endpoints HTTP, la aplicación realiza diferentes operaciones internas para administrar la información.

| Operación                  | Función                              |
| -------------------------- | ------------------------------------ |
| Registro                   | Crea nuevos usuarios                 |
| Inicio de sesión           | Comprueba las credenciales           |
| Recuperación de contraseña | Actualiza la contraseña              |
| Filtrado                   | Selecciona videojuegos por categoría |
| Carrito                    | Agrega y elimina productos           |
| Cálculo                    | Obtiene el total de la compra        |
| Compra                     | Registra una nueva transacción       |
| Historial                  | Consulta compras almacenadas         |
| Sesión                     | Mantiene identificado al usuario     |
---

## 10. Métodos JavaScript Utilizados
PixelVault utiliza diferentes funciones y métodos de JavaScript para procesar la información.

### `find()`
Se utiliza para localizar un usuario específico dentro de los usuarios registrados.

### `filter()`
Se utiliza para filtrar videojuegos por categoría y compras correspondientes al mes actual.

### `reduce()`
Se utiliza para calcular automáticamente el total de los productos del carrito.

### `JSON.stringify()`
Convierte los datos JavaScript en texto para poder almacenarlos en AsyncStorage.

### `JSON.parse()`
Convierte nuevamente los datos almacenados en objetos o arreglos JavaScript.

### `toLowerCase()`
Permite comparar los correos electrónicos sin diferenciar entre mayúsculas y minúsculas.
---

## 11. API REST
Actualmente PixelVault **no consume una API REST externa**.

Por lo tanto, no se utilizan actualmente:
```text
GET
POST
PUT
DELETE
```

contra un servidor remoto.
La aplicación funciona utilizando los datos incluidos en el proyecto y el almacenamiento local proporcionado por AsyncStorage.
---

## 12. Posibles Servicios Futuros
Como mejoras futuras, el proyecto podría incorporar:

* Un servidor Backend.
* Una base de datos en la nube.
* Autenticación segura.
* Una API REST.
* Una pasarela de pago real.
* Actualización de precios desde un servidor.
* Actualización de disponibilidad de videojuegos.
* Administración remota de productos.

Estas funciones corresponden a posibles ampliaciones y **no forman parte de la implementación actual** de PixelVault.
---

## 13. Resumen
La versión actual de PixelVault utiliza una arquitectura de almacenamiento local.

```text
Usuario
   ↓
Aplicación React Native
   ↓
Funciones JavaScript
   ↓
AsyncStorage
   ↓
Información local del dispositivo
```

Los principales datos administrados son:
```text
Usuarios
Sesión
Compras
```

Por lo tanto, la documentación de esta versión no incluye endpoints REST reales debido a que la aplicación actualmente no utiliza un servidor API externo.