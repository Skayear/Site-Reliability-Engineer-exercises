# Levantar Servicios Localmente y Crear Dockerfiles

Este proyecto tiene como objetivo levantar los servicios **backend** y **frontend** localmente, y posteriormente crear Dockerfiles individuales para cada uno.

---

## Backend

**Tecnología**: .NET 6  
**Puerto asignado**: 5146  

### Pasos para levantar el servicio localmente

1. **Accede al directorio del backend**  
   Navega al directorio raíz del proyecto del backend utilizando la terminal.

2. **Ejecuta el servicio**  
   Inicia el servicio localmente con el siguiente comando:
   `dotnet run ./`

3. **Verifica el estado del servicio**
    Asegúrate de que el backend esté corriendo en el puerto 5146. Puedes comprobarlo accediendo a:
    `http://localhost:5146`

## Frontend

**Tecnología**: Angular  
**Puerto asignado**: 4200

### Pasos para levantar el servicio localmente

1. **Accede al directorio del frontend**
    Navega al directorio raíz del proyecto del frontend utilizando la terminal.

2. **Instala las dependencias**
    Ejecuta el siguiente comando:
    `npm install`

3. **Compila el proyecto**
    Genera los archivos necesarios para la ejecución con:
    `npm run build`

4. **Ejecuta el servicio**
    Inicia el servidor de desarrollo con:
    `npm run start`

5. **Verifica el estado del servicio**
    Asegúrate de que el frontend esté corriendo en el puerto 4200. Puedes comprobarlo accediendo a:
    `http://localhost:4200`

---

# Notas

* Asegúrate de que los puertos 5146 y 4200 no estén ocupados antes de iniciar los servicios.

* Reemplaza NombreDelProyecto.dll y NOMBRE_DEL_PROYECTO por los valores correspondientes a tu proyecto.