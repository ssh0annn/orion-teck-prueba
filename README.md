📄 Documentación Técnica: Sistema de Gestión de Clientes OrionTek

Este proyecto implementa una solución informática para gestionar clientes y sus direcciones, siguiendo el patrón de arquitectura CQRS (Command Query Responsibility Segregation)

Componente	Tecnología	Versión Clave	Notas y Emojis
Lenguaje	Java	21+	☕ Base del desarrollo.
Framework	Spring Boot	3.2+	🍃 Core del Backend y API REST.
Persistencia	Spring Data JPA / Hibernate	-	💾 Mapeo Objeto-Relacional.
Base de Datos	PostgreSQL	14+	🐘 Base de datos relacional robusta.
Arquitectura	CQRS	-	📐 Separación de Lectura/Escritura.
Build Tool	Maven	3.x	📦 Gestión de dependencias.



⚙️ Instalación y Configuración del Entorno
Sigue estos pasos para obtener una copia del proyecto y ponerlo en marcha en tu entorno local.

1. Requisitos Previos
Asegúrate de tener instalados los siguientes componentes:

JDK (Java Development Kit): Versión 21 o superior.
Maven: 3.x.
PostgreSQL: Servidor de base de datos instalado y corriendo (local).
Git: Para clonar el repositorio.

2. Clonar el Repositorio
git clone <URL-DE-TU-REPOSITORIO>
cd oriontek-clientes-cqrs

3. Configuración de la Base de Datos
El proyecto utiliza PostgreSQL. Debes crear la base de datos y actualizar las credenciales en el archivo de configuración.

4. Ejecutar la Aplicación
Puedes iniciar la aplicación usando Maven:

🔬 Pruebas de Endpoints (Flujo CQRS)

Paso 1: Crear Cliente (COMANDO - Escritura)

Característica,Detalle
Método,POST
Ruta,/api/clientes
Cuerpo (JSON),Requerido

Cuerpo de la Petición:
JSON

{
  "nombre": "Juan",
  "apellido": "Pérez",
  "email": "juan.perez@test.com"
}

Respuesta Esperada: 201 Created y el objeto Cliente, incluyendo el id (UUID o Long) generado. Guarda este ID.

Paso 2: Agregar Dirección a Cliente (scritura)
Esta operación asocia una dirección al cliente creado en el paso anterior.
Característica,Detalle
Método,POST
Ruta,/api/clientes/{id_del_cliente}/direcciones
Cuerpo (JSON),Requerido

Cuerpo de la Petición (ejemplo):
{
  "calle": "Calle 5, Sector Olímpico",
  "ciudad": "Santo Domingo",
  "pais": "República Dominicana",
  "descripcion": "Dirección de la casa",
  "esPrincipal": true
}
