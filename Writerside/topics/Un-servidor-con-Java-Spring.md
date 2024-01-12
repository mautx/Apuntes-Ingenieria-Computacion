# Un servidor Restful con Java Spring

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

![Esto](spring-compiled.png){height=32 thumbnail=true}

Ya estamos listos para darle estructura al proyecto


## Parte 2, creación de una entidad

Ahora, procederemos a crear una entidad. ¿Cuál es su propósito? Una entidad, también conocida como "entity" en inglés, desempeña un papel fundamental en el framework Spring, especialmente cuando se utiliza la tecnología JPA (Java Persistence API). En este contexto, una entidad representa una clase que será persistida en una base de datos.

La creación de una entidad es esencial para que Spring, a través de JPA, tenga la capacidad de mapear objetos Java a registros en la base de datos. En otras palabras, la entidad actúa como una representación de la estructura de datos en tu aplicación, permitiendo que los objetos de esa clase se almacenen y recuperen de la base de datos de manera eficiente.

Antes de crear la entidad, creamos un package nuevo llaado entity. Ahí irán todos los modelos de la base de datos.

Lo primero es indicarle a Spring que vamos a hacer una entidad:

``` Java
 @Entity
public class Employee {
}
``` 

Forzosamente esta entidad te pide que generes un ID como atributo de la entidad.

``` Java
    @Id@GeneratedValue
    private Long id;
``` 

Ingresamos los atributos que queramos en el empleado, en este caso name y role:

``` Java
    @Id@GeneratedValue
    private Long id;    
    private String name;
    private String role;

``` 

y al generar el constructor por default, el constructor que llena los atributos y los getters y setters quedaría:

``` Java
@Entity
public class Employee {

    @Id@GeneratedValue
    private Long id;


    private String name;


    private String role;

    public Employee(){}
    Employee(String name, String role){
        this.name = name;
        this.role = role;
    }

    public String getName() {
        return name;
    }
    public String getRole() {
        return role;
    }

    public void setRole(String role) {
        this.role = role;
    }

    public void setName(String name) {
        this.name = name;
    }



    public void setId(Long id) {
        this.id = id;
    }

    public Long getId() {
        return id;
    }

    @Override
    public String toString() {
        return "Employee{" +
                "id=" + id +
                ", name='" + name + '\'' +
                ", role='" + role + '\'' +
                '}';
    }
}
```
Recuerda que Java es muy verboso, pero realmente el código es muy sencillo.
## Parte 3, creación de la interfáz repository. 

Ahora, abordaremos una tarea relativamente sencilla: la creación de una interfaz que nos permita implementar JpaRepository. Dado que estamos trabajando con templates, es esencial indicar explícitamente que la interfaz operará con el tipo <Employee, Long>, donde Long será el tipo de dato del identificador (id).

```


<seealso>
<!--Give some related links to how-to articles-->
</seealso>
