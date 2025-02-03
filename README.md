# API de Clientes con MuleSoft

## Descripción del Proyecto
Este repositorio contiene la implementación de una API desarrollada con **MuleSoft** para exponer información de clientes almacenada en una base de datos MySQL. La API permite a los equipos de marketing acceder a los datos de los clientes para crear campañas personalizadas que mejoren la experiencia y satisfacción del cliente.

## Características de la Aplicación
- Exposición de la información de clientes mediante el endpoint:
  - `GET /api/v1/sps/customers`
- Uso de **MuleSoft Anypoint Studio** para la implementación.
- Configuraciones separadas para entornos de desarrollo y producción.
- Seguridad mejorada con **secure properties** para la protección de credenciales.
- Despliegue de la aplicación en **CloudHub**.

## Estructura del Proyecto
```
practica_tecnica/
│-- src/
│   ├── main/
│   │   ├── mule/
│   │   │   ├── practica_tecnica.xml   # Lógica de flujo principal
│   │   │   ├── global.xml             # Configuraciones globales
│   ├── resources/
│   │   ├── local.properties           # Configuración local
│   │   ├── dev.properties             # Configuración de desarrollo
│   │   ├── local.secure.properties     # Propiedades seguras (local)
│   │   ├── dev.secure.properties       # Propiedades seguras (desarrollo)
│-- pom.xml                             # Archivo de configuración Maven
│-- mule-artifact.json                   # Metadata del proyecto MuleSoft
│-- README.md                            # Documentación del proyecto
```

## Configuración del Proyecto

### Prerrequisitos
Para ejecutar este proyecto necesitas:
- **Anypoint Studio** (Mule 4)
- **MySQL Database**
- Cuenta en **MuleSoft CloudHub**

### Instalación
1. Clona este repositorio:
   ```bash
   git clone https://github.com/alexower/practica_tecnica.git
   cd practica_tecnica
   ```
2. Abre el proyecto en **Anypoint Studio**.
3. Configura las propiedades necesarias en `src/main/resources/`:
   - `local.properties` para entorno local.
   - `dev.properties` para entorno de desarrollo.
4. Configura las credenciales de la base de datos cifradas en `*.secure.properties`.

## Descripción del Flujo de Trabajo

1. **Configuración del Listener HTTP:**
   - Endpoint: `/api/v1/sps/customers`
   - Puerto: `8081`

2. **Conexión con la Base de Datos:**
   - Configuración de la conexión MySQL.
   - Consulta SQL utilizada: `SELECT * FROM customers;`

3. **Transformación de Datos:**
   - Conversión de los datos a formato JSON mediante el componente `Transform Message`.

4. **Gestíon de Configuraciones:**
   - Configuración en archivos separados para diferentes entornos.

5. **Seguridad:**
   - Protección de credenciales con `Secure Properties Tool`.

6. **Despliegue en CloudHub:**
   - Uso de credenciales seguras.
   - Pruebas con Postman.

## Despliegue en CloudHub
Para desplegar la aplicación en **CloudHub**, sigue estos pasos:

1. Inicia sesión en [Anypoint Platform](https://anypoint.mulesoft.com/).
2. Ve a **Runtime Manager > Deploy Application**.
3. Sube el archivo `*.jar` generado desde Anypoint Studio.
4. Configura las propiedades según el entorno.
5. Verifica el estado de la aplicación.



## Pruebas
Puedes probar el funcionamiento de la API utilizando **Postman**, realizando una petición `GET` al endpoint:
```http
GET http://localhost:8081/api/v1/sps/customers
```

## Contribución
Si deseas contribuir a este proyecto:

1. Haz un fork del repositorio.
2. Crea una nueva rama con la mejora o corrección.
3. Envía un pull request.

## Autor
**Alex Miguel Alavez Carrada**


