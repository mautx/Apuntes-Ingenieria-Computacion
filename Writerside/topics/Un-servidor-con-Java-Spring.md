# Un servidor con Java Spring

Hacer servidores RESTful con Java y spring es muy sencillo. Spring, con su versión springboot
permite hacer por ti los mapeos, funciona como ORM y monta un servidor para vincular los handlers
con las string url relacionada

En éste tutorial aprenderás a:
* Montar un servidor SpringBoot desde cero.
* Crear un Handler que permita vincular una url con su método correspondiente.

Requisitos:
* Alguna Base de datos configurada en tu computadora (MongoDB, MYSQL MariaDB)
* Java, preferentemente en su versión más reciente.
* Un IDE de tu preferenciaa

## Parte 1 - Generar y Configurar el proyecto.

Describe what the user will learn and accomplish in the first part,
then write a step-by-step procedure but on a real-world example.

1. Ingresa a [Spring initializr](https://start.spring.io/) y genera un proyecto con:
* El grupo (group) en Maven se utiliza para organizar y categorizar los proyectos.  Si el nombre de dominio de tu organización es "example.com", el grupo podría ser algo como "com.example". 
* El artefacto (artifact) representa el producto de construcción del proyecto.       c Puede ser un archivo JAR, un archivo WAR (en el contexto de aplicaciones web), o cualquier otro resultado del proceso de construcción.
  **Ejemplo:** Si estás construyendo una biblioteca, el artefacto podría ser algo como "mi-biblioteca". Si es una aplicación web, podría ser "mi-aplicacion-web".
* El nombre (name) es simplemente el nombre descriptivo del proyecto. Proporciona información adicional sobre la identidad del proyecto.
**Ejemplo:** Si el proyecto es una aplicación de gestión de tareas, el nombre podría ser "Gestor de Tareas".
* En este proyecto usaremos Maven, pero puedes ocupar cualquier gestionador.
*  En las dependencias agrega tu base de datos (en mi caso MariaDB), JPA (Java Persistence API) y Web

2. Ahora ya tienes el archivo, pero faltan algunas configuraciones.
Ingresa a tu archivo *src/main/resources/application.properties* e ingresa las siguientes líneas:
donde tienes que reemplazar tu base de datos, el nombre de la base de datos, tu usuario y tu contraseña.
``` Java
    spring.datasource.url=jdbc:mariadb://localhost:3306/your_database_name
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.datasource.driver-class-name=org.mariadb.jdbc.Drivers

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

   ```

Prueba compilar y ejecutar y deberias de ver algo como 

![Esto](spring-compiled.png)
2. Step with a [link](https://www.jetbrains.com)

3. Final step in part 1.

## Part 2

This is the second part of the tutorial:

1. Step 1
2. Step 2
3. Step n

## What you've learned {id="what-learned"}

Summarize what the reader achieved by completing this tutorial.

<seealso>
<!--Give some related links to how-to articles-->
</seealso>
