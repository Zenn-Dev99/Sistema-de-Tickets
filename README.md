# Sistema-de-Tickets
- Trabajo solicitado para la asignatura patrones de diseño

## Descripcion del Sistema
Simulacion de un sistema de numeros o ticket para un servicio, el cual no esta especificado, generalmente en los sitemas publicos hay lugares donde sacar numeros para ver en que momento te atiende.
Este proyecto simula en modo totalmente diguital

## Aciones del sistema
  - Solitar o anular un ticket
  - Solicitar un tiket para adulto mayor
  - Recivir notificacion del ticket
  - Ver el reguistro de tickets
  - Enrolar un numero de tikets en el sistema
  - Administracion de usuarios

## Objetivos
  - Diagrama de caso de uso completo y justificado
  - Diagrama de clases completo y justificado
  - Diagrama de implementacion completo y justificado
  - Aplicacion de los patrones prototype, adapter y sigleton

# Diagrama de caso de uso UML
![image](https://github.com/user-attachments/assets/7cb62e54-ae62-44b8-ab1f-fe0d2d477a2a)

### Descripcion general
Diagrama que representa las acciones de los actores en el sistema

### Actores
  - Usuario: Actor principal el cual puede solicitar un tickek o anularlo, ademas puede ver en que número van
  - Auditor: Tiene acceso al reguistro de tikets para asegurar la integridad de la aplicaccion
  - Aministrador: Es el que inicia la aplicacion asi mismo como el que da el numero de tikets que se pueden sacar, ademas puede administrar los usuarios

### Relaciones destacadas
  - Solicitar tikket tiene un `<<include>>` a recivir una notificacion, ya que cuando llege su turno se le notificara
  - Recivir un ticket de adulto mayor en un `<<extend>>` a solicitar ticket, ya que al hacer esta accion es opcional solicitar ese servicio
  - Solicitar un ticket usa un `<<include>>` para ingresar con el rut, o sea si no se ingresa el rut no se puede solicitar
  - Solicitar un ticket tambien usa un `<<include>>` a registro de tickets, osea cada ves que se solicite uno, se va aregistrar

### Justificacion de las relaciones
La relacion `<<include>>` se uso para acciones del sistema que dependen de otras
La relacion `<<extend>>` se uso para acciones que son opcionales o otra

# Diagrama de Clases UML
![image](https://github.com/user-attachments/assets/40dc1f68-9756-474b-b9fc-b8eaa0f6d399)

  - La seleccion de patrones no fue arbitraria, ahora se explicara el porque de cada uno de ellos

## Singleton
El patrón Singleton garantiza que haya una única instancia de una clase en todo el sistema. Se usa para manejar estados globales, como una configuración compartida o una base de datos en una aplicación.
- En nuestro modelo, la clase SistemaTickets usa Singleton porque representa el sistema centralizado de tickets.
- Solo debe existir una instancia para gestionar los tickets y su numeración.
- Se logra mediante un atributo estático instance y un método getInstance() que devuelve la única instancia.

## Prototype
El patrón Prototype se usa cuando necesitamos crear copias de objetos en lugar de instancias completamente nuevas. Es útil cuando la creación de un objeto es costosa o compleja.
- En el diagrama, la clase Ticket implementa el patrón Prototype al definir un método clone(), que permite crear una copia de un ticket sin necesidad de instanciar uno nuevo desde cero.
- Esto es útil porque los tickets suelen tener configuraciones similares, y clonarlos evita repetir lógica en la creación

## Adapter
El patrón Adapter se usa para permitir que una clase existente trabaje con otra sin modificar su estructura. Es útil cuando queremos hacer que una interfaz existente funcione con otra diferente.
- En el modelo, la clase UsuarioAdapter actúa como intermediaria entre Usuario y el sistema de tickets.
- El usuario podría tener métodos incompatibles con SistemaTickets, y el Adapter ajusta su comportamiento para que pueda interactuar correctamente.

### Resumen
- Prototype facilita la clonación de tickets sin crear nuevas instancias desde cero.
- Singleton garantiza que el sistema de tickets tenga una única instancia compartida.
- Adapter permite que Usuario pueda interactuar con SistemaTickets mediante UsuarioAdapter.

# Diagrama de implementacion de clases UML
![image](https://github.com/user-attachments/assets/78e0de5d-1a14-415d-9afb-371c80b4f2e9)

## Explicación

### Paquetes 
Organizamos el sistema en módulos (Sistema de Tickets, Modelo de Datos, Usuarios y Administración) para estructurar mejor la implementación.
### Componentes 
Cada clase clave del sistema se representa como un componente dentro de su paquete correspondiente.
### Relaciones
- SistemaTickets administra la creación y anulación de tickets.
- Ticket usa Prototype para clonación de objetos.
- SistemaTickets es Singleton, asegurando que haya una única instancia en el sistema.
- UsuarioAdapter implementa Adapter, facilitando la comunicación entre Usuario y SistemaTickets.

# Reflexión
Este modelo de sistema de tickets no solo estructura una solución funcional, sino que también incorpora patrones de diseño clave para mejorar su escalabilidad, reutilización y mantenimiento. Prototype optimiza la creación de objetos repetitivos, Singleton asegura que exista una única instancia centralizada para gestionar los tickets, y Adapter facilita la integración de clases con diferentes interfaces.





