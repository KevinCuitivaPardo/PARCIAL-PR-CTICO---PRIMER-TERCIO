# DOSW-ParcialT1
**Estudiante:** KEVIN CUITIVA PARDO

## Compilar y ejecutar

### Compilar el proyecto
```
mvnw.cmd clean install
```

### Ejecutar la aplicación
```
mvnw.cmd spring-boot:run
```
### Ejecutar tests
```
 mvnw.cmd test
```

## Estructura del proyecto

```
DOSW-ParcialT1
|-- pom.xml
|-- src
|   |-- main
|   |   |-- java
|   |       |-- edu/dosw/parcial/App.java
|-- test
|   |-- java
|       |-- edu/dosw/parcial/AppTest.java
|-- docs/
|   |-- uml/          # Diagramas UML exportados en PDF o PNG
|   |-- images/       # Capturas de ejecución
|   |-- requirements/ # Requisitos funcionales y no funcionales
|-- .gitignore
|-- README.md
```

## PARTE PARCIAL TEORICO 
### PRIMERA PUNTO ( diagrama de contexto ):
<img width="1333" height="590" alt="image" src="https://github.com/user-attachments/assets/23ad45bd-568f-4592-a34b-b1c2e45ad1ed" />

- Desarrollo primer punto del parcial, generalidades del sistema (Resalto puntos importantes a tener en cuenta para entender el sistema y el uso de otros externos, tambien agrego usuarios que pueden usar el sistema y se hace entender que dependiendo las reglas cada uno tiene algunas restricciones de uso del sistema, aparte de esas restricciones tienes REGLAS de horarios, espacios y tiempos.

### SEGUNDO PUNTO ( patrones ):

- FACTORY (Creacional) : Este es bastante util para las reservas ya que a la hora del desarollo podemos evitar varias condicionales y codigo que tal vez no sea tan "eficiente" Cuando alicamos este metodo podemos hacer uso de los tipos de reserva que hay (Salones de clase, Oficinas, Salon de estudio y equipos de computo) sin hacer uso de condicionales como if para ingresar a cada uno, aparte de eso pues se pude hacer la creacionde diferentes metodos en cada uno o re usar los que se necesitan por ejemplo las personas que lo usan, tambien se puede definir tiempos de uso, cantidad de personas que van a hacer uso del espacio o equipo.

- Aapter (Estructura) :  Este nos ayudara a definir como necesita nuestro sistema su entrada de datos, este sera un intermedio entre enlace - silabinfo y recursoshumanos -silabinfo, ya que nosotros podriamos traer la informacion que necesitamos de estos sistemas pero filtrarla por este patron para el correcto funcionamiento de nuestro sistema. Por ejemplo si necesitara yo id, nombre, correo de un profesor podriamos traer la base de datos de alla, buscar la tabla profesor, que claro esta tendra mas info, lo que haremos es filtrar esta info y dejar solo la que resive nuestr sistema. Tambien es bueno si en algun momento necesitamos hacer uso de alguna funcion nueva, tal vez necesitemos mas informacion de la materia en el caso de enlace, o los horarios de atencion del profe en caso de recursos humanos.

  
### TERCERO, CUARTO Y QUINTO PUNTO ( requerimientos ) :

# 📄 Requerimientos del Sistema SILABINFO

##  Lista general de requerimientos

El sistema de silabinfo tiene los siguientes requerimientos (descripción a alto nivel): 


###  Requerimientos funcionales

El sistema de Bankify debe tener:

1. Reservar segun el tipo de recurso ( PATRON FACTORY ).
2. Gestion de datos usuarios ( profesores, estudiantes y monitores).
3. Conexion con sistemas externos de la universidad enlace academico y recursos humanos ( PATRON ADAPTER )


## Requerientos no funcionales 
1. Silabinfo no peritira guardar datos de estudiantes
2. Silabinfo no guardara informacionde las materias.

## Diagrama de casos de uso
<img width="480" height="447" alt="image" src="https://github.com/user-attachments/assets/6dcf8202-4e39-42ad-bc86-9000ed193d16" />


- En este diagrama de caso de uso, tenemos como usuario el profesor y el estudiante , entonces el profesor necesita gestionar una reserva a un salon de clases y unos equipos, con esto podemos ver que los dos requerimientos que hacen uso de los patrones son importantes ya que se puede usar el FACTORY para verificar cual es la reserva que desea hacer y asi mismo hacer un llamado a recursos humanos para filtrar la informacion del profesor o filtrar la informacion del estudiante en enlace con el ADPATER.



###  Requerimiento Funcional 1

| Campo | Descripción |
|------|-------------|
| **ID** | RF-01 |
| **Nombre del requerimiento** | *Reservar segun el tipo de recurso*|
| **Descripción** | *El sistema debe debe identificar el tipo de recurso a el cual se le quiere hacer la reserva, para tener claro sus reglas, como el tiempo, quien pude hacer la reserva, si necesita materias especificas, capacidad del lugar, si cuenta con servicio o no.* |
| **Precondiciones** | *Para que el sistema cumpla con este requerimiento, silabinfo debe tener previamente claras las reglas de cada lugar al que esta disponible en el sistema* |
| **Actor** | *(Profesor, Estudiante, Monitor)* |
| **Flujo principal** | 1. El actor se identifica <br> 2. El actor hace una reserva <br>3. El sistema identifica que tipo de reservas puede hacer <br>4. El sistema devuelve el tipo de reserva permitido <br>5. El actor escoge <br>6. El sistema informa que tipo de reglas tiene la reserva <br> El actor confirma |
| **Diagrama de caso de uso** | <img width="452" height="256" alt="image" src="https://github.com/user-attachments/assets/b4ddf33a-b267-408f-8adb-48984906dbe8" />
|
| **Poscondiciones** | *Se espera como resultado que el sistema pueda informar al usuario sobre sus beneficios en la reserva escogida, de tal manera que el usuario(ACTOR) ueda escoger si hacer uso o que otro beneficio necesita segun la reserva* |


###  Requerimiento Funcional 2

| Campo | Descripción |
|------|-------------|
| **ID** | RF-02 |
| **Nombre del requerimiento** | *Conexion con sistemas externos de la universidad*|
| **Descripción** | *El sistema debe traer y filtrar informacion de otros sistemas como enlace academico y recursos humanos* |
| **Precondiciones** | *Para que el sistema cumpla con este requerimiento, Bankify debe tener previamente conexion con los sistemas de la universidad para hacer peticiones mayormente de GET* |
| **Actor** | *(Profesor, Estudiante, Monitor)* |
| **Flujo principal** | 1. El actor se identifica <br>2. El sistema hace una peticion al sistema necesario <br>3. El sistema filtra y identifica cual es el usurioy sus restrucciones |
| **Diagrama de caso de uso** | *<img width="396" height="128" alt="image" src="https://github.com/user-attachments/assets/f8fe89c7-5837-474a-aa3f-6eefafc7d4a0" />
*|
| **Poscondiciones** | *Se espera como resultado que el sistema pueda filtrar segun sus requerimientos usuarios y materias* |

## SEXTA PARTE ( Descomponer requerimiento ) :
## REQUERIMIENTO : 
- Gestion de reservas 
## EPICA : 
- Generar reserva por usuario y tipo de reserva 
## HISTORIA DE USUARIO :
- Como profesor quiero reservar equipos para poder desarrollar el parcial intermedio de la materia ECDI.
## TAREA
  - Gestion de reservas ( descripcion: Identificar cuales son las reglas necesarias de cada reserva, que usuarios pueden entrar, cantidad de horas necesarias, benedicios de la reserva)
  - PUNTOS ESTIMADOS: 8

  - Gestion de usuarios ( descripcion : Generar conexion con enlace academico para solicitar informacion del estudiante (GET) esto para poder asignar la reserva al usuario y poder revisar que permisos tiene en el sistema) 
  - PUNTOS ESTIMADOS: 5

  - Gestion de base de datos ( descripcion: Almacenar horas de reserva, usuarios que reservaron y el lugar que reservaron, esto con el fin de que el sistema identifique que franjas se encuentran disponibles y asi mismo poder informar a otros usuarios de fechas y horas disponibles. )
  - PUNTOS ESTIMADOS 3




## SEPTIMO PUNTO ( diagrama de clases, SOLID ) :

## DIAGRAMA:

<img width="1297" height="659" alt="image" src="https://github.com/user-attachments/assets/68e833f4-7cad-478d-b222-003eccb7c36b" />

- Diagrama de clases con el uso de patrones sobre el sistema


- Solid: se usa la O porque estamos abiertos a cambios en tal de necesitar un nuevo espacio se puede crear, se pude actualizar y puede avanzar segun se requiera.

