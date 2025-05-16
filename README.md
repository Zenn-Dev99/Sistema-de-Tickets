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
  - Solicitar tikket tiene un <<include>> a recivir una notificacion, ya que cuando llege su turno se le notificara
  - Recivir un ticket de adulto mayor en un <<extend>> a solicitar ticket, ya que al hacer esta accion es opcional solicitar ese servicio
  - Solicitar un ticket usa un <<include>> para ingresar con el rut, o sea si no se ingresa el rut no se puede solicitar
  - Solicitar un ticket tambien usa un <<include>> a registro de tickets, osea cada ves que se solicite uno, se va aregistrar

### Justificacion de las relaciones
La relacion <<include>> se uso para acciones del sistema que dependen de otras
La relacion <<extend>> se uso para acciones que son opcionales o otra



